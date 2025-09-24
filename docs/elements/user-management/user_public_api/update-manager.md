# Update Manager of A Specific User

Use this API to update manager of specific user of a customer tenant in AvePoint Online Services. 

## Permissions

The following permission is required to call the API.  
You must register an app through Elements > API app registration to authenticate and authorize your access to AvePoint Graph API. For details, refer to [App Registration](https://cdn.avepoint.com/assets/apelements-webhelp/avepoint-elements-for-partners/index.htm#!Documents/appregistration.htm).

| API | Permission  |
|-----------|--------|
| `/external/v3/um/customers/{customerId}/tenants/{tenantId}/users/{userId}/manager`|elements.um.user.readwrite.all|  

## Request

This section outlines the details of the HTTP method and endpoint used to update manager about a user.

| Method | Endpoint | Description |
|-----------|--------|------------|
| PUT | `/external/v3/um/customers/{customerId}/tenants/{tenantId}/users/{userId}/manager` | Update manager about a user of a customer tenant in AvePoint Online Services.|

## URL Parameters

This section describes the query parameters that can be added to the URL when sending a PUT request, allowing you to update manager about a user according to your specific requirements and preferences.

| Parameter | Description | Type | Required |
| --- | --- | --- |---|
| customerId | The customer ID of the customer. | string | Yes |
| tenantId | The specific tenant ID of the customer. | string | Yes |
| userId | Unique identifier for the specific user whose details are being requested. | string | Yes |

## Request Body

This section outlines the required fields to update the manager of a user.

| Parameter | Description | Type | Required | MaxLength
| --- | --- | --- | --- | ---|
| id | The ID of the manager. | string | Yes | 40 character |
| userPrincipalName | The user PrincipalName of the manager. | string | Yes | 1024 character|

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
  "id": "631b0def-f500-482d-a4cd-5811518ebbea",
  "userPrincipalName": "Jackson@element.onmicrosoft.com"
}
```