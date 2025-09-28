# Get the scan profile daily summary in Avepoint Online Services for a customer

Use this API to get the scan profile daily summary in Avepoint Online Services for a customer. 

 ## Permissions

The following permission is required to call the API.  
You must register an app through Elements > API app registration to authenticate and authorize your access to AvePoint Graph API. For details, refer to [App Registration](https://cdn.avepoint.com/assets/apelements-webhelp/avepoint-elements-for-partners/index.htm#!Documents/appregistration.htm).

| API | Permission  |
|-----------|--------|
| `partner/external/v3/general/customers/{customerId}/scan-profiles/{scanProfileId}/daily/summary`|elements.scanprofiles.read.all|  

## Request

This section outlines the details of the HTTP method and endpoint used to get the scan profile daily summary in Avepoint Online Services for a customer.

| Method | Endpoint | Description |
|-----------|--------|------------|
| GET | `partner/external/v3/general/customers/{customerId}/scan-profiles/{scanProfileId}/daily/summary` | Get the scan profile daily summary in Avepoint Online Services for a customer.|

## Response

If the request has been successfully processed, a 200 OK response will be returned along with the requested information displayed in the response body.
 
| Field | Description | Type |
| --- | --- | --- |
| profileName               | The profile name of the profile.                 | string |
| profileId     | The profile id of the profile.       | string |
| description       | The description of the profile.      | string |
| tenantId | The tenant id of the profile. | string |
| tenantDomain | The tenant domain of the profile. | string |
| scanMode | The scan mode of the profile. <ul><li>**0** - Express</li><li>**1** - Filter</li></ul> | integer |
| modifiedTime | The modify time of the profile. | string |
| lastUpdateTime | The last update time of the profile. | string |
| lastScanStatus | The last scan status of the profile. <ul><li>**0** - None</li><li>**1** - Running</li><li>**2** - Finished</li><li>**3** - Failed</li><li>**4** - FinishedWithException</li><li>**5** - Skipped</li><li>**6** - Pending</li><li>**7** - ErrorStart</li><li>**8** - Canceled</li><li>**9** - Rejected</li><li>**10** - Stopped</li><li>**11** - NotScan</li><li>**12** - Disabled</li><li>**13** - NotStart</li><li>**14** - WaitForTheConfiguration</li></ul> | integer |
| newRegisteredContentCount | The new register content count the profile. | integer |
| movedToAnotherContainer | The moved to another container of the profile. | integer |
| removedFromMicrosoft365OrOutofPolicy | The removed from microsoft365 or out of policy of the profile. | integer |

## Request Sample
To use this API, send a GET request to the specified endpoint, including necessary parameters as defined in the references.
```json
https://graph.avepointonlineservices.com/partner/external/v3/general/customers/{customerId}/scan-profiles/{scanProfileId}/daily/summary
```
 
## Response Sample
If the request has been successfully processed, a 200 OK response will be returned along with the requested information displayed in the response body.
For more details on the HTTP status code, refer to [Http Status Code](https://learn.avepoint.com/docs/Use-AvePoint-Graph-API.html#http-status-code).
```json
{
    "profileName": "Default Microsoft 365 Scan Profile",
    "profileId": "47dba9a1-1004-4c2d-b2ce-8f5e66f5842d",
    "tenantDomain": "v0s40",
    "tenantId": "c2350b99-c7a2-4605-b7d4-79e8646f66c3",
    "description": "This is a partner-configured scan profile.",
    "scanMode": 0,
    "modifiedTime": "2025-09-11T03:19:14Z",
    "lastUpdateTime": "2025-09-11T03:19:14Z",
    "lastScanStatus": 2,
    "newRegisteredContentCount": 0,
    "movedToAnotherContainer": 0,
    "removedFromMicrosoft365OrOutofPolicy": 0
}
```