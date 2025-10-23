# Retrieve Risky Action Count

Use this API to retrieve the risky action count in a customer's tenant.

## Permission

The following permission is required to call the API.  
You must register an app through Elements > API app registration to authenticate and authorize your access to Elements API. For details, refer to [App Registration](../../register-app.md).

| API | Permission  |
|-----------|--------|
| `/partner/external/v3/um/customers/{customerId}/tenants/{tenantId}/overview/security/compliances/actions`|elements.um.user.read.all|  

## Request

This section outlines the details of the HTTP method and endpoint used to retrieve the risky action count in 
a customer's tenant.

| Method | Endpoint | Description |
|-----------|--------|------------|
| GET | `/partner/external/v3/um/customers/{customerId}/tenants/{tenantId}/overview/security/compliances/actions` | 	Retrieves the risky action count in a customer's tenant.

## URL Parameters

This section describes the query parameters that can be added to the URL when sending a GET request, allowing you to retrieve the risky action count in a customer's tenant according to your specific requirements and preferences.

| Parameter | Description | Type | Required |
| --- | --- | --- |---|
| customerId | The ID of the customer. | string | Yes |
| tenantId | The ID of the tenant. | string | Yes |

## Query Parameters

This section outlines the optional parameters used to specify the information for the type you want to retrieve.

| Parameter | Description | Type | Required |
| --- | --- | --- | --- |
| types | The types of actions that you want to retrieve. <ul><li>**0** - Normal action</li><li>**1** - Risky action</li></ul> | integer| No |


## Response

If the request has been successfully processed, a 200 OK response will be returned along with the requested information displayed in the response body.
 
| Response | Description | Type |
| --- | --- | --- |
| riskyActionCount |  The count of the risky actions in the tenant. | integer |
| normalActionCount |  The count of normal actions in the tenant. | integer |


## Request Sample

To use this API, send a GET request to the specified endpoint, including necessary parameters as defined in the references. 

```json
https://graph.avepointonlineservices.com/partner/external/v3/um/customers/966f35cc-****-87b1-****-25cdbcf82a07/tenants/0c7715b3-****-88b2-****-f3634dcfacec/overview/security/compliances/actions
```

## Response Sample

If the request has been successfully processed, a 200 OK response will be returned along with the requested information displayed in the response body. For more details on the HTTP status code, refer to [Http Status Code](../../Use-AvePoint-Graph-API.md#http-status-code).

```json
{
    "riskyActionCount": 10, // The count of the risky actions in the tenant
    "normalActionCount": 20 // The count of normal actions in the tenant
}
```