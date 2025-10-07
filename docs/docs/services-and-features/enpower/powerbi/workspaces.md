# Retrieve Power BI Workspace Details

Use this API to access and retrieve information of your Power BI workspaces.

## Permission

The following permission is required to call the API.
You must register the app through AvePoint Online Services > App registrations to authenticate and authorize your access to AvePoint Graph API.
For details, refer to [Authentication and Authorization](https://learn.avepoint.com/docs/Use-AvePoint-Graph-API.html#authentication-and-authorization).

| API   | Permission |
|-------------------|---------------|
|`/smp/powerplatform/powerbi/workspaces` | enpower.data.read.all | 

## Request

This section provides details on the HTTP method and endpoint used to retrieve general information of your Power BI workspaces.

| Method | Endpoint | Description | 
|--- | --- | --- |
| GET | `/smp/powerplatform/powerbi/workspaces` | Retrieves your Power BI workspaces' information | 

## Query Parameters

The API supports several query parameters to refine and customize the data retrieval process.

| Parameters | Description | Type | Required |
|--- | --- | --- | --- |
| top | The number of workspace records retrieved and returned each page. The default number is 100. You can enter a number from 1 to 1000. | integer | No |
| tenant | The tenant in which data of workspaces are retrieved. By default, workspaces of all tenants are retrieved. | string | No |

## Responses

The API response provides detailed information about the Power BI workspaces retrieved. Each workspace in the response includes various attributes that describe its properties and status.

| Elements           | Description                                                           | Type   | 
|--------------------|-----------------------------------------------------------------------|--------|
| workspaces             | A list containing workspaces with detailed information. For the detailed list of responses, refer to [Workspace Details](#workspace-details).              | list  | 
| totalCount      | Total number of apps retrieved.                   | integer    | 
| nextLink | Reference to the next page of results | string |

### Workspace Details

| Response                    | Description                                                                 | Type    |
|-----------------------------|-----------------------------------------------------------------------------|---------|
| id                          | The unique identifier for the Power BI workspace.                           | string  |
| name                        | The name of the Power BI workspace.                                         | string  |
| description                 | A brief description of the Power BI workspace.                              | string  |
| tenantId                    | The unique identifier for the tenant where the workspace is hosted.         | string  |
| tenantName                  | The name of the tenant where the workspace is hosted.                       | string  |
| containerId                 | The unique identifier for the container that holds the workspace.           | string  |
| container                   | The name of the container that holds the workspace.                         | string  |
| type                        | The workspace type.                                                         | string  |
| state                       | The current workspace status.                                               | string  |
| capacityId                  | The unique identifier for the capacity associated with the workspace.       | string  |
| capacityName                | The name of the capacity associated with the workspace.                     | string  |
| capacitySkuTier             | The SKU tier of the associated capacity.                                    | string  |
| isOnDedicatedCapacity | Indicates whether the workspace is on dedicated capacity. <br> Valid values: <br> <ul><li> **true** for yes <br> </li><li> **false** for no <br> | boolean |
| upgradeStatus               | The current upgrade status of the workspace.                                | string  |
| resourceUrl                 | The URL of workspace resources.                                             | string  |
| hasContextDetail | Indicates if context-related details are enabled for the workspace. <br> Valid values: <br> <ul><li> **true** for yes <br> </li><li> **false** for no <br> | boolean |
| createdDateTime             | The date and time when the workspace was created.                           | string  |
| contacts                    | The contact information associated with the workspace.                      | string  |
| sharePointStorage           | The SharePoint storage associated with the workspace.                       | string  |
| isServiceApp | Indicates if the workspace is a service application. <br> Valid values: <br> <ul><li> **true** for yes <br> </li><li> **false** for no <br> | boolean |
| allowContributorUpdateApp | Indicates if contributors are allowed to update apps in the workspace. <br> Valid values: <br> <ul><li> **true** for yes <br> </li><li> **false** for no <br> | boolean |
| azureConnection             | The Azure connection used for the workspace.                                | string  |
| numberOfReports             | The number of reports in the workspace.                                     | integer |
| numberOfPaginatedReports    | The number of paginated reports in the workspace.                           | integer |
| numberOfDashboards          | The number of dashboards in the workspace.                                  | integer |
| numberOfDataFlows           | The number of dataflows in the workspace.                                   | integer |
| numberOfDataSets            | The number of datasets in the workspace.                                    | integer |
| numberOfDatamarts           | The number of datamarts in the workspace.                                   | integer |
| numberOfAdmins              | The number of administrators in the workspace.                              | integer |
| numberOfMembers             | The number of members in the workspace.                                     | integer |
| numberOfContributors        | The number of contributors in the workspace.                                | integer |
| numberOfViewers             | The number of viewers in the workspace.                                     | integer |
| isDeleted | Indicates if the workspace has been deleted. <br> Valid values: <br> <ul><li> **true** for yes <br> </li><li> **false** for no <br> | boolean |
| numberOfGuests              | The number of guests in the workspace.                                      | integer |
| hasRequest | Indicates if EnPower business context has been requested for this workspace. <br> Valid values: <br> <ul><li> **true** for yes <br> </li><li> **false** for no <br> | boolean |
| hasResponse | Indicates if EnPower business context request for this workspace has been responded. <br> Valid values: <br> <ul><li> **true** for yes <br> </li><li> **false** for no <br> | boolean |
| numberOfUsers               | The number of users in the workspace.                                       | integer |
| lastActivityD7              | The number of activities in the last 7 days in the workspace.               | integer |
| lastActivityTime            | The date and time when the last activity occurred in the workspace.         | string  |
| numberOfScorecards          | The number of scorecards in the workspace.                                  | integer |
| primaryContact              | The Cloud Governance primary contact of the workspace. For the detailed user properties, refer to [User Details](#user-details).                     | object  |
| secondaryContact            | The Cloud Governance secondary contact of the workspace. For the detailed user properties, refer to [User Details](#user-details).                   | object  |
| phase                       | The current phase of the workspace in Cloud Governance.                     | string  |
| phaseAssignees              | The individuals assigned to the current phase of the workspace in Cloud Governance. For the detailed user properties, refer to [User Details](#user-details). | object  |
| lastRenewalTime             | The last time when the workspace was renewed.                               | string  |
| phaseStartTime              | The renewal start time of the workspace.                |  string |
| renewalDueDate              | The renewal due date of the workspace.                |  string |
| nextRenewalDate              | The next renewal date of the workspace.                |  string |
| lastRenewalBy               | The latest user who renewed the workspace. For the detailed user properties, refer to [User Details](#user-details).                                 | object  |
| renewProfileApplied | Indicates if a renewal profile has been applied to the workspace. <br> Valid values: <br> <ul><li> **true** for yes <br> </li><li> **false** for no <br> | boolean |
| isRegistered | Indicates if the workspace has been imported to Cloud Governance. <br> Valid values: <br> <ul><li> **true** for yes <br> </li><li> **false** for no <br> | boolean |
| renewProfile                | The Cloud Governance renewal profile applied to the workspace. For the detailed profile properties, refer to [Cloud Governance Profile Details](#cloud-governance-profile-details).                              | object  |
| metadata                    | The Cloud Governance metadata associated with the workspace. For the detailed metadata properties, refer to [Cloud Governance Metadata Details](#cloud-governance-metadata-details).                | list    |
| electionProfileApplied | Indicates if a contact election profile has been applied to the workspace. <br> Valid values: <br> <ul><li> **true** for yes <br> </li><li> **false** for no <br> | boolean |
| electionProfile             | The Cloud Governance contact election profile applied to the workspace. For the detailed profile properties, refer to [Cloud Governance Profile Details](#cloud-governance-profile-details).                             | object  |
| claimStatus                 | The Cloud Governance claim status of the workspace.                         | string  |
| datasource                  | The data source of the workspace.                                           | string  |

### User Details

| Elements                | Description                                                                 | Type    |
|-------------------------|-----------------------------------------------------------------------------|---------|
| id                      | The unique identifier for the user.                                         | string  |
| displayName             | The display name associated with the user.                                  | string  |
| email                   | The email address associated with the user.                                 | string  |
| tenantId                | The unique identifier for the tenant where the user is hosted.              | string  |
| userPrincipalName       | The user principal name of the user.                                        | string  |
| objectId                | The unique object ID for the user.                                          | string  |
| jobTitle                | The job title associated with the user.                                     | string  |
| department              | The department associated with the user.                                    | string  |
| companyName             | The company name associated with the user.                                  | string  |
| office                  | The office location associated with the user.                               | string  |
| city                    | The city associated with the user.                                          | string  |
| countryOrRegion         | The country or region associated with the user.                             | string  |

### Cloud Governance Metadata Details

| Elements                | Description                                                                 | Type    |
|-------------------------|-----------------------------------------------------------------------------|---------|
| metadataType | The type of metadata. <br> Valid values: <br> <ul><li> **0** for none <br> </li><li> **1** for single line of text <br></li><li> **2** for multiple lines of text <br></li><li> **3** for yes/no <br></li><li> **4** for choice <br></li><li> **5** for people picker filter profile <br></li><li> **6** for managed metadata <br></li><li> **7** for hyperlink <br></li><li> **8** for user profile property <br></li><li> **9** for Microsoft Entra property <br></li><li> **10** for lookup </li></ul> | integer | 
| value                   | The metadata value.                                                         | object  |
| id                      | The unique identifier for the metadata.                                     | string  |
| name                    | The metadata name.                                                          | string  |
| metadataSetting         | The custom metadata.                                                        | object  |

### Cloud Governance Profile Details

| Elements                | Description                                                                 | Type    |
|-------------------------|-----------------------------------------------------------------------------|---------|
| id                      | The unique identifier for the profile.                                      | string  |
| name                    | The name for the profile.                                                   | string  |

## Request Sample

To use this API, send a GET request to the specified endpoint, including necessary parameters as defined in the references. This will return the relevant object details in a structured format, enabling easy integration with other systems or applications. The following request is an API call to the EnPower environment in the US - East region.

```json
https://graph-us.avepointonlineservices.com/smp/powerplatform/powerbi/workspaces
```

## Response Sample

If the request has been successfully processed, a 200 OK response will be returned along with the requested information displayed in the response body. For more details on the HTTP status code, refer to [HTTP Status Code](https://learn.avepoint.com/docs/Use-AvePoint-Graph-API.html#http-status-code).

```json
{
  "workspaces": [
    {
      "id": "83985b94-9fd0-4614-****-aeef875fd6e0", // The unique identifier of the Power BI workspace
      "name": "Sample Workspace", // The name of the Power BI workspace
      "description": null, // A brief description of the Power BI workspace
      "tenantId": "", // The unique identifier for the tenant where the workspace is hosted
      "tenantName": "Sample", // The name of the tenant where the workspace is hosted
      "containerId": "", // The unique identifier for the container that holds the workspace
      "container": "Sample-Workspaces", // The name of the container that holds the workspace
      "type": "Workspace", // The workspace type
      "state": "Active", // The current workspace status
      "capacityId": null, // The unique identifier for the capacity associated with the workspace
      "capacityName": null, // The name of the capacity associated with the workspace
      "capacitySkuTier": null, // The SKU tier of the associated capacity
      "isOnDedicatedCapacity": false, // Indicates whether the workspace is on dedicated capacity
      "upgradeStatus": "N/A", // The current upgrade status of the workspace
      "resourceUrl": "", // The URL of the workspace resources
      "hasContextDetail": false, // Indicates if context-related details are enabled for the workspace
      "createdDateTime": "", // The date and time when the workspace was created
      "contacts": null, // The contact information associated with the workspace
      "sharePointStorage": null, // The SharePoint storage associated with the workspace
      "isServiceApp": null, // Indicates if the workspace is a service application
      "allowContributorUpdateApp": null, // Indicates if contributors are allowed to update apps in the workspace
      "azureConnection": null, // The Azure connection used for the workspace
      "numberOfReports": 0, // The number of reports in the workspace
      "numberOfPaginatedReports": 0, // The number of paginated reports in the workspace
      "numberOfDashboards": 0, // The number of dashboards in the workspace
      "numberOfDataFlows": 0, // The number of dataflows in the workspace
      "numberOfDataSets": 0, // The number of datasets in the workspace
      "numberOfDatamarts": 0, // The number of datamarts in the workspace
      "numberOfAdmins": 0, // The number of administrators in the workspace
      "numberOfMembers": 0, // The number of members in the workspace
      "numberOfContributors": 0, // The number of contributors in the workspace
      "numberOfViewers": 0, // The number of viewers in the workspace
      "isDeleted": false, // Indicates if the workspace has been deleted
      "numberOfGuests": 0, // The number of guests in the workspace
      "hasRequest": false, // Indicates if EnPower business context has been requested for this workspace
      "hasResponse": false, // Indicates if EnPower business context request for this workspace has been responded
      "numberOfUsers": 0, // The number of users in the workspace
      "lastActivityD7": 0, // The number of activities in the last 7 days in the workspace
      "lastActivityTime": "", // The date and time when the last activity occurred in the workspace
      "numberOfScorecards": 0, // The number of scorecards in the workspace
      "primaryContact": null, // The Cloud Governance primary contact of the workspace
      "secondaryContact": null, // The Cloud Governance secondary contact of the workspace
      "phase": null, // The current phase of the workspace in Cloud Governance
      "phaseAssignees": null, // The individuals assigned to the current phase of the workspace in Cloud Governance
      "lastRenewalTime": "", // The last time when the workspace was renewed
      "phaseStartTime": "", // The renewal start time of the workspace
      "renewalDueDate": "", // The renewal due date of the workspace
      "nextRenewalDate": "", // The next renewal date of the workspace
      "lastRenewalBy": null, // The latest user who renewed the workspace
      "renewProfileApplied": null, // Indicates if a renewal profile has been applied to the workspace
      "isRegistered": false, // Indicates if the workspace has been imported to Cloud Governance
      "renewProfile": null, // The Cloud Governance renewal profile applied to the workspace
      "metadata": [], // The Cloud Governance metadata associated with the workspace
      "electionProfileApplied": null, // Indicates if a contact election profile has been applied to the workspace
      "electionProfile": null, // The Cloud Governance contact election profile applied to the workspace
      "claimStatus": null, // The Cloud Governance claim status of the workspace
      "datasource": null // The data source of the workspace
    }
  ],
  "totalCount": 1, 
  "nextLink": "" 
}