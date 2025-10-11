# Update Office Location Information of a Specific User

Use this API to update the office location information of a specific user in a customer's tenant. 

## Permission

The following permission is required to call the API.  
You must register an app through Elements > API app registration to authenticate and authorize your access to Elements API. For details, refer to [App Registration](../../register-app.md).

| API | Permission  |
|-----------|--------|
| `/partner/external/v3/um/customers/{customerId}/tenants/{tenantId}/users/{userId}/office-information`|elements.um.user.readwrite.all|  

## Request

This section outlines the details of the HTTP method and endpoint used to update the office location information of a specific user in a cutomer's tenant.

| Method | Endpoint | Description |
|-----------|--------|------------|
| PUT | `/partner/external/v3/um/customers/{customerId}/tenants/{tenantId}/users/{userId}/office-information` | Updates the office location information of a specific user in a customer's tenant.|

## URL Parameters

This section describes the query parameters that can be added to the URL when sending a PUT request, allowing you to update the office location information of a user according to your specific requirements and preferences.

| Parameter | Description | Type | Required |
| --- | --- | --- |---|
| customerId | The ID of the customer. | string | Yes |
| tenantId | The ID of the tenant. | string | Yes |
| userId | The unique identifier of the user. | string | Yes |

## Request Body

This section outlines the required fields to update the office location information of a user.

| Parameter | Description | Type | Required |
| --- | --- | --- | --- |
| postalCode | The postal code of the office. The maximum length is 40 characters.| string | Yes |
| countryRegion | The country or region of the office. The maximum length is 255 characters. For details, refer to [Countries or Regions](../../../elements/user-management/user_public_api/countryorregion.md).| string | Yes |
| state | The state of the office. The maximum length is 128 characters. | string | Yes |
| address | The address of the office. The maximum length is 1024 characters. | string | Yes |

## Response

If the request has been successfully processed, a 204 No Content response will be returned. For more details on the HTTP status code, refer to [Http Status Code](../../Use-AvePoint-Graph-API.md#http-status-code).

## Request Sample

To use this API, send a PUT request to the specified endpoint, including necessary parameters as defined in the references. 

```json
https://graph.avepointonlineservices.com/partner/external/um/v3/customers/966f35cc-****-****-****-25cdbcf82a07/tenants/0c7715b3-****-****-****-f3634dcfacec/users/7c18fd6f-****-****-****-5725fa9edc3f/office-information
```
## Request Body Sample

```json
{
  "postalCode": "2121", // The postal code of the office
  "countryRegion": " Angola", // The country or region of the office
  "state": "Luanda", // The state of the office
  "address": "Dande" // The address of the office
}
```