# Retrieve Workflow Information

Use this API to retrieve inforamtion of workflows in a customer's tenant.

## Permission

The following permission is required to call the API.  
You must register an app through Elements > API app registration to authenticate and authorize your access to AvePoint Graph API. For details, refer to [App Registration](https://cdn.avepoint.com/assets/apelements-webhelp/avepoint-elements-for-partners/index.htm#!Documents/appregistration.htm).

| API | Permission  |
|-----------|--------|
| `/partner/external/v3/um/customers/{customerId}/tenants/{tenantId}/overview/security/compliances/workflows`|elements.um.user.read.all|  

## Request

This section outlines the details of the HTTP method and endpoint used to retrieve information of workflows in a customer's tenant.

| Method | Endpoint | Description |
|-----------|--------|------------|
| GET | `/partner/external/v3/um/customers/{customerId}/tenants/{tenantId}/overview/security/compliances/workflows` | 	Retrieves information of workflows in a customer's tenant.

## URL Parameters

This section describes the query parameters that can be added to the URL when sending a GET request, allowing you to retrieve information of workflows in a customer's tenant according to your specific requirements and preferences.

| Parameter | Description | Type | Required |
| --- | --- | --- |---|
| customerId | The ID of the customer. | string | Yes |
| tenantId | The ID of the tenant. | string | Yes |

## Query Parameters

This section outlines the optional parameters used to specify the information for the type you want to retrieve.

| Parameter | Description | Type | Required |
| --- | --- | --- | --- |
| catagory | The category of the risky actions. <ul><li>**1** - Network security</li><li>**2** - Endpoint security</li><li>**3** - Identity access</li><li>**4** - Configuration security</li></ul> | integer | No |
| pageIndex | The page number of the data which will be retrieve, the default value is 1. | integer | No |
| pageSize | The number of users API will retrieved in a time, the default value is 100. | integer | No |

## Response

If the request has been successfully processed, a 200 OK response will be returned along with the requested information displayed in the response body.
 
| Response | Description | Type |
| --- | --- | --- |
| workflowId |  The ID of the workflow. | string |
| workflowDisplayName |  The display name of the workflow. | string |

## Request Sample

To use this API, send a GET request to the specified endpoint, including necessary parameters as defined in the references. 

```json
https://aostestpartnergcc.sharepointguild.com:5000/external/v3/um/customers/966f35cc-****-****-****-25cdbcf82a07/tenants/0c7715b3-****-****-****-f3634dcfacec/overview/security/compliances/workflows
```

## Response Sample

If the request has been successfully processed, a 200 OK response will be returned along with the requested information displayed in the response body.
For more details on the HTTP status code, refer to [Http Status Code](https://learn.avepoint.com/docs/Use-AvePoint-Graph-API.html#http-status-code).

```json
{
    "data": [
        {
            "workflowId": "8fc933ed-5d54-41fe-909c-afbf326f27ff", // The ID of the workflow
            "workflowDisplayName": "User MFA disabled" // The display name of the workflow
        }
    ],
    "metadata": {
        "pageIndex": 1, // The page index of current request
        "pageSize": 50, // The number will be retrieved in one request
        "totalCount": 1 // The total number count that matches the request
    }
}
```