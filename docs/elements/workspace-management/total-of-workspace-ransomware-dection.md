# Retrieve Total of workspaces

Use this API to retrieve records for information about the workspace ransomware-detetion for a specific tenant in AvePoint Online Services.  

## Permissions  

The following permission is required to call the API.  
You must register an app through Elements > API app registration to authenticate and authorize your access to AvePoint Graph API. For details, refer to [App Registration](https://cdn.avepoint.com/assets/apelements-webhelp/avepoint-elements-for-partners/index.htm#!Documents/appregistration.htm).

| API | Permission |
|-----------|-----------|
| `/partner/external/wm/customers/{customerId}/tenants/{tenantId}/overview/data-protection/ransomware-detetion` | partner.wm.read.all |  


## Request

This section outlines the HTTP method and endpoint used to retrieve your customer's information for all scan profiles configured in AvePoint Online Services.

| Method | Endpoint | Description |
|-----------|-----------|-----------|
|GET|`/partner/external/wm/customers/{customerId}/tenants/{tenantId}/overview/data-protection/ransomware-detetion`|Retrieves records for information about the workspace ransomware-detetion that are match for a specific tenant in AvePoint Online Services.|

## Query Parameters

This section outlines the parameters required to specify which tenant's workspace detail records you want to retrieve.

| Parameter | Description | Type | Required |
| --- | --- | --- | --- |
| CustomerId | The customer's ID. | string | Yes |
| TenantId | The customer tenant's ID. | string | Yes |


## Response

If the request has been successfully processed, a 200 OK response will be returned along with the requested information displayed in the response body.

| Response | Description | Type |
| --- | --- | --- |
| TeamsUnderPotentialRansomwareAttack | The number Of TeamsUnderPotentialRansomwareAttack. | integer |
| TeamsWithUnusualActivities | The number Of TeamsWithUnusualActivities. | integer |
| SharePointSitesUnderPotentialRansomwareAttack | The number Of SharePointSitesUnderPotentialRansomwareAttack.  | integer |
| SharePointSitesWithUnusualActivities | The number Of SharePointSitesWithUnusualActivities. | integer |
| OneDrivesUnderPotentialRansomwareAttack | The number Of OneDrivesUnderPotentialRansomwareAttack. | integer |
| OneDrivesWithUnusualActivities | The number Of OneDrivesWithUnusualActivities. | integer |
| GroupsUnderPotentialRansomwareAttack | The number Of GroupsUnderPotentialRansomwareAttack. | integer |
| GroupsWithUnusualActivities | The number Of GroupsWithUnusualActivities. | integer |
| TeamsWithSuspiciousObjects | The number Of TeamsWithSuspiciousObjects. | integer |
| SharePointSitesWithSuspiciousObjects | The number Of SharePointSitesWithSuspiciousObjects. | integer |
| OneDrivesWithSuspiciousObjects | The number Of OneDrivesWithSuspiciousObjects. | integer |
| GroupsWithSuspiciousObjects | The number Of GroupsWithSuspiciousObjects. | integer |


## Request Sample

To use this API, send a GET request to the specified endpoint, including necessary parameters as defined in the references.

```json
https://graph.avepointonlineservices.com/partner/customers/966f35cc-61f4-4070-819c-25cdbcf82a07/tenants/0c7715b3-bc2f-4c4c-a8a0-f3634dcfacec/overview/data-protection/ransomware-detetion
```

## Response Sample

If the request has been successfully processed, a 200 OK response will be returned along with the requested information displayed in the response body. For more details on the HTTP status code, refer to [Http Status Code](https://learn.avepoint.com/docs/Use-AvePoint-Graph-API.html#http-status-code).

```json 
{
    "TeamsUnderPotentialRansomwareAttack": 10,
    "SharePointSitesUnderPotentialRansomwareAttack": 0,
    "OneDrivesUnderPotentialRansomwareAttack": 0,
    "GroupsUnderPotentialRansomwareAttack": 16,
    "TeamsWithUnusualActivities": 0,
    "SharePointSitesWithUnusualActivities": 1,
    "OneDrivesWithUnusualActivities": 22,
    "GroupsWithUnusualActivities": 0,
    "TeamsWithSuspiciousObjects": 12,
    "SharePointSitesWithSuspiciousObjects": 0,
    "OneDrivesWithSuspiciousObjects": 0,
    "GroupsWithSuspiciousObjects": 1
}