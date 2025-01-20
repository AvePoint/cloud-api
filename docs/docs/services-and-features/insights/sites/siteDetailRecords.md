# Retrieve Site Detail Records

This API method (`/insights/sites/{siteId}/detailRecords` navigation property) allows users to retrieve detailed records for a specific SharePoint site. This method is useful for obtaining comprehensive information about the site content's properties and activities.

[Detail record? site content? ]: #

## Permission

The following permission is required to call this API.  
You must register an app through AvePoint Online Services > App registration to authenticate and authorize your access to AvePoint Graph Modern API. For details, refer to [Authentication and Authorization](https://learn.avepoint.com/docs/Use-AvePoint-Graph-Modern-API.html#authentication-and-authorization).

| API     | Permission required | 
|-------------------|---------------|
| `/insights/sites/{siteId}/detailRecords` | insights.graph.readwrite.all  |

## Request

This section outlines the HTTP method and endpoint used to retrieve the detail records within a site. It provides a concise description of the action performed by the API call. 

| HTTP Method | Endpoint | Description |
| --- | --- | --- |
| GET | `/insights/sites/{siteId}/detailRecords` | Retrieves the detail records within a site. |



## Query Parameters

The API supports several query parameters to refine and customize the data retrieval process. These parameters allow users to specify the site ID to filter the results effectively.

| Parameter | Description | Type    | Required? |
|-----------|-------------|---------|-----------|
| siteId    | SharePoint site ID | string  | Yes       |
| nextLink  | Sets the number of results for one page. 100 results on one page at most. | string  | No        |

## Responses

The API response provides detailed information about the site detail records retrieved. Each record in the response includes various attributes that describe its properties and status.

| Elements | Description                                      | Type    |
|----------|--------------------------------------------------|---------|
| status   | The HTTP response status code                    | integer |
| message  | The error message                                | string  |
| nextLink | The token to be used to get the remaining results of this request | string  |
| values   | A list of detail records in the site          | array   |

**Detail Record**

| Property          | Description                                                                 |
|-------------------|-----------------------------------------------------------------------------|
| id                | Unique identifier for the object                                             |
| name              | Name of the object                                                            |
| location          | URL where the object is stored                                                |
| objectType        | Type of object                                     |
| createdBy         | User who created the object                                                   |
| module            | Module or application where the object belongs                                |
| inheritance       | Indicates whether the object inherits permissions from its parent                  |
| siteName          | Name of the SharePoint site where the object is stored                        |
| sensitivityLevel  | Sensitivity level of the object                                               |
| exposureLevel     | Exposure level of the object                                                  |
| scannedTime       | Timestamp when the object was last scanned                                    |
| createdTime       | Timestamp when the object was created                                         |
| modifiedTime      | Timestamp when the object was last modified                                   |
| channelName       | Name of the Microsoft Teams channel where the object is shared                |
| riskLevel         | Risk level associated with the object                                         |
| privacy           | Privacy setting of the object                                                 |
| sensitiveInfoType | Types of sensitive information contained in the object                        |
| sensitivityLabel  | Sensitivity label applied to the object                                       |
| tagName           | Tag associated with the object                                                |
| retentionLabel    | Retention label applied to the object                                         |
| creatorEmail      | Email of the user who created the object                                      |


## Request Sample

To use this API, send a GET request to the specified endpoint, including necessary parameters as defined in the references. This will return the relevant site detail records in a structured format, enabling easy integration with other systems or applications.

```json
https://graph.avepointonlineservices.com/insights/sites/0d6c1549-cd2d-4dd2-94b5-28df6da1f7e2/detailrecords?nextLink=1312312
```

## Response Sample

The following response returns a list of detail records in the queried site with their properties and statuses in a structured format.  

```json
{
  "values": [
    {
      "id": "b68d027a-7583-a089-479d-f15f68739762", // Unique identifier for the object
      "name": "good Or bad.xlsx", // Name of the object
      "location": "https://alitamarkettest.sharepoint.com/sites/mibeautifulteams-misharedchannel/shared documents/good or bad.xlsx", // URL where the object is stored
      "objectType": "object", // Type of object, in this case, a object
      "createdBy": "alita adminIstratorRename", // User who created the object
      "module": "Microsoft Teams", // Module or application where the object is used
      "inheritance": "Yes", // Indicates if the object inherits permissions from its parent
      "siteName": "Mi beautiful Teams-Mi shared channel", // Name of the SharePoint site where the object is stored
      "sensitivityLevel": "Low", // Sensitivity level of the object
      "exposureLevel": "Low", // Exposure level of the object
      "scannedTime": "2024-11-11T02:46:58Z", // Timestamp when the object was last scanned
      "createdTime": "2024-02-22T02:28:40Z", // Timestamp when the object was created
      "modifiedTime": "2024-02-22T02:28:40Z", // Timestamp when the object was last modified
      "channelName": "Mi shared channel", // Name of the Microsoft Teams channel where the object is shared
      "riskLevel": "Low", // Risk level associated with the object
      "privacy": "Private", // Privacy setting of the object
      "sensitiveInfoType": [
        "Mi CR 2" // Types of sensitive information contained in the object
      ],
      "sensitivityLabel": "Jason object Only Label", // Sensitivity label applied to the object
      "tagName": "", // Tag associated with the object
      "retentionLabel": null, // Retention label applied to the object
      "creatorEmail": "admin@alitamarkettest.onmicrosoft.com" // Email of the user who created the object
    },
    {
      "id": "3e471efc-0417-74fa-d5cc-b2bd3552bb0f", // Unique identifier for the object
      "name": "miley PP.pptx", // Name of the object
      "location": "https://alitamarkettest.sharepoint.com/sites/mibeautifulteams-misharedchannel/shared documents/miley pp.pptx", // URL where the object is stored
      "objectType": "object", // Type of object, in this case, a object
      "createdBy": "alita adminIstratorRename", // User who created the object
      "module": "Microsoft Teams", // Module or application where the object is used
      "inheritance": "No", // Indicates if the object inherits permissions from its parent
      "siteName": "Mi beautiful Teams-Mi shared channel", // Name of the SharePoint site where the object is stored
      "sensitivityLevel": "N/A", // Sensitivity level of the object
      "exposureLevel": "Medium", // Exposure level of the object
      "scannedTime": "2024-11-01T09:22:18Z", // Timestamp when the object was last scanned
      "createdTime": "2024-04-03T06:57:39Z", // Timestamp when the object was created
      "modifiedTime": "", // Timestamp when the object was last modified
      "channelName": "Mi shared channel", // Name of the Microsoft Teams channel where the object is shared
      "riskLevel": "N/A", // Risk level associated with the object
      "privacy": "Private", // Privacy setting of the object
      "sensitiveInfoType": [], // Types of sensitive information contained in the object
      "sensitivityLabel": null, // Sensitivity label applied to the object
      "tagName": "", // Tag associated with the object
      "retentionLabel": "", // Retention label applied to the object
      "creatorEmail": "admin@alitamarkettest.onmicrosoft.com" // Email of the user who created the object
    }
  ],
  "status": 200, // HTTP status code indicating the operation is successful.
  "message": "",
  "nextLink": null
}
```