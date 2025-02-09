# Retrieve Site Permissions

This API method (`/insights/sites/permission` navigation property) allows users to retrieve permission-related information of specific site collections. This method is useful for obtaining detailed insights into the permissions granted to site collections.

## Permission

The following permission is required to call this API.  
You must register an app through AvePoint Online Services > App registration to authenticate and authorize your access to AvePoint Graph Modern API. For details, refer to [Authentication and Authorization](https://learn.avepoint.com/docs/Use-AvePoint-Graph-Modern-API.html#authentication-and-authorization).

| API     | Permission required | 
|-------------------|---------------|
| `/insights/sites/permission` | insights.graph.readwrite.all |

## Request

This section outlines the HTTP method and endpoint used to retrieve site permissions. It provides a concise description of the action performed by the API call. 

| HTTP Method | Endpoint | Description |
| --- | --- | --- |
| GET | `/insights/sites/permission` | Retrieves the site permissions. |


### Query Parameters

The API supports several query parameters to refine and customize the data retrieval process. These parameters allow users to specify the site URLs, page size, and next link to filter the results effectively.

| Parameter | Description | Type    | Required? |
|-----------|-------------|---------|-----------|
| siteUrls  | Sets the URLs of site collections for which you want to get the permission related information | list   | Yes       |
| pageSize  | Sets the number of results for one page. 100 results on one page at most | integer | No        |
| nextLink  | Sets whether to get the remaining results of a request of which the results are more than 100 | string  | No        |

## Responses

The API response provides detailed information about the site permissions retrieved. Each site permission in the response includes various attributes that describe its properties and status.

| Elements  | Description | Type    |
|-----------|-------------|---------|
| status    | The HTTP response status code | integer |
| message   | The error message | string  |
| nextLink  | The token to be used to get the remaining results of this request | string  |
| values    | A list of site permission objects | list  |


**Site Permission**

| Parameter           | Description                                                | Type    |
|---------------------|------------------------------------------------------------|---------|
| module              | The data source from which the permission information is retrieved   | string  |
| name                | The name of the permission                                 | string  |
| url                 | The sharing link to which the permission applies      | string  |
| objectType          | The object type                                            | string  |
| principalName       | The name of the user or group that has the permission      | string  |
| email               | The email address of the user/group                        | string  |
| principalType       | The type of the user or group                              | string  |
| permission          | The level of permission granted                            | string  |
| numberOfMembers     | The number of members in the group, if principalType is a group | integer     |
| isExternalUser      | Indicates whether the user is an external user.                   | boolean    |
| inheritType         | The status of permission inheritance from its parent | string  |
| linkGivingAccessTo  | The members who are granted access via sharing link         | string  |


**Request Sample**

To use this API, send a `GET` request to the specified endpoint, including necessary parameters as defined in the references. This will return the relevant permission details in a structured format, enabling easy integration with other systems or applications. The following request is an API call to the Insights for Microsoft 365 environment in the US - East region.

```json
https://graph-us.avepointonlineservices.com/insights/sites/permission?siteUrls=https%3A%2F%2Finsights*****.sharepoint.com%2Fsites%2F365groupchangeteams01&pageSize=100&nextLink=1231
```

## Response Sample

The following is a sample response for retrieving the site permissions. Each property in response is explained with a comment for better understanding. 

```json
{
    "values": [
        {
            "module": "Microsoft Teams", // The data source from which the permission information is retrieved
            "name": "365Group***team1", // The name of the permission
            "url": "https://insights****.sharepoint.com/sites/365groupchange****", // The URL of the object to which the permission applies
            "objectType": "Site Collection", // The type of the object (e.g., file, folder, site, site collection)
            "principalName": "365Group****** Owners", // The name of the user or group that has the permission
            "email": "", // The email address of the user or group
            "principalType": "SharePoint Group", // The type of the user or group
            "permission": "Full Control", // The level of permission granted 
            "numberOfMembers": 0, // The number of members in the group, if the principal is a group
            "isExternalUser": false, // Indicates whether the user is an external user (true/false)
            "inheritType": "Unique", // Indicates whether the object inherits permissions from its parent
            "linkGivingAccessTo": null // The members who are granted access via a sharing link
        }
    ],
    "status": 200, // The HTTP status code of the response
    "message": "", // The message accompanying the response, if any
    "nextLink": "I5xQOaI5xQOaI5xQOaI5xQOaI5xQOaI5xQOaI5xQOaI5xQOaI5xQOaI5xQOaI5xQOaI5xQOaI5xQOaI5xQOaI5xQOaI5xQOaI5xQOaI5xQOaI5xQOaI5xQOaI5xQOaI5xQOaI5xQOaI5xQOaI5xQOaI5xQOaI5xQOaI5xQOaI5xQOaI5xQOaI5xQOaI5xQOaI5xQOaI5xQOaI5xQOaI5xQOaI5xQOa" // The token for the next page of results, if applicable
}
```