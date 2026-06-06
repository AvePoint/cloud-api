# Retrieve End-of-Life SharePoint Online Sites

Use this API to access and retrieve information of your end-of-life SharePoint Online sites and their details.

>[!NOTE]
> Currently, only sites whose end-of-life operations were performed via MyHub can be retrieved via this API. For more information on MyHub or to request additional object retrieval, contact your Sales Representative.

## Permission

The following permission is required to call the API.
You must register the app through AvePoint Online Services > App registrations to authenticate and authorize your access to AvePoint Graph API.
For details, refer to [Authentication and Authorization](https://learn.avepoint.com/docs/Use-AvePoint-Graph-API.html#authentication-and-authorization).

| API   | Permission |
|-------------------|---------------|
|`smp/lifecycle/microsoft365/sites` | enpower.data.read.all | 

## Request

This section provides details on the HTTP method and endpoint used to retrieve general information of your sites.

| Method | Endpoint | Description | 
|--- | --- | --- |
| GET | `smp/lifecycle/microsoft365/sites` | Retrieves end-of-life sites and their properties. | 

## Query Parameters

The API supports several query parameters to refine and customize the data retrieval process.

| Parameters | Description | Type | Required |
|--- | --- | --- | --- |
| top | The number of site records retrieved and returned each page. The default number is 100. You can enter a number from 1 to 1000. | integer | No |
| tenant | The tenant in which data of sites are retrieved. By default, sites of all tenants are retrieved. | string | No |

## Responses

The API response provides detailed information about the end-of-life sites retrieved. Each site in the response includes various attributes that describe its properties and status.

| Element | Description | Type |
| --- | --- | --- |
| objectId | The unique identifier of the site. | string |
| tenantId | The unique identifier of the tenant where the site is hosted. | string |
| tenantName | The tenant name of the site. | string |
| displayName | The display name of the site. | string |
| url | The URL of the site. | string |
| templateName | The template name of the site. | string |
| ownerName | The name of the site owner. | string |
| ownerEmail | The email address of the site owner. | string |
| siteConnectGroup | Indicates whether the site is group-connected. | string |
| connectedGroupId | The ID of the group connected to the site. | string |
| isTeamsSite | Indicates whether the site is a Microsoft Teams site. | string |
| hubSiteDisplayName | The display name of the hub site. | string |
| createdDateTime | The date and time when the site was created. | DateTime |
| createdBy | The display name of the site creator. | string |
| createdByEmail | The email address of the site creator. | string |
| createdFrom | The source from which the site was created. | string |
| deletedTime | The date and time when the site was deleted. | DateTime |
| deletedBy | The display name of the user who deleted the site. | string |
| storageUsed | The storage used by the site. | string |
| fileViewedOrEdited | The number of files viewed or edited | integer |
| pageViews | The number of page views | integer |
| pageVisits | The number of page visits | integer |
| fileStored | The number of files stored | integer |
| externalSharing | Indicates whether external sharing is allowed. | string |
| actionTime | The date and time when the lifecycle action was performed on the site. | DateTime |
| operatorUserPrincipalName | The user principal name of the user who performed the lifecycle action. | string |
| operatorDisplayName | The display name of the user who performed the lifecycle action. | string |
| platform | The platform where this lifecycle action is performed (only MyHub can now be retrieved):<ul><li> **0** for None </li><li> **1** for Cloud Governance </li><li> **2** for MyHub </li><li> **4** for Policies for Microsoft 365 </li><li> **8** for EnPower </li><li> **16** for Microsoft | integer |


## Request Sample

To use this API, send a GET request to the specified endpoint, including necessary parameters as defined in the references. This will return the relevant object details in a structured format, enabling easy integration with other systems or applications. The following request is an API call to the EnPower environment in the US - East region.

```json
https://graph-us.avepointonlineservices.com/smp/lifecycle/microsoft365/sites
```
## Response Sample

If the request has been successfully processed, a 200 OK response will be returned along with the requested information displayed in the response body. For more details on the HTTP status code, refer to [HTTP Status Code](https://learn.avepoint.com/docs/Use-AvePoint-Graph-API.html#http-status-code).

```json
{
    "eolReportSPSites": [
        {
            "displayName": "Sample Site 1", // The display name of the site.
            "url": "https://****.sharepoint.com/sites/samplesite", // The URL of the site.
            "templateName": "Team site (no Microsoft 365 group)", // The template name of the site.
            "ownerName": "Sample Owner", // The name of the site owner.
            "ownerEmail": "owneremail@contoso.com", // The email address of the site owner.
            "siteConnectGroup": "No", // Indicates whether the site is group-connected.
            "connectedGroupId": "00000000-0000-0000-0000-000000000000", // The ID of the group connected to the site.
            "isTeamsSite": "No", // Indicates whether the site is a Microsoft Teams site.
            "hubSiteDisplayName": "", // The display name of the hub site.
            "createdDateTime": "2026-03-11T09:49:12", // The date and time when the site was created.
            "createdBy": "Sample Owner", // The display name of the site creator.
            "createdByEmail": "owneremail@contoso.com", // The email address of the site creator.
            "createdFrom": "Microsoft 365 Group", // The source from which the site was created.
            "deletedTime": "2026-03-11T10:46:42", // The date and time when the site was deleted.
            "deletedBy": "SharePoint App", // The display name of the user who deleted the site.
            "storageUsed": "0", // The storage used by the site.
            "fileViewedOrEdited": null, // The number of files viewed or edited.
            "pageViews": null, // The number of page views.
            "pageVisits": null, // The number of page visits.
            "fileStored": null, // The number of files stored.
            "externalSharing": "Off", // Indicates whether external sharing is allowed.
            "scanTime": "2026-03-11T09:52:26.8780497",
            "tenantName": null,
            "tenantId": "3950bd4b-****-****-****-59e24efa58cb", // The unique identifier of the tenant where the site is hosted.
            "objectId": "ccda39b0-****-****-****-c8b042cf6ff6", // The unique identifier of the site.
            "actionType": 1,
            "actionTime": "2026-03-11T10:46:38.5472831", // The date and time when the lifecycle action was performed on the site.
            "operatorId": "7f549606-****-****-****-1689e19807c1",
            "operatorUserPrincipalName": "owneremail@contoso.com", // The user principal name of the user who performed the lifecycle action.
            "operatorDisplayName": "Sample Owner", // The display name of the user who performed the lifecycle action.
            "platform": 2 // The platform where this lifecycle action is performed.
        },
        {
            "displayName": "Sample Site 2", // The display name of the site.
            "url": "https://****.sharepoint.com/sites/samplesite2", // The URL of the site.
            "templateName": "Communication site", // The template name of the site.
            "ownerName": "", // The name of the site owner.
            "ownerEmail": "owneremail@contoso.com", // The email address of the site owner.
            "siteConnectGroup": "No", // Indicates whether the site is group-connected.
            "connectedGroupId": "00000000-0000-0000-0000-000000000000", // The ID of the group connected to the site.
            "isTeamsSite": "No", // Indicates whether the site is a Microsoft Teams site.
            "hubSiteDisplayName": "", // The display name of the hub site.
            "createdDateTime": "2026-03-11T09:50:19", // The date and time when the site was created.
            "createdBy": "Sample Owner", // The display name of the site creator.
            "createdByEmail": "owneremail@contoso.com", // The email address of the site creator.
            "createdFrom": "Microsoft 365 Group", // The source from which the site was created.
            "deletedTime": "2026-03-11T10:41:19", // The date and time when the site was deleted.
            "deletedBy": "SharePoint App", // The display name of the user who deleted the site.
            "storageUsed": "0", // The storage used by the site.
            "fileViewedOrEdited": null, // The number of files viewed or edited.
            "pageViews": null, // The number of page views.
            "pageVisits": null, // The number of page visits.
            "fileStored": null, // The number of files stored.
            "externalSharing": "Off", // Indicates whether external sharing is allowed.
            "scanTime": "2026-03-11T09:54:13.0238485",
            "tenantName": null,
            "tenantId": "3950bd4b-****-****-****-59e24efa58cb", // The unique identifier of the tenant where the site is hosted.
            "objectId": "a93a967f-****-****-****-9e1e16dc9b9a", // The unique identifier of the site.
            "actionType": 1,
            "actionTime": "2026-03-11T10:41:16.625103", // The date and time when the lifecycle action was performed on the site.
            "operatorId": "7f549606-****-****-****-1689e19807c1",
            "operatorUserPrincipalName": "owneremail@contoso.com", // The user principal name of the user who performed the lifecycle action.
            "operatorDisplayName": "Sample Owner", // The display name of the user who performed the lifecycle action.
            "platform": 2 // The platform where this lifecycle action is performed.
        }
    ],
    "totalCount": 2,
    "nextLink": ""
}

```