# Retrieve Daily Scan Profile Changes in AvePoint Online Services for a Customer

Use this API to retrieve the daily scan profile changes in AvePoint Online Services for a customer. 

 ## Permission

The following permission is required to call the API.  
You must register an app through Elements > API app registration to authenticate and authorize your access to AvePoint Graph API. For details, refer to [App Registration](../../../elements/register-app.md).

| API | Permission  |
|-----------|--------|
| `/partner/external/v3/general/customers/{customerId}/scan-profiles/{scanProfileId}/daily/summary`|elements.scanprofiles.read.all|  

## Request

This section outlines the details of the HTTP method and endpoint used to retrieve the daily scan profile changes in AvePoint Online Services for a customer.

| Method | Endpoint | Description |
|-----------|--------|------------|
| GET | `/partner/external/v3/general/customers/{customerId}/scan-profiles/{scanProfileId}/daily/summary` | Retrieve the daily scan profile changes in AvePoint Online Services for a customer.|

## Response

If the request has been successfully processed, a 200 OK response will be returned along with the requested information displayed in the response body.
 
| Field | Description | Type |
| --- | --- | --- |
| profileName               | The name of the scan profile.                 | string |
| profileId     | The ID of the scan profile.       | string |
| description       | The description of the scan profile.      | string |
| tenantId | The tenant ID of the scan profile. | string |
| tenantDomain | The tenant domain of the scan profile. | string |
| scanMode | The scan mode of the profile. <ul><li>**0** - Express mode</li><li>**1** - Advanced mode</li></ul> | integer |
| modifiedTime | The last modified time of the scan profile. | string |
| lastUpdateTime | The time the daily report for the scan profile was generated. If no daily report has been generated, the time will be the last modified time of the scan profile. | string |
| lastScanStatus | The last scan job status of the scan profile. <ul><li>**0** - None</li><li>**1** - Running</li><li>**2** - Finished</li><li>**3** - Failed</li><li>**4** - Finished with exception</li><li>**5** - Skipped</li><li>**6** - Pending</li><li>**7** - Failed to tart</li><li>**8** - Canceled</li><li>**9** - Rejected</li><li>**10** - Stopped</li><li>**11** - Not scanned</li><li>**12** - Disabled</li><li>**13** - Not started</li><li>**14** - Wait for configuration</li></ul> | integer |
| newRegisteredContentCount | The number of newly registered objects in the daily report of the scan profile. | integer |
| movedToAnotherContainer | The number of objects moved to another container in the daily report of the scan profile. | integer |
| removedFromMicrosoft365OrOutofPolicy | The number of objects removed from Microsoft 365 or out of policy in the daily report of the scan profile. | integer |

## Request Sample
To use this API, send a GET request to the specified endpoint, including necessary parameters as defined in the references.
```json
https://graph.avepointonlineservices.com/partner/external/v3/general/customers/caf9****-2cc6-****-b04b-794c****5ea3/scan-profiles/{47db****-1004-****-b2ce-8f5e****842d}/daily/summary
```
 
## Response Sample
If the request has been successfully processed, a 200 OK response will be returned along with the requested information displayed in the response body.
For more details on the HTTP status code, refer to [Http Status Code](../../Use-AvePoint-Graph-API.md#http-status-code).
```json
{
    "profileName": "Default Microsoft 365 Scan Profile", // The name of the scan profile. 
    "profileId": "47db****-1004-****-b2ce-8f5e****842d", // The ID of the scan profile. 
    "tenantDomain": "Domain", // The tenant domain of the scan profile. 
    "tenantId": "c235****-c7a2-****-b7d4-79e8****66c3", // The tenant ID of the scan profile. 
    "description": "This is a partner-configured scan profile.", // The description of the scan profile. 
    "scanMode": 0, // The scan mode of the profile: 0 represents the Express mode. 
    "modifiedTime": "2025-09-11T03:19:14Z", // The last modified time of the scan profile. 
    "lastUpdateTime": "2025-09-11T03:19:14Z", // The last updated time of the scan profile. 
    "lastScanStatus": 2, // The last scan job status of the scan profile: 2 represents finished. 
    "newRegisteredContentCount": 0, // The number of newly registered objects in the daily report of the scan profile. 
    "movedToAnotherContainer": 0, // The number of objects moved to another container in the daily report of the scan profile. 
    "removedFromMicrosoft365OrOutofPolicy": 0 // The number of objects removed from Microsoft 365 or out of policy in the daily report of the scan profile. 
}
```