# Retrieve Specific Customers

Use this API to access information for a specific  customer that you manage.


## Permissions  

The following permission is required to call the API.  
You must register an app through Elements for Partners > API app registration to authenticate and authorize your access to AvePoint Graph API. For details, refer to [App Registration](https://cdn.avepoint.com/assets/apelements-webhelp/avepoint-elements-for-partners/index.htm#!Documents/appregistration.htm).

| API | Permission  |
|-----------|----------|
| `/partner/customers/{id}` |partner.customers.read.all|  

## Request  

This section provides details on the HTTP method and endpoint used to retrieve a specific customer's information.

| Method | Endpoint | Description |
| --- | --- | --- |
| GET | `/partner/customers/{id}` | Retrieves the general information of a specific customer that you manage. |

## Query Parameters  

This section outlines the parameters required to specify which customer's general information you want to retrieve.  

| Parameter | Description | Type | Required |
| --- | --- | --- | --- |
| Id | The tenant owner ID of the customer. | string | Yes |

## Response

If the request has been successfully processed, a 200 OK response will be returned along with the requested information displayed in the response body.

| Response | Description | Type |
| --- | --- | --- |
| id | The tenant owner ID of the customer. | string |
| organization | The organization name of the customer. | string |
| ownerEmail | The tenant owner email address of the customer. | string |
| jobStatus | The status of the customer’s tenant. | string |
| countryOrRegion | The country or region name of the customer. | string |

## Request Sample

To use this API, send a GET request to the specified endpoint, including necessary parameters as defined in the references. 

```json
https://graph.avepointonlineservices.com/partner/customers/00427fbc-8832-46cf-a1d2-582fa46ec63
```

## Response Sample  

If the request has been successfully processed, a 200 OK response will be returned along with the requested information displayed in the response body. For more details on the HTTP status code, refer to [HttpStatusCode](https://learn.avepoint.com/docs/Use-AvePoint-Graph-Modern-API.html#http-status-code).

```json
{
    "@odata.context": "https://graph.avepointonlineservices.com/partner/$metadata#Customers/$entity",
    "id": "00427fbc-8832-46cf-a1d2-582fa46ec638", // The tenant owner ID of the customer
    "organization": "AvePoint test", // The organization name of the customer
    "ownerEmail": "aptest***s8@avepoint.com", // The tenant owner email address of the customer
    "jobStatus": "Working", // The status of the customer’s tenant
    "countryOrRegion": "Vietnam" // The country or region name of the customer.
}