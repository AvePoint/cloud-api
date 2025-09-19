# Get all customers managed by current partner

Use this API to get all customers managed by current partner. 

 ## Permissions

The following permission is required to call the API.  
You must register an app through Elements > API app registration to authenticate and authorize your access to AvePoint Graph API. For details, refer to [App Registration](https://cdn.avepoint.com/assets/apelements-webhelp/avepoint-elements-for-partners/index.htm#!Documents/appregistration.htm).

| API | Permission  |
|-----------|--------|
| `partner/external/v3/general/customers`|elements.customers.read.all|  

## Request

This section outlines the details of the HTTP method and endpoint used to get all customers managed by current partner.

| Method | Endpoint | Description |
|-----------|--------|------------|
| GET | `partner/external/v3/general/customers` | Get all customers managed by current partner.|
 

## Query Parameters

This section outlines the parameters optional required to specify paging information about the users you want to retrieve.

| Parameter | Description | Type | Required |
| --- | --- | --- | --- |
| pageIndex | The page number of the data which will be retrieve, the default value is 1. | integer | False |
| pageSize | The number of customers API will retrieved in a time, the default value is 100. | integer | False |

## Response

If the request has been successfully processed, a 200 OK response will be returned along with the requested information displayed in the response body.
 
| Field | Description | Type |
| --- | --- | --- |
| id               | The ID of the customer.                 | string |
| organization     | The organization of the customer.       | string |
| ownerEmail       | The email address of the customer.      | string |
| jobStatus        | The job status of the customer.<ul><li>**0** - N/A</li><li>**1** - Working</li><li>**2** - Failed</li><li>**3** - Waiting for Configuration</li><li>**4** - Multiple Issues Found</li><li>**5** - Finished with Exception</li><li>**6** - No Backup Update</li></ul>                                                     | string |
| countryOrRegion  | The country of the customer.            | string |
| managementMode   | The management mode of the user.        | int    |
| tenants.Id       | The id of the tenant.                   | string |
| tenants.Name     | The name of the tenant.                 | string |

## Request Sample
To use this API, send a GET request to the specified endpoint, including necessary parameters as defined in the references.
```json
https://graph.avepointonlineservices.com/partner/external/v3/general/customers
```
 
## Response Sample
If the request has been successfully processed, a 200 OK response will be returned along with the requested information displayed in the response body.
For more details on the HTTP status code, refer to [Http Status Code](https://learn.avepoint.com/docs/Use-AvePoint-Graph-API.html#http-status-code).
```json
{
    "data": [
        {
            "id": "03f7382e-xxxx-xxxx-xxxx-dd9af05974f0",
            "organization": "test_fly_license_06",
            "ownerEmail": "test_xxx@163.com",
            "jobStatus": "N/A",
            "countryOrRegion": "Afghanistan",
            "managementMode": 1,
            "tenants":
            [
                {
                    "id":"03f7382e-xxxx-xxxx-xxxx-dd9af05974f0",
                    "name":"v40t"
                }
            ]
        },
    ],
    "metadata": {
        "pageIndex": 1,
        "pageSize": 50,
        "totalCount": 1
    }
}
```