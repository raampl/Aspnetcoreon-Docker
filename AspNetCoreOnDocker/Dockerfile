FROM mcr.microsoft.com/dotnet/aspnet:5.0 AS build
WORKDIR /code
COPY . .
RUN dotnet restore
RUN dotnet publish --output /output --configuration Release

#FROM microsoft/aspnetcore:2.0.6
COPY --from=build /output /app
WORKDIR /app
ENTRYPOINT ["dotnet", "AspNetCoreOnDocker.dll"]