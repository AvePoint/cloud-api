# Retrieve Connections Details

Use this API to access and retrieve information of your Power Platform connections.

## Permission

The following permission is required to call the API.
You must register the app through AvePoint Online Services > App registrations to authenticate and authorize your access to AvePoint Graph API.  
For details, refer to [Authentication and Authorization](https://learn.avepoint.com/docs/Use-AvePoint-Graph-API.html#authentication-and-authorization).

| API    | Permission |
|-------------------|---------------|
|`/smp/powerplatform/connections` | enpower.data.read.all | 

## Request

This section provides details on the HTTP method and endpoint used to retrieve general information of your connections.

| Method | Endpoint | Description | 
|--- | --- | --- |
| GET | `/smp/powerplatform/connections` | Retrieves your connections' information | 

## Query Parameters

The API supports several query parameters to refine and customize the data retrieval process.

| Parameters | Description | Type | Required |
|--- | --- | --- | --- |
| top | The number of connection records retrieved and returned each page. The default number is 100. You can enter a number from 1 to 1000. | integer | No |
| tenant | The tenant in which data of connections are retrieved. By default, connections of all tenants are retrieved. | string | No |

## Responses

The API response provides detailed information about the connections retrieved. Each connection in the response includes various attributes that describe its properties and status.

| Elements           | Description                                                           | Type   | 
|--------------------|-----------------------------------------------------------------------|--------|
| connections             | A list containing connections with detailed information.              | list  | 
| totalCount      | Total number of connections retrieved.                   | integer    | 
| nextLink | Reference to the next page of results | string |

**Connection details**

| Elements                        | Description                                                                 | Type    |
|---------------------------------|-----------------------------------------------------------------------------|---------|
| id                              | The unique identifier for the connection.                                   | string  |
| tenantId                        | The unique identifier for the tenant that the connection belongs to.        | string  |
| tenantName                      | The name for the tenant that the connection belongs to.                     | string  |
| containerId                     | The unique identifier for the container that the connection belongs to.      | string  |
| containerName                   | The name for the container that the connection belongs to.                   | string  |
| displayName                     | The display name of the connection                                           | string  |
| iconUri                         | The URI of the icon for the connection.                                       | string  |
| connectorId                     | The unique identifier for the connector.                                    | string  |
| connectorDisplayName            | The name of the connector.                                                  | string  |
| connectorIconBrandColor         | The color of the connector icon.                                            | string  |
| environmentId                   | The unique identifier for the Power Platform environment that the connection belongs to. | string  |
| environmentDisplayName          | The display name of the environment.                                        | string  |
| isCustom | Indicates whether the connection is custom connector based. <br> Valid values: <br> <ul><li> **true** for yes <br> </li><li> **false** for no <br> | boolean
| tier                            | The tier of the connector.                                                  | string  |
| connectorOwnerDisplayName       | The display name of the connector owner.                                    | string  |
| connectorCreatedTime       | The created time of the custom connector.                                    | string  |
| publisher                       | The publisher of the connection.                                            | string  |
| powerAppCount                   | Number of Power Apps using this connection.                                 | integer |
| flowCount                       | Number of Power Automate flows using this connection.                       | integer |
| flowNames                       | The names of Power Automate flows using this connection.                    | list    |
| appNames                        | The names of Power Apps using this connection.                              | list    |
| status                          | The status of the connection.                                               | string  |
| connectionSource                | The source of this connection.                                              | string  |
| ownerId                         | The unique identifier of the connection owner.                              | string  |
| ownerDisplayName                | The display name of the connection owner.                                   | string  |
| ownerUserPrincipalName          | The user principal name of the connection owner.                            | string  |
| ownerStatus                     | The status of the connection owner.                                         | string  |
| ownerCountry       | The country of the connector owner.                                    | string  |

## Request Sample

To use this API, send a GET request to the specified endpoint, including necessary parameters as defined in the references. This will return the relevant object details in a structured format, enabling easy integration with other systems or applications. The following request is an API call to the EnPower environment in the US - East region.

```json
https://graph-us.avepointonlineservices.com/smp/powerplatform/connections
```

## Response Sample

If the request has been successfully processed, a 200 OK response will be returned along with the requested information displayed in the response body. For more details on the HTTP status code, refer to [HTTP Status Code](https://learn.avepoint.com/docs/Use-AvePoint-Graph-API.html#http-status-code).

```json
{
  "connections": [
    {
      "id": "62f0d4b761ea43fda9*****fbd1981fd", // The unique identifier for the connection
      "tenantId": "", // The unique identifier for the tenant that the connection belongs to
      "tenantName": "Sample", // The name for the tenant that the connection belongs to
      "containerId": "", // The unique identifier for the container that the connection belongs to
      "containerName": "Sample-Connections", // The name for the container that the connection belongs to
      "displayName": "Sample Connection", // The display name of the connection
      "iconUri": "", // The URI of the icon for the connection
      "connectorId": "shared_***training", // The unique identifier for the connector
      "connectorDisplayName": "365 Training", // The name of the connector
      "connectorIconBrandColor": "#175497", // The color of the connector icon
      "environmentId": "", // The unique identifier for the Power Platform environment that the connection belongs to
      "environmentDisplayName": "environment", // The display name of the environment
      "isCustom": false, // Indicates whether the connection is custom connector based
      "tier": "Premium", // The tier of the connector
      "connectorOwnerDisplayName": null, // The display name of the connector owner
      "connectorCreatedTime": "", // The created time of the custom connector
      "publisher": "We Speak You Learn, LLC", // The publisher of the connection
      "powerAppCount": 0, // Number of Power Apps using this connection
      "flowCount": 0, // Number of Power Automate flows using this connection
      "flowNames": [], // The names of Power Automate flows using this connection
      "appNames": [], // The names of Power Apps using this connection
      "status": "Connected", // The status of the connection
      "connectionSource": null, // The source of this connection
      "ownerId": "", // The unique identifier of the connection owner
      "ownerDisplayName": "", // The display name of the connection owner
      "ownerUserPrincipalName": "", // The user principal name of the connection owner
      "ownerStatus": "Enabled" // The status of the connection owner
      "ownerCountry": "", // The country of the connection owner
    }
  ],
  "totalCount": 1, 
  "nextLink": "" 
}
