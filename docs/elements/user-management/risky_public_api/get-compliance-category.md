# Retrieve Compliance Information

Use this API to retrieve compliance information of a specific workflow in a customer's tenant. 

## Permission

The following permission is required to call the API.  
You must register an app through Elements > API app registration to authenticate and authorize your access to AvePoint Graph API. For details, refer to [App Registration](https://cdn.avepoint.com/assets/apelements-webhelp/avepoint-elements-for-partners/index.htm#!Documents/appregistration.htm).

| API | Permission  |
|-----------|--------|
| `/partner/external/v3/um/customers/{customerId}/tenants/{tenantId}/overview/security/compliances/workflows/{workflowId}`|elements.um.user.read.all|  

## Request

This section outlines the details of the HTTP method and endpoint used to retrieve compliance information of a specific workflow in a customer's tennant.

| Method | Endpoint | Description |
|-----------|--------|------------|
| GET | `/partner/external/v3/um/customers/{customerId}/tenants/{tenantId}/overview/security/compliances/workflows/{workflowId}` | 	Retrieves compliances information of a specific workflow in a customer's tenant.

## URL Parameters

This section describes the query parameters that can be added to the URL when sending a GET request, allowing you to retrieve compliance information of a customer's tenant according to your specific requirements and preferences.

| Parameter | Description | Type | Required |
| --- | --- | --- |---|
| customerId | The ID of the customer. | string | Yes |
| tenantId | The ID of the tenant. | string | Yes |
| workflowId | The ID of the workflow. | string | Yes |
## Query Parameters

This section outlines the parameters optional required to specify paging information about the users you want to retrieve.

| Parameter | Description | Type | Required |
| --- | --- | --- | --- |
| pageIndex | The page number of the data which will be retrieve, the default value is 1. | integer | No |
| pageSize | The number of users API will retrieved in a time, the default value is 100. | integer | No |

## Response

If the request has been successfully processed, a 200 OK response will be returned along with the requested information displayed in the response body.
 
| Response | Description | Type |
| --- | --- | --- |
| riskUserCount |  The number of users who trigger the risk based on the workflow. | integer |
| last7DayFixCount |  The number of fixed risky actions in last 7 days. | integer |
| userDisplayName |  The display name of the risky user. | string |
| userPrincipalName |  The user principal name of the risky user. | string |
| userId |  The unique identifier of the risky user. | string |
| loginIP |  The IP address in which a user signs in to Microsoft 365. | string |
| loginTime |  The sign-in time when user signs in to Microsoft 365. | string |
| deviceName |  The name of the device that user uses to sign in to Microsoft 365. | string |  
| accessedFileName |  The name of the file that has been accessed. | string |
| sensitiveInformation |  The sensitive information of the file. | string |
| accessTime |  The time when the user accesses the file. | string |
## Request Sample

To use this API, send a GET request to the specified endpoint, including necessary parameters as defined in the references. 

```json
https://graph.avepointonlineservices.com/partner/external/v3/um/customers/966f35cc-61f4-4070-819c-25cdbcf82a07/tenants/0c7715b3-****-****-****-f3634dcfacec/overview/security/compliances/workflows/4dbd4e4e-****-****-****-2e224d38b0c4
```

## Response Sample
If the request has been successfully processed, a 200 OK response will be returned along with the requested information displayed in the response body.
For more details on the HTTP status code, refer to [Http Status Code](https://learn.avepoint.com/docs/Use-AvePoint-Graph-API.html#http-status-code).

### Response Sample Multiple IP Login & Multiple Login Failed & External IP Login & Guest User Login

```json
{
  "last7DayFixCount": 8, // The number of fixed risky actions in last 7 days
  "riskUserCount": 12, // The number of users who trigger the risk based on the workflow
  "riskUsers": {
    "items": [
      {
        "userDisplayName": "Mark Kevin", // The display name of the risky user
        "userPrincipalName": "mark@element.onmicrosoft.com", // The user principal name of the risky user
        "userId": "c2aa00d3-ef87-40aa-a80a-9e9c79232bfe", // The unique identifier of the risky user
        "loginIps": [
          {
            "loginIP": "23.98.122.140", // The IP address in which a user signs in to Microsoft 365
            "loginTime": "1970-01-01T00:00:00Z" // The sign-in time when user signs in to Microsoft 365
          }
        ],
        "files": [
          {
            "accessedFileName": "report.docx", // The name of the file that has been accessed
            "accessTime": "1970-01-01T00:00:00Z", // The time when the user accesses the file
            "sensitiveInformation": "Personal Data" // The sensitive information of the file
          }
        ],
        "devices": [
          {
            "deviceName": "DESKTOP-ABC123" // The name of the device that user uses to sign into Microsoft 365
          }
        ]
      }
    ],
    "totalCount": 1, // The page index of current request
    "pageSize": 50, // The user number will be retrieved in one request
    "pageIndex": 1 // The total number count that matches the request
  }
}
```