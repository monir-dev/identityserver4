# identityserver4
Identity Server 4 practical implementation with entity framework core.
Official documentations: https://identityserver4.readthedocs.io


# Instructions:

Run Server Project:
1. Run IdentityServer Or IdentityServerAspNetIdentity project on port 5000. If you want entity framework version run "IdentityServerAspNetIdentity". 

Run Api Project:
2. Run API project on port 6001 port.

Authenticate with client project:
There is two client project. "MvcClient" and "JavaScriptClient". Run either one to authenticate.


# Register new Client: 
IdentityServer Or IdentityServerAspNetIdentity project has a Config.cs file.
Add new client to Client List.

```
new Client
{
    ClientId = "js",
    ClientName = "JavaScript Client",
    AllowedGrantTypes = GrantTypes.Code,
    RequireClientSecret = false,

    RedirectUris =           { "https://localhost:5053/callback.html" },
    PostLogoutRedirectUris = { "https://localhost:5053/index.html" },
    AllowedCorsOrigins =     { "https://localhost:5053" },

    AllowedScopes =
    {
        IdentityServerConstants.StandardScopes.OpenId,
        IdentityServerConstants.StandardScopes.Profile,
        "api1"
    }
}
```
