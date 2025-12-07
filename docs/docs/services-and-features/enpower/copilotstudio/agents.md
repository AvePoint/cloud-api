# Retrieve Agent Details

Use this API to access and retrieve information of your Copilot Studio agents.

## Permission

The following permission is required to call the API.
You must register the app through AvePoint Online Services > App registrations to authenticate and authorize your access to AvePoint Graph API.
For details, refer to [Authentication and Authorization](https://learn.avepoint.com/docs/Use-AvePoint-Graph-API.html#authentication-and-authorization).

| API   | Permission |
|-------------------|---------------|
|`/smp/powerplatform/bot` | enpower.data.read.all | 

## Request

This section provides details on the HTTP method and endpoint used to retrieve general information of your agents.

| Method | Endpoint | Description | 
|--- | --- | --- |
| GET | `/smp/powerplatform/bot` | Retrieves your agents' information | 

## Query Parameters

The API supports several query parameters to refine and customize the data retrieval process.

| Parameters | Description | Type | Required |
|--- | --- | --- | --- |
| top | The number of agent records retrieved and returned each page. The default number is 100. You can enter a number from 1 to 1000. | integer | No |
| tenant | The tenant in which data of dagents are retrieved. By default, agents of all tenants are retrieved. | string | No |

## Responses

The API response provides detailed information about the agents retrieved. Each agent in the response includes various attributes that describe its properties and status.

| Elements                | Description                                                  | Type    |
|-------------------------|--------------------------------------------------------------|---------|
| botId                   | The unique identifier for the agent.                        | string  |
| tenantId                | The unique identifier of the tenant that the agent belongs to.| string  |
| tenantName              | The name of the tenant that the agent belongs to.           | string  |
| containerId             | The unique identifier of the container that the agent belongs to.| string  |
| container               | The name of the container that the agent belongs to.        | string  |
| environmentId           | The unique identifier of the environment that the agent belongs to. | string  |
| environment             | The name of the environment that the agent belongs to.      | string  |
| displayName             | The display name of the agent.                              | string  |
| description             | The description of the agent.                               | string  |
| ownerId                 | The unique identifier of the agent owner.                   | string  |
| ownerUserPrincipalName  | The user principal name of the agent owner.                 | string  |
| creatorId               | The unique identifier of the agent creator.                 | string  |
| creatorDisplayName      | The display name of the agent creator.                      | string  |
| creatorUserPrincipalName | The user principal name of the agent creator.               | string  |
| creatorDepartment        | The department of the agent creator.                        | string  |
| creatorOffice           | The office of the agent creator.                            | string  |
| creatorCountry          | The country of the agent creator.                           | string  |
| creatorJobTitle         | The job title of the agent creator.                         | string  |
| creatorEmail            | The email of the agent creator.                             | string  |
| createdTime             | The created time of the agent.                             | string  |
| lastModifiedTime        | The latest agent modification time.                         | string  |
| lastPublishedTime       | The latest published time of the agent.                    | string  |
| activityCountLast7D    | The number of activities in the last 7 days.               | integer |
 activityCountLast30D    | The number of activities in the last 30 days         | integer |
| activityCountLast90D    | The number of activities in the last 90 days         | integer |
| activityCountLast180D   | The number of activities in the last 180 days        | integer |
| lastActivityTime        | The latest agent activity date.                             | string  |
| primaryLanguage         | The primary language of the agent.                          | string  |
| sharedWithOrganization  | Indicates whether the agent is shared with the organization. <br> Valid values: <br> <ul><li> true for yes <br> </li><li> false for no <br> | boolean |
| sharedUsers             | Number of users this agent was shared with.                | integer |
| sharedGroups            | Number of groups this agent was shared with.               | integer |
| instructions            | The instructions of the agent                        | string  |
| useAIGeneralKnowledge   | Indicates whether the agent is using AI general knowledge | boolean |
| useGenAIOrchestration   | Indicates whether the agent is using Gen AI orchestration | boolean |
| knowledgeSourceCount    | The total knowledge source count of the agent        | integer |
| promptCount             | The total prompt count of the agent                  | integer |
| skillCount              | The total skill count of the agent                   | integer |
| toolCount               | The total tool count of the agent                    | integer |
| restAPIToolCount        | The total Rest API tool count of the agent           | integer |
| useWebSearch            | Indicates whether the agent is using web search      | boolean |


## Request Sample

To use this API, send a GET request to the specified endpoint, including necessary parameters as defined in the references. This will return the relevant object details in a structured format, enabling easy integration with other systems or applications. The following request is an API call to the EnPower environment in the US - East region.

```json
https://graph-us.avepointonlineservices.com/smp/powerplatform/bot
```
## Response Sample

If the request has been successfully processed, a 200 OK response will be returned along with the requested information displayed in the response body. For more details on the HTTP status code, refer to [HTTP Status Code](https://learn.avepoint.com/docs/Use-AvePoint-Graph-API.html#http-status-code).

```json
{
  "bots": [
    {
      "botId": "", // The unique identifier for the agent
      "tenantId": "", // The unique identifier of the tenant that the agent belongs to
      "tenantName": "", // The name of the tenant that the agent belongs to
      "containerId": "", // The unique identifier of the container that the agent belongs to
      "container": "", // The name of the container that the agent belongs to
      "environmentId": "", // The unique identifier of the environment that the agent belongs to
      "environment": "", // The name of the environment that the agent belongs to
      "displayName": "", // The display name of the agent
      "description": "", // The description of the agent
      "ownerId": "", // The unique identifier of the agent owner
      "ownerUserPrincipalName": "", // The user principal name of the agent owner
      "creatorId": "", // The unique identifier of the agent creator
      "creatorDisplayName": "", // The display name of the agent creator
      "creatorUserPrincipalName": "", // The user principal name of the agent creator
      "creatorDepartment": "", // The department of the agent creator
      "creatorOffice": "", // The office of the agent creator
      "creatorCountry": "", // The country of the agent creator
      "creatorJobTitle": "", // The job title of the agent creator
      "creatorEmail": "", // The email of the agent creator
      "createdTime": "", // The created time of the agent
      "lastModifiedTime": "", // The latest agent modification time
      "lastPublishedTime": "", // The latest published time of the agent
      "activityCountLast7D": 0, // The number of activities in the last 7 days
      "activityCountLast30D": 0, // The number of activities in the last 30 days
      "activityCountLast90D": 0, // The number of activities in the last  90 days
      "activityCountLast180D": 0, // The number of activities in the last 180 days
      "lastActivityTime": "", // The latest agent activity date
      "primaryLanguage": "", // The primary language of the agent
      "sharedWithOrganization": false, // Indicates whether the agent is shared with the organization
      "sharedUsers": 0, // Number of users this agent was shared with
      "sharedGroups": 0 // Number of groups this agent was shared with
      "instructions": "" //The instructions of the agent
      "useAIGeneralKnowledge": false //Indicates whether the agent is using AI general knowledge
      "useGenAIOrchestration": false //Indicates whether the agent is using Gen AI orchestration
      "knowledgeSourceCount": 0  //The total knowledge source count of the agent
      "promptCount": 0  //The total prompt count of the agent
      "skillCount": 0  //The total skill count of the agent
      "toolCount": 0  //The total tool count of the agent
      "restAPIToolCount": 0 //The total Rest API tool count of the agent
      "useWebSearch": false //Indicates whether the agent is using web search
    }
  ],
  "totalCount": 1,
  "nextLink": ""
}