# Onboard a Customer

Use this API to onboard a customer to the current partner.

## Permission

The following permission is required to call the API.  
You must register an app through Elements > API app registration to authenticate and authorize your access to AvePoint Graph API. For details, refer to [App Registration](../../../elements/register-app.md).  

| API  | Permission  |
|-----------|--------|
| `/partner/external/v3/general/customers` | elements.customers.readwrite.all     |

## Request

This section provides details on the HTTP method and endpoint used to onboard customers to the current partner.

| Method | Endpoint | Description |
| --- | --- | --- |
| POST | `/partner/external/v3/general/customers` | Onboard a customer to the current partner. |

## Request Body Parameters

You can provide a customer basic information in the request body to onboard a customer. This field is required.

|Parameter|Description | Type|Required?|
|---|---|---|---|
|firstName            |The first name of the customer.                   |string      |Yes|
|lastName             |The last name of the customer.                    |string      |Yes|
|organizationName     |The organization name of the customer.            |string      |Yes|
|registrationAccount  |The registration account of the customer.         |string      |Yes|
|countryCode          |The country code of the customer.                 |string      |Yes|
|telephoneNumber      |The telephone number of the customer.             |string      |No |
|dataCenter           |The data center ID of the customer. Commercial environment:<ul></li><li>**0b635b49-4c56-4e52-800a-1fa79b2d5b08** - Australia Southeast (Victoria)</li><li>**7b9835ec-7299-4177-85e3-ba5cb3b2e0411** - Canada Central (Toronto)</li><li>**e44bb3ed-f1d8-4055-8c77-c8fd8cd634092** - East US (Virginia)</li><li>**49681f94-26a7-4825-aca2-df2eca7c0f81** - France Central (Paris)</li><li>**ab2faf29-9e66-45ce-bf37-32f8cf484fb2** - GCP for Australia Southeast (Sydney)</li><li>**7bd9748b-b52b-4e4d-9389-e70dccee3b2d** - GCP for East US (Moncks Corner)</li><li>**4f77581e-1a6f-47fd-9f68-9134a4f6989b** - GCP for Japan (Tokyo)</li><li>**8998f218-708f-4084-8647-32ed67042487** - GCP for South Korea (Seoul)</li><li>**e38cb1b7-efa9-490e-ab46-83b45a94d1da** - GCP for West Europe (Eemshaven, Netherlands)</li><li>**3225f6f8-a98c-425e-8279-c6696d99659d** - Germany West Central (Frankfurt)</li><li>**ca577c72-83bd-454c-af62-da3d0586691d** - Japan West (Osaka)</li><li>**e4f66389-8219-4432-9af1-01a9fe62a640** - Korea Central (Seoul)</li><li>**f1cdd2b2-ac32-4509-8784-fb2b947ef519** - North Europe (Ireland)</li><li>**0d4a9846-97ad-4c09-bb1c-8fbe93eaf3c6** - Southeast Asia (Singapore)</li><li>**f8ccd75d-d979-417c-96ee-ae256a3af091** - Switzerland North (Zurich)</li><li>**d95b9c82-a426-400f-8256-70646fdd1b4f** - UK South (London)</li><li>**4f93bdff-9b11-47b9-aa68-a86bfa09f61c** - West Europe (Netherlands)</li></ul>GOV environment:<ul></li><li>**d9210f50-bdb1-4f8f-a2bb-99694d11f2da** - US Gov Virginia (Virginia)</li></ul>              |string      |Yes|
|password             |The password of the customer.                     |string      |Yes|
|tags                 |The tags of the customer.                         |string[]    |No |
|managementMode       |The management mode of the customer.              |boolean     |No |

## Response

If the request has been successfully processed, a 200 OK response will be returned along with the onboarding status and customer ID displayed in the response body.

| Response | Description | Type |
| --- | --- | --- |
| id     | The ID of the onboarded customer.     | string |
| status | The status of the customer.<ul><li>**1** - Successful</li><li>**2** - Failed</li><li>**3** - Customer does not exist</li><li>**4** - Failed to register customer</li><li>**5** - Customer is managed by current partner</li><li>**6** - Customer is the same as current partner</li><li>**7** - Customer already exists</li></ul> | integer |

## Request Sample

To use this API, send a POST request to the specified endpoint.

```json
https://graph.avepointonlineservices.com/partner/external/v3/general/customers

{
    "firstName":"Tony", // The first name of the customer
    "lastName":"Brown", // The last name of the customer
    "organizationName":"OrganizationABC", // The organization name of the customer
    "RegistrationAccount": "user@domain.com", // The registration account of the customer
    "password":"**********", // The password of the customer
    "countryCode":"AF", // The country code of the customer
    "dataCenter":"7e4ffcae-****-****-****-c6ef****50d5", // The data center ID of the customer
    "tags":["tagA"] // The tags of the customer
}
```

## Response Sample  

If the request has been successfully processed, a 200 OK response will be returned along with the requested information displayed in the response body. For more details on the HTTP status code, refer to [Http Status Code](../../../elements/Use-AvePoint-Graph-API.md#http-status-code).

```json
{
    "status":1, //The status of onboarding the customer: 1 represents Successful
    "id":"76f5dc9e-****-****-****-d7ef****36i5" //The ID of the customer
}