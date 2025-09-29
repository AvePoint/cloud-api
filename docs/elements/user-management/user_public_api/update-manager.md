# Update Manager of a Specific User

Use this API to update the manager of a specific user in a customer's tenant. 

## Permission

The following permission is required to call the API.  
You must register an app through Elements > API app registration to authenticate and authorize your access to AvePoint Graph API. For details, refer to [App Registration](https://cdn.avepoint.com/assets/apelements-webhelp/avepoint-elements-for-partners/index.htm#!Documents/appregistration.htm).

| API | Permission  |
|-----------|--------|
| `/external/v3/um/customers/{customerId}/tenants/{tenantId}/users/{userId}/manager`|elements.um.user.readwrite.all|  

## Request

This section outlines the details of the HTTP method and endpoint used to update the manager of a specific user in a customer's tenant.

| Method | Endpoint | Description |
|-----------|--------|------------|
| PUT | `/external/v3/um/customers/{customerId}/tenants/{tenantId}/users/{userId}/manager` | Updates the manager of a specific user in a customer's tenant.|

## URL Parameters

This section describes the query parameters that can be added to the URL when sending a PUT request, allowing you to update the manager of a user according to your specific requirements and preferences.

| Parameter | Description | Type | Required |
| --- | --- | --- |---|
| customerId | The ID of the customer. | string | Yes |
| tenantId | The ID of the tenant. | string | Yes |
| userId | The unique identifier of the specific user whose details are being requested. | string | Yes |

## Request Body

This section outlines the required fields to update the manager of a specific user in a customer's tenant.

| Parameter | Description | Type | Required |
| --- | --- | --- | --- |
| id | The ID of the manager. The maximum length is 40 characters.| string | Yes |
| userPrincipalName | The user principal name of the manager. The maximum length is 1024 characters.| string | Yes |

## Response

If the request has been successfully processed, a 204 No Content response will be returned

## Request Sample

To use this API, send a PUT request to the specified endpoint, including necessary parameters as defined in the references. 

```json
https://graph.avepointonlineservices.com/partner/external/v3/um/customers/966f35cc-61f4-4070-819c-25cdbcf82a07/tenants/0c7715b3-bc2f-4c4c-a8a0-f3634dcfacec/users/7c18fd6f-fb26-4353-8dbd-5725fa9edc3f/manager
```
## Request Body Sample

```json
{
  "id": "631b0def-****-****-****-5811518ebbea", // The ID of the manager
  "userPrincipalName": "tony@element.onmicrosoft.com" // The user principal name of the manager
}
```