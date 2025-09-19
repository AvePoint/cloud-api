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
|dataCenter           |The data center id of the customer. <ul><li>**Commercial env**</li><li>**0b635b49-4c56-4e52-800a-1fa79b2d5b08** - Australia Southeast (Victoria)</li><li>**7b9835ec-7299-4177-85e3-ba5cb3b2e0411** - Canada Central (Toronto)</li><li>**e44bb3ed-f1d8-4055-8c77-c8fd8cd634092** - East US (Virginia)</li><li>**49681f94-26a7-4825-aca2-df2eca7c0f81** - France Central (Paris)</li><li>**ab2faf29-9e66-45ce-bf37-32f8cf484fb2** - GCP for Australia Southeast (Sydney)</li><li>**7bd9748b-b52b-4e4d-9389-e70dccee3b2d** - GCP for East US (Moncks Corner)</li><li>**4f77581e-1a6f-47fd-9f68-9134a4f6989b** - GCP for Japan (Tokyo)</li><li>**8998f218-708f-4084-8647-32ed67042487** - GCP for South Korea (Seoul)</li><li>**e38cb1b7-efa9-490e-ab46-83b45a94d1da** - GCP for West Europe (Eemshaven, Netherlands)</li><li>**3225f6f8-a98c-425e-8279-c6696d99659d** - Germany West Central (Frankfurt)</li><li>**ca577c72-83bd-454c-af62-da3d0586691d** - Japan West (Osaka)</li><li>**e4f66389-8219-4432-9af1-01a9fe62a640** - Korea Central (Seoul)</li><li>**f1cdd2b2-ac32-4509-8784-fb2b947ef519** - North Europe (Ireland)</li><li>**0d4a9846-97ad-4c09-bb1c-8fbe93eaf3c6** - Southeast Asia (Singapore)</li><li>**f8ccd75d-d979-417c-96ee-ae256a3af091** - Switzerland North (Zurich)</li><li>**d95b9c82-a426-400f-8256-70646fdd1b4f** - UK South (London)</li><li>**4f93bdff-9b11-47b9-aa68-a86bfa09f61c** - West Europe (Netherlands)</li><li>**GOV env**</li><li>**d9210f50-bdb1-4f8f-a2bb-99694d11f2da** - US Gov Virginia (Virginia)</li></ul>              |string      |Yes|
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

To use this API, send a POST request to the specified endpoint.

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