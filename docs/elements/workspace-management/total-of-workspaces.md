# Retrieve Workspace Overview of Tenant

Use this API to retrieve the workspace overview statistics of a specific tenant in Elements.  

## Permission  

The following permission is required to call the API.  
You must register an app through Elements > API app registration to authenticate and authorize your access to AvePoint Graph API. For details, refer to [App Registration](../register-app.md).

| API | Permission |
|-----------|-----------|
| `/partner/external/wm/customers/{customerId}/tenants/{tenantId}/overview/workspace` | elements.wm.read.all |  


## Request

This section outlines the HTTP method and endpoint used to retrieve the workspace overview statistics. It provides a concise description of the action performed by the API call.

| Method | Endpoint | Description |
|-----------|-----------|-----------|
|GET|`/partner/external/wm/customers/{customerId}/tenants/{tenantId}/overview/workspace`|Retrieves statistics of workspcaes for a specific tenant.|

## URL Parameters

This section outlines the parameters required to specify which tenant's workspace overview statistics you want to retrieve.

| Parameter | Description | Type | Required |
| --- | --- | --- | --- |
| customerId | The customer ID | string | Yes |
| tenantId | The tenant ID of the customer | string | Yes |


## Response

If the request has been successfully processed, a 200 OK response will be returned along with the requested information displayed in the response body.

| Response | Description | Type |
| --- | --- | --- |
| workspaces | The total number of workspaces. | integer |
| teams | The number of Teams. | integer |
| sharePointSites | The number of SharePoint sites.  | integer |
| oneDrives | The number of OneDrives. | integer |
| groups | The number of groups. | integer |
| exchangeMailboxes | The number of Exchange mailboxes. | integer |
| activeWorkspaces | The number of active workspaces. | integer |
| inactiveWorkspaces | The number of inactive workspaces. | integer |
| orphanedWorkspaces | The total number of orphaned workspaces. | integer |
| orphanedTeams | The number of orphaned Teams. | integer |
| orphanedSharePointSites | The number of orphaned SharePoint sites. | integer |
| orphanedOneDrives | The number of orphaned OneDrives. | integer |
| orphanedGroups | The number of orphaned groups. | integer |
| workspacesWithGuestUsers | The total number of workspaces with guest users. | integer |
| teamsWithGuestUsers | The number of Teams with guest users. | integer |
| sharePointSitesWithGuestUsers | The number of SharePoint sites with guest users. | integer |
| oneDrivesWithGuestUsers | The number of OneDrives with guest users. | integer |
| groupsWithGuestUsers | The number of groups with guest users. | integer |
| reachingStorageLimitWorkspaces | The total number of workspaces that have reached 90% of their storage limits. | integer |
| reachingStorageLimitTeams | The number of Teams that have reached 90% of their storage limits. | integer |
| reachingStorageLimitSharePointSites | The number of SharePoint sites that have reached 90% of their storage limits. | integer |
| reachingStorageLimitOneDrives | The number of OneDrives that have reached 90% of their storage limits. | integer |
| reachingStorageLimitGroups | The number of groups that have reached 90% of their storage limits. | integer |
| reachingStorageLimitMailboxes | The number of mailboxes that have reached 90% of their storage limits. | integer |


## Request Sample

To use this API, send a GET request to the specified endpoint, including necessary parameters as defined in the references.

```json
https://graph.avepointonlineservices.com/partner/customers/966f35cc-****-4070-****-25cd****2a07/tenants/0c7715b3-****-4c4c-****-f363****acec/overview/workspace
```

## Response Sample

If the request has been successfully processed, a 200 OK response will be returned along with the requested information displayed in the response body. For more details on the HTTP status code, refer to [Http Status Code](../Use-AvePoint-Graph-API.md/#http-status-code).

```json 
{
    "workspaces": 4285, // The total number of workspaces
    "teams": 171, // The number of Teams
    "sharePointSites": 865, // The number of SharePoint sites
    "oneDrives": 12, // The number of OneDrives
    "groups": 2989, // The number of groups
    "exchangeMailboxes": 248, // The number of Exchange mailboxes
    "activeWorkspaces": 159, // The number of active workspaces
    "inactiveWorkspaces": 399, // The number of inactive workspaces
    "orphanedWorkspaces": 264, // The total number of orphaned workspaces
    "orphanedTeams": 56, // The number of orphaned Teams
    "orphanedGroups": 192, // The number of orphaned groups
    "orphanedSharePointSites": 15, // The number of orphaned SharePoint sites
    "workspacesWithGuestUsers": 88, // The total number of workspaces with guest users
    "orphanedOneDrives": 1, // The number of orphaned OneDrives
    "teamsWithGuestUsers": 13, // The number of Teams with guest users
    "sharePointSitesWithGuestUsers": 37, // The number of SharePoint sites with guest users
    "oneDrivesWithGuestUsers": 0, // The number of OneDrives with guest users
    "groupsWithGuestUsers": 38, // The number of groups with guest users
    "reachingStorageLimitWorkspaces": 0, // The total number of workspaces that have reached 90% of their storage limits
    "reachingStorageLimitTeams": 0, // The number of Teams that have reached 90% of their storage limits
    "reachingStorageLimitSharePoint": 0, // The number of SharePoint sites that have reached 90% of their storage limits
    "reachingStorageLimitOneDrives": 0, // The number of OneDrives that have reached 90% of their storage limits
    "reachingStorageLimitGroups": 0, // The number of groups that have reached 90% of their storage limits
    "reachingStorageLimitMailboxes": 0, // The number of mailboxes that have reached 90% of their storage limits
    "reachingStorageLimitSharePointSites": 0 // The number of SharePoint sites that have reached 90% of their storage limits
}