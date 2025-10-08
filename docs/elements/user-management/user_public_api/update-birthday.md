# Update Birthday of a Specific User

Use this API to update the birthday of a specific user in a customer's tenant. 

## Permission

The following permission is required to call the API.  
You must register an app through Elements > API app registration to authenticate and authorize your access to AvePoint Graph API. For details, refer to [App Registration](../../register-app.md).

| API | Permission  |
|-----------|--------|
| `/partner/external/v3/um/customers/{customerId}/tenants/{tenantId}/users/{userId}/birthday`|elements.um.user.readwrite.all|  

## Request

This section outlines the details of the HTTP method and endpoint used to update the birthday of a specific user in a customer's tenant.

| Method | Endpoint | Description |
|-----------|--------|------------|
| PUT | `/partner/external/v3/um/customers/{customerId}/tenants/{tenantId}/users/{userId}/birthday` | Updates the birthday of a specific user in a customer's tenant.|

## URL Parameters

This section describes the query parameters that can be added to the URL when sending a PUT request, allowing you to update the birthday of a user according to your specific requirements and preferences.

| Parameter | Description | Type | Required |
| --- | --- | --- |---|
| customerId | The ID of the customer. | string | Yes |
| tenantId | The ID of the tenant. | string | Yes |
| userId | The unique identifier of the user. | string | Yes |

## Request Body

This section outlines the required fields to update the birthday of a specific user in a customer's tenant.

| Parameter | Description | Type | Required |
| --- | --- | --- | --- |
| birthday | The birthday of the user. | string | Yes |

## Response

If the request has been successfully processed, a 204 No Content response will be returned.

## Request Sample

To use this API, send a PUT request to the specified endpoint, including necessary parameters as defined in the references. 

```json
https://graph.avepointonlineservices.com/partner/external/v3/um/customers/966f35cc-****-****-****-25cdbcf82a07/tenants/0c7715b3-****-****-****-f3634dcfacec/users/7c18fd6f-****-****-****-5725fa9edc3f/birthday
```
## Request Body Sample

```json
{
  "birthday": "1970-01-01T00:00:00Z" // The birthday of the user
}
```