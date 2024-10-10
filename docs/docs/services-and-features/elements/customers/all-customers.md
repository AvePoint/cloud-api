# List All Customers

The  to retrieve information of your customers, including services, job details, and scan profiles.

## Permissions  

The following permission is required to call the APIs.  
You must register an app through AvePoint Online Services > App registration to authenticate and authorize your access to AvePoint Graph Modern API. For details, refer to [Authentication and Authorization](/Use%20AvePoint%20Graph%20Modern%20API.md/#authentication-and-authorization)

| API  | Permission  |
|-----------|--------|
| `/customers` | partner.customers.read.all|  

## API Method

| Method | Path | Description |
| --- | --- | --- |
| GET | `customers` | Gets the job information of Cloud Backup for Microsoft 365. |

## Response

If the request has been successfully processed, a 200 OK response will be returned along with the requested information displayed in the response body.

| Response | Description | Type |
| --- | --- | --- |
| Id | The tenant owner ID of the customer. | String |
| Organization | The organization name of the customer. | String |
| OwnerEmail | The tenant owner email address of the customer. | String |
| JobStatus | The status of the customer’s tenant. | String |
| CountryOrRegion | The country or region name of the customer. | String |

## Response Example 

