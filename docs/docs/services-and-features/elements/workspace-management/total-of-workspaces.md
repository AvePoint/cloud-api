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
| numberOfWorkspaces | The number Of Workspaces. | integer |
| numberOfTeams | The number Of Teams. | integer |
| numberOfSharePointSites | The number Of SharePointSites.  | integer |
| numberOfOneDrives | The number Of OneDrives. | integer |
| numberOfGroups | The number Of Groups. | integer |
| numberOfExchangeMailboxes | The number Of ExchangeMailboxes. | integer |
| numberOfActiveWorkspaces | The number Of ActiveWorkspaces. | integer |
| numberOfInactiveWorkspaces | The number Of InactiveWorkspaces. | integer |
| numberOfOrphanedWorkspaces | The number Of OrphanedWorkspaces. | integer |
| numberOfOrphanedTeams | The number Of OrphanedTeams. | integer |
| numberOfOrphanedSharePointSites | The number Of OrphanedSharePointSites. | integer |
| numberOfOrphanedOneDrives | The number Of OrphanedOneDrives. | integer |
| numberOfOrphanedGroups | The number Of OrphanedGroups. | integer |
| numberOfWorkspacesWithGuestUsers | The number Of WorkspacesWithGuestUsers. | integer |
| numberOfTeamsWithGuestUsers | The number Of TeamsWithGuestUsers. | integer |
| numberOfSharePointSitesWithGuestUsers | The number Of SharePointSitesWithGuestUsers. | integer |
| numberOfOneDrivesWithGuestUsers | The number Of OneDrivesWithGuestUsers. | integer |
| numberOfGroupsWithGuestUsers | The number Of GroupsWithGuestUsers. | integer |
| numberOfReachingStorageLimitWorkspaces | The number Of ReachingStorageLimitWorkspaces. | integer |
| numberOfReachingStorageLimitTeams | The number Of ReachingStorageLimitTeams. | integer |
| numberOfReachingStorageLimitSharePointSites | The number Of ReachingStorageLimitSharePointSites. | integer |
| numberOfReachingStorageLimitOneDrives | The number Of ReachingStorageLimitOneDrives. | integer |
| numberOfReachingStorageLimitGroups | The number Of ReachingStorageLimitGroups. | integer |
| numberOfReachingStorageLimitMailboxes | The number Of ReachingStorageLimitMailboxes. | integer |


## Request Sample

To use this API, send a GET request to the specified endpoint, including necessary parameters as defined in the references.

```json
https://graph.avepointonlineservices.com/partner/customers/966f35cc-61f4-4070-819c-25cdbcf82a07/tenants/0c7715b3-bc2f-4c4c-a8a0-f3634dcfacec/overview/workspace
```

## Response Sample

If the request has been successfully processed, a 200 OK response will be returned along with the requested information displayed in the response body. For more details on the HTTP status code, refer to [Http Status Code](https://learn.avepoint.com/docs/Use-AvePoint-Graph-API.html#http-status-code).

```json 
{
    "numberOfWorkspaces": 4285,
    "numberOfTeams": 171,
    "numberOfSharePointSites": 865,
    "numberOfOneDrives": 12,
    "numberOfGroups": 2989,
    "numberOfExchangeMailboxes": 248,
    "numberOfActiveWorkspaces": 159,
    "numberOfInactiveWorkspaces": 399,
    "numberOfOrphanedWorkspaces": 264,
    "numberOfOrphanedTeams": 56,
    "numberOfOrphanedGroups": 192,
    "numberOfOrphanedSharePointSites": 15,
    "numberOfWorkspacesWithGuestUsers": 88,
    "numberOfOrphanedOneDrives": 1,
    "numberOfTeamsWithGuestUsers": 13,
    "numberOfSharePointSitesWithGuestUsers": 37,
    "numberOfOneDrivesWithGuestUsers": 0,
    "numberOfGroupsWithGuestUsers": 38,
    "numberOfReachingStorageLimitWorkspaces": 0,
    "numberOfReachingStorageLimitTeams": 0,
    "numberOfReachingStorageLimitSharePoint": 0,
    "numberOfReachingStorageLimitOneDrives": 0,
    "numberOfReachingStorageLimitGroups": 0,
    "numberOfReachingStorageLimitMailboxes": 0,
    "numberOfReachingStorageLimitSharePointSites": 0
}