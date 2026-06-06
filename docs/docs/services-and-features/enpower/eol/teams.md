# Retrieve End-of-Life Teams

Use this API to access and retrieve information of your end-of-life Microsoft Teams and their details.

>[!NOTE]
> Currently, only Teams whose end-of-life operations were performed via MyHub can be retrieved via this API. For more information on MyHub or to request additional object retrieval, contact your Sales Representative.

## Permission

The following permission is required to call the API.
You must register the app through AvePoint Online Services > App registrations to authenticate and authorize your access to AvePoint Graph API.
For details, refer to [Authentication and Authorization](https://learn.avepoint.com/docs/Use-AvePoint-Graph-API.html#authentication-and-authorization).

| API   | Permission |
|-------------------|---------------|
|`smp/lifecycle/microsoft365/teams` | enpower.data.read.all | 

## Request

This section provides details on the HTTP method and endpoint used to retrieve general information of your Teams.

| Method | Endpoint | Description | 
|--- | --- | --- |
| GET | `smp/lifecycle/microsoft365/teams` | Retrieves end-of-life Teams and their properties. | 

## Query Parameters

The API supports several query parameters to refine and customize the data retrieval process.

| Parameters | Description | Type | Required |
|--- | --- | --- | --- |
| top | The number of Teams records retrieved and returned each page. The default number is 100. You can enter a number from 1 to 1000. | integer | No |
| tenant | The tenant in which data of Teams are retrieved. By default, Teams of all tenants are retrieved. | string | No |

## Responses

The API response provides detailed information about the end-of-life Teams retrieved. Each Team in the response includes various attributes that describe its properties and status.

| Element | Description | Type |
| --- | --- | --- |
| objectId | The unique identifier of the Team. | string |
| tenantId | The unique identifier of the tenant where the Team is hosted. | string |
| tenantDomain | The tenant domain of the Team. | string |
| displayName | The display name of the Team. | string |
| description | A brief description of the Team. | string |
| emailAddress | The email address of the Team. | string |
| sensitivity | The sensitivity label of the Team. | string |
| teamVisibilityType | The privacy setting for this Team: <ul><li> **1** for Public </li><li> Other values for Private | integer |
| classification | The classification of the Team. | string |
| groupId | The unique identifier of the group connected to the Team. | string |
| siteUrl | The URL of the site connected to the Team. | string |
| storageUsed | The storage used by the Team. | string |
| createTime | The date and time when the Team was created. | DateTime |
| actionType | The lifecycle action applied to the Team: <ul><li> **0** for None </li><li> **1** for Delete </li><li> **2** for Archive </li><li> **4** for No-access </li><li> **8** for Read-only </li><li> **16** for Disabled </li><li>  **32** for Quarantine </li><li> **64** for Deactivate </li><li> **128** for Archive via Opus | integer |
| actionTime | The date and time when the lifecycle action was performed on the Team. | DateTime |
| operatorId | The unique identifier of the user who performed the lifecycle action. | string |
| operatorUserPrincipalName | The user principal name of the user who performed the lifecycle action. | string |
| operatorDisplayName | The display name of the user who performed the lifecycle action. | string |
| platform | The platform where this lifecycle action was performed (only MyHub can now be retrieved): <ul><li> **0** for None </li><li> **1** for Cloud Governance </li><li> **2** for MyHub </li><li> **4** for Policies for Microsoft 365 </li><li> **8** for EnPower </li><li> **16** for Microsoft | integer |



## Request Sample

To use this API, send a GET request to the specified endpoint, including necessary parameters as defined in the references. This will return the relevant object details in a structured format, enabling easy integration with other systems or applications. The following request is an API call to the EnPower environment in the US - East region.

```json
https://graph-us.avepointonlineservices.com/smp/lifecycle/microsoft365/teams
```
## Response Sample

If the request has been successfully processed, a 200 OK response will be returned along with the requested information displayed in the response body. For more details on the HTTP status code, refer to [HTTP Status Code](https://learn.avepoint.com/docs/Use-AvePoint-Graph-API.html#http-status-code).

```json
{
    "eolReportTeams": [
        {
            "displayName": "Sample Team", // The display name of the Team.
            "description": "The sample Team for API response.", // A brief description of the Team.
            "emailAddress": "sampleteam@contoso.com", // The email address of the Team.
            "sensitivity": "", // The sensitivity label of the Team.
            "tenantDomain": "sample.contoso.com", // The tenant domain of the Team.
            "privacy": 1, // The privacy setting for this Team.
            "classification": null, // The classification of the Team.
            "groupId": "893c9d3a-****-****-****-7975b2b33e56", // The unique identifier of the group connected to the Team.
            "siteUrl": "https://****.sharepoint.com/sites/sampleteam", // The URL of the site connected to the Team.
            "storageUsed": "0.00", // The storage used by the Team.
            "createTime": "2026-03-10T10:14:19.051", // The date and time when the Team was created.
            "tenantId": "3950bd4b-****-****-****-59e24efa58cb", // The unique identifier of the tenant where the Team is hosted.
            "objectId": "893c9d3a-****-****-****-7975b2b33e56", // The unique identifier of the Team.
            "actionType": 1, // The lifecycle action applied to the Team.
            "actionTime": "2026-03-11T10:08:01.685853", // The date and time when the lifecycle action was performed on the Team.
            "operatorId": "7f549606-****-****-****-1689e19807c1", // The unique identifier of the user who performed the lifecycle action.
            "operatorUserPrincipalName": "sampleuser@contoso.com", // The user principal name of the user who performed the lifecycle action.
            "operatorDisplayName": "Sample User", // The display name of the user who performed the lifecycle action.
            "platform": 2 // The platform where this lifecycle action was performed.
        }
    ],
    "totalCount": 1,
    "nextLink": ""
}


```