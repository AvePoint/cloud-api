# Retrieve Customer Details

The `/customers/{id}` API retrieves the general information of a specific customer that you manage.

## Permissions  

The following permission is required to call the APIs.  
You must register an app through AvePoint Online Services > App registration to authenticate and authorize your access to AvePoint Graph Modern API. For details, refer to [Authentication and Authorization](/Use%20AvePoint%20Graph%20Modern%20API.md/#authentication-and-authorization)

| API || Permission Required |
|-----------|----------|

| `/customers/{id}` |partner.customers.read.all|  

## Query Parameters  

| Parameter | Description | Type |
| --- | --- | --- |
| Id | The tenant owner ID of the customer. | String |

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

