# Retrieve Customer Details

The `/customers/{id}` API retrieves the general information of a specific customer that you manage.

## Permissions  

The following permission is required to call the APIs.  
You must register an app through Elements for Partners > App Registration to authenticate and authorize your access to AvePoint Graph Modern API. For details, refer to [App Registration](https://cdn.avepoint.com/assets/apelements-webhelp/avepoint-elements-for-partners/index.htm#!Documents/appregistration.htm)

| API | Permission Required |
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

