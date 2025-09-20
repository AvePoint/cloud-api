# Retrieve Power BI Artifact Details

Use this API to access and retrieve information of your Power BI artifacts.

## Permission

The following permission is required to call the API.
You must register the app through AvePoint Online Services > App registrations to authenticate and authorize your access to AvePoint Graph API.
For details, refer to [Authentication and Authorization](https://learn.avepoint.com/docs/Use-AvePoint-Graph-API.html#authentication-and-authorization).

| API   | Permission |
|-------------------|---------------|
|`/smp/powerplatform/powerbi/artifacts` | enpower.data.read.all | 

## Request

This section provides details on the HTTP method and endpoint used to retrieve general information of your Power BI artifacts.

| Method | Endpoint | Description | 
|--- | --- | --- |
| GET | `/smp/powerplatform/powerbi/artifacts` | Retrieves your Power BI artifacts' information | 

## Query Parameters

The API supports several query parameters to refine and customize the data retrieval process.

| Parameters | Description | Type | Required |
|--- | --- | --- | --- |
| top | The number of artifact records retrieved and returned each page. The default number is 100. You can enter a number from 1 to 1000. | integer | No |
| tenant | The tenant in which data of artifacts are retrieved. By default, artifacts of all tenants are retrieved. | string | No |

## Responses

The API response provides detailed information about the artifacts retrieved. Each artifact in the response includes various attributes that describe its properties and status.

| Elements           | Description                                                           | Type   | 
|--------------------|-----------------------------------------------------------------------|--------|
| artifacts             | A list containing artifacts with detailed information.              | list  | 
| totalCount      | Total number of artifacts retrieved.                   | integer    | 
| nextLink | Reference to the next page of results | string |

**Artifact details**

Each artifact retrieved through the API includes detailed attributes that provide insight into its properties and status. 


| Elements                    | Description                | Type    |
|-----------------------------|----------------------------|---------|
| id                         | The unique identifier of the artifact.                                     | string  |
| name                       | The name of the artifact.                                                  | string  |
| description                | The description of the artifact.                                           | string  |
| tenantId                   | The unique identifier of the tenant where the artifact is hosted.          | string  |
| tenantName                 | The name of the tenant where the artifact is hosted.                       | string  |
| containerId                | The unique identifier of the container where the artifact is held.         | string  |
| container                  | The name of the container where the artifact is held.                      | string  |
| owner                      | The owner of the artifact.                                                 | string  |
| type                       | The type of the artifact.                                                  | string  |
| state                      | The status of the artifact.                                                | string  |
| resourceUrl                | The URL of the artifact resource.                                          | string  |
| hasContextDetail | Indicates if the artifact has context-related details. <br> Valid values: <br> <ul><li> **true** for yes <br> </li><li> **false** for no <br> | boolean |
| workspaceId                | The unique identifier for the workspace that the artifact belongs to.      | string  |
| parentName                 | The name of the artifact parent.                                           | string  |
| parentType                 | The type of the artifact parent.                                           | string  |
| parentState                | The status of the artifact parent.                                         | string  |
| sensitivityLabelId         | The unique identifier for the sensitivity label applied to the artifact.   | string  |
| sensitivityLabelName       | The name of the sensitivity label applied to the artifact.                 | string  |
| createdDateTime            | The date and time when the artifact was created.                           | string  |
| createdBy                  | The user who created the artifact.                                         | string  |
| createdById                | The unique identifier of the user who created the artifact.                | string  |
| modifiedBy                 | The user who last modified the artifact.                                   | string  |
| modifiedDateTime           | The date and time when the artifact was last modified.                     | string  |
| modifiedById               | The unique identifier of the latest user who modified the artifact.        | string  |
| configuredBy               | The user who configured the artifact.                                      | string  |
| configuredById             | The unique identifier of the user who configured the artifact.             | string  |
| isDeleted | Indicates if the artifact was deleted. <br> Valid values: <br> <ul><li> **true** for yes <br> </li><li> **false** for no <br> | boolean |
| numberOfGuests             | The number of guests users who have access to the artifact.                | integer |
| hasRequest | Indicates if EnPower business context has been requested for this artifact. <br> Valid values: <br> <ul><li> **true** for yes <br> </li><li> **false** for no <br> | boolean |
| hasResponse | Indicates if EnPower business context request for this flow has been responded. <br> Valid values: <br> <ul><li> **true** for yes <br> </li><li> **false** for no <br> | boolean |
| lastRenewNotifyTime              | The last time a renewal notification was sent for the Power BI artifact.                       | string |
| numberOfUsers              | The number of users who have access to the artifact.                       | integer |
| lastActivityD7             | The activity count in the last 7 days for the artifact.                    | integer |
| lastActivityTime           | The date and time of the artifact’s latest activity.                       | string  |
| lastRefreshDate            | The date and time of the artifact’s latest refresh.                        | string  |
| numberOfDirectShares       | The number of direct shares of the artifact.                               | integer |
| lastViewedTime             | The last time that the artifact was viewed.                                | string  |
| datasource                 | The data source associated with the artifact.                              | string  |
| numberOfRefreshHistories   | The number of refresh histories of the artifact.                           | integer |
| creatorDisplayName             | The display name of artifact's creator.                       | string |
| creatorDepartment              | The display name of artifact's creator                       | string |
| viewsOfLast7Days              | Artifact view count in last 7 days.                       | integer |
| uniqueViewersOfLast7Days              | Artifact unique viewer count in last 7 days.                       | integer |
| viewsOfLast30Days              | Artifact view count in last 30 days.                       | integer |
| uniqueViewersOfLast30Days              | Artifact unique viewer count in last 30 days.                       | integer |
| viewsOfLast90Days              | Artifact view count in last 90 days.                       | integer |
| uniqueViewersOfLast90Days              | Artifact unique viewer count in last 90 days.                       | integer |

## Request Sample

To use this API, send a GET request to the specified endpoint, including necessary parameters as defined in the references. This will return the relevant object details in a structured format, enabling easy integration with other systems or applications. The following request is an API call to the EnPower environment in the US - East region.

```json
https://graph-us.avepointonlineservices.com/smp/powerplatform/powerbi/artifacts
```

## Response Sample

If the request has been successfully processed, a 200 OK response will be returned along with the requested information displayed in the response body. For more details on the HTTP status code, refer to [HTTP Status Code](https://learn.avepoint.com/docs/Use-AvePoint-Graph-API.html#http-status-code).

```json
{
  "artifacts": [
    {
      "id": "3cf0f5c6-4793-4996-bf39-a8583b2b9b2f", // The unique identifier of the artifact
      "name": "0001", // The name of the artifact
      "description": null, // The description of the artifact
      "tenantId": "", // The unique identifier for the tenant where the artifact is hosted
      "tenantName": "Sample", // The name of the tenant where the artifact is hosted
      "containerId": "", // The unique identifier of the container where the artifact is held
      "container": "Sample-Artifacts", // The name of the container where the artifact is held
      "owner": "", // The owner of the artifact
      "type": "Report", // The type of the artifact
      "state": "Active", // The state of the artifact
      "resourceUrl": "", // The URL of the artifact resource
      "hasContextDetail": false, // Indicates if the artifact has context-related details
      "workspaceId": "", // The unique identifier for the workspace that the artifact belongs to
      "parentName": "Alice_WS_20240716_01_zryfw_edit", // The name of artifact parent
      "parentType": "Workspace", // The type of the artifact parent
      "parentState": "Active", // The status of the artifact parent
      "sensitivityLabelId": "", // The unique identifier for the sensitivity label applied to the artifact
      "sensitivityLabelName": "EntrustEncryptedLabel1", // The name of the sensitivity label applied to the artifact
      "createdDateTime": "2024-12-20 09:29:58", // The date and time when the artifact was created
      "createdBy": "admin@sample.onmicrosoft.com", // The user who created the artifact
      "createdById": "", // The unique identifier of the user who created the artifact
      "modifiedBy": "admin@sample.onmicrosoft.com", // The user who last modified the artifact
      "modifiedDateTime": "2024-12-20 09:29:58", // The date and time when the artifact was last modified
      "modifiedById": "", // The unique identifier of the user who last modified the artifact
      "configuredBy": null, // The user who configured the artifact
      "configuredById": null, // The unique identifier of the user who configured the artifact
      "isDeleted": false, // Indicates if the artifact was deleted
      "numberOfGuests": null, // The number of guests users who have access to the artifact
      "hasRequest": false, // Indicates if EnPower business context has been requested for this artifact
      "hasResponse": false, // Indicates if there is a response for the Power BI artifact
      "lastRenewNotifyTime": "", // The last time a renewal notification was sent for the Power BI artifact
      "numberOfUsers": null, // The number of users who have access to the Power BI artifact
      "lastActivityD7": 0, // The activity count in the last 7 days for the Power BI artifact
      "lastActivityTime": "", // The date and time when the Power BI artifact had its last activity
      "lastRefreshDate": "", // The date and time when the Power BI artifact was last refreshed
      "numberOfDirectShares": null, // The number of direct shares for the Power BI artifact
      "lastViewedTime": "", // The last time the Power BI artifact was viewed
      "datasource": null, // The data source associated with the Power BI artifact
      "creatorDisplayName": "" // Display name of artifact creator
      "creatorDepartment": "" // Department of artifact creator
      "viewsOfLast7Days": 0 // View count in last 7 days
      "uniqueViewersOfLast7Days": 0 // Viewer count in last 7 days
      "viewsOfLast30Days": 0 // View count in last 30 days
      "uniqueViewersOfLast30Days": 0 // Viewer count in last 30 days
      "viewsOfLast90Days": 0 // View count in last 90 days
      "uniqueViewersOfLast90Days": 0 // Viewer count in last 90 days
    }
  ],
  "totalCount": 1,
  "nextLink": ""
}