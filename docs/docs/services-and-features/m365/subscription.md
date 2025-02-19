# Retrieve Subscription Consumption

Get the subscription consumption information (`/backup/m365/licenseconsumption` navigation property) of Cloud Backup for Microsoft 365. By invoking the `/backup/m365/licenseconsumption` endpoint, users can gain comprehensive insights into subscription usage, facilitating efficient resource management and ensuring service compliance.  

## Permission

The following permission is required to call this API.  
You must register an app through AvePoint Online Services > App registration to authenticate and authorize your access to AvePoint Graph Modern API. For details, refer to [Authentication and Authorization](https://learn.avepoint.com/docs/Use-AvePoint-Graph-Modern-API.html#authentication-and-authorization).

| API   | Permission  |
|-------------------|----------------------|
|`/backup/m365/licenseconsumption`|microsoft365backup.subscriptionInfo.read.all |

## Request

This section outlines the HTTP method and endpoint used to retrieve the subscription consumption information. It provides a concise description of the action performed by the API call.

| Method | Path | Description |
| --- | --- | --- |
| GET | `/backup/m365/licenseconsumption` | Gets the subscription consumption information of Cloud Backup for Microsoft 365. |

## Responses

The API provides detailed metrics on subscription consumption, aiding in understanding resource allocation and usage. It includes data on user seats and storage, offering crucial insights for managing resources effectively and ensuring compliance with subscription limits.

| Elements | Description | Type |
| --- | --- | --- |
| outOfPolicyTime | The UTC timestamp when the subscription went out of policy. | long |
| purchasedUserSeats | Total number of purchased user seats | integer |
| assignedUserSeats | Number of user seats currently assigned | integer |
| purchasedStorageSize | Total purchased storage size (in GB) | integer |
| protectedSize | Protected data size (in GB) | integer |

## Request Sample

To use this API, send a GET request to the specified endpoint. This will return the subscription consumption information in a structured format, enabling easy integration with other systems or applications. The following request is an API call to the Cloud Backup for Microsoft 365 environment in the US - East region.

```json
https://graph-us.avepointonlineservices.com/backup/m365/licenseconsumption
```

## Response Sample

If successful, this method returns a 200 OK response code and the subscription consumption information in the response body.  
For details on the HTTP status code, refer to [HttpStatusCode](https://learn.avepoint.com/docs/Use-AvePoint-Graph-Modern-API.html#http-status-code).

```json
{
    "outOfPolicyTime": 0, // UTC timestamp for when the subscription expires
    "purchasedUserSeats": 100, //Total number of purchased user seats
    "assignedUserSeats": 47, // Current number of assigned user seats.
    "purchasedStorageSize": 0, //Total purchased storage capacity (in GB)
    "protectedSize": 0, //Protected storage size (in GB).
}
```
