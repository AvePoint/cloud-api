# Retrieve Sign-in Information

Use this API to retrieve users' sign-in information in a customer's tenant. 

## Permission

The following permission is required to call the API.  
You must register an app through Elements > API app registration to authenticate and authorize your access to Elements API. For details, refer to [App Registration](../../register-app.md).

| API | Permission  |
|-----------|--------|
| `/partner/external/v3/um/customers/{customerId}/tenants/{tenantId}/overview/security/compliances/signins`|elements.um.user.read.all|  

## Request

This section outlines the details of the HTTP method and endpoint used to retrieve users' sign-in information in a customer's tenant.

| Method | Endpoint | Description |
|-----------|--------|------------|
| GET | `/partner/external/v3/um/customers/{customerId}/tenants/{tenantId}/overview/security/compliances/signins` | 	Retrieves users' sign-in information in a customer's tenant.

## URL Parameters

This section describes the query parameters that can be added to the URL when sending a GET request, allowing you to retrieve users' sign-in information in a customer's tenant according to your specific requirements and preferences.

| Parameter | Description | Type | Required |
| --- | --- | --- |---|
| customerId | The ID of the customer. | string | Yes |
| tenantId | The ID of the tenant. | string | Yes |

## Query Parameters

This section outlines the parameters optional required to specify paging information about the users you want to retrieve.

| Parameter | Description | Type | Required |
| --- | --- | --- | --- |
| pageIndex | The page number of the data which will be retrieve, the default value is 1. | integer | No |
| pageSize | The number of users API will retrieved in a time, the default value is 100. | integer | No |
| risky | Indicate whether you want to retrieve only risky sign-ins. | bool | No |

## Response

If the request has been successfully processed, a 200 OK response will be returned along with the requested user information displayed in the response body.
 
| Response | Description | Type |
| --- | --- | --- |
| id |  The unique identifier of the sign-in record. | string |
| loginTime |  The sign-in time. | long |
| userId |  The unique identifier of the user. | string |
| userDisplayName |  The display name of the user. | string |
| userPrincipalName |  The user principal name. | string |
| ip |  The IP address of the sign-in record. | string |
| lat |  The latitude of the sign-in record. | double |
| lon |  The longitude of the sign-in record. | double |
| country |  The country or region of the sign-in record. | string |
| city |  The city of the sign-in record. | string |
| isRisk |  The risk status of the sign-in record. | bool |

## Request Sample

To use this API, send a GET request to the specified endpoint, including necessary parameters as defined in the references. 

```json
https://graph.avepointonlineservices.com/partner/external/v3/um/customers/966f35cc-61f4-4070-819c-25cdbcf82a07/tenants/0c7715b3-bc2f-4c4c-a8a0-f3634dcfacec/overview/security/compliances/signins
```

## Response Sample

If the request has been successfully processed, a 200 OK response will be returned along with the requested information displayed in the response body. For more details on the HTTP status code, refer to [Http Status Code](../../Use-AvePoint-Graph-API.md#http-status-code).

```json
{
    "data": [
        {
            "id": "001f0090-****-****-****-b2c060e52500", // The unique identifier of the sign-in record
            "loginTime": 638907426550000000, //  The sign-in time
            "userId": "4140b563-****-****-****-5f44dadcf0fd", // The unique identifier of the user
            "userDisplayName": "Bob Mark", // The display name of the user.
            "userPrincipalName": "mark@element.onmicrosoft.com", //  The user principal name
            "ip": "74.207.240.85", // The IP address of the sign-in record
            "lat": 37.56699, // The latitude of the sign-in record
            "lon": -121.9827, // The longitude of the sign-in record
            "country": "US", // The country or region of the sign-in record
            "city": "Fremont", // The city of the sign-in record
            "isRisk": false // The risk status of the sign-in record
        },
    ],
     "metadata": {
        "pageIndex": 1, // The page index of current request
        "pageSize": 50, // The number will be retrieved in one request
        "totalCount": 1 // The total number count that matches the request
    }
}
```