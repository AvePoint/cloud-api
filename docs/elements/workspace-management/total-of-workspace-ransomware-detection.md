# Retrieve Data Protection Statistics

Use this API to retrieve the data protection statistics of a specific tenant in Elements.  

## Permissions  

The following permission is required to call the API.  
You must register an app through Elements > API app registration to authenticate and authorize your access to AvePoint Graph API. For details, refer to [App Registration](https://cdn.avepoint.com/assets/apelements-webhelp/avepoint-elements-for-partners/index.htm#!Documents/appregistration.htm).

| API | Permission |
|-----------|-----------|
| `/partner/external/wm/customers/{customerId}/tenants/{tenantId}/overview/data-protection/ransomware-detetion` | partner.wm.read.all |  


## Request

This section outlines the HTTP method and endpoint used to retrieve the data protection statistics of a specific tenant in Elments.

| Method | Endpoint | Description |
|-----------|-----------|-----------|
|GET|`/partner/external/wm/customers/{customerId}/tenants/{tenantId}/overview/data-protection/ransomware-detetion`|Retrieves the data protection statistics.|

## Query Parameters

This section outlines the parameters required to specify which tenant's data protection statistics you want to retrieve.

| Parameter | Description | Type | Required |
| --- | --- | --- | --- |
| customerId | The customer ID | string | Yes |
| tenantId | The tenant ID of the customer | string | Yes |


## Response

If the request has been successfully processed, a 200 OK response will be returned along with the requested information displayed in the response body.

| Response | Description | Type |
| --- | --- | --- |
| TeamsUnderPotentialRansomwareAttack | The number of Teams under potential ransomware attack over the last 7 days. | integer |
| TeamsWithUnusualActivities | The number of Teams with unusual activities over the last 7 days. | integer |
| SharePointSitesUnderPotentialRansomwareAttack | The number of SharePoint sites under potential ransomware attack over the last 7 days.  | integer |
| SharePointSitesWithUnusualActivities | The number of SharePoint sites with unusual activities over the last 7 days. | integer |
| OneDrivesUnderPotentialRansomwareAttack | The number of OneDrives under potential ransomware attack over the last 7 days. | integer |
| OneDrivesWithUnusualActivities | The number of OneDrives with unusual activities over the last 7 days. | integer |
| GroupsUnderPotentialRansomwareAttack | The number of Groups under potential ransomware attack over the last 7 days. | integer |
| GroupsWithUnusualActivities | The number of Groups with unusual activities over the last 7 days. | integer |
| TeamsWithSuspiciousObjects | The number of Teams with suspicious objects over the last 7 days. | integer |
| SharePointSitesWithSuspiciousObjects | The number of SharePoint sites with suspicious objects over the last 7 days. | integer |
| OneDrivesWithSuspiciousObjects | The number of OneDrives with suspicious objects over the last 7 days. | integer |
| GroupsWithSuspiciousObjects | The number of Groups with suspicious objects over the last 7 days. | integer |


## Request Sample

To use this API, send a GET request to the specified endpoint, including necessary parameters as defined in the references.

```json
https://graph.avepointonlineservices.com/partner/customers/966f35cc-****-4070-****-25cd****2a07/tenants/0c7715b3-****-4c4c-****-f363****acec/overview/data-protection/ransomware-detetion
```

## Response Sample

If the request has been successfully processed, a 200 OK response will be returned along with the requested information displayed in the response body. For more details on the HTTP status code, refer to [Http Status Code](https://learn.avepoint.com/docs/Use-AvePoint-Graph-API.html#http-status-code).

```json 
{
    "teamsUnderPotentialRansomwareAttack": 10,
    "sharePointSitesUnderPotentialRansomwareAttack": 0,
    "oneDrivesUnderPotentialRansomwareAttack": 0,
    "groupsUnderPotentialRansomwareAttack": 16,
    "geamsWithUnusualActivities": 0,
    "sharePointSitesWithUnusualActivities": 1,
    "oneDrivesWithUnusualActivities": 22,
    "groupsWithUnusualActivities": 0,
    "teamsWithSuspiciousObjects": 12,
    "sharePointSitesWithSuspiciousObjects": 0,
    "oneDrivesWithSuspiciousObjects": 0,
    "groupsWithSuspiciousObjects": 1
}