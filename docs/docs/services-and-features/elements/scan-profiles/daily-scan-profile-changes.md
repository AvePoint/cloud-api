# Retrieve Daily Scan Profile Changes

Use this API to retrieve your customer's daily scan profile changes in AvePoint Online Services.

## Permissions  

The following permission is required to call the API.  
You must register an app through Elements for Partners > App registration to authenticate and authorize your access to AvePoint Graph API. For details, refer to [App Registration](https://cdn.avepoint.com/assets/apelements-webhelp/avepoint-elements-for-partners/index.htm#!Documents/appregistration.htm).

| API | Permission  |
|-----------|--------|
| `/partner/customers/{id}/scanProfilesDailyNew/profileId/{ProfileId}` | partner.scanprofiles.read.all |  

## Request

This section outlines the details on the HTTP method and endpoint used to retrieve your customer's daily scan profile changes in AvePoint Online Services.

| Method | Endpoint | Description |
|-----------|--------|-----------|
|GET|`/partner/customers/{id}/scanProfilesDailyNew/profileId/{ProfileId}`|Retrieves your customer's daily scan profile changes in AvePoint Online Services.|

## Query Parameters

This section outlines the parameters required to specify which customer's specific daily scan profile changes in AvePoint Online Services you want to retrieve.

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
| description | The description of the scan profile. | string |
| scanMode | The scan mode of the scan profile:<br> <ul><li>**0** represents **Express mode**<li>**1** represents **Advanced mode**| integer |
| modifiedTime | The last modified time of the scan profile. | string |
| lastUpdateTime | The time the daily report for the scan profile was generated. If no daily report has been generated, the time will be the last modified time of the scan profile. | string |
| lastScanStatus | The last scan job status of the scan profile:<br><ul><li>**2** represents **Finished**<li>**3** represents **Failed**<li>**4** represents **Finished with exception**<li>**5** represents **Skipped**<li>**10** represents **Stopped** | integer |
| newRegisteredContentCount | The number of newly registered objects in the daily report of the scan profile. | integer |
| movedToAnotherContainer | The number of objects moved to another container in the daily report of the scan profile. | integer |
| removedFromMicrosoft365OrOutofPolicy | The number of objects removed from Microsoft 365 or out of policy in the daily report of the scan profile. | integer |

## Request Sample

To use this API, send a GET request to the specified endpoint, including necessary parameters as defined in the references.

```json
https://graph.avepointonlineservices.com/partner/customers/caf94a75-2cc6-43aa-b04b-794cb9af5ea3/scanProfilesDailyNew/profileId/0e5c152d-65ec-4206-9829-636ee72c88c3
```

## Response Sample

If the request has been successfully processed, a 200 OK response will be returned along with the requested information displayed in the response body. For more details on the HTTP status code, refer to [HttpStatusCode](https://learn.avepoint.com/docs/Use-AvePoint-Graph-Modern-API.html#http-status-code).

```json 
{
    "@odata.context": "https://graph.avepointonlineservices.com/partner/api/V1.1/$metadata#Portal.Api.Model.ProfileDailyNewDetailInfo",
    "profileName": "test oop", // The name of the scan profile
    "profileID": "0e5e152d-65cc-4206-9829-636ee72c88c3", // The ID of the scan profile
    "tenantDomain": "v0s40", // The tenant domain of the scan profile
    "tenantID": "c2350b99-c7a2-4605-b7d4-79e8646f66c3", // The tenant ID the scan profile
    "description": "aa", // The description of the scan profile
    "scanMode": 0, // The scan mode of the scan profile: 0 represents Express mode
    "modifiedTime": "2024-10-27T17:08:24Z", // The last modified time of the scan profile
    "lastUpdateTime": "2024-12-27T17:08:24Z", // The time the daily report for the scan profile was generated. If no daily report has been generated, the time will be the last modified time of the scan profile
    "lastScanStatus": 2, // The last scan job status of the scan profile: 2 represents Finished
    "removedFromMicrosoft365OrOutofPolicyObjects": 0 // The details of objects moved to another container in the daily report of the scan profile
    "newRegistedContent": 0, // Deprecated. The details of newly registered objects in the daily report of the scan profile
    "newRegisteredContentCount": 0, // The details of newly registered objects in the daily report of the scan profile
    "movedToAnotherContainerObjects": 0, // The details of objects removed from Microsoft 365 or out of policy in the daily report of the scan profile
}