# Retrieve End-of-Life Groups

Use this API to access and retrieve information of your end-of-life Groups and their details.

>[!NOTE]
> Currently, only Groups whose end-of-life operations were performed via MyHub can be retrieved via this API. For more information on MyHub or to request additional object retrieval, contact your Sales Representative.

## Permission

The following permission is required to call the API.
You must register the app through AvePoint Online Services > App registrations to authenticate and authorize your access to AvePoint Graph API.
For details, refer to [Authentication and Authorization](https://learn.avepoint.com/docs/Use-AvePoint-Graph-API.html#authentication-and-authorization).

| API   | Permission |
|-------------------|---------------|
|`smp/lifecycle/microsoft365/groups` | enpower.data.read.all | 

## Request

This section provides details on the HTTP method and endpoint used to retrieve general information of your Groups.

| Method | Endpoint | Description | 
|--- | --- | --- |
| GET | `smp/lifecycle/microsoft365/groups` | Retrieves end-of-life Groups and their properties. | 

## Query Parameters

The API supports several query parameters to refine and customize the data retrieval process.

| Parameters | Description | Type | Required |
|--- | --- | --- | --- |
| top | The number of Group records retrieved and returned each page. The default number is 100. You can enter a number from 1 to 1000. | integer | No |
| tenant | The tenant in which data of Groups are retrieved. By default, Groups of all tenants are retrieved. | string | No |

## Responses

The API response provides detailed information about the end-of-life Groups retrieved. Each Group in the response includes various attributes that describe its properties and status.

| Element | Description  | Type |
|-|-|-|
| objectId | The unique identifier of the group. | string    |
| tenantId  | The unique identifier of the tenant where the group is hosted. | string |
| tenantDomain | The tenant domain of the group. | string |
| displayName | The display name of the group. | string |
| mail | The email address of the group. | string    |
| mailNickname | The mail nickname of the group. | string    |
| mailEnabled | Indicates whether the group is mail-enabled. | boolean   |
| groupType                   | The type of the group: <ul><li> **1** for Microsoft 365 Group </li><li> **2** for Security group </li><li> **4** for Distribution Group </li><li> **8** for Mail-enabled security group </li><li> **-1** for Unknown| integer   |
| deletedDateTime  | The date and time when the group was deleted. | DateTime  |
| teamStatus  | The Microsoft Teams connection status of the group: <ul><li> **1** for Not connected </li><li> **2** for Connected </li><li> **4** for Archived </li><li> **-1** for Unknown| integer   |
| membershipType | The membership type of the group: <ul><li> **1** for Assigned </li><li> **2** for Dynamic </li><li> **-1** for Unknown | integer   |
| visibility  | The privacy setting of the group: <ul><li> **1** for Public </li><li> **2** for Private </li><li> **4** for Membership hidden </li><li> **-1** for Unknown| integer   |
| createTime | The date and time when the group was created. | DateTime  |
| actionType | The lifecycle action applied to the group: <ul><li> **0** for None </li><li> **1** for Delete </li><li> **2** for Archive </li><li> **4** for No-access </li><li> **8** for Read-only </li><li> **16** for Disabled </li><li>  **32** for Quarantine </li><li> **64** for Deactivate </li><li> **128** for Archive via Opus | integer   |
| actionTime | The date and time when the lifecycle action was performed on the group. | DateTime  |
| operatorId | The unique identifier of the user who performed the lifecycle action. | string    |
| operatorUserPrincipalName   | The user principal name of the user who performed the lifecycle action. | string    |
| operatorDisplayName | The display name of the user who performed the lifecycle action. | string    |
| platform | The platform where this lifecycle action was performed (only MyHub can now be retrieved): <ul><li> **0** for None </li><li> **1** for Cloud Governance </li><li> **2** for MyHub </li><li> **4** for Policies for Microsoft 365 </li><li> **8** for EnPower </li><li> **16** for Microsoft | integer   |

## Request Sample

To use this API, send a GET request to the specified endpoint, including necessary parameters as defined in the references. This will return the relevant object details in a structured format, enabling easy integration with other systems or applications. The following request is an API call to the EnPower environment in the US - East region.

```json
https://graph-us.avepointonlineservices.com/smp/lifecycle/microsoft365/groups
```
## Response Sample

If the request has been successfully processed, a 200 OK response will be returned along with the requested information displayed in the response body. For more details on the HTTP status code, refer to [HTTP Status Code](https://learn.avepoint.com/docs/Use-AvePoint-Graph-API.html#http-status-code).

```json
{
    "eolReportGroups": [
        {
            "displayName": "Sample Group 1", // The display name of the group.
            "tenantDomain": null, // The tenant domain of the group.
            "mail": "sampleemail1@contoso.com", // The email address of the group.
            "mailNickname": "", // The mail nickname of the group.
            "mailEnabled": null, // Indicates whether the group is mail-enabled.
            "groupType": 4, // The type of the group.
            "deletedDateTime": "2026-05-18T09:21:34.2944957", // The date and time when the group was deleted.
            "teamStatus": -1, // The Microsoft Teams connection status of the group.
            "membershipType": 0, // The membership type of the group.
            "visibility": -1, // The privacy setting of the group.
            "createdDateTime": "2025-06-17T09:45:29", // The date and time when the group was created.
            "tenantId": "3950bd4b-****-****-****-59e24efa58cb", // The unique identifier of the tenant where the group is hosted.
            "objectId": "01d023b8-****-****-****-4c769b7cebee", // The unique identifier of the group.
            "actionType": 1, // The lifecycle action applied to the group.
            "actionTime": "2026-05-18T09:21:34.8344583", // The date and time when the lifecycle action was performed on the group.
            "operatorId": "7f549606-****-****-****-1689e19807c1", // The unique identifier of the user who performed the lifecycle action.
            "operatorUserPrincipalName": "sampleemail2@contoso.com", // The user principal name of the user who performed the lifecycle action.
            "operatorDisplayName": "Sample User 1", // The display name of the user who performed the lifecycle action.
            "platform": 2 // The platform where this lifecycle action was performed.
        },
        {
            "displayName": "Sample Group 2", // The display name of the group.
            "tenantDomain": null, // The tenant domain of the group.
            "mail": "samplemail3@contoso.com", // The email address of the group.
            "mailNickname": "", // The mail nickname of the group.
            "mailEnabled": null, // Indicates whether the group is mail-enabled.
            "groupType": 8, // The type of the group.
            "deletedDateTime": "2026-05-18T09:21:04.811264", // The date and time when the group was deleted.
            "teamStatus": -1, // The Microsoft Teams connection status of the group.
            "membershipType": 0, // The membership type of the group.
            "visibility": -1, // The privacy setting of the group.
            "createdDateTime": "2026-01-13T07:38:44", // The date and time when the group was created.
            "tenantId": "3950bd4b-****-****-****-59e24efa58cb", // The unique identifier of the tenant where the group is hosted.
            "objectId": "0120f165-****-****-****-bc17b19b77a8", // The unique identifier of the group.
            "actionType": 1, // The lifecycle action applied to the group.
            "actionTime": "2026-05-18T09:21:06.7001009", // The date and time when the lifecycle action was performed on the group.
            "operatorId": "7f549606-****-****-****-1689e19807c1", // The unique identifier of the user who performed the lifecycle action.
            "operatorUserPrincipalName": "sampleemail4@contoso.com", // The user principal name of the user who performed the lifecycle action.
            "operatorDisplayName": "Sample User 2", // The display name of the user who performed the lifecycle action.
            "platform": 2 // The platform where this lifecycle action was performed.
        }
    ],
    "totalCount": 2, // The total number of retrieved groups.
    "nextLink": "" // The URL to retrieve the next page of results.
}
```