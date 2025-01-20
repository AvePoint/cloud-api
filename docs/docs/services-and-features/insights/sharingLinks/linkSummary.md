# Retrieve Sharing Links Summary

This API method (`/insights/sharingLinks/{siteUrl}/summary` navigation property) allows users to retrieve the summary information of sharing links. This method is useful for obtaining an overview of link properties and statuses.

## Permission

The following permission is required to call this API.  
You must register an app through AvePoint Online Services > App registration to authenticate and authorize your access to AvePoint Graph Modern API. For details, refer to [Authentication and Authorization](https://learn.avepoint.com/docs/Use-AvePoint-Graph-Modern-API.html#authentication-and-authorization).

| API     | Permission required | 
|-------------------|---------------|
| `/insights/sharingLinks/{siteUrl}/summary` |  |


## Request

This section outlines the HTTP method and endpoint used to retrieve the summary of specific sharing links. It provides a concise description of the action performed by the API call.

| HTTP Method | Endpoint | Description |
| --- | --- | --- |
| GET | `/insights/sharingLinks/{siteUrl}/summary` | Retrieves the link summaries. |


### Query Parameters

The API supports several query parameters to refine and customize the data retrieval process. These parameters allow users to specify pagination, link types, and other criteria to filter the results effectively.

| Parameter | Description            | Type    | Required? |
|-----------|------------------------|---------|-----------|
| siteUrl | The SharePoint site URL | string |No    |
| linkType  | The type of the link. **32** for Flexible link; **64** for Organization link; **128** for Anonymous link.  | integer | Yes        |
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
| logonName      | The link login name                              | string  |
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

```json
https://graph.avepointonlineservices.com/insights/sharingLinks/https%253A%252F%252Fm365x636363.sharepoint.com%252Fsites%252Fjuly2022publicteam01/summary?linkType=32&pageSize=100&nextLink=1231


## Response Sample

The following is a sample response for retrieving the sharing link summary. Each property in response is explained with a comment for better understanding. 

{
    "values": [
        {
            "id": "2f3a2d78-e02c-8ba4-0b00-fe2009ef1df6,e733b955-2ace-4978-9206-a6e26776dc1d", // The unique identifier for the link summary
            "siteId": "0203bcc8-4eed-4f48-9dc9-fb4f3ed90193", // The site ID where the object is shared
            "selfId": "e3f887e1-395e-42ba-a4fa-d2d0e486ab7d", // The self ID of the object being shared
            "linkId": "e733b955-2ace-4978-9206-a6e26776dc1d", // The unique identifier for the link
            "logonName": "sharinglinks.e3f887e1-395e-42ba-a4fa-d2d0e486ab7d.flexible.e733b955-2ace-4978-9206-a6e26776dc1d", // The login name associated with the link
            "createTime": "2022-05-30T07:20:05.58Z", // The timestamp when the link was created
            "expireTime": null, // The timestamp when the link will expire, if applicable
            "name": "File share 365 Group(1).docx", // The name of the object being shared
            "objectUrl": "https://m365x636363.sharepoint.com/sites/july2022publicteam01/shared documents/general/for share/file share 365 group(1).docx", // The URL of the shared object
            "linkType": "Links for Specific External Users", // The type of the link
            "shareBy": "FNU LNU", // The user who created the link
            "inheritFrom": null, // The parent from which the permission inherits, if applicable
            "inheritType": "Unique", // The inheritance type of the permission
            "shareWith": 1, // The number of users and groups with whom the link is shared
            "linkUrl": "https://m365x636363.sharepoint.com/:w:/s/July2022PublicTeam01/EeGH-ONeObpCpPrS0OSGq30BXkUE0qRbGiVQ_xkav5ARQQ", // The URL of the link
            "permission": "Edit", // The permission level of the link
            "fileType": "File", // The type of the object being shared
            "sensitivityLevel": "Low" // The sensitivity level of the shared object
        },
        {
            "id": "9db028c3-bff5-c445-6056-16a1bd3ee75f,f862aa0f-3103-4c2c-8215-e1dc6c7bbd34",
            "siteId": "0203bcc8-4eed-4f48-9dc9-fb4f3ed90193",
            "selfId": "377847a8-c541-43c7-9e13-ddcb606d5b11",
            "linkId": "f862aa0f-3103-4c2c-8215-e1dc6c7bbd34",
            "logonName": "sharinglinks.377847a8-c541-43c7-9e13-ddcb606d5b11.flexible.f862aa0f-3103-4c2c-8215-e1dc6c7bbd34",
            "createTime": "2022-05-30T08:17:52.001Z",
            "expireTime": null,
            "name": "sensitive info",
            "objectUrl": "https://m365x636363.sharepoint.com/sites/july2022publicteam01/shared documents/general/sensitive info",
            "linkType": "Links for Specific External Users",
            "shareBy": "FNU LNU",
            "inheritFrom": null,
            "inheritType": "Unique",
            "shareWith": 1,
            "linkUrl": "https://m365x636363.sharepoint.com/:f:/s/July2022PublicTeam01/EqhHeDdBxcdDnhPdy2BtWxEB4Qgp4V3PHnzAdR3qeBL-Xw",
            "permission": "Edit",
            "fileType": "Folder",
            "sensitiveLevel": "N/A"
        }
    ],
    "status": 200,
    "message": "",
    "nextLink": "[{\"token\":\"+RID:~SZ5kAO3ZabkBOQAAAAAAAA==#RT:1#TRC:10#ISV:2#IEO:65567#QCF:8#FPC:AgEAAAAIAAG5HYIBwIQA\",\"range\":{\"min\":\"\",\"max\":\"FF\"}}]"
}