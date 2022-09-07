# A (very very) quick start to dockerize an AspNet application

## Create project

Execute command below: 

```cmd
dotnet new webapi -o Poc.Docker/Poc.Docker.Web
cd .\Poc.Docker\
dotnet new sln
dotnet sln add .\Poc.Docker.Web\
.\Poc.Docker.sln
```

## Create Dockerfile

Create file `Poc.Docker/Poc.Docker.Web/Dockerfile`

```Dockerfile
FROM mcr.microsoft.com/dotnet/aspnet:6.0 AS base
WORKDIR /app
EXPOSE 80
EXPOSE 443

FROM mcr.microsoft.com/dotnet/sdk:6.0 AS build
WORKDIR /src
COPY ["Poc.Docker.Web/Poc.Docker.Web.csproj", "Poc.Docker.Web/"]
RUN dotnet restore "Poc.Docker.Web/Poc.Docker.Web.csproj"
COPY . .
WORKDIR "/src/Poc.Docker.Web"
RUN dotnet build "Poc.Docker.Web.csproj" -c Release -o /app/build

FROM build AS publish
RUN dotnet publish "Poc.Docker.Web.csproj" -c Release -o /app/publish

FROM base AS final
WORKDIR /app
COPY --from=publish /app/publish .
ENTRYPOINT ["dotnet", "Poc.Docker.Web.dll"]
```

Create file `Poc.Docker/Poc.Docker.Web/.dockerignore`

```
**/.dockerignore
**/.env
**/.git
**/.gitignore
**/.project
**/.settings
**/.toolstarget
**/.vs
**/.vscode
**/.idea
**/*.*proj.user
**/*.dbmdl
**/*.jfm
**/azds.yaml
**/bin
**/charts
**/docker-compose*
**/Dockerfile*
**/node_modules
**/npm-debug.log
**/obj
**/secrets.dev.yaml
**/values.dev.yaml
LICENSE
README.md
```

## Build and run image

Run the following command to build and create an image :

`docker build -t aspnetdockerized -f .\Poc.Docker.Web\Dockerfile .`

- `-t`: give a tag to image build
- `-f`: give the path to the Dockerfile
- `.`: give the context from where the Dockerfile instruction are executed

Run the following to run the image in the container :

`docker run -d -p 8080:80 --name pocAspnet aspnetdockerized`

- `-d`: detach the running process from the terminal
- `-p`: map the host and the container protocol
- `--name`: give a name to the container
- `aspnetdockerized`: the image name value

If you want to check the swagger page you have to execute the run command with environnement variable 
to developpment : `-e "ASPNETCORE_ENVIRONMENT=Development"`

## Test

Type the url `http://localhost:8080/WeatherForecast` in your favorite browser and check the response.

## Debug

For Rider user, see the [Debugging ASP.NET Core apps in a local Docker container](https://blog.jetbrains.com/dotnet/2018/07/18/debugging-asp-net-core-apps-local-docker-container/) article.