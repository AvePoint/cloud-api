# List All Customers

The `/partner/customers` API to retrieve general information of your customers. This endpoint is crucial for understanding customer details and maintaining effective partnership.  

## Permissions  

The following permission is required to call the APIs.  
You must register an app through Elements for Partners > App Registration to authenticate and authorize your access to AvePoint Graph Modern API. For details, refer to [App Registration](https://cdn.avepoint.com/assets/apelements-webhelp/avepoint-elements-for-partners/index.htm#!Documents/appregistration.htm)  

| API  | Permission  |
|-----------|--------|
| `/partner/customers` | partner.customers.read.all|  

## API Method

This section provides details on the method used to retrieve customer information.

| Method | Path | Description |
| --- | --- | --- |
| GET | `/partner/customers` | Gets the general information of the customers that you manage. |

## Response

If the request has been successfully processed, a 200 OK response will be returned along with the requested information displayed in the response body.

| Response | Description | Type |
| --- | --- | --- |
| Id | The tenant owner ID of the customer. | String |
| Organization | The organization name of the customer. | String |
| OwnerEmail | The tenant owner email address of the customer. | String |
| JobStatus | The status of the customer’s tenant. | String |
| CountryOrRegion | The country or region name of the customer. | String |

## Response Sample  

This section provides an example of the response you can expect when the API request is successfully processed.  
