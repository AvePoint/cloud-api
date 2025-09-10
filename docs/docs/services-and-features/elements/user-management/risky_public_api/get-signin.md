# Retrieve User Signin Actions

Use this API to retrieve user signin actions information of a customer tenant in AvePoint Online Services. 

## Permissions

The following permission is required to call the API.  
You must register an app through Elements > API app registration to authenticate and authorize your access to AvePoint Graph API. For details, refer to [App Registration](https://cdn.avepoint.com/assets/apelements-webhelp/avepoint-elements-for-partners/index.htm#!Documents/appregistration.htm).

| API | Permission  |
|-----------|--------|
| `/external/v3/um/customers/{customerId}/tenants/{tenantId}/overview/security/compliances/signins/batch`|partner.um.user.read.all|  

## Request

This section outlines the details of the HTTP method and endpoint used to retrieve risk signins users information of a customer tennants.

| Method | Endpoint | Description |
|-----------|--------|------------|
| GET | `/external/v3/um/customers/{customerId}/tenants/{tenantId}/overview/security/compliances/signins/batch` | 	Retrieve signin actions information of a customer tennant in AvePoint Online Services.

## URL Parameters

This section describes the query parameters that can be added to the URL when sending a GET request, allowing you to retrieve risk signin according to your specific requirements and preferences.

| Parameter | Description | Type | Required |
| --- | --- | --- |---|
| customerId | The customer ID of the customer. | string | Yes |
| tenantId | The specific tenant ID of the customer. | string | Yes |

## Query Parameters

This section outlines the parameters optional required to specify paging information about the users you want to retrieve.

| Parameter | Description | Type | Required |
| --- | --- | --- | --- |
| pageIndex | The page number of the data which will be retrieve, the default value is 1. | integer | False |
| pageSize | The number of users API will retrieved in a time, the default value is 100. | integer | False |
| risky | Filter for only risky signins. | bool | False |

## Response

If the request has been successfully processed, a 200 OK response will be returned along with the requested user information displayed in the response body.
 
| Response | Description | Type |
| --- | --- | --- |
| id |  The id of the user signin record. | string |
| loginTime |  The login time of the user signin record. | long |
| customerId |  The customerId of the user signin record. | string |
| tenantId |  The tenantId of the user signin record. | string |
| userId |  The userId of the user signin record. | string |
| userDisplayName |  The user DisplayName of the user signin record. | string |
| userPrincipalName |  The user PrincipalName of the user signin record. | string |
| ip |  The ip address of the user signin record. | string |
| lat |  The lat of the user signin record. | double |
| lon |  The lon of the user signin record. | double |
| country |  The country of the user signin record. | string |
| city |  The city of the user signin record. | string |
| isRisk |  The risk status of the user signin record. | bool |
| city_Country |  The city_country format value of the user signin record. | string |
| deviceDisplayName |  The device display name used when user singin. | string |

## Request Sample

To use this API, send a GET request to the specified endpoint, including necessary parameters as defined in the references. 

```json
https://graph.avepointonlineservices.com/partner/external/v3/um/customers/966f35cc-61f4-4070-819c-25cdbcf82a07/tenants/0c7715b3-bc2f-4c4c-a8a0-f3634dcfacec/overview/security/compliances/signins/batch
```

## Response Sample

If the request has been successfully processed, a 200 OK response will be returned along with the requested information displayed in the response body.
For more details on the HTTP status code, refer to [Http Status Code](https://learn.avepoint.com/docs/Use-AvePoint-Graph-API.html#http-status-code).

```json
{
    "data": [
        {
            "id": "001f0090-5daf-4ea3-b540-b2c060e52500",
            "loginTime": 638907426550000000,
            "customerId": "966f35cc-61f4-4070-819c-25cdbcf82a07",
            "tenantId": "0c7715b3-bc2f-4c4c-a8a0-f3634dcfacec",
            "userId": "4140b563-7c45-4a8a-b0bf-5f44dadcf0fd",
            "userDisplayName": "Bob Mark",
            "userPrincipalName": "mark@element.onmicrosoft.com",
            "ip": "74.207.240.85",
            "lat": 37.56699,
            "lon": -121.9827,
            "country": "US",
            "city": "Fremont",
            "isRisk": false,
            "city_Country": "Fremont, US",
            "deviceDisplayName": "Laptop"
        },
    ],
     "metadata": {
        "pageIndex": 1,
        "pageSize": 50,
        "totalCount": 1
    }
}
```