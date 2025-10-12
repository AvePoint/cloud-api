# Retrieve All Scan Profiles for a Customer

Use this API to retrieve all scan profiles configured for a specific customer in AvePoint Online Services.

 ## Permissions

The following permission is required to call the API.  
You must register an app through Elements > API app registration to authenticate and authorize your access to Elements API. For details, refer to [App Registration](../../../elements/register-app.md).

| API | Permission  |
|-----------|--------|
| `/partner/external/v3/general/customers/{customerId}/scan-profiles/batch`|elements.scanprofiles.read.all|  

## Request

This section outlines the details of the HTTP method and endpoint used to retrieve all scan profiles configured for a specific customer in AvePoint Online Services.

| Method | Endpoint | Description |
|-----------|--------|------------|
| POST | `/partner/external/v3/general/customers/{customerId}/scan-profiles/batch` | Retrieve all scan profiles configured for a specific customer in AvePoint Online Services|

## Query Parameters

This section outlines the parameters optional required to specify paging information about the profile you want to retrieve.

| Parameter | Description | Type | Required |
| --- | --- | --- | --- |
| pageIndex | The page number of the data which will be retrieve, the default value is 1. | integer | No |
| pageSize | The number of customers API will retrieved in a time, the default value is 100. | integer | No |

## Request Body Parameters

This section outlines the request body required to specify which scan profiles you want to retrieve.

| Parameter | Description | Type | Required |
| --- | --- | --- | --- |
| scanProfileIds | The IDs of the scan profiles to be retrieved | string[] | No |

## Response

If the request has been successfully processed, a 200 OK response will be returned along with the requested information displayed in the response body.
 
| Field | Description | Type |
| --- | --- | --- |
| profileName               | The name of the scan profile.                 | string |
| profileId     | The ID of the scan profile.       | string |
| scanMode       | The scan mode of the scan profile. <ul><li>**0** - Express mode</li><li>**1** - Advanced mode</li></ul>     | integer |
| modifiedTime | The last modified time of the scan profile. | string |

## Request Sample
To use this API, send a GET request to the specified endpoint, including necessary parameters as defined in the references.
```json
https://graph.avepointonlineservices.com/partner/external/v3/general/customers/caf9****-2cc6-****-b04b-794c****5ea3/scan-profiles/batch
```
 
## Response Sample
If the request has been successfully processed, a 200 OK response will be returned along with the requested information displayed in the response body.
For more details on the HTTP status code, refer to [Http Status Code](../../Use-AvePoint-Graph-API.md#http-status-code).
```json

{
    "data": [
        {
            "profileName": "Default Microsoft 365 Scan Profile", // The name of the scan profile
            "profileId": "47db****-1004-****-b2ce-8f5e****842d", // The ID of the scan profile
            "scanMode": 0, // The scan mode of the scan profile: 0 represents Express mode
            "modifiedTime": "2025-09-11T03:19:14Z" // The last modified time of the scan profile
        }
    ],
    "metadata": {
        "pageIndex": 1, // The current display page
        "pageSize": 50, // The number of objects on the display page
        "totalCount": 1 // The total number of objects matching the query parameters
    }
}
```