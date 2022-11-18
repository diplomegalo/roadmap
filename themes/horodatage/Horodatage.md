# Préambule
**TimeStamping** est un standard formel défini par la RFC-3161 qui décrit les formats des requêtes et réponses.

![[Trusted_timestamping.svg]]

Une fois qu'un hash sur un document a été horodaté, la preuve d'horodatage pourra 

- soit être conservée séparément du fichier. Dans ce cas, le format ne contiendra donc pas la preuve d'horodatage.
- soit si le format le permet (comme pour un pdf ou un xml) incorporée dans le conteneur du document qui est horodaté). Lors de l'horodatage d'un pdf ou d'un xml, c'est donc une partie du document (data + quelques metadatas) qui sera horodatée (le mécanisme est le même pour la signature) et cet horodatage sera ajouté au pdf dans une partie prévue (hors data + quelques metadatas) de façon à pouvoir en garantir l'intégrité.


# Le protocole
Voici une brève description du protocole d'horodatage : 
1. Le client TSA calcule une valeur de hachage unidirectionnelle pour un fichier de données et envoie le hachage à la TSA. 
2. Le TSA associe la date et l'heure actuelles à la valeur de hachage reçue, les signe et renvoie le jeton d'horodatage au client. En créant ce jeton, la TSA certifie l'existence du fichier de données d'origine au moment de la génération de la réponse. 
3. Le client TSA reçoit le jeton d'horodatage et vérifie la signature qu'il contient. Il vérifie également si le jeton contient la même valeur de hachage qu'il avait envoyé à la TSA.

# Exemple concret
Dans cet exemple, dans le but d'être OS et language indépendant, on va utiliser openSSL pour interroger un service de timestamping indépendant servant à horodater un fichier. Cet horodatage ne sera pas inclus au document (comme pour un pdf), car dans ce cas il faut utiliser une librairie ou application tierce afin de l'incorporer. 
Pour solution programmatique, il existe des librairies (utilisant par exemple bouncyCastle) qui permettent d'intégrer les mêmes fonctionnalités dans une application.

## Etapes
Les étapes seront les suivantes : 
1. Calcul du hash du fichier (agnostique du format)
2. Création d'une requête d'horodatage (RFC-3161 compliant)
3. Envoi de la requête et récupération du timestamp
4. Vérification du timestamp (sur base du fichier timestamp reçu)

Dans ce use case, on va avoir un horodatage **externe au fichier**. 

### 1. Calcul du hash du fichier : 

en ligne de commande, il existe plusieurs moyens, 
   - sous windows, on peut utiliser l'utilitaire certutil : `Certutil -hashfile (Path_to_file) [HashAlgo]`, la commande powerShell `Get-FileHash` 

   - Comme décrit préalablement, on va utiliser openSSL : 
     `openssl dgst -<hash_algorithm> -out <digest> <input_file>` 
	 
	 Exemple : On va cacluler un hash sur base du fichier *Test.pdf* et va nous fournir un output sous la forme d'un fihcer *test_pdf_hashSHA512_openssl.log*
	 
     `openssl dgst -sha512 -out test_pdf_hashSHA512_openssl.log Test.pdf`

<div style="border: 2px solid transparent;padding:1.875rem 2.5rem;border-radius:3px;margin-top:1.5635rem;margin-bottom:1.5635rem;background:#E2DAF1;color:#64645c">
	 
Le contenu du fichier aura la forme de (`cat test_pdf_hashSHA512_openssl.log`)
SHA512(Test.pdf)= 3d3e5448a01330c3ad85b8296fb6b9eacb69f0c66eb39e39c49b88a36dfba0f3f83f9cd861fca1339db7730056fe8cda6a42976112ffb828d6a6c975a5507ac3

**Remarque** dans ce cas-ci on va utiliser l'algorithme SHA512
</div>
 
	 
### 2. Création de la requête RFC-3161
En utilisant openSSL, on va créer une requête RFC-3161 compliant. Le fichier créé aura pour extension **.tsq** (*timestamp-query*), ce call se fera sur base du hash et non pas avec le fichier en tant que tel. 

<div style="border: 2px solid transparent;padding:1.875rem 2.5rem;border-radius:3px;margin-top:1.5635rem;margin-bottom:1.5635rem;background:#F36E30;color:#212121;">
Le fichier ne sera pas envoyé à l'autorité d'horodatage, c'est important du point de vue sécurité de l'information : la confiance (et responsabilité) qu'on accorde à l'autorité d'horodatage se limite à signer le hash, elle n'aura pas connaissance du contenu du ficher.
</div>

Exemple de commande OpenSSL générant le fichier de request (*test_pdf_hashSHA512_openssl.tsq*)

`openssl ts -query -data test_pdf_hashSHA512_openssl.log -no_nonce -sha512 -out test_pdf_hashSHA512_openssl.tsq`

### 3. Envoi de la requête et récupération du timestamp

La requête générée peut maintenant être envoyée à l'autorité d'horodatage. Pour l'exemple on va utiliser un tsget ou un curl. L'autorité certificative de cette exemple utilisera FreeTSA service. 

`curl --verbose -H "Content-Type: application/timestamp-query" --data-binary @test_pdf_hashSHA512_openssl.tsq https://freetsa.org/tsr > test_pdf_hashSHA512_openssl.tsr`

Si le serveur de timestamping accepte la requêtee, il va retourner un timestamp compliant RFC-3161 (usuellement un fichier .tsr - *timestamp-response*). Afin de s'assurer du contenu de l'horodatage, on peut ouvrir la réponse via : 

`openssl ts -reply -in test_pdf_hashSHA512_openssl.tsr -text`

```Status info:
Status: Granted.
Status description: unspecified
Failure info: unspecified

TST info:
Version: 1
Policy OID: 1.2.3.4.1
Hash Algorithm: sha512
Message data:
    0000 - b8 f6 21 7f 74 d1 92 52-45 ce 07 84 1a 2c 6d 58   ..!.t..RE....,mX
    0010 - 7c 4e 6d f8 69 ba ec b5-96 e5 37 83 36 24 84 2c   |Nm.i.....7.6$.,
    0020 - 57 81 72 87 20 8d 8f 5a-7b 78 11 01 a9 26 52 9f   W.r. ..Z{x...&R.
    0030 - 2a cb 7a 59 2e 09 cb 82-7a 6f 1e c5 34 3f ee 7b   *.zY....zo..4?.{
Serial number: 0x01472559
Time stamp: Oct 13 14:15:29 2021 GMT
Accuracy: unspecified
Ordering: yes
Nonce: unspecified
TSA: DirName:/O=Free TSA/OU=TSA/description=This certificate digitally signs documents and time stamp requests made using the freetsa.org online services/CN=www.freetsa.org/emailAddress=busilezas@gmail.com/L=Wuerzburg/C=DE/ST=Bayern
Extensions:
```

### 4. Vérification du timestamp (sur base du fichier timestamp reçu)
La vérification se fait sur base d'un fichier requête *.tsq* et de la réponse (*.tsr*). 
Une copie du fichier éponse (*.tsr*) fournit la preuve du résultat de l'acquisition de l'horodatage. C'est donc elle qui va falloir conserver et confronter.  

Exemple de commande servant à vérifier une requête à une réponse d'horodatage : 

`openssl ts -verify -in test_pdf_hashSHA512_openssl.tsr -queryfile test_pdf_hashSHA512_openssl.tsq -CAfile cacert.pem -untrusted tsa.crt`

```
Verification: OK
```

Certains paramètres peuvent être nécessaires (ils apparaissent ici pour les besoins de l'exemple et les certificats qui les composent sont propres à l'autorité certificatrice et sa configuration) : 
- `cacert.pem` Ce fichier contient la liste de toutes les autorités de certification dignes de confiance, de sorte que les certificats serveur signés par ces autorités de certification soient acceptés.
- `tsa.crt` ensemble de certificats non fiables supplémentaires au format PEM qui peuvent être nécessaires lors de la création de la chaîne de certificats pour le certificat de signature de la TSA. Ce fichier doit contenir le certificat de signature TSA et tous les certificats CA intermédiaires, sauf si la réponse les inclut.

# Exemple de code

L'exemple ci-dessous utilise les fonctionnalités native de la classe [Rfc3161TimestampRequest](https://docs.microsoft.com/en-us/dotnet/api/system.security.cryptography.pkcs.rfc3161timestamprequest?view=windowsdesktop-5.0) en .NET.

```csharp
            var data = "Ceci est un test";
            using var sha512 = SHA512.Create();
            var actual = sha512.ComputeHash(Encoding.UTF8.GetBytes(data));

            var nonce = new byte[8];
            using RandomNumberGenerator rng = RandomNumberGenerator.Create();
            rng.GetBytes(nonce);

            var tsRequest = Rfc3161TimestampRequest.CreateFromData(actual,
                HashAlgorithmName.SHA512,
                requestSignerCertificates: true,
                nonce: nonce);
            var requestRaw = tsRequest.Encode();

            var webRequest = WebRequest.Create("http://timestamp.digicert.com");
            webRequest.Method = "POST";
            webRequest.ContentType = "application/timestamp-query";
            webRequest.ContentLength = requestRaw.Length;

            var stream = webRequest.GetRequestStream();
            stream.Write(requestRaw, 0, requestRaw.Length);
            stream.Close();

            using var response = webRequest.GetResponse();
            using var responseStream = response.GetResponseStream();
            using var memoryStream = new MemoryStream();
            responseStream?.CopyTo(memoryStream);
            responseStream?.Close();
            var responseRaw = memoryStream.ToArray();

            var token = tsRequest.ProcessResponse(responseRaw, out _);

            Console.WriteLine(
                $"Data encoded at {token.TokenInfo.Timestamp} by {token.TokenInfo.GetTimestampAuthorityName()}");
            
            var expected = sha512.ComputeHash(Encoding.UTF8.GetBytes(data));
            Console.WriteLine($"Check : {token.VerifySignatureForData(expected, out _)}");
```

# Liens utiles et références

- FreeTSA: https://freetsa.org/index_en.php
- OpenSSL documentation sur TS: https://www.openssl.org/docs/man1.1.0/man1/openssl-ts.html
- Documentation globalSign concernant le service timeStamp: https://www.globalsign.com/en/timestamp-service
- Liste d'applications permettant de signer un pdf https://freetsa.org/guide/
- Documentation de la classe [Rfc3161TimestampRequest](https://docs.microsoft.com/en-us/dotnet/api/system.security.cryptography.pkcs.rfc3161timestamprequest?view=windowsdesktop-5.0)
- Librairie Java permettant la manipulation des Pdfs : https://pdfbox.apache.org/
- Implémentation de référence de solution de e-signature : https://ec.europa.eu/cefdigital/wiki/display/CEFDIGITAL/Digital+Signature+Service+-++DSS