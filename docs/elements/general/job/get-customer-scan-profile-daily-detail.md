# Retrieve Daily Scan Profile Change Details in AvePoint Online Services for a Customer

Use this API to retrieve the scan profile change details in AvePoint Online Services for a customer. 

 ## Permission

The following permission is required to call the API.  
You must register an app through Elements > API app registration to authenticate and authorize your access to AvePoint Graph API. For details, refer to [App Registration](../../../elements/register-app.md).

| API | Permission  |
|-----------|--------|
| `/partner/external/v3/general/customers/{customerId}/scan-profiles/{scanProfileId}/daily/detail`|elements.scanprofiles.read.all|  

## Request

This section outlines the details of the HTTP method and endpoint used to retrieve the daily scan profile change details in AvePoint Online Services for a customer.

| Method | Endpoint | Description |
|-----------|--------|------------|
| GET | `/partner/external/v3/general/customers/{customerId}/scan-profiles/{scanProfileId}/daily/detail` | Retrieve the daily scan profile change details in AvePoint Online Services for a customer.|

## Response

If the request has been successfully processed, a 200 OK response will be returned along with the requested information displayed in the response body.
 
| Field | Description | Type |
| --- | --- | --- |
| profileName               | The name of the scan profile.                 | string |
| profileId     | The ID of the scan profile.       | string |
| tenantId | The tenant ID of the scan profile. | string |
| tenantDomain | The tenant domain of the scan profile. | string |
| lastUpdateTime | The last updated time of the scan profile. | string |
| newRegisteredContent | The information of the newly registered objects in the daily report of the scan profile. | list |
| removedFromMicrosoft365OrOutOfPolicyObjects | The objects removed from Microsoft 365 or out of policy in the daily report of the scan profile. | string[] |
| movedToAnotherContainerObjects | The information of the objects moved to another container in the daily report of the scan profile. | list |

**New registered content information:**

| Field | Description | Type |
| --- | --- | --- |
| objectName | The newly registered object name in the daily report of the profile. | string |
| containerName | The newly registered container name in the daily report of the scan profile. | string |

**Moved to another container container information:**

| Field | Description | Type |
| --- | --- | --- |
| objectName | The moved to another container object name of the profile. | string |
| containerName | The moved to another container container name of the profile. | string |

## Request Sample
To use this API, send a GET request to the specified endpoint, including necessary parameters as defined in the references.
```json
https://graph.avepointonlineservices.com/partner/external/v3/general/customers/caf9****-2cc6-****-b04b-794c****5ea3/scan-profiles/{47db****-1004-****-b2ce-8f5e****842d}/daily/detail
```
 
## Response Sample
If the request has been successfully processed, a 200 OK response will be returned along with the requested information displayed in the response body.
For more details on the HTTP status code, refer to [Http Status Code](../../Use-AvePoint-Graph-API.md#http-status-code).
```json
{
    "profileName": "Default Microsoft 365 Scan Profile", // The name of the scan profile
    "profileId": "47db****-1004-****-b2ce-8f5e****842d", // The ID of the scan profile
    "tenantDomain": "domain", // The tenant domain of the scan profile
    "tenantId": "c235****-c7a2-****-b7d4-79e8****66c3", // The tenant ID of the scan profile
    "lastUpdateTime": "2025-09-11T03:19:14Z", // The last updated time of the scan profile
    "newRegisteredContent": [], // The information of the newly registered object in the daily report
    "removedFromMicrosoft365OrOutOfPolicyObjects": [], // The objects removed from Microsoft 365 or out of policy in the daily report
    "movedToAnotherContainerObjects": [] // The information of the objects moved to another container in the daily report
}
```