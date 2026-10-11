# Update External User Property of a User

Use this API to update the external user property of a user in a customer's tenant to indicate whether the user is an external user. 

## Permission

The following permission is required to call the API.  
You must register an app through Elements > API app registration to authenticate and authorize your access to Elements API. For details, refer to [App Registration](../../register-app.md).

| API | Permission  |
|-----------|--------|
| `/partner/external/v3/um/customers/{customerId}/tenants/{tenantId}/users/{userId}/isexternal`|elements.um.user.readwrite.all|  

## Request

This section outlines the details of the HTTP method and endpoint used to update the external user property of
a user in a customer's tenant to indicate whether the user is an external user.

| Method | Endpoint | Description |
|-----------|--------|------------|
| PUT | `/partner/external/v3/um/customers/{customerId}/tenants/{tenantId}/users/{userId}/isexternal` | Updates the external user property of a user in a customer's tenant to indicate whether the user is an external user.|

## URL Parameters

This section describes the query parameters that can be added to the URL when sending a PUT request, allowing you to update the external user property of a user to indicate whether the user is an external user according to your specific requirements and preferences.

| Parameter | Description | Type | Required |
| --- | --- | --- |---|
| customerId | The ID of the customer. | string | Yes |
| tenantId | The ID of the tenant. | string | Yes |
| userId | The unique identifier of the user whose information you want to update. | string | Yes |

## Request Body

This section outlines the required fields to update the external user property of a user in a customer's tenant to indicate whether the user is an external user.

| Parameter | Description | Type | Required
| --- | --- | --- | ---
| isExternal | Indicates whether this user account is an external user. | bool | Yes |

## Response

If the request has been successfully processed, a 204 No Content response will be returned. For more details on the HTTP status code, refer to [Http Status Code](../../Use-AvePoint-Graph-API.md#http-status-code).

## Request Sample

To use this API, send a PUT request to the specified endpoint, including necessary parameters as defined in the references. 

```json
https://graph.avepointonlineservices.com/partner/external/v3/um/customers/966f35cc-****-78d4-****-25cdbcf82a07/tenants/0c7715b3-****-89v1-****-f3634dcfacec/users/7c18fd6f-****-86c9-****-5725fa9edc3f/isexternal
```
## Request Body Sample

```json
{
    "isExternal" : true // Indicates whether this user is an external user.
}
```