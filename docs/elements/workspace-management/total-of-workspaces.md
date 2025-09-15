# Retrieve Total of workspaces

Use this API to retrieve records for Total of workspaces for a specific tenant in AvePoint Online Services.  

## Permissions  

The following permission is required to call the API.  
You must register an app through Elements > API app registration to authenticate and authorize your access to AvePoint Graph API. For details, refer to [App Registration](https://cdn.avepoint.com/assets/apelements-webhelp/avepoint-elements-for-partners/index.htm#!Documents/appregistration.htm).

| API | Permission |
|-----------|-----------|
| `/partner/external/wm/customers/{customerId}/tenants/{tenantId}/overview/workspace` | partner.wm.read.all |  


## Request

This section outlines the HTTP method and endpoint used to retrieve your customer's information for all scan profiles configured in AvePoint Online Services.

| Method | Endpoint | Description |
|-----------|-----------|-----------|
|GET|`/partner/external/wm/customers/{customerId}/tenants/{tenantId}/overview/workspace`|Retrieves records for all workspcaes that are match for a specific tenant in AvePoint Online Services.|

## Query Parameters

This section outlines the parameters required to specify which tenant's workspace detail records you want to retrieve.

| Parameter | Description | Type | Required |
| --- | --- | --- | --- |
| CustomerId | The customer's ID. | string | Yes |
| TenantId | The customer tenant's ID. | string | Yes |


## Response

If the request has been successfully processed, a 200 OK response will be returned along with the requested information displayed in the response body.

| Response | Description | Type |
| --- | --- | --- |
| Workspaces | The number Of Workspaces. | integer |
| Teams | The number Of Teams. | integer |
| SharePointSites | The number Of SharePointSites.  | integer |
| OneDrives | The number Of OneDrives. | integer |
| Groups | The number Of Groups. | integer |
| ExchangeMailboxes | The number Of ExchangeMailboxes. | integer |
| ActiveWorkspaces | The number Of ActiveWorkspaces. | integer |
| InactiveWorkspaces | The number Of InactiveWorkspaces. | integer |
| OrphanedWorkspaces | The number Of OrphanedWorkspaces. | integer |
| OrphanedTeams | The number Of OrphanedTeams. | integer |
| OrphanedSharePointSites | The number Of OrphanedSharePointSites. | integer |
| OrphanedOneDrives | The number Of OrphanedOneDrives. | integer |
| OrphanedGroups | The number Of OrphanedGroups. | integer |
| WorkspacesWithGuestUsers | The number Of WorkspacesWithGuestUsers. | integer |
| TeamsWithGuestUsers | The number Of TeamsWithGuestUsers. | integer |
| SharePointSitesWithGuestUsers | The number Of SharePointSitesWithGuestUsers. | integer |
| OneDrivesWithGuestUsers | The number Of OneDrivesWithGuestUsers. | integer |
| GroupsWithGuestUsers | The number Of GroupsWithGuestUsers. | integer |
| ReachingStorageLimitWorkspaces | The number Of ReachingStorageLimitWorkspaces. | integer |
| ReachingStorageLimitTeams | The number Of ReachingStorageLimitTeams. | integer |
| ReachingStorageLimitSharePointSites | The number Of ReachingStorageLimitSharePointSites. | integer |
| ReachingStorageLimitOneDrives | The number Of ReachingStorageLimitOneDrives. | integer |
| ReachingStorageLimitGroups | The number Of ReachingStorageLimitGroups. | integer |
| ReachingStorageLimitMailboxes | The number Of ReachingStorageLimitMailboxes. | integer |


## Request Sample

To use this API, send a GET request to the specified endpoint, including necessary parameters as defined in the references.

```json
https://graph.avepointonlineservices.com/partner/customers/966f35cc-61f4-4070-819c-25cdbcf82a07/tenants/0c7715b3-bc2f-4c4c-a8a0-f3634dcfacec/overview/workspace
```

## Response Sample

If the request has been successfully processed, a 200 OK response will be returned along with the requested information displayed in the response body. For more details on the HTTP status code, refer to [Http Status Code](https://learn.avepoint.com/docs/Use-AvePoint-Graph-API.html#http-status-code).

```json 
{
    "Workspaces": 4285,
    "Teams": 171,
    "SharePointSites": 865,
    "OneDrives": 12,
    "Groups": 2989,
    "ExchangeMailboxes": 248,
    "ActiveWorkspaces": 159,
    "InactiveWorkspaces": 399,
    "OrphanedWorkspaces": 264,
    "OrphanedTeams": 56,
    "OrphanedGroups": 192,
    "OrphanedSharePointSites": 15,
    "WorkspacesWithGuestUsers": 88,
    "OrphanedOneDrives": 1,
    "TeamsWithGuestUsers": 13,
    "SharePointSitesWithGuestUsers": 37,
    "OneDrivesWithGuestUsers": 0,
    "GroupsWithGuestUsers": 38,
    "ReachingStorageLimitWorkspaces": 0,
    "ReachingStorageLimitTeams": 0,
    "ReachingStorageLimitSharePoint": 0,
    "ReachingStorageLimitOneDrives": 0,
    "ReachingStorageLimitGroups": 0,
    "ReachingStorageLimitMailboxes": 0,
    "ReachingStorageLimitSharePointSites": 0
}