# Update Information of a Specific User

Use this API to update information of a specific user in a customer's tenant. 

## Permission

The following permission is required to call the API.  
You must register an app through Elements > API app registration to authenticate and authorize your access to AvePoint Graph API. For details, refer to [App Registration](../../register-app.md).

| API | Permission  |
|-----------|--------|
| `/partner/external/v3/um/customers/{customerId}/tenants/{tenantId}/users/{userId}/account-information`|elements.um.user.readwrite.all|

## Request

This section outlines the details of the HTTP method and endpoint used to update information of a specific user in a customer's tenant.

| Method | Endpoint | Description |
|-----------|--------|------------|
| PUT | `/partner/external/v3/um/customers/{customerId}/tenants/{tenantId}/users/{userId}/account-information` | Updates information of a specific user in a customer's tenant.|

## URL Parameters

This section describes the query parameters that can be added to the URL when sending a PUT request, allowing you to update information of a specific user in a customer's tenant according to your specific requirements and preferences.

| Parameter | Description | Type | Required |
| --- | --- | --- |---|
| customerId | The ID of the customer. | string | Yes |
| tenantId | The ID of the tenant. | string | Yes |
| userId | The unique identifier of the user. | string | Yes |

## Request Body

This section outlines the required fields to update the information of a specific user in a cutomer's tenant.

| Parameter | Description | Type | Required |
| --- | --- | --- | --- |
| mail | The mail of the user. The maximum length is 256 characters. | string | Yes |
| usageLocation | The usage location of the user. The maximum length is 128 characters. For details, refer to [Usage Locations](../../../elements/user-management/user_public_api/usage_location.md).| string | Yes |
| preferredLanguage |  The preferred language of the user. For details, refer to [Preferred Languages](../../../elements/user-management/user_public_api/language.md). | string | Yes | 
| enforceStart | Indicates whether account enforcement start date is enabled. | bool | Yes | 
| enforceStartDateTime |The date and time when account enforcement begins.| string | Yes | 
| enforceEnd |Indicates whether account enforcement end date is enabled. | bool | Yes | 
| enforceEndDateTime |The date and time when account enforcement ends. | string | Yes | 

## Response

If the request has been successfully processed, a 204 No Content response will be returned. For more details on the HTTP status code, refer to [Http Status Code](../../Use-AvePoint-Graph-API.md#http-status-code).

## Request Sample

To use this API, send a PUT request to the specified endpoint, including necessary parameters as defined in the references. 

```json
https://graph.avepointonlineservices.com/partner/external/v3/um/customers/966f35cc-****-****-****-25cdbcf82a07/tenants/0c7715b3-****-****-****-f3634dcfacec/users/7c18fd6f-****-****-****-5725fa9edc3f/account-information
```
## Request Body Sample

```json
{
  "mail": "tony@element.onmicrosoft.com", // The mail of the user
  "usageLocation": "AF", // The usage location of the user
  "preferredLanguage": "af-NA", // The preferred language of the user
  "enforceStart": true, // Indicates whether account enforcement start date is enabled
  "enforceStartDateTime": "1970-01-01T00:00:00Z", // The date and time when account enforcement begins
  "enforceEnd": true, // Indicates whether account enforcement end date is enabled
  "enforceEndDateTime": "1970-01-01T00:00:00Z" // The date and time when account enforcement ends
}
```