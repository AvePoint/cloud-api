# Retrieve Basic Information of users

Use this API to retrieve basic informations of multiple users of a customer tenant in AvePoint Online Services.  

## Permissions  

The following permission is required to call the API.  
You must register an app through Elements > API app registration to authenticate and authorize your access to AvePoint Graph API. For details, refer to [App Registration](https://cdn.avepoint.com/assets/apelements-webhelp/avepoint-elements-for-partners/index.htm#!Documents/appregistration.htm).

| API | Permission |
|-----------|-----------|
| `/external/v3/um/customers/{customerId}/tenants/{tenantId}/users/batch` | elements.um.user.read.all |  

## Request

This section outlines the HTTP method and endpoint used to retrieve basic information for specific users of a customer tenant in AvePoint Online Services.

| Method | Endpoint | Description |
|-----------|-----------|-----------|
|POST|`/external/v3/um/customers/{customerId}/tenants/{tenantId}/users/batch`|Retrieves basic information for specific users of a customer tenant in AvePoint Online Services.|

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
| pageIndex | The page number of the data which will be retrieve, the default value is 1. | integer | No |
| pageSize | The number of users API will retrieved in a time, the default value is 100. | integer | No |

## Request Body

This section outlines the request body required to specify which users you want to retrieve.

| Parameter | Description | Type | Required |
| --- | --- | --- | --- |
| userIds | Array value include the ID of the users to be retrived | string[] | No |

## Response

If the request has been successfully processed, a 200 OK response will be returned along with the requested information displayed in the response body.

| Response | Description | Type |
| --- | --- | --- |
| id | The ID of the user. | string |
| userPrincipalName | The user principle name of the user. | string |
| mail | The email of the user. | string |
| displayName | The displayName of the user. | string |
| firstName | The firstName of the user. | string |
| lastName | The lastName of the user. | string |
| employeeId | The employeeId of the user. | string |
| location | The location of the user. | string |
| company | The company of the user. | string |
| department | The department of the user. | string |
| mobile | The mobile of the user. | string |
| jobTitle | The jobTitle of the user. | string |
| isTestUser | If the user is test or not. | bool |
| age | The password age of the user. | integer |
| startDate | The enforce start date of the user. | string |
| endDate | The enforce end date of the user. | string |
| officePhone | The office phone of the user. | string |
| countryOrRegion | The country region of the user. | string |
| status | The current status of the user account (Expire, Inactive, etc.). <ul><li>**0** - MFA disabled</li><li>**1** - Sign-in blocked</li><li>**2** - Password expired</li><li>**3** - High risk</li><li>**4** - Medium risk</li><li>**5** - Compliance</li><li>**6** - Inactive</li><li>**7** - Pending deletion</li><li>**8** - Test user</li></ul> | integer[] |
| pageIndex | The page index of current request. | integer |
| pageSize | The user number will be retrieved in one request. | integer |
| totalCount | The total number count that match the request. | integer |

## Request Sample

To use this API, send a GET request to the specified endpoint, including necessary parameters as defined in the references.

```json
https://graph.avepointonlineservices.com/partner/external/v3/um/customers/966f35cc-61f4-4070-819c-25cdbcf82a07/tenants/0c7715b3-bc2f-4c4c-a8a0-f3634dcfacec/users/batch
```

## Response Sample

If the request has been successfully processed, a 200 OK response will be returned along with the requested information displayed in the response body. For more details on the HTTP status code, refer to [Http Status Code](https://learn.avepoint.com/docs/Use-AvePoint-Graph-API.html#http-status-code).

```json 
{
    "data": [
        {
            "id": "c2aa00d3-ef87-40aa-a80a-9e9c79232bff",// The ID of the user
            "userPrincipalName": "kevin@element.onmicrosoft.com",// The user principle name of the user
            "displayName": "Kevin Mark",// The displayname of the user
            "firstName": "Kevin",// The firstName of the user
            "lastName": "Mark",// The lastName of the user
            "department": "DEV",// The department of the user
            "mobile": "11122",// The mobile of the user
            "jobTitle": "Software developer",// The jobTitle of the user
            "status": [
                    0, 
                    1
            ],// The status of the user
            "isTestUser": false,// If the user is test or not
            "age": 12,// The password age of the user
            "startDate": "1970-01-01T00:00:00Z",// The enforce start date of the user
            "endDate": "1970-01-01T00:00:00Z",// The enforce end date of the user
            "company": "BK Company",// The company of the user
            "countryOrRegion": "Slovenia"// The country region of the user
        }
    ],
    "metadata": {
        "pageIndex": 1,// The page index of current request
        "pageSize": 50,// The user number will be retrieved in one request
        "totalCount": 1// The total number count that match the request
    }
}
