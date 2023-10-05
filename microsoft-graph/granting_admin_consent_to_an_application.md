# Granting Admin Consent to an Application

Examples below use the Microsoft Graph PowerShell SDK, though this could also be done using the API directly.

Granting consent for delegated permissions (OAuth2 scopes):

```powershell
New-MgOauth2PermissionGrant -ClientId $appNeedingPermissions.Id -ConsentType "AllPrincipals" `
    -ResourceId $appExposingPermissions.Id -Scope $scopesToGrant
```

Granting consent for application permissions (app roles):

```powershell
New-MgServicePrincipalAppRoleAssignment -ServicePrincipalId $appNeedingPermissions.Id -PrincipalId `
    $appNeedingPermissions.Id -ResourceId $appExposingPermissions.Id -AppRoleId $idOfExposedPermission
```

Note that if you are viewing existing delegated (`Get-MgOauth2PermissionGrant`) or application permission (`Get-MgServicePrincipalAppRoleAssignment`) grants on an app, only delegated grants actually contain the names of permissions (scopes). Application permission grants only contain their ID. Meaning while you can use a list of scope names for comparison in automation to determine if any additional delegated grants are needed, you'll have to use IDs to perform the same comparison for application permissions.

## References

- [Microsoft - Granting Admin Consent](https://learn.microsoft.com/en-us/azure/active-directory/manage-apps/grant-admin-consent?pivots=ms-powershell)
- [Microsoft - IMicrosoftGraphOAuth2PermissionGrant Interface](https://learn.microsoft.com/en-us/dotnet/api/microsoft.azure.powershell.cmdlets.resources.msgraph.models.apiv10.imicrosoftgraphoauth2permissiongrant?view=az-ps-latest)
- [Microsoft - IMicrosoftGraphAppRoleAssignment Interface](https://learn.microsoft.com/en-us/dotnet/api/microsoft.azure.powershell.cmdlets.resources.msgraph.models.apiv10.imicrosoftgraphapproleassignment?view=az-ps-latest)
