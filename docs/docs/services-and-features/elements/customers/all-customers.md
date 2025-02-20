# Retrieve All Customers

Use this API to access general information for all of your customers. 

## Permissions  

The following permission is required to call the API.  
You must register an app through Elements for Partners > App registration to authenticate and authorize your access to AvePoint Graph API. For details, refer to [App Registration](https://cdn.avepoint.com/assets/apelements-webhelp/avepoint-elements-for-partners/index.htm#!Documents/appregistration.htm).  

| API  | Permission  |
|-----------|--------|
| `/partner/customers` | partner.customers.read.all|  

## Request

This section provides details on the HTTP method and endpoint used to retrieve general information for all of your customers.

| Method | Endpoint | Description |
| --- | --- | --- |
| GET | `/partner/customers` | Retrieves general information for all of your customers. |

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

To use this API, send a GET request to the specified endpoint.

```json
https://graph.avepointonlineservices.com/partner/customers
```

## Response Sample  

If the request has been successfully processed, a 200 OK response will be returned along with the requested information displayed in the response body. For more details on the HTTP status code, refer to [HttpStatusCode](https://learn.avepoint.com/docs/Use-AvePoint-Graph-Modern-API.html#http-status-code).

```json
{
    "@odata.context": "https://graph.avepointonlineservices.com/partner/$metadata#Customers",
    "value": [
        {
            "id": "00427fbc-8832-****-***-582fa46ec638", // The tenant owner ID of the customer
            "organization": "AvePoint test", // The organization name of the customer
            "ownerEmail": "aptest***opus8@avepoint.com", // The tenant owner email address of the customer
            "jobStatus": "Working", //The status of the customer’s tenant
            "countryOrRegion": "Vietnam" // The country or region name of the customer
        },
        {
            "id": "0088e14d-5275-****-***-bcb9fc33ebdb",
            "organization": "AvePoint test",
            "ownerEmail": "aptest***opus9@avepoint.com",
            "jobStatus": "Working",
            "countryOrRegion": "Vietnam"
        },
        {
            "id": "00e4dde9-9b3f-****-***-25705db15101",
            "organization": "AvePoint HN test",
            "ownerEmail": "aptest***pg@avepoint.com",
            "jobStatus": "Working",
            "countryOrRegion": "United States"
        }
    ]
}