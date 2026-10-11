# Retrieve Hybrid Agent Information

Use this API to retrieve information of hybrid agents for a customer's tenant.  

## Permission  

The following permission is required to call the API.  
You must register an app through Elements > API app registration to authenticate and authorize your access to Elements API. For details, refer to [App Registration](../../register-app.md).

| API | Permission |
|-----------|-----------|
| `/partner/external/v3/um/customers/{customerId}/tenants/{tenantId}/agents` | elements.um.user.read.all |  

## Request

This section outlines the HTTP method and endpoint used to retrieve information of hybrid agents for a customer's tenant.

| Method | Endpoint | Description |
|-----------|-----------|-----------|
|GET|`/partner/external/v3/um/customers/{customerId}/tenants/{tenantId}/agents`|Retrieves information of hybrid agents for a customer's tenant.|

## URL Parameters

This section outlines the parameters required to specify the hybrid agent you want to retrieve.

| Parameter | Description | Type | Required |
| --- | --- | --- | --- |
| customerId | The ID of the customer. | string | Yes |
| tenantId | The ID of the tenant. | string | Yes |


## Response

If the request has been successfully processed, a 200 OK response will be returned along with the requested information displayed in the response body.

| Response | Description | Type |
| --- | --- | --- |
| agentList | The list of hybrid agents in the customer's tenant. | `Array[HybridAgentStatusAPIModel]` |

 **Hybrid Agent List Items**
| Response | Description | Type |
| --- | --- | --- |
| id | The ID of the agent. | string |
| serverName | The local server name of the agent. | string |
| version | The version of the agent. | string |
| status | The basic status of the agent. <ul><li>**0** - Not installed</li><li>**1** - Inactive</li><li>**2** - Active</li></ul> | integer |
| syncTime | The time when the agent syncs status to Elements. | string |
| collectTime | The time when the agent finishes collecting logs. | string |
| connectionStatus | Status of connection between the agent and LDAP server. <ul><li>**0** - Connected</li><li>**1** - Disconnected</li></ul> | integer |
| advanceMessage | Some detailed tips for the partner to manage the agent connection status. Format: domainname : message | string |

## Request Sample

To use this API, send a GET request to the specified endpoint, including necessary parameters as defined in the references.

```json
https://graph.avepointonlineservices.com/partner/external/v3/um/customers/966f35cc-****-25v7-****-25cdbcf82a07/tenants/0c7715b3-****-17b9-****-f3634dcfacec/agents
```


## Response Sample

If the request has been successfully processed, a 200 OK response will be returned along with the requested information displayed in the response body. For more details on the HTTP status code, refer to [Http Status Code](../../Use-AvePoint-Graph-API.md#http-status-code).

```json 
{
     [
        {
            "id": "c2aa00d3-****-36v7-****-9e9c79232bff", // The ID of the agent
            "serverName": "win2025server.testhybrid.com", // The local server name of the agent
            "version": "3.3.21.529", // The version of the agent
            "status": 2, // The basic status of the agent
            "syncTime": "2026-01-01T00:00:00Z", // The time when the agent syncs status to Elements
            "collectTime": "2026-01-01T00:00:00Z", // The time when the agent finishes collecting logs
            "connectionStatus": 0, // Status of connection between the agent and LDAP server
            "advanceMessage": "credential changed for the password, you need update" // Some detailed tips for the customer to manage the agent
        }
    ]
}
