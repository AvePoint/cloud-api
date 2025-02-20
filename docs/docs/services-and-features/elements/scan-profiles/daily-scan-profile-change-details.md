# Retrieve Daily Scan Profiles Change Details

Use this API to retrieve your customer's daily scan profile change details in AvePoint Online Services.

## Permissions  

The following permission is required to call the API.  
You must register an app through Elements for Partners > App registration to authenticate and authorize your access to AvePoint Graph API. For details, refer to [App Registration](https://cdn.avepoint.com/assets/apelements-webhelp/avepoint-elements-for-partners/index.htm#!Documents/appregistration.htm).

| API | Permission  |
|-----------|--------|
| `/partner/customers/{id}/scanProfilesDailyNewDetail/profileId/{ProfileId}`| partner.scanprofiles.read.all|  

## Request

This section outlines the HTTP method and endpoint used to retrieve customer's daily scan profile change details in AvePoint Online Services.

| Method | Endpoint | Description |  
|-----------|-----------|-----------|
|GET|`/partner/customers/{id}/scanProfilesDailyNewDetail/profileId/{ProfileId}`| Retrieves your customer's daily scan profile change details in AvePoint Online Services.|


## Query Parameters

This section outlines the parameters required to specify which customer's daily scan profile change details in AvePoint Online Services you want to retrieve.

| Parameter | Description | Type | Required |
| --- | --- | --- | --- |
| id | The tenant owner ID of the customer. | string | Yes |
| profileId | The ID of the scan profile. | string | Yes |

## Responses

If the request has been successfully processed, a 200 OK response will be returned along with the requested information displayed in the response body.

| Response | Description | Type |
| --- | --- | --- |
| profileName | The name of the scan profile. | string |
| profileId | The ID of the scan profile. | string |
| tenantDomain | The tenant domain of the scan profile. | string |
| tenantId | The tenant ID the scan profile. | string |
| lastUpdateTime | The time of generating the daily report for the scan profile. If no daily report has been generated, the time is the last modified time of the scan profile. | string |
|removedFromMicrosoft365OrOutOfPolicyObjects | The details of objects moved to another container in the daily report of the scan profile. | list |
| newRegisteredContent | The details of newly registered objects in the daily report of the scan profile. | list |
| movedToAnotherContainerObjects | The details of objects removed from Microsoft 365 or out of policy in the daily report of the scan profile. | list |

## Request Sample

To use this API, send a GET request to the specified endpoint, including necessary parameters as defined in the references.  

```json
https://graph.avepointonlineservices.com/partner/customers/caf94a75-2cc6-43bb-b04b-794cb9af5ea3/scanProfilesDailyNewDetail/profileId/0e5e152d-65cc-4206-9829-636ee72c88c3
```

## Response Sample

If the request has been successfully processed, a 200 OK response will be returned along with the requested information displayed in the response body. For more details on the HTTP status code, refer to [HttpStatusCode](https://learn.avepoint.com/docs/Use-AvePoint-Graph-Modern-API.html#http-status-code).

```json 
{
    "@odata.context": "https://graph.avepointonlineservices.com/partner/$metadata#Portal.Api.Model.ProfileDailyNewDetailInfo",
    "profileName": "M365 3216p0 hana", // The name of the scan profile
    "profileID": "02d305fb-ddba-4460-b533-74a25a875e3c", // The ID of the scan profile
    "tenantDomain": "3216p0",// The tenant domain of the scan profile
    "tenantID": "848aa322-4bbf-4637-954f-7b930a80f46c",// The tenant ID.
    "lastUpdateTime": "2024-11-22T23:59:24Z", // The time the daily report for the scan profile was generated. If no daily report has been generated, the time will be the last modified time of the scan profile
    "removedFromMicrosoft365OrOutOfPolicyObjects": [], //The details of objects moved to another container in the daily report of the scan profile
    "newRegistedContent": [], // Deprecated. A list of newly registered objects in the daily report of the scan profile
    "newRegisteredContent": [], // A list of newly registered objects in the daily report of the scan profile
    "movedToAnotherContainerObjects": [] // A list of objects removed from Microsoft 365 or out of policy in the daily report of the scan profile
}

