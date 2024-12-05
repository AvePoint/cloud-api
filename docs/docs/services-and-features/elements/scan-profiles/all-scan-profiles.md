# Retrieve All Scan Profiles

Use this API to retrieve all the scan profiles configured for a specific customer in AvePoint Online Services.  

## Permissions  

The following permission is required to call the API.  
You must register an app through Elements for Partners > App registration to authenticate and authorize your access to AvePoint Graph Modern API. For details, refer to [App Registration](https://cdn.avepoint.com/assets/apelements-webhelp/avepoint-elements-for-partners/index.htm#!Documents/appregistration.htm).

| API | Permission |
|-----------|-----------|
| `/partner/customers/{id}/scanProfiles` | partner.scanprofiles.read.all |  


## Request

This section outlines the HTTP method and endpoint used to retrieve your customer's information for all scan profiles configured in AvePoint Online Services.

| Method | Endpoint | Description |
|-----------|-----------|-----------|
|GET|`/partner/customers/{id}/scanProfiles`|Retrieves all the scan profiles configured for a specific customer in AvePoint Online Services.|

## Query Parameters

This section outlines the parameters required to specify which customer's scan profile information you want to retrieve.

| Parameter | Description | Type | Required |
| --- | --- | --- | --- |
| Id | The tenant owner ID of the customer. | String | Yes |

## Response

If the request has been successfully processed, a 200 OK response will be returned along with the requested information displayed in the response body.

| Response | Description | Type |
| --- | --- | --- |
| profileName | The name of the scan profile. | String |
| profileId | The ID of the scan profile. | String |
| scanMode | The scan mode of the scan profile:<br> <ul><li> **0** represents **Express mode**</li><li> **1** represents **Advanced mode** | Int |
| modifiedTime | The last modified time of the scan profile. | String |

## Request Sample

To use this API, send a GET request to the specified endpoint, including necessary parameters as defined in the references.

```json
https://graph.avepointonlineservices.com/partner/customers/caf94a89-2cc6-47aa-b04b-794cb9af5ea3/ScanProfiles
```

## Response Sample

If the request has been successfully processed, a 200 OK response will be returned along with the requested information displayed in the response body. For more details on the HTTP status code, refer to [HttpStatusCode](https://learn.avepoint.com/docs/Use-AvePoint-Graph-Modern-API.html#http-status-code).

```json 
{
    "@odata.context": "https://graph.avepointonlineservices.com/partner/$metadata#Collection(Portal.Api.Model.ProfileInfo)",
    "value": [
        {
            "profileName": "test oop", // The name of the scan profile
            "profileId": "0e5e152d-65cc-4206-9829-636ee72c88c3", // The ID of the scan profile
            "scanMode": 0, // The scan mode of the scan profile: 0 represents Express mode
            "modifiedTime": "08/01/2024 06:29:55" // The last modified time of the scan profile
        }
    ]
}
```