# Update General Information of a Specific User

Use this API to update the general information of a specific user in a customer's tenant. 

## Permission

The following permission is required to call the API.  
You must register an app through Elements > API app registration to authenticate and authorize your access to AvePoint Graph API. For details, refer to [App Registration](https://cdn.avepoint.com/assets/apelements-webhelp/avepoint-elements-for-partners/index.htm#!Documents/appregistration.htm).

| API | Permission  |
|-----------|--------|
| `/external/v3/um/customers/{customerId}/tenants/{tenantId}/users/{userId}/general-information`|elements.um.user.readwrite.all|  

## Request

This section outlines the details of the HTTP method and endpoint used to update the general information
of a user in a customer's tenant.

| Method | Endpoint | Description |
|-----------|--------|------------|
| PUT | `/external/v3/um/customers/{customerId}/tenants/{tenantId}/users/{userId}/general-information` | Updates the general information of a specific user in a customer's tenant.|

## URL Parameters

This section describes the query parameters that can be added to the URL when sending a PUT request, allowing you to update the general information of a user according to your specific requirements and preferences.

| Parameter | Description | Type | Required |
| --- | --- | --- |---|
| customerId | The ID of the customer. | string | Yes |
| tenantId | The ID of the tenant. | string | Yes |
| userId | The unique identifier of the user. | string | Yes |

## Request Body

This section outlines the required fields to update the general information of a user.

| Parameter | Description | Type | Required |
| --- | --- | --- | --- |
| firstName | The first name of the user. The maximum length is 64 characters. | string | Yes |
| lastName | The last name of the user. The maximum length is 64 characters.| string | Yes |
| displayName |  The display name of the user. The maximum length is 256 characters.| string | Yes |
| jobTitle | The job title of the user. | string | Yes |
| employeeId |The employee ID of the user. The maximum length is 16 characters.| string | Yes |

## Response

If the request has been successfully processed, a 204 No Content response will be returned

## Request Sample

To use this API, send a PUT request to the specified endpoint, including necessary parameters as defined in the references. 

```json
https://graph.avepointonlineservices.com/partner/external/v3/um/customers/966f35cc-****-****-****-25cdbcf82a07/tenants/0c7715b3-****-****-****-f3634dcfacec/users/7c18fd6f-****-****-****-5725fa9edc3f/general-information
```
## Request Body Sample

```json
{
  "firstName": "Tony", // The first name of the user
  "lastName": "Brown", // The last name of the user
  "displayName": "Tony Brown", // The display name of the user
  "jobTitle" : "IT", // The job title of the user
  "employeeId" : "e3f1a9b8-4d2c" // The employee ID of the user
}
```