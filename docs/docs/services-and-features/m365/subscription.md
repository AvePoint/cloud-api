# Retrieve Subscription Consumption

Get the subscription consumption information (`/cloudbackup/licenseconsumption` navigation property) of Cloud Backup for Microsoft 365. By invoking the `/cloudbackup/licenseconsumption` endpoint, users can gain comprehensive insights into subscription usage, facilitating efficient resource management and ensuring service compliance.  

## Permission

The following permission is required to call this API.  
You must register an app through AvePoint Online Services > App registration to authenticate and authorize your access to AvePoint Graph Modern API. For details, refer to [Authentication and Authorization](https://learn.avepoint.com/docs/Use-AvePoint-Graph-Modern-API.html#authentication-and-authorization).

| API   | Permission  |
|-------------------|----------------------|
|`/cloudbackup/licenseconsumption`|microsoft365backup.subscriptionInfo.read.all |

## Request

| Method | Path | Description |
| --- | --- | --- |
| GET | `/cloudbackup/licenseconsumption` | Gets the subscription consumption information of Cloud Backup for Microsoft 365. |

## Responses

The API provides detailed metrics on subscription consumption, aiding in understanding resource allocation and usage. It includes data on user seats and storage, offering crucial insights for managing resources effectively and ensuring compliance with subscription limits.

| Elements | Description | Type |
| --- | --- | --- |
| outOfPolicyTime | The UTC timestamp when the subscription went out of policy. | long |
| purchasedUserSeats | Total number of purchased user seats | int |
| assignedUserSeats | Number of user seats currently assigned | int |
| purchasedStorageSize | Total purchased storage size (in GB) | int |
| protectedSize | Protected data size (in GB) | int |

## Response Sample

If successful, this method returns a 200 OK response code and a collection of jobs in the response body.  
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
