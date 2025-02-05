# Retrieve User Summary

Retrieve the summary information of users. By invoking the `/insights/users/summary` endpoint, you can retrieve a summary of specific users. This method is useful for obtaining an overview of user properties and statuses. 

## Permission 

The following permission is required to call this API.  
You must register an app through AvePoint Online Services > App registration to authenticate and authorize your access to AvePoint Graph Modern API. For details, refer to [Authentication and Authorization](https://learn.avepoint.com/docs/Use-AvePoint-Graph-Modern-API.html#authentication-and-authorization).

| API     | Permission required | 
|-------------------|---------------|
| `/insights/users/summary` | insights.graph.readwrite.all |

## Request 

This section outlines the HTTP method and endpoint used to retrieve user summary information. It provides a concise description of the action performed by the API call. 

| HTTP Method | Endpoint | Description |
| --- | --- | --- |
| GET | `/insights/users/summary` | Retrieves the user summary information. |


## Query Parameters

The API supports several query parameters to refine and customize the data retrieval process. These parameters allow users to specify pagination and page size to filter the results effectively.


| Parameter | Description | Type    | Required? |
|-----------|-------------|---------|-----------|
| startPage | The starting page of the query starts from 0 | integer | Yes        |
| pageSize  | Sets the number of results for one page. 100 results on one page at most. | integer | Yes        |

### Responses

The API response provides detailed information about the users retrieved. Each group in the response includes various attributes that describe its properties and status.

| Elements | Description                                      | Type    |
|----------|--------------------------------------------------|---------|
| status   | The HTTP response status code                    | integer |
| message  | The error message                             | string  |
| nextLink | The token to be used to get the remaining results of this request | string  |
| results   | A list of user summary objects               | list   |

**User summary**

| Property         | Description                                                                 |Type
|------------------|-----------------------------------------------------------------------------|------|
| displayName    | The display name of the user                                                | string|
| loginName      | The principal name of the user                                      | String|
| email          | The email address of the user                                               | string|
| userStatus     | The Sign-in status of the Microsoft 365 user. (e.g., **Blocked**, **Active**) For users that do not exist in Azure AD, the status will be **Not in Azure AD**.                     | string|
| trustStatus    | The trust status of the user in Insights for Microsoft 365 (e.g., **Trusted**, **Not Trusted**)                     | string|
| sensitiveItems | The number of sensitive items associated with the user                      |integer|
| lastSignIn     | The time range of the user's last sign-in. (e.g., **Less than 90 Days**, **More than 90 Days**, **More than 180 Days**, **None**, **N/A**)_            |string|
| createdOn      | The date and time when the user account was created in Microsoft Entra, in ISO 8601 format     |


## Request Sample

To use this API, send a `GET` request to the specified endpoint, including necessary parameters as defined. This will return the relevant user summary details in a structured format, enabling easy integration with other systems or applications. 

```json
https://graph-us.avepointonlineservices.com/insights/users/summary?startPage=1&pageSize=50
```

## Response Sample  

The following is a sample response for this API method, which includes summary information of the users retrieved: 

```json
{
    "results": [
        {
            "displayName": "Adele Vance", // username
            "loginName": "adelev00606@m365x****63.onmicrosoft.com", // user principal name
            "email": "AdeleV00606@m365x****63.onmicrosoft.com", // user email
            "userStatus": "Active", // current status of the user
            "trustStatus": "Not Trusted", // trust status of the user
            "sensitiveItems": 87, // number of sensitive items associated with the user
            "LastSignIn": "Less than 90 Days", // last sign-in time frame
            "createdOn": "2021-08-23T03:39:55" // account creation date and time
        },
        {
            "displayName": "Insights1 Tester001", // username
            "loginName": "insight********_***insightstest.onmicrosoft.com#ext#@m365x********.onmicrosoft.com", // user principal name
            "email": "Insights********@***insightstest.onmicrosoft.com", // user email
            "userStatus": "Blocked", // current status of the user
            "trustStatus": "Trusted", // trust status of the user
            "sensitiveItems": 55, // number of sensitive items associated with the user
            "LastSignIn": "Less than 90 Days", // last sign-in time frame
            "createdOn": "2021-08-24T06:12:55" // account creation date and time
        },
        {
            "displayName": "Internal User Change0406-2", // username
            "loginName": "userchange0406-2@m365x******.onmicrosoft.com", // user principal name
            "email": "", // user email (empty in this case)
            "userStatus": "Blocked", // current status of the user
            "trustStatus": "Not Trusted", // trust status of the user
            "sensitiveItems": 38, // number of sensitive items associated with the user
            "LastSignIn": "None", // last sign-in time frame
            "createdOn": "2022-04-06T06:40:21" // account creation date and time
        },
        {
            "displayName": "Insights Tester003", // username
            "loginName": "tester003_******insightstest.onmicrosoft.com#ext#@m365x******.onmicrosoft.com", // user principal name
            "email": "Tester003@***insightstest.onmicrosoft.com", // user email
            "userStatus": "Active", // current status of the user
            "trustStatus": "Trusted", // trust status of the user
            "sensitiveItems": 36, // number of sensitive items associated with the user
            "LastSignIn": "More than 180 Days", // last sign-in time frame
            "createdOn": "2021-08-24T06:12:55" // account creation date and time
        }
    ],
    "status": 200, // HTTP status code indicating the request was successful
    "message": "", // additional information about the status (empty in this case)
    "nextLink": null // link to the next set of results, if applicable; null if there are no more results
}
```