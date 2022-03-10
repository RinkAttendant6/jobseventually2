# JobsEventually 2

Demo of Microsoft Identity Platform integration with .NET Core app.

❗ IMPORTANT: The project is a demo only and the code is very barebones based on what [`dotnet new`](https://docs.microsoft.com/en-us/dotnet/core/tools/dotnet-new) generates. **The code should not be considered production-ready whatsoever.**

## How this was built

### The identity provider

1. Buy an Azure tenant with Azure Active Directory
1. Register a new application (see step 1: https://docs.microsoft.com/en-us/azure/active-directory/develop/web-app-quickstart?pivots=devlang-aspnet-core)

### The app

Pre-requisite: `dotnet` is installed. [Install dotnet](https://docs.microsoft.com/en-us/dotnet/core/install/)

```shell
dotnet new webapp -o MyAwesomeApp --auth SingleOrg --client-id "YOUR_CLIENT_ID" --tenant-id "YOUR_TENANT_ID" --domain "YOUR_DOMAIN"

dotnet run --project MyAwesomeApp
```

## How to run

The tenant ID, client ID, and domain fields need to be specified at runtime.

This can be done by putting the values in `appsettings.json` on dev, specify them using environment variables, or [some other appropriate method](https://docs.microsoft.com/en-us/aspnet/core/security/app-secrets?view=aspnetcore-6.0).

Example using environment variables on Linux:

```
AZUREAD__TENANTID=abcedf01-2345-6789-abcd-ef0123456789 AZUREAD__DOMAIN=contoso.onmicrosoft.com AZUREAD__CLIENTID=01234567-89ab-cdef-0123-456789abcedf dotnet run --project MyAwesomeApp
```
