# Onboard a customer to current partner

Use this API to onboard a customer to current partner.

## Permissions  

The following permission is required to call the API.  
You must register an app through Elements > API app registration to authenticate and authorize your access to AvePoint Graph API. For details, refer to [App Registration](https://cdn.avepoint.com/assets/apelements-webhelp/avepoint-elements-for-partners/index.htm#!Documents/appregistration.htm).  

| API  | Permission  |
|-----------|--------|
| `/partner/external/v3/general/customers` | elements.customers.readwrite.all     |

## Request

This section provides details on the HTTP method and endpoint used to onboard customers to current partner.

| Method | Endpoint | Description |
| --- | --- | --- |
| POST | `/partner/external/v3/general/customers` | Onboard a customer to current partner. |

## Request Body Parameters

You can provide a customer basic information in the request body to onboard a customer. This field is required.

|Parameter|Description | Type|Required?|
|---|---|---|---|
|firstName            |The first name of the customer.                   |string      |Yes|
|lastName             |The last name of the customer.                    |string      |Yes|
|organizationName     |The organization name of the customer.            |string      |Yes|
|registrationAccount  |The Registration account of the customer.         |string      |Yes|
|countryCode          |The country code of the customer.                 |string      |Yes|
|telephoneNumber      |The telephone number of the customer.             |string      |No |
|dataCenter           |The data center id of the customer.               |string      |Yes|
|password             |The password of the customer.                     |string      |Yes|
|tags                 |The tags of the customer.                         |string array|No |
|managementMode       |The management mode of the customer.              |bool        |Yes|

## Response

If the request has been successfully processed, a 200 OK response will be returned along with the created status and customer id displayed in the response body.

| Response | Description | Type |
| --- | --- | --- |
| id     | The id of the created customer.     | string |
| status | The status of the created customer.<ul><li>**1** - Success</li><li>**2** - Add to current partner failed</li><li>**3** - Customer is not exist</li><li>**4** - Register customer failed</li><li>**5** - Customer is managed by current partner</li><li>**6** - Customer is same as current partner</li><li>**7** - Customer is exist</li></ul> | int |

## Request Sample

To use this API, send a GET request to the specified endpoint.

```json
https://graph-us.avepointonlineservices.com/partner/external/v3/general/customers

{
    "firstName":"A",
    "lastName":"P",
    "organizationName":"test_open_api_07",
    "RegistrationAccount":"test_open_api_07@163.com",
    "password":"demo12!@",
    "countryCode":"AF",
    "dataCenter":"7e4ffcae-xxxx-xxxx-xxxx-c6efa0b250d5",
    "tags":["test3"]
}
```

## Response Sample  

If the request has been successfully processed, a 200 OK response will be returned along with the created customer id and status displayed in the response body. For more details on the HTTP status code, refer to [HttpStatusCode](https://learn.avepoint.com/docs/Use-AvePoint-Graph-API.html#http-status-code).

```json
{
    "status":1,
    "customerId":"76f5dc9e-xxxx-xxxx-xxxx-d7efa0b536i5"
}