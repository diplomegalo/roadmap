# Create a docker container with graphql running on aspnet core application and using sql server with ef core

>[!info] Pre require  
>Instructions below are based on the [[GraphQL-AspNetCore]] cookbook.

## Dockerfile

Add the intstruction below in a new Dockerfile at the root directory of your web api project `Poc.GraphQL/Poc.GraphQL.Web/Dockerfile`.

```Dockerfile
FROM mcr.microsoft.com/dotnet/aspnet:6.0 AS base  
WORKDIR /app  
EXPOSE 80  
EXPOSE 443  
  
FROM mcr.microsoft.com/dotnet/sdk:6.0 AS build  
WORKDIR /src  
COPY ["Poc.GraphQL.Web/Poc.GraphQL.Web.csproj", "Poc.GraphQL.Web/"]  
RUN dotnet restore "Poc.GraphQL.Web/Poc.GraphQL.Web.csproj"  
COPY . .  
WORKDIR "/src/Poc.GraphQL.Web"  
RUN dotnet build "Poc.GraphQL.Web.csproj" -c Release -o /app/build  
  
FROM build AS publish  
RUN dotnet publish "Poc.GraphQL.Web.csproj" -c Release -o /app/publish  
  
FROM base AS final  
WORKDIR /app  
COPY --from=publish /app/publish .  
ENTRYPOINT ["dotnet", "Poc.GraphQL.Web.dll"]
```

## Docker-compose

Creates new `docker-compose.yml` file with the following information at the root of your solution directory `Poc.GraphQL/`.

```yml
version: '3.4'  
  
services:  
  sqlserver:  
    image: mcr.microsoft.com/mssql/server  
    restart: always  
    ports:  
      - "3090:1433"  
      - "3091:1434"  
    environment:  
      - "ACCEPT_EULA=Y"  
      - "SA_PASSWORD=1StrongPwd!!"  
  graphql:  
    image: graphql  
    build:  
      context: .  
      dockerfile: .\Poc.GraphQL.Web\Dockerfile  
    ports:  
      - "8080:80"  
    depends_on:  
      - sqlserver  
    environment:  
      - "ASPNETCORE_ENVIRONMENT=Development"
```

>[!info] Environment variable  
>The environment variable `ASPNETCORE_ENVIRONMENT` with value `Development` is require to be able to see the swagger documentation page.

## Run containers

>[!hint] Docker  
>Before begining you can check existing images and containers by executing `docker images` and `docker container ls`.

>[!hint] Sqlcmd  
>Check also if the [sqlcmd utility](https://docs.microsoft.com/en-us/sql/tools/sqlcmd-utility?view=sql-server-ver16) is installed by executing `sqlcmd -?`

Run containers with the command below where `-d` option detach the executing thread from the terminal :

```
docker-compose up -d
```

Then check that the AspNet application and the Sql Server is up and running :

1. Type the URL `localhost:8080/ui/altair` in a browser which should return the altair interface.
2. Execute the following command where :  
	- the `-S` option is to give the server information,  
	- the `-P` option is to give the password value,  
	- the `-U` option is to give the login id.

```cmd
sqlcmd -S localhost,3090 -P 1StrongPwd!! -U sa
```

You should have an output like below which means that your are connected

```cmd
1>_
```

>[!hint]  
> You can also enter the following sql request to test the sql version :  
> `1> SELECT @@ version`  
> `2> GO`

## Bind `Dbcontext` with database.

From the path `Poc.GraphQL\Poc.GraphQL.Web`, install the `Microsoft.EntityFrameworkCore.SqlServer` package by executing the command below.

```cmd
dotnet add package Microsoft.EntityFrameworkCore.SqlServer
```

---

Tags : #GraphQL, #EFCore, #AspNetCore, #Docker
