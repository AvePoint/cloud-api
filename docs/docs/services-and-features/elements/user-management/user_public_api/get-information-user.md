# Get Detail Information of A Specific User

Use this API to retrieve detail informations of specific users of a customer tenant in AvePoint Online Services. 

## Permissions

The following permission is required to call the API.  
You must register an app through Elements > API app registration to authenticate and authorize your access to AvePoint Graph API. For details, refer to [App Registration](https://cdn.avepoint.com/assets/apelements-webhelp/avepoint-elements-for-partners/index.htm#!Documents/appregistration.htm).

| API | Permission  |
|-----------|--------|
| `/external/v3/um/customers/{customerId}/tenants/{tenantId}/users/{userId}`|partner.um.user.read.all|  

## Request

This section outlines the details of the HTTP method and endpoint used to retrieve information about a user.

| Method | Endpoint | Description |
|-----------|--------|------------|
| GET | `/external/v3/um/customers/{customerId}/tenants/{tenantId}/users/{userId}` | 	Retrieves basic information for specific users of a customer tenant in AvePoint Online Services.|

## URL Parameters

This section describes the query parameters that can be added to the URL when sending a GET request, allowing you to retrieve user information according to your specific requirements and preferences.

| Parameter | Description | Type | Required |
| --- | --- | --- |---|
| customerId | The customer ID of the customer. | string | Yes |
| tenantId | The specific tenant ID of the customer. | string | Yes |
| userId | Unique identifier for the specific user whose details are being requested. | string | Yes |

## Response

If the request has been successfully processed, a 200 OK response will be returned along with the requested user information displayed in the response body.
 
| Response | Description | Type |
| --- | --- | --- |
| Id |  The ID of the user. | string |
| Manager | The manager of the user | string |
| FirstName | The first name of the user. | string |
| LastName | The last name of the user. | string |
| DisplayName | The display name of the user | string |
| JobTitle | The job title of the user. | string |
| EmployeeId |The employeeId of the user. | string |
| AlternativeEmailAddress | The alternate email address or the user. | List<string> |
| Company | The company of the user. | string |
| Department | The department  of the user. | string |
| Location | The location of the user. | string |
| PasswordNeverExpire | Indicates whether the user's password is set to never expire. | boolean |
| LastChangeDate | The date and time when the user account was last modified. | long |
| Age | The calculated age of the user based on their birthday. | int |
| IsTestUser | Indicates whether this is a test user account for development purposes. | boolean |
| OfficePhone | The business phone number of the user. | string |
| Mobile | The mobile phone number of the user. | string |
| Birthday | The birthday of the user | long |
| Mail | The primary email address of the user. | string |
| UsageLocation | The usage location for the user account, typically a country code. | string |
| PreferredLanguage | The preferred language setting for the user interface. | string |
| EnforceStart | Indicates whether account enforcement start date is enabled. | boolean |
| EnforceStartDateTime | The date and time when account enforcement begins. | long |
| EnforceEnd | Indicates whether account enforcement end date is enabled. | boolean |
| EnforceEndDateTime | The date and time when account enforcement ends. | long |
| PostalCode | The postal code of the user. | string |
| CountryRegion | The country or region where the user is located. | string |
| State | The state or province where the user is located. | string |
| Address | The street address of the user's location. | string |
| LoginName | The login name or user principal name used for authentication. | string |
| Status | The current status of the user account (Active, Inactive, etc.). | enum |

## Request Sample

To use this API, send a GET request to the specified endpoint, including necessary parameters as defined in the references. 

```json
https://graph.avepointonlineservices.com/partner/external/v3/um/customers/966f35cc-61f4-4070-819c-25cdbcf82a07/tenants/0c7715b3-bc2f-4c4c-a8a0-f3634dcfacec/users/7c18fd6f-fb26-4353-8dbd-5725fa9edc3f
```

## Response Sample

If the request has been successfully processed, a 200 OK response will be returned along with the requested information displayed in the response body.
For more details on the HTTP status code, refer to [Http Status Code](https://learn.avepoint.com/docs/Use-AvePoint-Graph-API.html#http-status-code).

```json
{
    "id": "7c18fd6f-fb26-4353-8dbd-5725fa9edc3f",
    "manager": "jack@element.onmicrosoft.com",
    "firstName": "Kevin",
    "lastName": "Mark",
    "displayName": "Kevin Mark",
    "jobTitle": "IT",
    "employeeId": "099999",
    "alternativeEmailAddress": [
        "kevin_Al@element.onmicrosoft.com"
    ],
    "company": "BK Company",
    "department": "DEV",
    "location": "2298",
    "passwordNeverExpire": true,
    "lastChangeDate": 638894480510000000,
    "age": 37,
    "isTestUser": true,
    "officePhone": "2323111dsd",
    "mobile": "323111dsd",
    "birthday": 0,
    "mail": "kevin@element.onmicrosoft.com",
    "usageLocation": "AF",
    "preferredLanguage": "af-NA",
    "enforceStart": false,
    "enforceStartDateTime": 0,
    "enforceEnd": false,
    "enforceEndDateTime": 0,
    "postalCode": "2121",
    "countryRegion": "Antarctica",
    "state": "British Antarctic Territory",
    "address": "Rothera Research Station",
    "loginName": "kevin@element.onmicrosoft.com",
    "status": 25
}
```