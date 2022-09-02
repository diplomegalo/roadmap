# Dockerize aspnet core with sql server

## Dockerfile

Add `Dockerfile` add the root directory of your web api project.

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
```

Test