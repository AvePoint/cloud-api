# Update Manager of a Specific User

Use this API to update the manager of a specific user in a customer's tenant. 

## Permission

The following permission is required to call the API.  
You must register an app through Elements > API app registration to authenticate and authorize your access to Elements API. For details, refer to [App Registration](../../register-app.md).

| API | Permission  |
|-----------|--------|
| `/partner/external/v3/um/customers/{customerId}/tenants/{tenantId}/users/{userId}/manager`|elements.um.user.readwrite.all|  

## Request

This section outlines the details of the HTTP method and endpoint used to update the manager of a specific user in a customer's tenant.

| Method | Endpoint | Description |
|-----------|--------|------------|
| PUT | `/partner/external/v3/um/customers/{customerId}/tenants/{tenantId}/users/{userId}/manager` | Updates the manager of a specific user in a customer's tenant.|

## URL Parameters

This section describes the query parameters that can be added to the URL when sending a PUT request, allowing you to update the manager of a user according to your specific requirements and preferences.

| Parameter | Description | Type | Required |
| --- | --- | --- |---|
| customerId | The ID of the customer. | string | Yes |
| tenantId | The ID of the tenant. | string | Yes |
| userId | The unique identifier of the user. | string | Yes |

## Request Body

This section outlines the required fields to update the manager of a specific user in a customer's tenant.

| Parameter | Description | Type | Required |
| --- | --- | --- | --- |
| userPrincipalName | The user principal name of the manager. The maximum length is 1024 characters. For user types other than cloud users, the userPrincipalName property contains the distinguished name (DN) of the manager. Example: "userPrincipalName": "CN=Terry Gu,DC=dev1,DC=com".| string | Yes |

## Response

If the request has been successfully processed, a 204 No Content response will be returned. For more details on the HTTP status code, refer to [Http Status Code](../../Use-AvePoint-Graph-API.md#http-status-code).

## Request Sample

To use this API, send a PUT request to the specified endpoint, including necessary parameters as defined in the references. 

```json
https://graph.avepointonlineservices.com/partner/external/v3/um/customers/966f35cc-****-4070-****-25cd****2a07/tenants/0c7715b3-****-4c4c-****-f363****acec/users/7c18fd6f-****-4353-****-5725****dc3f/manager
```
## Request Body Sample

```json
{
  "userPrincipalName": "tony@domain.com" // The user principal name of the manager
}
```