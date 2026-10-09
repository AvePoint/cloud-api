# Update Notes of a Hybrid/Local User

Use this API to update the notes of a hybrid/local user in a customer's tenant. 

## Permission

The following permission is required to call the API.  
You must register an app through Elements > API app registration to authenticate and authorize your access to Elements API. For details, refer to [App Registration](../../register-app.md).

| API | Permission  |
|-----------|--------|
| `/partner/external/v3/um/customers/{customerId}/tenants/{tenantId}/local-users/{userId}/notes`|elements.um.user.readwrite.all|  

## Request

This section outlines the details of the HTTP method and endpoint used to update the notes of a hybird/local user in a customer's tenant.

| Method | Endpoint | Description |
|-----------|--------|------------|
| PUT | `/partner/external/v3/um/customers/{customerId}/tenants/{tenantId}/local-users/{userId}/notes` | Updates the notes of a hybrid/local user in a customer's tenant.|

## URL Parameters

This section describes the query parameters that can be added to the URL when sending a PUT request, allowing you to update the notes of a hybrid/local user according to your specific requirements and preferences.

| Parameter | Description | Type | Required |
| --- | --- | --- |---|
| customerId | The ID of the customer. | string | Yes |
| tenantId | The ID of the tenant. | string | Yes |
| userId | The unique identifier of the user whose information you want to update. | string | Yes |

## Request Body

This section outlines the required fields to update the notes of a hybrid/local user in a customer's tenant.

| Parameter | Description | Type | Required |
| --- | --- | --- | --- |
| notes | The notes you want to make for the user. The maximum length is 1024 characters.| string | Yes |

## Response

If the request has been successfully processed, a 204 No Content response will be returned. For more details on the HTTP status code, refer to [Http Status Code](../../Use-AvePoint-Graph-API.md#http-status-code).

## Request Sample

To use this API, send a PUT request to the specified endpoint, including necessary parameters as defined in the references. 

```json
https://graph.avepointonlineservices.com/partner/external/v3/um/customers/966f35cc-****-4070-****-25cd****2a07/tenants/0c7715b3-****-4c4c-****-f363****acec/local-users/7c18fd6f-****-4353-****-5725****dc3f/notes
```
## Request Body Sample

```json
{
  "notes": "This is a sample note for the user." // The notes you want to make for the user
}
```