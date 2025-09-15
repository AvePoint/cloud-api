# Get Overview Security Users

Use this API to retrieve overview information for security users of a customer tenant in AvePoint Online Services. 

 ## Permissions

The following permission is required to call the API.  
You must register an app through Elements > API app registration to authenticate and authorize your access to AvePoint Graph API. For details, refer to [App Registration](https://cdn.avepoint.com/assets/apelements-webhelp/avepoint-elements-for-partners/index.htm#!Documents/appregistration.htm).

| API | Permission  |
|-----------|--------|
| `/external/v3/um/customers/{customerId}/tenants/{tenantId}/overview/security/users/batch`|partner.um.user.read.all|  

## Request

This section outlines the details of the HTTP method and endpoint used to retrieve information about a user.

| Method | Endpoint | Description |
|-----------|--------|------------|
| GET | `/external/v3/um/customers/{customerId}/tenants/{tenantId}/overview/security/users/batch` | Retrieves overview information for security users of a customer tenant in AvePoint Online Services.|
 
## URL Parameters

This section outlines the parameters required to specify which customer tenant you want to retrieve.

| Parameter | Description | Type | Required |
| --- | --- | --- | --- |
| customerId | The customer ID of the customer. | string | Yes |
| tenantId | The specific tenant ID of the customer. | string | Yes |

## Query Parameters

This section outlines the parameters optional required to specify paging information about the users you want to retrieve.

| Parameter | Description | Type | Required |
| --- | --- | --- | --- |
| pageIndex | The page number of the data which will be retrieve, the default value is 1. | integer | False |
| pageSize | The number of users API will retrieved in a time, the default value is 100. | integer | False |
| status | An array containing the statuses that the user wants to retrieve | `List<int>` (0:MFADisabled,1:SignInBlocked,2:PasswordExpired,3:HighRisk,4:MediumRisk,5:Compliance)  | False |

## Response

If the request has been successfully processed, a 200 OK response will be returned along with the requested information displayed in the response body.
 
| Field | Description | Type |
| --- | --- | --- |
| Id | The ID of the user. | string |
| DisplayName |  The displayName of the user. | string |
| Mail | The email address of the user. | string |
| FirstName | The first name of the user. | string |
| LastName | The last name of the user. | string |
| EmployeeId | The employeeId of the user. | string |
| Location | The location of the user. | string |
| Department | The department of the user. | string |
| Mobile | The mobile phone number of the user. | string |
| JobTitle | The jobTitle of the user. | string |
| Status |  The status of the user. | enum |
| IsTestUser |  If the user is test or not. | boolean |
| Age | The password age of the user.  | integer |
| StartDate | The enforce start date of the user. | Long |
| EndDate | The enforce end date of the user. | Long |
| OfficePhone | The business phone number of the user. | string |
| Company | The company of the user | string |
| CountryRegion | The country or region of the user | string |
| pageIndex | The page index of current request. | integer |
| pageSize | The user number will be retrieved in one request. | integer |
| totalCount | The total number count that match the request. | integer |

## Request Sample
To use this API, send a GET request to the specified endpoint, including necessary parameters as defined in the references.
```json
https://graph.avepointonlineservices.com/partner/external/v3/um/customers/966f35cc-61f4-4070-819c-25cdbcf82a07/tenants/0c7715b3-bc2f-4c4c-a8a0-f3634dcfacec/overview/security/users/batch
```
 
## Response Sample
If the request has been successfully processed, a 200 OK response will be returned along with the requested information displayed in the response body.
For more details on the HTTP status code, refer to [Http Status Code](https://learn.avepoint.com/docs/Use-AvePoint-Graph-API.html#http-status-code).
```json
{
    "data": [
        {
            "id": "f04d7aee-341e-4ab9-9e1a-65215f92e596",
            "userPrincipalName": "mark@element.onmicrosoft.com",
            "displayName": "Bob Mark",
            "firstName": "Bob",
            "lastName": "Mark",
            "employeeId": "s12123",
            "location": "0711",
            "department": "09",
            "mobile": "55444",
            "jobTitle": "Software developer",
            "status": 13,
            "isTestUser": true,
            "age": 0,
            "startDate": 0,
            "endDate": 0,
            "company": "BK Company",
            "officePhone":"43344",
            "countryRegion": "Slovenia"
        }
    ],
    "metadata": {
        "pageIndex": 1,
        "pageSize": 50,
        "totalCount": 1
    }
}
```