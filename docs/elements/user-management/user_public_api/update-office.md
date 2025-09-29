# Update Office of a Specific User

Use this API to update the office of a specific user in a customer's tenant. 

## Permission

The following permission is required to call the API.  
You must register an app through Elements > API app registration to authenticate and authorize your access to AvePoint Graph API. For details, refer to [App Registration](https://cdn.avepoint.com/assets/apelements-webhelp/avepoint-elements-for-partners/index.htm#!Documents/appregistration.htm).

| API | Permission  |
|-----------|--------|
| `/external/v3/um/customers/{customerId}/tenants/{tenantId}/users/{userId}/office`|elements.um.user.readwrite.all|  

## Request

This section outlines the details of the HTTP method and endpoint used to update the office
of a specific user in a cutomer's tenant.

| Method | Endpoint | Description |
|-----------|--------|------------|
| PUT | `/external/v3/um/customers/{customerId}/tenants/{tenantId}/users/{userId}/office` | Updates the office of a specific user in a customer's tenant.|

## URL Parameters

This section describes the query parameters that can be added to the URL when sending a PUT request, allowing you to update office about a user according to your specific requirements and preferences.

| Parameter | Description | Type | Required |
| --- | --- | --- |---|
| customerId | The customer ID of the customer. | string | Yes |
| tenantId | The specific tenant ID of the customer. | string | Yes |
| userId | Unique identifier for the specific user whose details are being requested. | string | Yes |

## Request Body

This section outlines the required fields to update the office of a user.

| Parameter | Description | Type | Required |
| --- | --- | --- | --- |
| company | The company of the user. The maximum length is 64 characters.| string | Yes |
| department | The department of the user. The maximum length is 64 characters.| string | Yes |
| location |  The location of the user. The maximum length is 64 characters. | string | Yes | 

## Response

If the request has been successfully processed, a 204 No Content response will be returned

## Request Sample

To use this API, send a PUT request to the specified endpoint, including necessary parameters as defined in the references. 

```json
https://graph.avepointonlineservices.com/partner/external/v3/um/customers/966f35cc-****-****-****-25cdbcf82a07/tenants/0c7715b3-****-****-****-f3634dcfacec/users/7c18fd6f-****-****-****-5725fa9edc3f/office
```
## Request Body Sample

```json
{
  "company": "Organization ABC", // The company of the user
  "department": "09", // The department of the user
  "location": "0711" // The location of the user
}
```