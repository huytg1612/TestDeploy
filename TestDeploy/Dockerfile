FROM mcr.microsoft.com/dotnet/sdk:3.1 as build
WORKDIR /App
COPY . .
RUN dotnet restore
RUN dotnet publish -c Release -o out

FROM mcr.microsoft.com/dotnet/aspnet:3.1
COPY --from=build /App/out .
# ENV ASPNETCORE_URLS=http://*:5000
# ENV ASPNETCORE_ENVIRONMENT=”development”
# EXPOSE 5000
ENTRYPOINT [ "dotnet", "TestDeploy.dll" ]