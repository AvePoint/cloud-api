# Retrieve Power App Details

Use this API to access and retrieve information of your Power Apps.

## Permission

The following permission is required to call the API.
You must register the app through AvePoint Online Services > App registrations to authenticate and authorize your access to AvePoint Graph Modern API.
For details, refer to [Authentication and Authorization](https://learn.avepoint.com/docs/Use-AvePoint-Graph-Modern-API.html#authentication-and-authorization).

| API   | Permission |
|-------------------|---------------|
|`/smp/powerplatform/powerapps` | enpower.data.read.all | 

## Request

This section provides details on the HTTP method and endpoint used to retrieve general information of your Power Apps.

| Method | Endpoint | Description | 
|--- | --- | --- |
| GET | `/smp/powerplatform/powerapps` | Retrieves your Power Apps' information | 

## Query Parameters

The API supports several query parameters to refine and customize the data retrieval process.

| Parameters | Description | Type | Required |
|--- | --- | --- | --- |
| top | The number of Power App records retrieved and returned each page. The default number is 100. You can enter a number from 1 to 1000. | integer | No |
| tenant | The tenant in which data of Power Apps are retrieved. By default, Power Apps of all tenants are retrieved. | string | No |

## Responses

The API response provides detailed information about the Power Apps retrieved. Each app in the response includes various attributes that describe its properties and status.

| Elements           | Description                                                           | Type   | 
|--------------------|-----------------------------------------------------------------------|--------|
| powerApps             | A list containing Power Apps with detailed information. For the detailed list of responses, refer to [Power App Details](#power-app-details).              | list  | 
| totalCount      | Total number of apps retrieved.                   | integer    | 
| nextLink | Reference to the next page of results | string |


### Power App Details

| Response                        | Description                                                                 | Type    |
|---------------------------------|-----------------------------------------------------------------------------|---------|
| id                              | The unique identifier for the Power App.                                     | string  |
| appId                           | The unique application identifier within Power Platform.                    | string  |
| displayName                     | The display name of the Power App.                                           | string  |
| tenantId                        | The unique identifier for the tenant that the Power App belongs to.         | string  |
| tenantDomain                    | The domain name associated with the tenant.                                 | string  |
| containerId                     | The unique identifier for the container that the Power App belongs to.      | string  |
| container                       | The name of the container.                                                  | string  |
| environment                     | The Power Platform environment ID that the Power App belongs to.               | string  |
| environmentName                 | The display name of the environment.                                        | string  |
| ownerDisplayName                | The display name of the Power App owner.                              | string  |
| ownerStatus                     | The status of the Power App owner                                           | string  |
| createdOn                       | The date and time when the Power App was created                            | string  |
| modifiedOn                      | The date and time when the Power App was last modified                      | string  |
| lastLaunchedOn                  | The latest date and time when the Power App was launched                      | string  |
| sharedUsers                     | The number of users with shared access to the Power App.                    | integer |
| sharedGroups                    | The number of groups with shared access to the Power App.                   | integer |
| sharedOrganization | Indicates whether the Power App is shared with the organization. <br> Valid values: <br> <ul><li> **true** for yes <br> </li><li> **false** for no <br> | boolean |
| appType                         | The type of the Power App.                                                  | string  |
| appTypeDetail                   | Power App’s type details.                                                   | string  |
| siteUrl                         | The URL where the Power App can be accessed.                                | string  |
| backgroundImageUri              | The URI of the background image for the Power App.                          | string  |
| backgroundColor                 | The background color of the Power App's user interface.                     | string  |
| hasContextDetail | Indicates if the Power App has context-related details. <br> Valid values: <br> <ul><li> **true** for yes <br> </li><li> **false** for no <br> | boolean |
| coOwnerCount                    | The number of co-owners of the Power App.                                   | integer |
| ownerCount                      | The number of owners of the Power App.                                      | integer |
| userCount                       | The number of users who have access to the Power App.                       | integer |
| shadowUserCount                 | The number of shadow users of the Power App.                                | integer |
| guestUserCount                  | The number of guest users who have access to the Power App.                 | integer |
| ownerUserType                   | The user type of the Power App's owner.                                     | string  |
| connectorCount                  | The number of connectors the Power App is using.                            | integer |
| hasPremiumConnection | Indicates if the Power App uses a premium connector. <br> Valid values: <br> <ul><li> **true** for yes <br> </li><li> **false** for no <br> | boolean |
| environmentType                 | The type of the environment that the Power App belongs to.                  | string  |
| environmentHasSecurityGroup | Indicates whether the environment has a security group attached. <br> Valid values: <br> <ul><li> **true** for yes <br> </li><li> **false** for no <br> | boolean |
| creatorDepartment               | The department of the Power App creator.                                    | string  |
| creatorDisplayName              | The display name of the Power App creator.                                  | string  |
| connectorTier                   | The tier of the connector being used in the Power App                       | string  |
| withBusinessContextRequest | Indicates if the Power App has business context requested via EnPower. <br> Valid values: <br> <ul><li> **true** for yes <br> </li><li> **false** for no <br> | boolean |
| withBusinessContextResponse | Indicates if the Power App has responded EnPower’s business context request. <br> Valid values: <br> <ul><li> **true** for yes <br> </li><li> **false** for no <br> | boolean |
| businessContextLastResponseTime | The last time an EnPower business context request was responded.            | string  |
| lastActivityD7                  | The activity count in the last 7 days.                                      | integer |
| appLaunchedCount                | The number of times the Power App has been launched.                        | integer |
| lastPublishOn                   | The date and time when the Power App was last published.                    | string  |
| quarantineState                 | The quarantine status of the Power App.                                     | string  |
| status                          | The current status of the Power App.                                        | string  |
| solutionCount                   | The number of solutions associated with the Power App.                      | integer |
| solutionNames                   | The names of solutions associated with the Power App.                       | string  |
| backgroundModelDrivenImageUri   | URI of the background image for model-driven Power App.                     | string  |
| componentState                  | The status of the Power App’s components.                                   | string  |
| isManaged | Indicates whether the Power App is managed or unmanaged. <br> Valid values: <br> <ul><li> **true** for yes <br> </li><li> **false** for no <br> | boolean |
| actions                         | The number of actions associated with the Power App.                        | integer |
| ownerUserPrincipalName          | The user principal name of the Power App owner in the directory.            | string  |
| creatorUserPrincipalName        | The user principal name of the Power App creator in the directory           | string  |
| creatorOfficeLocation           | The office location of the Power App creator.                               | string  |
| primaryContact                  | The Cloud Governance primary contact of the Power App. For the detailed user properties, refer to [User Details](#user-details).                      | object  |
| secondaryContact                | The Cloud Governance secondary contact of the Power App. For the detailed user properties, refer to [User Details](#user-details).                     | object  |
| phase                           | The current phase of the Power App in Cloud Governance.                     | string  |
| phaseAssignees                  | The assignee of the current Cloud Governance phase. For the detailed user properties, refer to [User Details](#user-details).                        | object  |
| lastRenewalTime                 | The last time the Power App was renewed.                                    | string  |
| lastRenewalBy                   | The latest user who renewed the Power App. For the detailed user properties, refer to [User Details](#user-details).                                  | object  |
| renewalProfileApplied | Indicates if a Cloud Governance renewal profile has been applied to the Power App. <br> Valid values: <br> <ul><li> **true** for yes <br> </li><li> **false** for no <br> | boolean |
| isRegistered | Indicates if the Power App was imported to Cloud Governance. <br> Valid values: <br> <ul><li> **true** for yes <br> </li><li> **false** for no <br> | boolean |
| renewProfile                    | The Cloud Governance renewal profile applied to the Power App. For the detailed profile properties, refer to [Cloud Governance Profile Details](#cloud-governance-profile-details).              | object  |
| metadata                        | The Cloud Governance metadata associated with the Power App. For the detailed metadata properties, refer to [Cloud Governance Metadata Details](#cloud-governance-metadata-details).               | list  |
| electionProfileApplied | Indicates if a Cloud Governance contact election profile was applied to the Power App. <br> Valid values: <br> <ul><li> **true** for yes <br> </li><li> **false** for no <br> | boolean |
| electionProfile                 | The Cloud Governance contact election profile applied to the Power App. For the detailed profile properties, refer to [Cloud Governance Profile Details](#cloud-governance-profile-details).    | object  |
| claimStatus                     | The Cloud Governance claim status for the Power App.                        | string  |

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
https://graph-us.avepointonlineservices.com/smp/powerplatform/powerapps
```

## Response Sample

If the request has been successfully processed, a 200 OK response will be returned along with the requested information displayed in the response body. For more details on the HTTP status code, refer to [HTTP Status Code](https://learn.avepoint.com/docs/Use-AvePoint-Graph-Modern-API.html#http-status-code).

```json
{
  "powerApps": [
    {
      "id": "89508bda-8f4f-48ef-8363-c8890e5dfee4_4ec0fd45-0e35-4f8d-973f-10e45a334c17_default-4ec0fd45-0e35-4f8d-973f-10e45a334c17", // The unique identifier for the Power app
      "appId": "89508bda-8f4f-48ef-8363-c8890e5dfee4", // The unique application identifier within Power Platform
      "displayName": "0613-Ci data01_Restored202410010619_Restored202411120345", // The display name of the Power app
      "tenantId": "", // The unique identifier for the tenant that the Power App belongs to
      "tenantDomain": "Sample", // The domain name associated with the tenant
      "containerId": "", // The unique identifier for the container that the Power App belongs to
      "container": "Sample-Apps", // The name of the container
      "environment": "", // The Power Platform environment ID that the Power App belongs to
      "environmentName": "SMPDC (default)", // The display name of the environment
      "ownerDisplayName": "Sample Owner", // The display name of the Power App owner
      "ownerStatus": "Enable", // The status of the Power App owner
      "createdOn": "2024-06-13 03:19:48", // The date and time when the Power App was created
      "modifiedOn": "2024-12-26 03:58:17", // The date and time when the Power App was last modified
      "lastLaunchedOn": "0001-01-01 00:00:00", // The latest date and time when the Power App was launched
      "sharedUsers": 2, // The number of users with shared access to the Power App
      "sharedGroups": 1, // The number of groups with shared access to the Power App
      "sharedOrganization": false, // Indicates whether the Power App is shared with the organization
      "appType": "Canvas", // The type of the Power App
      "appTypeDetail": "Standard", // Power App’s type details
      "siteUrl": null, // The URL where the Power App can be accessed
      "backgroundImageUri": "", // The URI of the background image of the Power App
      "backgroundColor": "RGBA(0,176,240,1)", // The background color of the Power App's user interface
      "hasContextDetail": false, // Indicates if the Power App has context-related details 
      "coOwnerCount": 1, // The number of co-owners of the Power App
      "ownerCount": 0, // The number of owners of the Power App
      "userCount": 1, // The number of users who have access to the Power App
      "shadowUserCount": 0, // The number of shadow users of the Power App
      "guestUserCount": 0, // The number of guest users who have access to the Power App
      "ownerUserType": "Member", // The user type of the Power App's owner
      "connectorCount": 3, // The number of connectors the Power App is using
      "hasPremiumConnection": false, // Indicates if the Power App uses a premium connector 
      "environmentType": "Default", // The type of the environment that the Power App belongs to
      "environmentHasSecurityGroup": false, // Indicates whether the environment has a security group attached
      "creatorDepartment": "01", // The department of the Power App creator
      "creatorDisplayName": "Camilla Test", // The display name of the Power App creator
      "connectorTier": "Standard", // The tier of the connector being used in the Power App
      "withBusinessContextRequest": false, // Indicates if the Power App has business context requested via EnPower
      "withBusinessContextResponse": false, // Indicates if the Power App has responded EnPower’s business context request
      "businessContextLastResponseTime": "", // The last time an EnPower business context request was responded
      "lastActivityD7": 0, // The activity count in the last 7 days
      "appLaunchedCount": 0, // The number of times the Power app has been launched
      "lastPublishOn": "2024-12-26 03:58:11", // The date and time when the Power app was last published
      "quarantineState": "Quarantined", // The quarantine status of the Power App
      "status": "None", // The current status of the Power App
      "solutionCount": 0, // The number of solutions associated with the Power App
      "solutionNames": null, // The names of solutions associated with the Power App
      "backgroundModelDrivenImageUri": "", // URI of the background image for model-driven Power Apps
      "componentState": "", // The status of the Power App’s components
      "isManaged": null, // Indicates whether the Power App is managed or unmanaged 
      "actions": 0, // The number of actions associated with the Power App
      "ownerUserPrincipalName": "", // The user principal name of the Power App owner in the directory
      "creatorUserPrincipalName": "", // The user principal name of the Power App creator in the directory
      "creatorOfficeLocation": null, // The office location of the Power App creator
      "primaryContact": null, // The Cloud Governance primary contact of the Power App
      "secondaryContact": null, // The Cloud Governance secondary contact of the Power App
      "phase": null, // The current phase of the Power App in Cloud Governance
      "phaseAssignees": null, // The assignee of the current Cloud Governance phase
      "lastRenewalTime": "", // The last time the Power App was renewed
      "lastRenewalBy": null, // The latest user who renewed the Power App
      "renewProfileApplied": null, // Indicates if a Cloud Governance renewal profile has been applied to the Power App
      "isRegistered": false, // Indicates if the Power App was imported to Cloud Governance 
      "renewProfile": null, // The Cloud Governance renewal profile applied to the Power App
      "metadata": [], // The Cloud Governance metadata associated with the Power App
      "electionProfileApplied": null, // Indicates if a Cloud Governance contact election profile was applied to the Power App 
      "electionProfile": null, // The Cloud Governance contact election profile applied to the Power App
      "claimStatus": null // The Cloud Governance claim status for the Power App
    }
  ],
  "totalCount": 1,
  "nextLink": ""
}
```