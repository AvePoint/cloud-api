# Retrieve Workspace Overview

Use this API to retrieve the workspace overview statistics of a specific tenant in Elements.  

## Permission  

The following permission is required to call the API.  
You must register an app through Elements > API app registration to authenticate and authorize your access to AvePoint Graph API. For details, refer to [App Registration](https://cdn.avepoint.com/assets/apelements-webhelp/avepoint-elements-for-partners/index.htm#!Documents/appregistration.htm).

| API | Permission |
|-----------|-----------|
| `/partner/external/wm/customers/{customerId}/tenants/{tenantId}/overview/workspace` | partner.wm.read.all |  


## Request

This section outlines the HTTP method and endpoint used to retrieve the workspace overview statistics. It provides a concise description of the action performed by the API call.

| Method | Endpoint | Description |
|-----------|-----------|-----------|
|GET|`/partner/external/wm/customers/{customerId}/tenants/{tenantId}/overview/workspace`|Retrieves statistics of workspcaes for a specific tenant.|

## Query Parameters

This section outlines the parameters required to specify which tenant's workspace overview statistics you want to retrieve.

| Parameter | Description | Type | Required |
| --- | --- | --- | --- |
| customerId | The customer ID | string | Yes |
| tenantId | The tenant ID of the customer | string | Yes |


## Response

If the request has been successfully processed, a 200 OK response will be returned along with the requested information displayed in the response body.

| Response | Description | Type |
| --- | --- | --- |
| Workspaces | The total number of workspaces. | integer |
| Teams | The number of Teams. | integer |
| SharePointSites | The number of SharePoint sites.  | integer |
| OneDrives | The number of OneDrives. | integer |
| Groups | The number of Groups. | integer |
| ExchangeMailboxes | The number of Exchange mailboxes. | integer |
| ActiveWorkspaces | The number of active workspaces. | integer |
| InactiveWorkspaces | The number of inactive workspaces. | integer |
| OrphanedWorkspaces | The total number of orphaned workspaces. | integer |
| OrphanedTeams | The number of orphaned Teams. | integer |
| OrphanedSharePointSites | The number of orphaned SharePoint sites. | integer |
| OrphanedOneDrives | The number of orphaned OneDrives. | integer |
| OrphanedGroups | The number of orphaned Groups. | integer |
| WorkspacesWithGuestUsers | The total number of workspaces with guest users. | integer |
| TeamsWithGuestUsers | The number of Teams with guest users. | integer |
| SharePointSitesWithGuestUsers | The number of SharePoint sites with guest users. | integer |
| OneDrivesWithGuestUsers | The number of OneDrives with guest users. | integer |
| GroupsWithGuestUsers | The number of Groups with guest users. | integer |
| ReachingStorageLimitWorkspaces | The total number of workspaces that have reached 90% of their storage limits. | integer |
| ReachingStorageLimitTeams | The number of Teams that have reached 90% of their storage limits. | integer |
| ReachingStorageLimitSharePointSites | The number of SharePoint sites that have reached 90% of their storage limits. | integer |
| ReachingStorageLimitOneDrives | The number of OneDrives that have reached 90% of their storage limits. | integer |
| ReachingStorageLimitGroups | The number of Groups that have reached 90% of their storage limits. | integer |
| ReachingStorageLimitMailboxes | The number of mailboxes that have reached 90% of their storage limits. | integer |


## Request Sample

To use this API, send a GET request to the specified endpoint, including necessary parameters as defined in the references.

```json
https://graph.avepointonlineservices.com/partner/customers/966f35cc-****-4070-****-25cd****2a07/tenants/0c7715b3-****-4c4c-****-f363****acec/overview/workspace
```

## Response Sample

If the request has been successfully processed, a 200 OK response will be returned along with the requested information displayed in the response body. For more details on the HTTP status code, refer to [Http Status Code](https://learn.avepoint.com/elements/Use-AvePoint-Graph-API.html#http-status-code).

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