# Update Profile of a Hybrid/Local User

Use this API to update the profile of a hybrid/local user in a customer's tenant. 

## Permission

The following permission is required to call the API.  
You must register an app through Elements > API app registration to authenticate and authorize your access to Elements API. For details, refer to [App Registration](../../register-app.md).

| API | Permission  |
|-----------|--------|
| `/partner/external/v3/um/customers/{customerId}/tenants/{tenantId}/local-users/{userId}/profile`|elements.um.user.readwrite.all|  

## Request

This section outlines the details of the HTTP method and endpoint used to update the profile of a hybird/local user in a cutomer's tenant.

| Method | Endpoint | Description |
|-----------|--------|------------|
| PUT | `/partner/external/v3/um/customers/{customerId}/tenants/{tenantId}/local-users/{userId}/profile` | Updates the profile of a specific user in a customer's tenant.|

## URL Parameters

This section describes the query parameters that can be added to the URL when sending a PUT request, allowing you to update the profile of a hybrid/local user according to your specific requirements and preferences.

| Parameter | Description | Type | Required |
| --- | --- | --- |---|
| customerId | The customer ID of the customer. | string | Yes |
| tenantId | The tenant ID of the customer. | string | Yes |
| userId | The unique identifier of the user whose information you want to update. | string | Yes |

## Request Body

This section outlines the required fields to update the profile of a user.

| Parameter | Description | Type | Required |
| --- | --- | --- | --- |
| homeDirectory | The home directory of the user. The maximum length is 520 characters.| string | Yes |
| profilePath | The profile path of the user. The maximum length is 520 characters.| string | Yes |
| logonScript |  The logon script of the user. The maximum length is 520 characters.| string | Yes |

## Response

If the request has been successfully processed, a 204 No Content response will be returned. For more details on the HTTP status code, refer to [Http Status Code](../../Use-AvePoint-Graph-API.md#http-status-code).

## Request Sample

To use this API, send a PUT request to the specified endpoint, including necessary parameters as defined in the references. 

```json
https://graph.avepointonlineservices.com/partner/external/v3/um/customers/966f35cc-****-98b1-****-25cdbcf82a07/tenants/0c7715b3-****-16b5-****-f3634dcfacec/local-users/7c18fd6f-****-87b2-****-5725fa9edc3f/profile
```
## Request Body Sample

```json
{
  "homeDirectory": "\\server\\users\\home", // The home directory of the user
  "profilePath": "\\server\\profiles\\user", // The profile path of the user
  "logonScript": "logon.bat" // The logon script of the user
}
```