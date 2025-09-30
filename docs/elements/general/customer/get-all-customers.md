# Retrieve All Customers Managed by Current Partner

Use this API to retrieve the information of all customers managed by the current partner.

 ## Permission

The following permission is required to call the API.  
You must register an app through Elements > API app registration to authenticate and authorize your access to AvePoint Graph API. For details, refer to [App Registration](../../../elements/register-app.md).

| API | Permission  |
|-----------|--------|
| `/partner/external/v3/general/customers/batch`|elements.customers.read.all|  

## Request

This section outlines the details of the HTTP method and endpoint used to retrieve customers managed by the current partner.

| Method | Endpoint | Description |
|-----------|--------|------------|
| POST | `/partner/external/v3/general/customers/batch` | Retrieve customers managed by the current partner.|
 

## Query Parameters

This section outlines the parameters that allow users to specify pagination.

| Parameter | Description | Type | Required |
| --- | --- | --- | --- |
| pageIndex | The starting number of the page to get the violated objects. The default value is 1. | integer | No |
| pageSize | The number of objects to display on one page. The default value is 50 and the maximum value allowed is 100. | integer | No |

## Request Body Parameters

This section outlines the request body required to specify the customers you want to retrieve.

| Parameter | Description | Type | Required |
| --- | --- | --- | --- |
| customerId | The ID of the customer to be retrieved. | string | No |

## Response

If the request has been successfully processed, a 200 OK response will be returned along with the requested information displayed in the response body.

| Field | Description | Type |
| --- | --- | --- |
| id               | The ID of the customer.                 | string |
| organization     | The organization name of the customer.       | string |
| ownerEmail       | The email address of the customer.      | string |
| jobStatus        | The job status of the customer.<ul><li>**0** - N/A</li><li>**1** - Working</li><li>**2** - Failed</li><li>**3** - Waiting for configuration</li><li>**4** - Multiple issues found</li><li>**5** - Finished with exception</li><li>**6** - No backup update</li></ul>                                                     | integer |
| countryOrRegion  | The country or region of the customer.            | string |
| managementMode   | The management mode of the user.<ul><li>**0** - Customer management of tenant</li><li>**1** - Partner management of tenant</li><li>**2** - To be configured</li></ul>        | integer    |
| tenants          | The tenant information of the customer.               | list |

**Tenant information**:

| Field | Description | Type |
| --- | --- | --- |
| id               | The ID of the tenant.                 | string |
| name             | The name of the tenant.               | string |

## Request Sample
To use this API, send a POST request to the specified endpoint, including necessary parameters as defined in the references.
```json
https://graph.avepointonlineservices.com/partner/external/v3/general/customers/batch
```
 
## Response Sample
If the request has been successfully processed, a 200 OK response will be returned along with the requested information displayed in the response body.
For more details on the HTTP status code, refer to [Http Status Code](../../Use-AvePoint-Graph-API.md#http-status-code).
```json
{
    "data": [
        {
            "id": "03f7382e-****-****-****-dd9af05974f0", //The customer ID
            "organization": "OrganizationABC", //The organization name of the customer
            "ownerEmail": "user@domain.com", //The email address of the customer
            "jobStatus": 0, //The job status of the customer: 0 represents N/A
            "countryOrRegion": "Afghanistan", //The country or region of the customer
            "managementMode": 1, //The management mode of the customer: 1 represents partner management mode of tenant.
            "tenants":
            [
                {
                    "id":"03f7382e-xxxx-xxxx-xxxx-dd9af05974f0", //The ID of the tenant
                    "name":"Tenant ABC" //The name of the tenant
                }
            ]
        },
        {
            "id": "03f7382e-****-****-****-dd9adcs974f0",
            "organization": "OrganizationDEF",
            "ownerEmail": "userA@domain.com",
            "jobStatus": 0,
            "countryOrRegion": "Afghanistan",
            "managementMode": 2,
            "tenants":
            [

            ]
        }
    ],
    "metadata": {
        "pageIndex": 1, // The current display page
        "pageSize": 50, // The number of objects on the display page
        "totalCount": 2 // The total number of objects matching the query parameters
    }
}
```