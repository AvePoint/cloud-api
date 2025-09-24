# Retrieve Risk Action Count

Use this API to retrieve risk action count of a customer tenant in AvePoint Online Services.

## Permissions

The following permission is required to call the API.  
You must register an app through Elements > API app registration to authenticate and authorize your access to AvePoint Graph API. For details, refer to [App Registration](https://cdn.avepoint.com/assets/apelements-webhelp/avepoint-elements-for-partners/index.htm#!Documents/appregistration.htm).

| API | Permission  |
|-----------|--------|
| `/external/v3/um/customers/{customerId}/tenants/{tenantId}/overview/security/compliances/actions`|elements.um.user.read.all|  

## Request

This section outlines the details of the HTTP method and endpoint used to retrieve risk action
of a customer.

| Method | Endpoint | Description |
|-----------|--------|------------|
| GET | `/external/v3/um/customers/{customerId}/tenants/{tenantId}/overview/security/compliances/actions` | 	Retrieves risk action count of a customer tenant in AvePoint Online Services.

## URL Parameters

This section describes the query parameters that can be added to the URL when sending a GET request, allowing you to retrieve risk action according to your specific requirements and preferences.

| Parameter | Description | Type | Required |
| --- | --- | --- |---|
| customerId | The customer ID of the customer. | string | Yes |
| tenantId | The specific tenant ID of the customer. | string | Yes |

## Query Parameters

This section outlines the optional parameters used to specify the information for the type you want to retrieve.

| Parameter | Description | Type | Required |
| --- | --- | --- | --- |
| types | The array value includes the types you want to retrieve. <ul><li>**0** - Normal action</li><li>**1** - Risk action</li></ul> | integer[]| No |


## Response

If the request has been successfully processed, a 200 OK response will be returned along with the requested information displayed in the response body.
 
| Response | Description | Type |
| --- | --- | --- |
| riskActionCount |  The risk action count of the customer. | interger |
| normalActionCount |  The normal action count of the customer. | interger |


## Request Sample

To use this API, send a GET request to the specified endpoint, including necessary parameters as defined in the references. 

```json
https://graph.avepointonlineservices.com/partner/external/v3/um/customers/966f35cc-61f4-4070-819c-25cdbcf82a07/tenants/0c7715b3-bc2f-4c4c-a8a0-f3634dcfacec/overview/security/compliances/actions
```

## Response Sample

If the request has been successfully processed, a 200 OK response will be returned along with the requested information displayed in the response body.
For more details on the HTTP status code, refer to [Http Status Code](https://learn.avepoint.com/docs/Use-AvePoint-Graph-API.html#http-status-code).

```json
{
    "riskActionCount": 10,
    "normalActionCount": 20
}
```