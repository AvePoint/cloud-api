# Get the daily scan profile change detail in Avepoint Online Services for a customer

Use this API to get the daily scan profile change detail in Avepoint Online Services for a customer. 

 ## Permissions

The following permission is required to call the API.  
You must register an app through Elements > API app registration to authenticate and authorize your access to AvePoint Graph API. For details, refer to [App Registration](https://cdn.avepoint.com/assets/apelements-webhelp/avepoint-elements-for-partners/index.htm#!Documents/appregistration.htm).

| API | Permission  |
|-----------|--------|
| `partner/external/v3/general/customers/{customerId}/scan-profiles-v2/{scanProfileId}/detail`|elements.scanprofiles.read.all|  

## Request

This section outlines the details of the HTTP method and endpoint used to get the daily scan profile change detail in Avepoint Online Services for a customer.

| Method | Endpoint | Description |
|-----------|--------|------------|
| GET | `partner/external/v3/general/customers/{customerId}/scan-profiles-v2/{scanProfileId}/detail` | Get the daily scan profile change detail in Avepoint Online Services for a customer.|

## Response

If the request has been successfully processed, a 200 OK response will be returned along with the requested information displayed in the response body.
 
| Field | Description | Type |
| --- | --- | --- |
| profileName               | The profile name of the profile.                 | string |
| profileId     | The profile id of the profile.       | string |
| tenantId | The tenant id of the profile. | string |
| tenantDomain | The tenant domain of the profile. | string |
| scanMode | The scan mode of the profile. | int |
| lastUpdateTime | The last update time of the profile. | string |
| newRegisteredContent.objectName | The new registered content object name of the profile. | string |
| newRegisteredContent.containerName | The new registered content container name of the profile. | string |
| removedFromMicrosoft365OrOutOfPolicyObjects | The removed from microsoft365 or out of policy objects of the profile. | string array |
| movedToAnotherContainerObjects.objectName | The moved to another container object name of the profile. | string |
| movedToAnotherContainerObjects.containerName | The moved to another container container name of the profile. | string |

## Request Sample
To use this API, send a GET request to the specified endpoint, including necessary parameters as defined in the references.
```json
https://graph.avepointonlineservices.com/partner/external/v3/general/customers/{customerId}/scan-profiles-v2/{scanProfileId}/detail
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
    "lastUpdateTime": "2025-09-11T03:19:14Z",
    "newRegisteredContent": [],
    "removedFromMicrosoft365OrOutOfPolicyObjects": [],
    "movedToAnotherContainerObjects": []
}
```