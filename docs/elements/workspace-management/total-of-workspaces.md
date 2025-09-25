# Retrieve Workspace Overview

Use this API to retrieve the workspace overview statistics of a specific tenant in Elements.  

## Permission  

The following permission is required to call the API.  
You must register an app through Elements > API app registration to authenticate and authorize your access to AvePoint Graph API. For details, refer to [App Registration](https://cdn.avepoint.com/assets/apelements-webhelp/avepoint-elements-for-partners/index.htm#!Documents/appregistration.htm).

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
| groups | The number of Groups. | integer |
| exchangeMailboxes | The number of Exchange mailboxes. | integer |
| activeWorkspaces | The number of active workspaces. | integer |
| inactiveWorkspaces | The number of inactive workspaces. | integer |
| orphanedWorkspaces | The total number of orphaned workspaces. | integer |
| orphanedTeams | The number of orphaned Teams. | integer |
| orphanedSharePointSites | The number of orphaned SharePoint sites. | integer |
| orphanedOneDrives | The number of orphaned OneDrives. | integer |
| orphanedGroups | The number of orphaned Groups. | integer |
| workspacesWithGuestUsers | The total number of workspaces with guest users. | integer |
| teamsWithGuestUsers | The number of Teams with guest users. | integer |
| sharePointSitesWithGuestUsers | The number of SharePoint sites with guest users. | integer |
| oneDrivesWithGuestUsers | The number of OneDrives with guest users. | integer |
| groupsWithGuestUsers | The number of Groups with guest users. | integer |
| reachingStorageLimitWorkspaces | The total number of workspaces that have reached 90% of their storage limits. | integer |
| reachingStorageLimitTeams | The number of Teams that have reached 90% of their storage limits. | integer |
| reachingStorageLimitSharePointSites | The number of SharePoint sites that have reached 90% of their storage limits. | integer |
| reachingStorageLimitOneDrives | The number of OneDrives that have reached 90% of their storage limits. | integer |
| reachingStorageLimitGroups | The number of Groups that have reached 90% of their storage limits. | integer |
| reachingStorageLimitMailboxes | The number of mailboxes that have reached 90% of their storage limits. | integer |


## Request Sample

To use this API, send a GET request to the specified endpoint, including necessary parameters as defined in the references.

```json
https://graph.avepointonlineservices.com/partner/customers/966f35cc-****-4070-****-25cd****2a07/tenants/0c7715b3-****-4c4c-****-f363****acec/overview/workspace
```

## Response Sample

If the request has been successfully processed, a 200 OK response will be returned along with the requested information displayed in the response body. For more details on the HTTP status code, refer to [Http Status Code](https://learn.avepoint.com/elements/Use-AvePoint-Graph-API.html#http-status-code).

```json 
{
    "workspaces": 4285,
    "teams": 171,
    "sharePointSites": 865,
    "oneDrives": 12,
    "groups": 2989,
    "exchangeMailboxes": 248,
    "activeWorkspaces": 159,
    "inactiveWorkspaces": 399,
    "orphanedWorkspaces": 264,
    "orphanedTeams": 56,
    "orphanedGroups": 192,
    "orphanedSharePointSites": 15,
    "workspacesWithGuestUsers": 88,
    "orphanedOneDrives": 1,
    "teamsWithGuestUsers": 13,
    "sharePointSitesWithGuestUsers": 37,
    "oneDrivesWithGuestUsers": 0,
    "groupsWithGuestUsers": 38,
    "reachingStorageLimitWorkspaces": 0,
    "reachingStorageLimitTeams": 0,
    "reachingStorageLimitSharePoint": 0,
    "reachingStorageLimitOneDrives": 0,
    "reachingStorageLimitGroups": 0,
    "reachingStorageLimitMailboxes": 0,
    "reachingStorageLimitSharePointSites": 0
}