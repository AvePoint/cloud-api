# Retrieve Subscription Consumption

The `/cloudbackup/licenseconsumption` API endpoint empower users to monitor subscription consumption through standardized HTTP GET requests. This API offers comprehensive insights into subscription usage, helping users manage resources efficiently and ensure compliance with their service agreements.  

## Permission

The following permission is required to call this API.  
You must register an app through AvePoint Online Services > App registration to authenticate and authorize your access to AvePoint Graph Modern API. For details, refer to [Authentication and Authorization](/Use%20AvePoint%20Graph%20Modern%20API.md/#authentication-and-authorization)

| API   | Permission  |
|-------------------|----------------------|
|`/cloudbackup/licenseconsumption`|microsoft365backup.subscriptionInfo.read.all |

## API Method

| Method | Path | Description |
| --- | --- | --- |
| GET | `/cloudbackup/licenseconsumption` | Gets the subscription consumption information of Cloud Backup for Microsoft 365. |

## Responses

If the request has been successfully processed, a 200 OK response will be returned along with the requested information displayed in the response body.

| Response | Description | Type |
| --- | --- | --- |
| OutOfPolicyTime | The UTC timestamp when the subscription went out of policy. | long |
| PurchasedUserSeats | Total number of purchased user seats | int |
| AssignedUserSeats | Number of user seats currently assigned | int |
| PurchasedStorageSize | Total number of purchased storage size(in GB) | int |
| ProtectedSize | Amount of protected size(in GB) | int |

## Response Example (`application/json`):

The response provides detailed metrics on subscription consumption, helping you understand how resources are allocated and used. It includes information about user seats and storage. This insights is crucial for managing resources effectively and ensuring compliance with subscription limits.  

```ts
{
  OutOfPolicyTime?: long
  PurchasedUserSeats?: int
  AssignedUserSeats?: int
  PurchasedStorageSize?: int
  ProtectedSize?: int
}
```
