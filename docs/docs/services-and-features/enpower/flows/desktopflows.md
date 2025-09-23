# Retrieve Desktop Flow Details

Use this API to access and retrieve information of your Power Automate desktop flows.

## Permission

The following permission is required to call the API.
You must register the app through AvePoint Online Services > App registrations to authenticate and authorize your access to AvePoint Graph API.
For details, refer to [Authentication and Authorization](https://learn.avepoint.com/docs/Use-AvePoint-Graph-API.html#authentication-and-authorization).

| API   | Permission |
|-------------------|---------------|
|`/smp/powerplatform/powerautomate/desktopflows` | enpower.data.read.all | 

## Request

This section provides details on the HTTP method and endpoint used to retrieve general information of your desktop flows.

| Method | Endpoint | Description | 
|--- | --- | --- |
| GET | `/smp/powerplatform/powerautomate/desktopflows` | Retrieves your desktop flows' information | 

## Query Parameters

The API supports several query parameters to refine and customize the data retrieval process.

| Parameters | Description | Type | Required |
|--- | --- | --- | --- |
| top | The number of desktop flow records retrieved and returned each page. The default number is 100. You can enter a number from 1 to 1000. | integer | No |
| tenant | The tenant in which data of desktop flows are retrieved. By default, desktop flows of all tenants are retrieved. | string | No |

## Responses

The API response provides detailed information about the Power Automate desktop flows retrieved. Each flow in the response includes various attributes that describe its properties and status.

| Elements              | Description                                                  | Type    |
|----------------------|--------------------------------------------------------------|---------|
| flowId               | The unique identifier of the flow.                           | string  |
| displayName          | The display name of the flow.                               | string  |
| tenantId             | The unique identifier of the tenant that the flow belongs to.| string  |
| tenantName           | The tenant name that the flow belongs to.                   | string  |
| containerId          | The unique identifier of the container that the flow belongs to.| string  |
| container            | The container that the flow belongs to.                     | string  |
| environmentId        | The unique identifier of the environment that the flow belongs to.| string  |
| environment          | The environment that the flow belongs to.                   | string  |
| creatorId            | The unique identifier for Creator of the flow.              | string  |
| creatorDisplayName    | The display name of the flow creator.                       | string  |
| creatorType          | The user type of the flow creator.                          | string  |
| creatorDepartment     | The department of the flow creator.                         | string  |
| creatorUpn           | The user principal name of the flow creator.                | string  |
| creatorCountry       | The country of the flow creator.                            | string  |
| creatorEmail         | The email of the flow creator.                              | string  |
| creatorJobTitle      | The job title of the flow creator.                          | string  |
| creatorOffice        | The office of the flow creator.                             | string  |
| coOwners             | The number of flow co-owners.                              | integer |
| users                | The number of users who have access to the flow.           | integer |
| type                 | The flow type.                                            | string  |
| status               | The flow status.                                          | string  |
| triggered            | Indicates if the flow has been triggered.<br> Valid values: <br> <ul><li> **true** for yes <br> </li><li> **false** for no <br>                  | boolean |
| lastRunTime          | The latest flow running time.                              | string  |
| lastRunStatus        | The latest flow running status.                            | string  |
| flowRuns             | The number of times that the flow has run.                | integer |
| createdTime          | The flow created time.                                    | string  |
| modifiedTime         | The latest flow modification time.                         | string  |
| solutionCount        | The number of solutions related to this flow.              | integer |
| solutionDisplayNames  | The list of display names of the solutions related to this flow.| string  |
| schemaVersion        | The schema version of this flow.                           | string  |

## Request Sample

To use this API, send a GET request to the specified endpoint, including necessary parameters as defined in the references. This will return the relevant object details in a structured format, enabling easy integration with other systems or applications. The following request is an API call to the EnPower environment in the US - East region.

```json
https://graph-us.avepointonlineservices.com/smp/powerplatform/powerautomate/desktopflows
```
## Response Sample

If the request has been successfully processed, a 200 OK response will be returned along with the requested information displayed in the response body. For more details on the HTTP status code, refer to [HTTP Status Code](https://learn.avepoint.com/docs/Use-AvePoint-Graph-API.html#http-status-code).

```json
{
  "desktopFlows": [
    {
      "flowId": "dbca27a4-c6dc-42e5-9c6f-cac9f4d9b2ea", // The unique identifier of the flow
      "displayName": "FlowName", // The display name of the flow
      "tenantId": "", // The unique identifier of the tenant that the flow belongs to
      "tenantDomain": "sampledomain.com", // The domain name associated with the tenant
      "containerId": "", // The unique identifier of the container that the flow belongs to
      "container": "Sample container", // The container that the flow belongs to
      "environmentId": "", // The unique identifier of the environment that the flow belongs to
      "environment": "", // The environment that the flow belongs to
      "creatorId": "", // The unique identifier for creator of the flow
      "creatorDisplayName": "", // The display name of the flow creator
      "creatorType": "", // The user type of the flow creator
      "creatorDepartment": "", // The department of the flow creator
      "creatorUpn": "", // The user principal name of the flow creator
      "creatorCountry": "", // The country of the flow creator
      "creatorEmail": "", // The email of the flow creator
      "creatorJobTitle": "", // The job title of the flow creator
      "creatorOffice": "", // The office of the flow creator
      "coOwners": 0, // The number of flow co-owners
      "users": 0, // The number of users who have access to the flow
      "type": "", // The flow type
      "status": "", // The flow status
      "triggered": false, // Indicates if the flow has been triggered
      "lastRunTime": "", // The latest flow running time
      "lastRunStatus": "", // The latest flow running status
      "flowRuns": 0, // The number of times that the flow has run
      "createdTime": "", // The flow created time
      "modifiedTime": "", // The latest flow modification time
      "solutionCount": 0, // The number of solutions related to this flow
      "solutionDisplayNames": [], // The list of display names of the solutions related to this flow
      "schemaVersion": "", // The schema version of this flow
    }
  ],
  "totalCount": 1,
  "nextLink": "" 
}
