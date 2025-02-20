# Retrieve Sharing Links Summary

This API method (`/insights/sharingLinks/{siteUrl}/summary` navigation property) allows users to retrieve the summary information of sharing links. This method is useful for obtaining an overview of link properties and statuses.

## Permission

The following permission is required to call this API.  
You must register an app through AvePoint Online Services > App registration to authenticate and authorize your access to AvePoint Graph API. For details, refer to [Authentication and Authorization](https://learn.avepoint.com/docs/Use-AvePoint-Graph-API.html#authentication-and-authorization).

| API     | Permission required | 
|-------------------|---------------|
| `/insights/sharingLinks/{siteUrl}/summary` | insights.graph.readwrite.all |


## Request

This section outlines the HTTP method and endpoint used to retrieve the summary of specific sharing links. It provides a concise description of the action performed by the API call.

| HTTP Method | Endpoint | Description |
| --- | --- | --- |
| GET | `/insights/sharingLinks/{siteUrl}/summary` | Retrieves the link summaries. |


## Query Parameters

The API supports several query parameters to refine and customize the data retrieval process. These parameters allow users to specify pagination, link types, site URL, and other criteria to filter the results effectively.

| Parameter | Description            | Type    | Required? |
|-----------|------------------------|---------|-----------|
| siteUrl | The SharePoint site URL | string |Yes    |
| linkType  | The type of the link. <ul><li>**32** for Flexible link</li><li> **64** for Organization link</li><li> **128** for Anonymous link</li>  | integer | Yes        |
| pageSize  | The number of items per page | integer | No        |
| nextLink  | The token for the next page | string  | No        |

## Responses

The API response provides detailed information about the sharing links retrieved. Each link in the response includes various attributes that describe its properties and status.

| Elements       | Description                                      | Type    |
|----------------|--------------------------------------------------|---------|
| values | A list of sharing links  |list|
| status| the HTTP status code | integer |
| message | error message | string |
| nextLink | The token for the next page | string  | 


**link Summary**

| Elements       | Description                                      | Type    |
|----------------|--------------------------------------------------|---------|
| id             | The ID in the link summary                       | string  |
| siteId         | The site ID in which the object is shared by the link | string  |
| selfId         | The selfID of the object which is shared by the link | string  |
| linkId         | The link ID                                      | string  |
| logonName      | The link logonName contains the linkId and the object uniqueId.                              | string  |
| createTime     | The time when the link is created                | string  |
| expireTime     | The time when the link is expired                | string  |
| name           | The object name that is shared via the link      | string  |
| objectUrl      | The object URL that is shared via the link       | string  |
| linkType       | The link type                                    | string  |
| shareBy        | The user who created the link                    | string  |
| inheritFrom    | The parent from which the permission inherits    | string  |
| inheritType    | The status whether the permission is inherited   | string  |
| shareWith      | The number of users and groups with whom the link is shared | integer |
| linkUrl        | The link URL                                     | string  |
| permission     | The permission with which the link is shared     | string  |
| fileType       | The type of the object shared via the link       | string  |
| sensitivityLevel | The sensitivity level of the object shared via the link | string  |


[blockDownload is displayed in the sample of http://10.1.49.59:23456/showdoc/web/#/5/604, but not showing in the table]: # 
 
## Request Sample

To use this API, send a `GET` request to the specified endpoint, including necessary parameters as defined. This will return the relevant link summary details in a structured format, enabling easy integration with other systems or applications. The following request is an API call to the Insights for Microsoft 365 environment in the US - East region.

```json
https://graph-us.avepointonlineservices.com/insights/sharingLinks/https********Fm365x636363.sharepoint.com%252Fsites%252Fjuly2022******/summary?linkType=32&pageSize=100&nextLink=1231
```

## Response Sample

The following is a sample response for retrieving the sharing link summary. Each property in response is explained with a comment for better understanding. 

```json
{
    "values": [
        {
            "id": "e02ce02c-e02c-e02c-e02c-e02ce02ce02c,92069206-9206-9206-9206-920692069206", // The unique identifier for the link summary
            "siteId": "9dc99dc9-9dc9-9dc9-9dc9-9dc99dc99dc9", // The site ID where the object is shared
            "selfId": "a4faa4fa-a4fa-a4fa-a4fa-a4faa4faa4fa", // The self ID of the object being shared
            "linkId": "49784978-4978-4978-4978-497849784978", // The unique identifier for the link
            "logonName": "sharinglinks.49784978-4978-4978-4978-497849784978.flexible.2ace2ace-2ace-2ace-2ace-2ace2ace2ace", // The login name associated with the link
            "createTime": "2022-05-30T07:20:05.58Z", // The timestamp when the link was created
            "expireTime": null, // The timestamp when the link will expire, if applicable
            "name": "File share 365 Group-Word.docx", // The name of the object being shared
            "objectUrl": "https://m365x******.sharepoint.com/sites/*******publicteam1/shared documents/general/for share/File share 365 Group-Word.docx", // The URL of the shared object
            "linkType": "Links for Specific External Users", // The type of the link
            "shareBy": "FNU LNU", // The user who created the link
            "inheritFrom": null, // The parent from which the permission inherits, if applicable
            "inheritType": "Unique", // The inheritance type of the permission
            "shareWith": 1, // The number of users and groups with whom the link is shared
            "linkUrl": "https://m365x********.sharepoint.com/:w:/s/********PublicTeam1/EeGH-EeGHEeGHEeGHEeGHEeGHEeGHEeGHEeGH", // The URL of the link
            "permission": "Edit", // The permission level of the link
            "fileType": "File", // The type of the object being shared
            "sensitivityLevel": "Low" // The sensitivity level of the shared object
        },
        {
            "id": "60566056-6056-6056-6056-605660566056,31033103-3103-3103-3103-310331033103",
            "siteId": "4eed4eed-4eed-4eed-4eed-4eed4eed4eed4eed",
            "selfId": "43c743c7-43c7-43c7-43c7-43c743c743c7",
            "linkId": "82158215-8215-8215-8215-8215821582158215",
            "logonName": "sharinglinks.82158215-8215-8215-8215-821582158215.flexible.31033103-3103-3103-3103-3103310331033103",
            "createTime": "2022-05-30T08:17:52.001Z",
            "expireTime": null,
            "name": "sensitive info",
            "objectUrl": "https://m365x*****
            *****.sharepoint.com/sites/******publicteam1/shared documents/general/sensitive info",
            "linkType": "Links for Specific External Users",
            "shareBy": "FNU LNU",
            "inheritFrom": null,
            "inheritType": "Unique",
            "shareWith": 1,
            "linkUrl": "https://m365x******.sharepoint.com/:f:/s/*******PublicTeam1/EqhHEqhHEqhHEqhHEqhHEqhHEqhHEqhHEqhH-Xw",
            "permission": "Edit",
            "fileType": "Folder",
            "sensitiveLevel": "N/A"
        }
    ],
    "status": 200,
    "message": "",
    "nextLink": "[{\"token\":\"+RID:~EqhHEqhHEqhH==#RT:1#TRC:10#ISV:2#IEO:65567#QCF:8#FPC:AgEEqhHEqhHEqhHQA\",\"range\":{\"min\":\"\",\"max\":\"FF\"}}]"
}