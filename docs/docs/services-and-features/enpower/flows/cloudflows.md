# Retrieve Cloud Flow Details

Use this API to access and retrieve information of your Power Automate cloud flows.

## Permission

The following permission is required to call the API.
You must register the app through AvePoint Online Services > App registrations to authenticate and authorize your access to AvePoint Graph API.
For details, refer to [Authentication and Authorization](https://learn.avepoint.com/docs/Use-AvePoint-Graph-API.html#authentication-and-authorization).

| API   | Permission |
|-------------------|---------------|
|`/smp/powerplatform/powerautomate/cloudflows` | enpower.data.read.all | 

## Request

This section provides details on the HTTP method and endpoint used to retrieve general information of your cloud flows.

| Method | Endpoint | Description | 
|--- | --- | --- |
| GET | `/smp/powerplatform/powerautomate/cloudflows` | Retrieves your cloud flows' information | 

## Query Parameters

The API supports several query parameters to refine and customize the data retrieval process.

| Parameters | Description | Type | Required |
|--- | --- | --- | --- |
| top | The number of cloud flow records retrieved and returned each page. The default number is 100. You can enter a number from 1 to 1000. | integer | No |
| tenant | The tenant in which data of cloud flows are retrieved. By default, cloud flows of all tenants are retrieved. | string | No |

## Responses

The API response provides detailed information about the Power Automate cloud flows retrieved. Each flow in the response includes various attributes that describe its properties and status.

| Elements           | Description                                                           | Type   | 
|--------------------|-----------------------------------------------------------------------|--------|
| cloudFlows            | A list containing flows with detailed information. For the detailed list of responses, refer to [Flow Details](#flow-details).             | list  | 
| totalCount      | Total number of cloud flows retrieved.                   | integer    | 
| nextLink | Reference to the next page of results | string |

### Flow Details

| Elements                    | Description                                                                 | Type    |
|-----------------------------|-----------------------------------------------------------------------------|---------|
| flowId                      | The unique identifier of the flow.                                          | string  |
| displayName                 | The display name of the flow.                                               | string  |
| environmentId               | The unique identifier of the environment that the flow belongs to.          | string  |
| environment                 | The environment that the flow belongs to.                                   | string  |
| tenantId                    | The unique identifier of the tenant that the flow belongs to.               | string  |
| tenantDomain                | The domain name associated with the tenant.                                 | string  |
| containerId                 | The unique identifier of the container that the flow belongs to.            | string  |
| container                   | The container that the flow belongs to.                                     | string  |
| type                        | The flow type.                                                              | string  |
| createdTime                 | The time when the flow was created.                                         | string  |
| status                      | The flow status.                                                            | string  |
| flowTrigger                 | The flow trigger.                                                           | string  |
| triggered | Indicates if the flow has been triggered <br> Valid values: <br> <ul><li> **true** for yes <br> </li><li> **false** for no <br> | boolean |
| actionCount                 | The number of actions in this flow.                                         | integer |
| lastModifiedTime            | The latest flow modification time.                                          | string  |
| lastActivityDate            | The latest flow activity date.                                              | string  |
| lastRunTime                 | The latest flow running time.                                               | string  |
| flowRuns                    | The number that the flow has run.                                           | integer |
| runsLast7Days        | The number of runs in the last 7 days         | integer |
| runsLast30Days       | The number of runs in the last 30 days        | integer |
| runsLast90Days       | The number of runs in the last 90 days        | integer |
| runsLast180Days      | The number of runs in the last 180 days       | integer |
| activitiesLast7Days  | The number of activities in the last 7 days   | integer |
| activitiesLast30Days | The number of activities in the last 30 days  | integer |
| activitiesLast90Days | The number of activities in the last 90 days  | integer |
| activitiesLast180Days| The number of activities in the last 180 days | integer |
| creator                     | The creator of this flow.                                                   | string  |
| creatorDepartment           | The department of the flow creator.                                         | string  |
| creatorOffice               | The office of the flow creator.                                             | string  |
| creatorStatus               | The status of the flow creator.                                             | string  |
| creatorUserType             | The user type of the flow creator.                                          | string  |
| creatorCountry             | The country of the flow creator.                                          | string  |
| creatorEmail             | The email of the flow creator.                                          | string  |
| creatorId             | The unique identifier of the flow creator.                                          | string  |
| creatorJobTitle             | The job title of the flow creator.                                          | string  |
| creatorUpn             | The user principal name of the flow creator.                                          | string  |
| coOwners                    | The number of flow co-owners.                                               | integer |
| users                       | The number of users who have access to the flow.                            | integer |
| guests                      | The number of guest users who have access to the flow.                      | integer |
| shadowUsers                 | The number of shadow users who have access to the flow.                     | integer |
| requestEmailSent | Indicates if EnPower business context has been requested for this flow. <br> Valid values: <br> <ul><li> **true** for yes <br> </li><li> **false** for no <br> | boolean |
| businessContextResponded | Indicates if EnPower business context request for this flow has been responded. <br> Valid values: <br> <ul><li> **true** for yes <br> </li><li> **false** for no <br> | boolean |
| solutions                   | Solutions related to this flow.                                             | string  |
| connections                 | Connections being used by this flow. For the detailed connection properties, refer to [Connection Details](#connection-details).                                       | list    |
| primaryContact              | The Cloud Governance primary contact of the flow. For the detailed user properties, refer to [User Details](#user-details).                         | object  |
| secondaryContact            | The Cloud Governance secondary contact of the flow. For the detailed user properties, refer to [User Details](#user-details).                         | object  |
| phase                       | The Cloud Governance phase of the flow.                                     | string  |
| phaseAssignees              | The Cloud Governance phase assignee of the flow. For the detailed user properties, refer to [User Details](#user-details).                            | object  |
| lastRenewalTime             | The latest time when the flow was renewed.                                  | string  |
| phaseStartTime              | The renewal start time of the flow.                |  string |
| renewalDueDate              | The renewal due date of the flow.                |  string |
| nextRenewalDate              | The next renewal date of the flow.                |  string |
| lastRenewedBy               | The latest user who renewed this flow. For the detailed user properties, refer to [User Details](#user-details).                                      | object  |
| renewProfileApplied | Indicates if any Cloud Governance renewal profile is applied to this flow. <br> Valid values: <br> <ul><li> **true** for yes <br> </li><li> **false** for no <br> | boolean |
| registered | Indicates if the flow has been imported to Cloud Governance. <br> Valid values: <br> <ul><li> **true** for yes <br> </li><li> **false** for no <br> | boolean |
| renewalProfile              | The Cloud Governance renewal profile applied to this flow. For the detailed profile properties, refer to [Cloud Governance Profile Details](#cloud-governance-profile-details).                 | object  |
| metadata                    | The list of Cloud Governance metadata of this flow. For the detailed metadata properties, refer to [Cloud Governance Metadata Details](#cloud-governance-metadata-details).                        | list    |
| electionProfileApplied | Indicates if any Cloud Governance contact election profile is applied to this flow. <br> Valid values: <br> <ul><li> **true** for yes <br> </li><li> **false** for no <br> | boolean |
| contactElectionProfile      | The Cloud Governance renewal profile applied to this flow. For the detailed profile properties, refer to [Cloud Governance Profile Details](#cloud-governance-profile-details).                  | object  |
| claimStatus                 | The Cloud Governance claim status of this flow.                             | string  |

### Connection Details

| Elements                | Description                                                                 | Type    |
|-------------------------|-----------------------------------------------------------------------------|---------|
| connectionName          | The name of connection.                                                     | string  |
| connectionDisplayName   | The friendly name of connection.                                            | string  |
| connectorName           | The name of connector.                                                      | string  |
| connectorDisplayName    | The friendly name of connector.                                             | string  |
| iconUri                 | The icon URI of the connection.                                             | string  |
| type                    | The connection type.                                                        | string  |

### User Details

| Elements                | Description                                                                 | Type    |
|-------------------------|-----------------------------------------------------------------------------|---------|
| id                      | The unique identifier for the Cloud Governance user.                        | string  |
| displayName             | The display name of the Cloud Governance user.                              | string  |
| email                   | The email address associated with the Cloud Governance user.                | string  |
| tenantId                | The unique identifier for the tenant that the Cloud Governance user belongs to. | string  |
| userPrincipalName       | The user principal name of the Cloud Governance user.                       | string  |
| objectId                | The unique object ID for the Cloud Governance user.                         | string  |
| jobTitle                | The job title associated with the Cloud Governance user.                    | string  |
| department              | The department associated with the Cloud Governance user.                   | string  |
| companyName             | The company name associated with the Cloud Governance user.                 | string  |
| office                  | The office location associated with the Cloud Governance user.              | string  |
| city                    | The city associated with the Cloud Governance user.                         | string  |
| countryOrRegion         | The country or region associated with the Cloud Governance user.            | string  |

### Cloud Governance Metadata Details

| Elements                | Description                                                                 | Type    |
|-------------------------|-----------------------------------------------------------------------------|---------|
| metadataType | The type of metadata. <br> Valid values: <br> <ul><li> **0** for none <br> </li><li> **1** for single line of text <br></li><li> **2** for multiple lines of text <br></li><li> **3** for yes/no <br></li><li> **4** for choice <br></li><li> **5** for people picker filter profile <br></li><li> **6** for managed metadata <br></li><li> **7** for hyperlink <br></li><li> **8** for user profile property <br></li><li> **9** for Microsoft Entra property <br></li><li> **10** for lookup <br></li><li> **11** for user property </li></ul> | integer | 
| value                   | The metadata value.                                                         | object  |
| id                      | The unique identifier for the metadata.                                     | string  |
| name                    | The metadata name.                                                          | string  |
| metadataSetting         | The custom metadata.                                                        | object  |

### Cloud Governance Profile Details

| Elements                | Description                                                                 | Type    |
|-------------------------|-----------------------------------------------------------------------------|---------|
| id                      | The unique identifier of the profile.                                       | string  |
| name                    | The name of the profile.                                                    | string  |

## Request Sample

To use this API, send a GET request to the specified endpoint, including necessary parameters as defined in the references. This will return the relevant object details in a structured format, enabling easy integration with other systems or applications. The following request is an API call to the EnPower environment in the US - East region.

```json
https://graph-us.avepointonlineservices.com/smp/powerplatform/powerautomate/cloudflows
```
## Response Sample

If the request has been successfully processed, a 200 OK response will be returned along with the requested information displayed in the response body. For more details on the HTTP status code, refer to [HTTP Status Code](https://learn.avepoint.com/docs/Use-AvePoint-Graph-API.html#http-status-code).

```json
{
  "cloudFlows": [
    {
      "flowId": "dbca27a4-c6dc-42e5-****-cac9f4d9b2ea", // The unique identifier of the flow
      "displayName": "FlowName", // The display name of the flow
      "environmentId": "", // The unique identifier of the environment that the flow belongs to
      "environment": "", // The environment that the flow belongs to
      "tenantId": "", // The unique identifier of the tenant that the flow belongs to
      "tenantDomain": "Sample", // The domain name associated with the tenant
      "containerId": "", // The unique identifier of the container that the flow belongs to
      "container": "Sample-CloudFlows", // The container that the flow belongs to
      "type": "Instant", // The flow type
      "createdTime": "2023-11-21 09:56:13", // The time when the flow was created
      "status": "Stopped", // The flow status
      "flowTrigger": "PowerAppsButton", // The flow trigger
      "triggered": false, // Indicates if the flow has been triggered
      "actionCount": 1, // The number of actions in this flow
      "lastModifiedTime": "2024-07-08 06:25:11", // The latest flow modification time
      "lastActivityDate": "", // The latest flow activity date
      "lastRunTime": "", // The latest flow running time
      "flowRuns": 0, // The number that the flow has run
      "runsLast7Days": 0, // The number of runs in the last 7 days
      "runsLast30Days": 0, // The number of runs in the last 30 days
      "runsLast90Days": 0, // The number of runs in the last 90 days
      "runsLast180Days": 0, // The number of runs in the last 180 days
      "activitiesLast7Days": 0, // The number of activities in the last 7 days
      "activitiesLast30Days": 0, // The number of activities in the last 30 days
      "activitiesLast90Days": 0, // The number of activities in the last  90 days
      "activitiesLast180Days": 0, // The number of activities in the last 180 days
      "creator": "", // The creator of this flow
      "creatorDepartment": "Sample Department", // The department of the flow creator
      "creatorOffice": null, // The office of the flow creator
      "creatorStatus": "Enable", // The status of the flow creator
      "creatorUserType": "Member", // The user type of the flow creator
      "creatorCountry": "", // The country of the flow creator
      "creatorEmail": "", // The email of the flow creator
      "creatorId": "", // The unique identifier of the flow creator
      "creatorJobTitle": "", // The job title of the flow creator
      "creatorUpn": "", // The user principal name of the flow creator
      "coOwners": 3, // The number of flow co-owners
      "users": 0, // The number of users who have access to the flow
      "guests": 0, // The number of guest users who have access to the flow
      "shadowUsers": 0, // The number of shadow users who have access to the flow
      "requestEmailSent": true, // Indicates if EnPower business context has been requested for this flow
      "businessContextResponded": false, // Indicates if EnPower business context request for this flow has been responded
      "solutions": "None", // Solutions related to this flow
      "connections": [], // Connections being used by this flow
      "primaryContact": {
        "id": "", // The unique identifier of the primary contact for this flow
        "displayName": "", // The display name of the primary contact
        "email": "", // The email address of the primary contact
        "tenantId": null, // The tenant ID of the primary contact
        "userPrincipalName": "", // The user principal name of the primary contact
        "objectId": "", // The object ID of the primary contact
        "jobTitle": null, // The job title of the primary contact
        "department": null, // The department of the primary contact
        "companyName": null, // The company name of the primary contact
        "office": null, // The office of the primary contact
        "city": null, // The city of the primary contact
        "countryOrRegion": null // The country or region of the primary contact
      },
      "secondaryContact": null, // The Cloud Governance secondary contact of the flow
      "phase": "RenewalExpired", // The Cloud Governance phase of the flow
      "phaseAssignees": null, // The Cloud Governance phase assignee of the flow
      "lastRenewalTime": "", // The latest time when the flow was renewed
      "phaseStartTime": "", // The renewal start time of the flow
      "renewalDueDate": "", // The renewal due date of the flow
      "nextRenewalDate": "", // The next renewal date of the flow
      "lastRenewedBy": null, // The latest user who renewed this flow
      "renewProfileApplied": true, // Indicates if any Cloud Governance renewal profile is applied to this flow
      "registered": true, // Indicates if the flow has been imported to Cloud Governance
      "renewalProfile": {
        "name": "FlowRenewProfile", // The name of the Cloud Governance renewal profile applied to this flow
        "id": "" // The ID of the Cloud Governance renewal profile applied to this flow
      },
      "metadata": [], // The list of Cloud Governance metadata of this flow
      "electionProfileApplied": false, // Indicates if any Cloud Governance contact election profile is applied to this flow
      "contactElectionProfile": null, // The Cloud Governance renewal profile applied to this flow
      "claimStatus": "Claimed" // The Cloud Governance claim status of this flow
    }
  ],
  "totalCount": 1,
  "nextLink": "" 
}