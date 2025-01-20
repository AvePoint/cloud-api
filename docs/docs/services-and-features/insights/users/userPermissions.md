# Retrieve User Permissions

Retrieve the permission-related information for specific users. By invoking the `/insights/users/access` endpoint, you can retrieve a summary of specific users. This method is useful for obtaining detailed insights into the permissions granted to users. 

## Permission 

The following permission is required to call this API.  
You must register an app through AvePoint Online Services > App registration to authenticate and authorize your access to AvePoint Graph Modern API. For details, refer to [Authentication and Authorization](https://learn.avepoint.com/docs/Use-AvePoint-Graph-Modern-API.html#authentication-and-authorization).

| API     | Permission required | 
|-------------------|---------------|
| `/insights/users/access` | insights.graph.readwrite.all |

## Request 

This section outlines the HTTP method and endpoint used to retrieve user permissions. It provides a concise description of the action performed by the API call. 

| HTTP Method | Endpoint | Description |
| --- | --- | --- |
| GET | `/insights/users/access` | Retrieves the user permissions. |


## Query Parameters

The API supports several query parameters to refine and customize the data retrieval process. These parameters allow users to specify the site URLs, emails, and next link to filter the results effectively..


| Parameter  | Description                                                                 | Type   | Required? |
|------------|-----------------------------------------------------------------------------|--------|-----------|
| siteUrls | Sets the URLs of site collections for which you want to get the permission related information | array  | No        |
| emails | Sets the email addresses or logonName of users for which you want to export the permission report. | array  | No        |
| nextLink | Sets whether to get the remaining results of a request of which the results are more than 100 | string | No        |


[we have logonName Loginname and principal name? which one is it?]: # 

### Responses

The API response provides detailed information about the user permissions retrieved. Each user permission in the response includes various attributes that describe its properties and status.

| Elements | Description                                      | Type    |
|----------|--------------------------------------------------|---------|
| status   | The HTTP response status code                    | integer |
| message  | The error message                             | string  |
| nextLink | The token to be used to get the remaining results of this request | string  |
| results   | A list of user permission objects               | list   |

**User summary**

| Property         | Description                                                                 |Type\
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

To use this API, send a GET request to the specified endpoint, including necessary parameters as defined. This will return the relevant group summary details in a structured format, enabling easy integration with other systems or applications. 

```json
https://graph.avepointonlineservices.com/insights/users/summary?startPage=1&pageSize=50
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
            "loginName": "insightstester001_jasoninsightstest.onmicrosoft.com#ext#@m365x636363.onmicrosoft.com", // user principal name
            "email": "InsightsTester001@jasoninsightstest.onmicrosoft.com", // user email
            "userStatus": "Blocked", // current status of the user
            "trustStatus": "Trusted", // trust status of the user
            "sensitiveItems": 55, // number of sensitive items associated with the user
            "LastSignIn": "Less than 90 Days", // last sign-in time frame
            "createdOn": "2021-08-24T06:12:55" // account creation date and time
        },
        {
            "displayName": "Internal User Change0406-2", // username
            "loginName": "internaluserchange0406-2@m365x636363.onmicrosoft.com", // user principal name
            "email": "", // user email (empty in this case)
            "userStatus": "Blocked", // current status of the user
            "trustStatus": "Not Trusted", // trust status of the user
            "sensitiveItems": 38, // number of sensitive items associated with the user
            "LastSignIn": "None", // last sign-in time frame
            "createdOn": "2022-04-06T06:40:21" // account creation date and time
        },
        {
            "displayName": "Insights Tester003", // username
            "loginName": "insightstester003_jasoninsightstest.onmicrosoft.com#ext#@m365x636363.onmicrosoft.com", // user principal name
            "email": "InsightsTester003@jasoninsightstest.onmicrosoft.com", // user email
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