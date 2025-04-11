# Retrieve User Permissions

Retrieve the permission-related information for specific users. By invoking the `/insights/users/access` endpoint, you can retrieve the permissions of specific users. This method is useful for obtaining detailed insights into the permissions granted to users. 

## Permission 

The following permission is required to call this API.  
You must register an app through AvePoint Online Services > App registration to authenticate and authorize your access to AvePoint Graph API. For details, refer to [Authentication and Authorization](https://learn.avepoint.com/docs/Use-AvePoint-Graph-API.html#authentication-and-authorization).

| API     | Permission required | 
|-------------------|---------------|
| `/insights/users/access` | insights.graph.readwrite.all |

## Request 

This section outlines the HTTP method and endpoint used to retrieve user permissions. It provides a concise description of the action performed by the API call. 

| HTTP Method | Endpoint | Description |
| --- | --- | --- |
| GET | `/insights/users/access` | Retrieves the user permissions. |


## Query Parameters

The API supports several query parameters to refine and customize the data retrieval process. These parameters allow users to specify the site URLs, email addresses, and next link to filter the results effectively.


| Parameter  | Description                                                                 | Type   | Required? |
|------------|-----------------------------------------------------------------------------|--------|-----------|
| siteUrls | Sets the URLs of site collections for which you want to get the permission related information. | list  | No        |
| emails | Sets the email addresses or logonName of users for which you want to export the permission report. | list  | Yes        |
| nextLink | Sets whether to get the remaining results of a request of which the results are more than 100. | string | No        |


[we have logonName Loginname and principal name? which one is it?]: # 

## Responses

The API response provides detailed information about the user permissions retrieved. Each user permission in the response includes various attributes that describe its properties and status.

| Elements | Description                                      | Type    |
|----------|--------------------------------------------------|---------|
| status   | The HTTP response status code                    | integer |
| message  | The error message                                | string  |
| nextLink | The token to be used to get the remaining results of this request | string  |
| values   | A list of user permission objects               | list   |

**User permission**

| Property           | Description            | Type    |
|--------------------|------------------|---------|
| module             | The module where the object is located.               | string  |
| siteName           | The name of the site where the object is stored.     | string  |
| name               | The name of the object.                           | string  |
| location           | The URL where the object is located.             | string  |
| objectType         | The type of object.             | string  |
| inheritType        | Indicates whether the permissions are unique to this object.      | string  |
| permission         | The level of permission granted.                    | string  |
| sensitivityLevel   | The sensitivity level of the object.               | string  |
| sensitiveInfoType  | Types of sensitive information contained in the file. |string  |
| isDirect           | Indicates whether the permission is direct or inherited.               | boolean |
| sensitivityLabel   | The sensitivity label applied to the object          | string  |
| inheritedFrom      | The source from which the permissions are inherited.                     | string  |

## Request Sample

To use this API, send a `GET` request to the specified endpoint, including necessary parameters as defined. This will return the relevant user permissions in a structured format, enabling easy integration with other systems or applications. The following request is an API call to the Insights for Microsoft 365 environment in the US - East region.

```json
https://graph-us.avepointonlineservices.com/insights/users/access?siteUrls=https%3A%2F%2Fm********.sharepoint.com%2Fsites%2Fj*******m01&siteUrls=https%3A%2F%2Fm*****.sharepoint.com%2Fsites%2Fjuly2022publict****&emails=insights****001_j***insightstest.onmicrosoft.com%23ext%23%40m******.onmicrosoft.com&emails=insights******003_j****insightstest.onmicrosoft.com%23ext%23%40m********.onmicrosoft.com
```

## Response Sample  

The following is a sample response for this API method, which includes the permission details of users. Each property in response is explained with a comment for better understanding.

```json
{
    "values": [
        {
            "module": "Microsoft Teams",  // The module where the file is located.
            "siteName": "AutoC************Team",  // The name of the site where the file is stored.
            "name": "U.S. Personally Identifiable Information (PII) Data-High.docx",  // The name of the file.
            "location": "https://m365x******.sharepoint.com/sites/autocreated********team/shared documents/general/u.s. personally identifiable information (pii) data-high.docx",  // The URL where the file is located. 
            "objectType": "File",  // The type of object, which is a file in this case.
            "inheritType": "Unique",  // Indicates that the permissions are unique to this file.
            "permission": "Contribute",  // The level of permission granted.
            "sensitivityLevel": "High",  // The sensitivity level of the file.
            "sensitiveInfoType": "U.S. Individual Taxpayer Identification Number (ITIN), U.S. Social Security Number (SSN), U.S. / U.K. Passport Number",  // Types of sensitive information contained in the file.
            "isDirect": false,  // Indicates whether the permission is direct or inherited.
            "sensitivityLabel": "",  // The sensitivity label applied to the file, which is empty in this case.
            "inheritedFrom": "sharinglinks.2nnn3-5nnn-46nn7-bc32-8nnnnnnnnn.flexible.8nnnnnnnnn-c62b0-c62b0-c62b0-c62b0"  // The source from which the permissions are inherited.
        }
    ],
    "status": 200,  // The status code of the response, indicating success.
    "message": "",  // Any message included in the response, which is empty in this case.
    "nextLink": "fBMkYtVSN7/fBMGW+IDEbl3n2kYtVSN772/fBMGW+IDEbl3n2kYtVSN7fBMGW+IDEbl3n2kYtVSN7KyI3/0SeNe2gz8WjwRAJpKFfBMGW+IDEbl3n2kYtVSN7Fyx+eX/zgxCVPhsSowunsQcfDfBMGW+IDEbl3n2kYtVSN7LSZ76fBMGW+IDEbl3n2kYtVSN7KYyGQ=="  // The next link for pagination, if more data is available.
}