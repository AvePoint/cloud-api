# Retrieve Information of Security Users

Use this API to retrieve information of security users in a customer's tenant. 

 ## Permission

The following permission is required to call the API.  
You must register an app through Elements > API app registration to authenticate and authorize your access to Elements API. For details, refer to [App Registration](../../register-app.md).

| API | Permission  |
|-----------|--------|
| `/partner/external/v3/um/customers/{customerId}/tenants/{tenantId}/overview/security/users`|elements.um.user.read.all|  

## Request

This section outlines the details of the HTTP method and endpoint used to retrieve information of security users in a customer's tenant.

| Method | Endpoint | Description |
|-----------|--------|------------|
| GET | `/partner/external/v3/um/customers/{customerId}/tenants/{tenantId}/overview/security/users` | Retrieves information of security users of a customer's tenant.|
 
## URL Parameters

This section outlines the parameters required to specify the customer's tenant to retrieve its secuirty users.

| Parameter | Description | Type | Required |
| --- | --- | --- | --- |
| customerId | The ID of the customer. | string | Yes |
| tenantId | The ID of the tenant. | string | Yes |

## Query Parameters

This section outlines the parameters optional required to specify paging information about the users you want to retrieve.

| Parameter | Description | Type | Required |
| --- | --- | --- | --- |
| pageIndex | The starting number of the page to get security users. The default value is 1. | integer | No |
| pageSize | The number of objects to display on one page. The default value is 100. | integer | No |
| status | The status of the user that you want to retrieve. <ul><li>**0** - MFA disabled</li><li>**1** - Sign-in blocked</li><li>**2** - Password expired</li><li>**3** - High risk</li><li>**4** - Medium risk</li><li>**5** - Compliance</li><li>**6** - Inactive</li><li>**7** - Pending deletion</li><li>**8** - Test user</li></ul> | integer  | No |

## Response

If the request has been successfully processed, a 200 OK response will be returned along with the requested information displayed in the response body.
 
| Response | Description | Type |
| --- | --- | --- |
| id | The ID of the user. | string |
| userPrincipalName | The user principle name. | string |
| mail | The email of the user. | string |
| displayName | The display name of the user. | string |
| firstName | The first name of the user. | string |
| lastName | The last name of the user. | string |
| employeeId | The employee ID of the user. | string |
| location | The location of the user. | string |
| company | The company of the user. | string |
| department | The department of the user. | string |
| mobile | The mobile of the user. | string |
| jobTitle | The job title of the user. | string |
| isTestUser | Indicates whether this is a test user account for development purposes. | bool |
| age | The password age of the user. | integer |
| startDate | The start date in ISO 8601 format when the user account can sign in Microsoft 365. | string |
| endDate | The date in ISO 8601 format when the user account will be blocked from signing in. | string |
| countryOrRegion | The country or region of the user. | string |
| status | The current status of the user. <ul><li>**0** - MFA disabled</li><li>**1** - Sign-in blocked</li><li>**2** - Password expired</li><li>**3** - High risk</li><li>**4** - Medium risk</li><li>**5** - Compliance</li><li>**6** - Inactive</li><li>**7** - Pending deletion</li><li>**8** - Test user</li></ul> | integer |
| pageIndex | The current display page. | integer |
| pageSize | The number of objects on the display page. | integer |
| totalCount | The total number of objects matching the query parameters. | integer |

## Request Sample
To use this API, send a GET request to the specified endpoint, including necessary parameters as defined in the references.
```json
https://graph.avepointonlineservices.com/partner/external/v3/um/customers/966f35cc-****-87b4-****-25cdbcf82a07/tenants/0c7715b3-****-81b6-****-f3634dcfacec/overview/security/users
```
 
## Response Sample
If the request has been successfully processed, a 200 OK response will be returned along with the requested information displayed in the response body.
For more details on the HTTP status code, refer to [Http Status Code](../../Use-AvePoint-Graph-API.md#http-status-code).
```json
{
    "data": [
        {
            "id": "c2aa00d3-****-40aa-****-9e9c79232bff", // The ID of the user
            "userPrincipalName": "kevin@domain.com", // The user principle name
            "displayName": "Kevin Mark", // The display name of the user
            "firstName": "Kevin", // The first name of the user
            "lastName": "Mark", // The last name of the user
            "department": "DEV", // The department of the user
            "mobile": "11122", // The mobile of the user
            "jobTitle": "Software developer", // The job title of the user
            "mail": "tony@domain.com", // The mail of the user
            "location": "location", // The office location of the user
            "employeeId": "643477", // The employee ID of the user
            "status": [
                    0, // The status of the user. 0 represents "MFA disabled"
                    1 // The status of the user. 1 represents "Sign-in blocked"
            ], 
            "isTestUser": false, // Indicates whether this is a test user account for development purposes
            "age": 12, // The password age of the user
            "startDate": "1970-01-01T00:00:00Z", // The start date in ISO 8601 format when the user account can sign in Microsoft 365
            "endDate": "1970-01-01T00:00:00Z", // The date in ISO 8601 format when the user account will be blocked from signing in
            "company": "BK Company", // The company of the user
            "countryOrRegion": "Slovenia" // The country or region of the user
        }
    ],
    "metadata": {
        "pageIndex": 1, // The current display page
        "pageSize": 50, // The number of objects on the display page
        "totalCount": 1 // he total number of objects matching the query parameters
    }
}
```