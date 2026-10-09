# Add a Customer's Tenants to Modules

Use this API to add a customer's tenants to modules. Currently, this API only supports adding tenants to the User Management module.

## Permission

The following permission is required to call the API.  
You must register an app through Elements > API app registration to authenticate and authorize your access to Elements API. For details, refer to [App Registration](../../../elements/register-app.md).  

| API  | Permission  |
|-----------|--------|
| `/partner/external/v3/general/customers/connecttenant` | elements.customers.readwrite.all     |

## Request

This section provides details on the HTTP method and endpoint used to add a customer's tenants to modules.

| Method | Endpoint | Description |
| --- | --- | --- |
| POST | `/partner/external/v3/general/customers/connecttenant` | Adds a customer's tenants to modules. |

## Request Body Parameters

This section outlines the request body parameters required to add a customer's tenants to modules.

|Parameter|Description | Type|Required?|
|---|---|---|---|
|customerId | The ID of the customer.  | string | Yes |
|tenantIds  |The list of tenant IDs.   |`array[string]`      |Yes|
|productName |The module name: <ul><li>**PartnerUserManagement** - User management</li> |`array[string]` |Yes|
|hybridTenant  |Indicates whether the tenant is hybrid or not.  |boolean  |Yes |

## Response

If the request has been successfully processed, a 200 OK response will be returned along with the requested information displayed in the response body.

| Response | Description | Type |
| --- | --- | --- |
| ConnectTenantsResult     | The operation status and information.     | `list<string>` |
| FailedProducts | The failed services and reason. | `list<string>` |

**Operation Status and Information**

| Field | Description | Type |
| --- | --- | --- |
| isSuccess               | Indicate whether the request was processed successfully.                 | boolean |
| errorCode             | The detailed error code:  <ul><li>**0** - None</li><li>**1** - There are not enough subscriptions for assignment</li><li>**2** - The tenant has not been consented</li><li>**3** - The tenant is not found</li><li>**4** - The module is not supported</li></ul>| integer |

**Module Information**

| Field | Description | Type |
| --- | --- | --- |
| productName               | The name of the module.                 | string |
| errorCode             | The detailed error code: <ul><li>**0** - None</li><li>**1** - There are not enough subscriptions for assignment</li><li>**2** - The tenant has not been consented</li><li>**3** - The tenant is not found</li><li>**4** - The module is not supported</li></ul>| integer |


## Request Sample

To use this API, send a POST request to the specified endpoint.

```json
https://graph.avepointonlineservices.com/partner/external/v3/general/customers/connecttenant

{
    "CustomerId":"c1488793-****-****-****-5fac395afd75", // The ID of the customer
    "TenantIds":["0c7715b3-****-****-****-f3634dcfacec"], // The list of the tenant IDs
    "ProductName":["PartnerUserManagement","UnknowProduction"], // The name list of the modules
    "HybridTenant": true// Indicates whether the tenant is hybrid
}
```

## Response Sample  

If the request has been successfully processed, a 200 OK response will be returned along with the requested information displayed in the response body. For more details on the HTTP status code, refer to [Http Status Code](../../../elements/Use-AvePoint-Graph-API.md#http-status-code).

```json
{
    "connectTenantsResult": {
        "0c7715b3-****-****-****-f3634dcfacec": {
            "isSuccess": true, // Indicates whether the request was processed successfully
            "errorCode": 0 // The detailed error code
        }
    },
    "failedProducts": {
        "UnknowProduction":4 // The detailed error code
    }
}