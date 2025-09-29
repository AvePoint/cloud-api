# Retrieve Risk Analyze Workflow Detail

Use this API to retrieve risk analyze workflow detail of a customer tenant in AvePoint Online Services.

## Permissions

The following permission is required to call the API.  
You must register an app through Elements > API app registration to authenticate and authorize your access to AvePoint Graph API. For details, refer to [App Registration](https://cdn.avepoint.com/assets/apelements-webhelp/avepoint-elements-for-partners/index.htm#!Documents/appregistration.htm).

| API | Permission  |
|-----------|--------|
| `/external/v3/um/customers/{customerId}/tenants/{tenantId}/overview/security/compliances/workflows`|elements.um.user.read.all|  

## Request

This section outlines the details of the HTTP method and endpoint used to retrieve risk analyze workflow detail
of a customer.

| Method | Endpoint | Description |
|-----------|--------|------------|
| GET | `/external/v3/um/customers/{customerId}/tenants/{tenantId}/overview/security/compliances/workflows` | 	Retrieves risk analyze workflow detail of a customer tenant in AvePoint Online Services.

## URL Parameters

This section describes the query parameters that can be added to the URL when sending a GET request, allowing you to retrieve risk analyze workflow detail according to your specific requirements and preferences.

| Parameter | Description | Type | Required |
| --- | --- | --- |---|
| customerId | The customer ID of the customer. | string | Yes |
| tenantId | The specific tenant ID of the customer. | string | Yes |

## Query Parameters

This section outlines the optional parameters used to specify the information for the type you want to retrieve.

| Parameter | Description | Type | Required |
| --- | --- | --- | --- |
| catagory | The array value includes the category you want to retrieve. <ul><li>**1** - Network security</li><li>**2** - Endpoint security</li><li>**3** - Identity access</li><li>**4** - Configuration security</li></ul> | integer | No |
| pageIndex | The page number of the data which will be retrieve, the default value is 1. | integer | No |
| pageSize | The number of users API will retrieved in a time, the default value is 100. | integer | No |

## Response

If the request has been successfully processed, a 200 OK response will be returned along with the requested information displayed in the response body.
 
| Response | Description | Type |
| --- | --- | --- |
| id |  The ID of risk security | string |
| WorkflowId |  The workflow ID of the customer. | string |
| WorkflowDisplayName |  The workflow display name of the customer. | string |

## Request Sample

To use this API, send a GET request to the specified endpoint, including necessary parameters as defined in the references. 

```json
https://aostestpartnergcc.sharepointguild.com:5000/external/v3/um/customers/966f35cc-61f4-4070-819c-25cdbcf82a07/tenants/0c7715b3-bc2f-4c4c-a8a0-f3634dcfacec/overview/security/compliances/workflows
```

## Response Sample

If the request has been successfully processed, a 200 OK response will be returned along with the requested information displayed in the response body.
For more details on the HTTP status code, refer to [Http Status Code](https://learn.avepoint.com/docs/Use-AvePoint-Graph-API.html#http-status-code).

```json
{
    "data": [
        {
            "id": "83545853-9408-4d0b-902e-79b0beb5dac5",
            "workflowId": "8fc933ed-5d54-41fe-909c-afbf326f27ff",
            "workflowDisplayName": "User MFA disabled"
        }
    ],
    "metadata": {
        "pageIndex": 1,
        "pageSize": 50,
        "totalCount": 1
    }
}
```