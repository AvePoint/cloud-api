# Retrieve Compliances Detail Information

Use this API to retrieve compliances detail information of a customer tenant in AvePoint Online Services. 

## Permissions

The following permission is required to call the API.  
You must register an app through Elements > API app registration to authenticate and authorize your access to AvePoint Graph API. For details, refer to [App Registration](https://cdn.avepoint.com/assets/apelements-webhelp/avepoint-elements-for-partners/index.htm#!Documents/appregistration.htm).

| API | Permission  |
|-----------|--------|
| `/external/v3/um/customers/{customerId}/tenants/{tenantId}/overview/security/compliances/workflows/{workflowId}/batch`|partner.um.user.read.all|  

## Request

This section outlines the details of the HTTP method and endpoint used to retrieve compliances category information of a customer tennants.

| Method | Endpoint | Description |
|-----------|--------|------------|
| GET | `/external/v3/um/customers/{customerId}/tenants/{tenantId}/overview/security/compliances/workflows/{workflowId}/batch` | 	Retrieve compliances category information of a customer tennant in AvePoint Online Services.

## URL Parameters

This section describes the query parameters that can be added to the URL when sending a GET request, allowing you to retrieve compliances category information according to your specific requirements and preferences.

| Parameter | Description | Type | Required |
| --- | --- | --- |---|
| customerId | The customer ID of the customer. | string | Yes |
| tenantId | The specific tenant ID of the customer. | string | Yes |
| workflowId | The ID of the workflow. | string | Yes |
## Query Parameters

This section outlines the parameters optional required to specify paging information about the users you want to retrieve.

| Parameter | Description | Type | Required |
| --- | --- | --- | --- |
| pageIndex | The page number of the data which will be retrieve, the default value is 1. | integer | False |
| pageSize | The number of users API will retrieved in a time, the default value is 100. | integer | False |

## Response

If the request has been successfully processed, a 200 OK response will be returned along with the requested user information displayed in the response body.
 
| Response | Description | Type |
| --- | --- | --- |
| riskUserCount |  The number of user trigger the risk based on the flow. | integer |
| last7DayFixCount |  The number of fixed risky action in the last 7 Days. | integer |
| userDisplayName |  The DisplayName of the risk user. | string |
| userPrincipalName |  The PrincipalName of the risk user. | string |
| userId |  The unique Id of the risk user. | string |
| loginIP |  The ip address when user login 365 trigger the risky flow. | string |
| loginTime |  The login time when user login 365 trigger the risky flow. | long |
| deviceName |  The name of device . | string |  
| accessedFileName |  The name of file accessed. | string |
| sensitiveInformation |  The sensitive information of the file. | string |
| accessTime |  The time when the user access the file. | long |
## Request Sample

To use this API, send a GET request to the specified endpoint, including necessary parameters as defined in the references. 

```json
https://graph.avepointonlineservices.com/partner/external/v3/um/customers/966f35cc-61f4-4070-819c-25cdbcf82a07/tenants/0c7715b3-bc2f-4c4c-a8a0-f3634dcfacec/overview/security/compliances/workflows/4dbd4e4e-f657-44bc-a47d-2e224d38b0c4/batch
```

## Response Sample
If the request has been successfully processed, a 200 OK response will be returned along with the requested information displayed in the response body.
For more details on the HTTP status code, refer to [Http Status Code](https://learn.avepoint.com/docs/Use-AvePoint-Graph-API.html#http-status-code).

### Response Sample Multiple IP Login & Multiple Login Failed & External IP Login & Guest User Login

```json
{
  "last7DayFixCount": 8,
  "riskUserCount": 12,
  "riskUsers": {
    "items": [
      {
        "userDisplayName": "Mark Kevin",
        "userPrincipalName": "mark@element.onmicrosoft.com",
        "userId": "c2aa00d3-ef87-40aa-a80a-9e9c79232bfe",
        "loginIps": [
          {
            "loginIP": "23.98.122.140",
            "loginTime": 638925708260000000
          }
        ],
        "files": [
          {
            "accessedFileName": "report.docx",
            "accessTime": "638925708260000000",
            "sensitiveInformation": "Personal Data"
          }
        ],
        "devices": [
          {
            "deviceName": "DESKTOP-ABC123"
          }
        ]
      }
    ],
    "totalCount": 1,
    "pageSize": 50,
    "pageIndex": 1
  }
}
```