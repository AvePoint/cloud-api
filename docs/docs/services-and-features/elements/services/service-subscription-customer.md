# Elements API

Elements provides APIs to retrieve information of your customers, including services, job details, and scan profiles.

## Permissions  

The following permission is required to call the APIs.  
You must register an app through AvePoint Online Services > App registration to authenticate and authorize your access to AvePoint Graph Modern API. For details, refer to [Authentication and Authorization](/docs/docs/Use%20AvePoint%20Graph%20Modern%20API.md/#authentication-and-authorization)

| API |Method| Description | Permission Required |
|-----------|--------|-------|--------|
| [/Services/{id}](#getservicesid) | GET | Get the service subscription details of a specific customer that you manage. | partner.license.read.all |  

## References

### [GET]/Services/{id}

Get the service subscription details for a specific customer that you manage.

#### Parameters (Query)
| Parameter | Description | Type |
| --- | --- | --- |
| Id | The tenant owner ID of the customer. | String |

#### Responses

If the request has been successfully processed, a 200 OK response will be returned along with the requested information displayed in the response body.

| Response | Description | Type |
| --- | --- | --- |
| CustomerId | The tenant owner ID of the customer. | String |
| Organization | The organization name of the customer. | String |
| Customer | The tenant owner email address of the customer. | String |
| TenantId | The tenant ID of the customer. | String |
| Service | The service that the customer has subscriptions for. | String |
| SubscriptionModel | The subscription model of the customer’s service. | String |
| PurchasedUserSeats | The number of purchased user seats of the customer. | String |
| MicrosoftLicenseAssigned | The number of assigned Microsoft licenses of the customer. | String |
| MicrosoftLicenseAvailable | The number of available Microsoft licenses of the customer. | String |
| PurchasedCapacity | The purchased capacity of the customer. | String |
| Storage | The storage type of the customer. | String |
| Retention | The data retention period of the customer. | String |
| ConsumedStorage | The consumed storage size of the customer. | String |
| ExpirationDate | The expiration date of the customer’s service. | String |