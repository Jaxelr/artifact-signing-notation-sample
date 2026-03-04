FROM mcr.microsoft.com/dotnet/sdk:10.0 AS build
WORKDIR /app

# Copy solution and project files
COPY *.slnx ./
COPY src/HelloWorld/*.csproj src/HelloWorld/

# Restore dependencies
RUN dotnet restore src/HelloWorld/HelloWorld.csproj

# Copy source code and publish
COPY src/HelloWorld/ src/HelloWorld/
RUN dotnet publish src/HelloWorld/HelloWorld.csproj -c Release -o /app/publish

# Runtime image
FROM mcr.microsoft.com/dotnet/aspnet:10.0 AS runtime
WORKDIR /app
COPY --from=build /app/publish .
EXPOSE 8080
ENTRYPOINT ["dotnet", "HelloWorld.dll"]
