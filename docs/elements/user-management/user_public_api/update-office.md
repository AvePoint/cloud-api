# Update Office A Specific User

Use this API to update office of specific users of a customer tenant in AvePoint Online Services. 

## Permissions

The following permission is required to call the API.  
You must register an app through Elements > API app registration to authenticate and authorize your access to AvePoint Graph API. For details, refer to [App Registration](https://cdn.avepoint.com/assets/apelements-webhelp/avepoint-elements-for-partners/index.htm#!Documents/appregistration.htm).

| API | Permission  |
|-----------|--------|
| `/external/v3/um/customers/{customerId}/tenants/{tenantId}/users/{userId}/office`|partner.um.user.readwrite.all|  

## Request

This section outlines the details of the HTTP method and endpoint used to update office
about a user.

| Method | Endpoint | Description |
|-----------|--------|------------|
| PUT | `/external/v3/um/customers/{customerId}/tenants/{tenantId}/users/{userId}/office` | Update office about a user of a customer tenant in AvePoint Online Services.|

## URL Parameters

This section describes the query parameters that can be added to the URL when sending a PUT request, allowing you to update office about a user according to your specific requirements and preferences.

| Parameter | Description | Type | Required |
| --- | --- | --- |---|
| customerId | The customer ID of the customer. | string | Yes |
| tenantId | The specific tenant ID of the customer. | string | Yes |
| userId | Unique identifier for the specific user whose details are being requested. | string | Yes |

## Request Body

This section outlines the required fields to update the office of a user.

| Parameter | Description | Type | Required | MaxLength
| --- | --- | --- | --- | ---|
| Company | The company of the user. | string | Yes | 64 character |
| Department | The department of the user. | string | Yes | 64 character|
| Location |  The locatiuon of the user | string | Yes |  64 character|

## Response

If the request has been successfully processed, a 204 No Content response will be returned

## Request Sample

To use this API, send a PUT request to the specified endpoint, including necessary parameters as defined in the references. 

```json
https://graph.avepointonlineservices.com/partner/external/v3/um/customers/966f35cc-61f4-4070-819c-25cdbcf82a07/tenants/0c7715b3-bc2f-4c4c-a8a0-f3634dcfacec/users/7c18fd6f-fb26-4353-8dbd-5725fa9edc3f/office
```
## Request Body Sample

```json
{
  "company": "BS Company",
  "department": "09",
  "location": "0711"
}
```