FROM mcr.microsoft.com/dotnet/sdk:10.0 AS build
WORKDIR /app

COPY *.slnx ./
COPY src/HelloWorld/*.csproj src/HelloWorld/

RUN dotnet restore src/HelloWorld/HelloWorld.csproj

COPY src/HelloWorld/ src/HelloWorld/
RUN dotnet publish src/HelloWorld/HelloWorld.csproj -c Release -o /app/publish --no-restore

# Runtime image
FROM mcr.microsoft.com/dotnet/aspnet:10.0 AS runtime
WORKDIR /app
COPY --from=build /app/publish .
EXPOSE 8080
ENTRYPOINT ["dotnet", "HelloWorld.dll"]
