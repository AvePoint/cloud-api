# Retrieve Data Protection Statistics of Tenant

Use this API to retrieve the data protection statistics of a specific tenant in Elements.  

## Permission  

The following permission is required to call the API.  
You must register an app through Elements > API app registration to authenticate and authorize your access to AvePoint Graph API. For details, refer to [App Registration](../register-app.md).

| API | Permission |
|-----------|-----------|
| `/partner/external/wm/customers/{customerId}/tenants/{tenantId}/overview/data-protection/ransomware-detetion` | elements.wm.read.all |  


## Request

This section outlines the HTTP method and endpoint used to retrieve the data protection statistics of a specific tenant in Elments.

| Method | Endpoint | Description |
|-----------|-----------|-----------|
|GET|`/partner/external/wm/customers/{customerId}/tenants/{tenantId}/overview/data-protection/ransomware-detetion`|Retrieves the data protection statistics.|

## URL Parameters

This section outlines the parameters required to specify which tenant's data protection statistics you want to retrieve.

| Parameter | Description | Type | Required |
| --- | --- | --- | --- |
| customerId | The customer ID | string | Yes |
| tenantId | The tenant ID of the customer | string | Yes |


## Response

If the request has been successfully processed, a 200 OK response will be returned along with the requested information displayed in the response body.

| Response | Description | Type |
| --- | --- | --- |
| teamsUnderPotentialRansomwareAttack | The number of Teams under potential ransomware attack over the last 7 days. | integer |
| teamsWithUnusualActivities | The number of Teams with unusual activities over the last 7 days. | integer |
| sharePointSitesUnderPotentialRansomwareAttack | The number of SharePoint sites under potential ransomware attack over the last 7 days.  | integer |
| sharePointSitesWithUnusualActivities | The number of SharePoint sites with unusual activities over the last 7 days. | integer |
| oneDrivesUnderPotentialRansomwareAttack | The number of OneDrives under potential ransomware attack over the last 7 days. | integer |
| oneDrivesWithUnusualActivities | The number of OneDrives with unusual activities over the last 7 days. | integer |
| groupsUnderPotentialRansomwareAttack | The number of Groups under potential ransomware attack over the last 7 days. | integer |
| groupsWithUnusualActivities | The number of Groups with unusual activities over the last 7 days. | integer |
| teamsWithSuspiciousObjects | The number of Teams with suspicious objects over the last 7 days. | integer |
| sharePointSitesWithSuspiciousObjects | The number of SharePoint sites with suspicious objects over the last 7 days. | integer |
| oneDrivesWithSuspiciousObjects | The number of OneDrives with suspicious objects over the last 7 days. | integer |
| groupsWithSuspiciousObjects | The number of Groups with suspicious objects over the last 7 days. | integer |


## Request Sample

To use this API, send a GET request to the specified endpoint, including necessary parameters as defined in the references.

```json
https://graph.avepointonlineservices.com/partner/customers/966f35cc-****-4070-****-25cd****2a07/tenants/0c7715b3-****-4c4c-****-f363****acec/overview/data-protection/ransomware-detetion
```

## Response Sample

If the request has been successfully processed, a 200 OK response will be returned along with the requested information displayed in the response body. For more details on the HTTP status code, refer to [Http Status Code](../Use-AvePoint-Graph-API.md#http-status-code).

```json 
{
    "teamsUnderPotentialRansomwareAttack": 10, // The number of Teams under potential ransomware attack over the last 7 days
    "sharePointSitesUnderPotentialRansomwareAttack": 0, // The number of SharePoint sites under potential ransomware attack over the last 7 days
    "oneDrivesUnderPotentialRansomwareAttack": 0, // The number of OneDrives under potential ransomware attack over the last 7 days
    "groupsUnderPotentialRansomwareAttack": 16, // The number of Groups under potential ransomware attack over the last 7 days
    "teamsWithUnusualActivities": 0, // The number of Teams with unusual activities over the last 7 days
    "sharePointSitesWithUnusualActivities": 1, // The number of SharePoint sites with unusual activities over the last 7 days
    "oneDrivesWithUnusualActivities": 22, // The number of OneDrives with unusual activities over the last 7 days
    "groupsWithUnusualActivities": 0, // The number of Groups with unusual activities over the last 7 days
    "teamsWithSuspiciousObjects": 12, // The number of Teams with suspicious objects over the last 7 days
    "sharePointSitesWithSuspiciousObjects": 0, // The number of SharePoint sites with suspicious objects over the last 7 days
    "oneDrivesWithSuspiciousObjects": 0, // The number of OneDrives with suspicious objects over the last 7 days
    "groupsWithSuspiciousObjects": 1 // The number of Groups with suspicious objects over the last 7 days
}