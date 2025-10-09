# Monitor Tenant

Use this API to monitor a tenant by performing specific actions on the tenant. Currently, you can use this API to apply baselines to a tenant.

## Permission  

The following permission is required to call the API.  
You must register an app through Elements > API app registration to authenticate and authorize your access to AvePoint Graph API. For details, refer to [App Registration](../register-app.md).  

| API  | Permission  |
|-----------|--------|
| `/partner/external/v3/bm/customers/{customerId}/tenants/{tenantId}/actions` | elements.bm.tenant.readwrite.all|  

## Request

This section provides details on the HTTP method and endpoint used to monitor a tenant by performing specific actions on the tenant.

| Method | Endpoint | Description |
| --- | --- | --- |
| POST | `/partner/external/v3/bm/customers/{customerId}/tenants/{tenantId}/actions` | Monitors a tenant by performing specific actions on the tenant. |

## URL Parameters

This section describes the query parameters that can be added to the URL when sending a POST request.

| Parameter | Description | Type | Required |
| --- | --- | --- |---|
| customerId | The ID of the customer. | string | Yes |
| tenantId | The ID of the tenant. | string | Yes |

## Request Body Parameters

You can provide a object about the action.

|Parameter|Description | Type|Required?|
|---|---|---|---|
|actionType| The action that you want to perform on a tenant. (More actions will be supported in the future) <ul><li>**1** - Apply baselines to tenant</li></ul> |integer|Yes|
|data| The parameters of the action. |object|Yes|

### Apply Action Data Parameters

For the "Apply baselines to tenant" action, the parameters of the data object are as follows.

|Parameter|Description | Type|Required?|
|---|---|---|---|
|baselineId| The ID of the baseline. |integer|Yes|
|rankingOrder| The ranking order of the baseline among all applied baselines. |integer|Yes|


> [!NOTE]  
> Tenants in the following status cannot perform the "Apply baselines to tenant" action.<ul><li>**3** - Deploying</li><li>**6** - Expired</li><li>**11** - Restoring</li><li>**12** Retrieving setting</li></ul>
> Baselines in the following status cannot be used for the "Apply baselines to tenant" action.<ul><li>**1** - Retrieving settings</li><li>**4** - Settings retrieval failed</li><li>**6** - Draft</li></ul>

## Response

If the request has been successfully processed, a 200 OK response will be returned along with the action result in the response body.

| Response | Description | Type |
| --- | --- | --- |
| jobId | The ID of the job to apply baselines to tenant. | string |

## Request Sample

To use this API, send a POST request to the specified endpoint.

```json
https://graph-us.avepointonlineservices.com/partner/external/v3/bm/customers/38c6a73d-****-****-****-75b0f1959474/tenants/a2145aa5-****-****-****-7fffd6e0cc68/actions

//Apply baseline action
{
    "actionType": "1", // The action that you want to perform on the tenant. 1 represents "Apply baselines to tenant"
    "data": 
    [
        {
            "baselineId": "e12922f4-****-****-****-3a1c162b4cf2", // The ID of the baseline
            "rankingOrder": 1 // The ranking order of the baseline among all applied baselines
        },
        {
            "baselineId": "b4c84bff-****-****-****-3a1c16243555",
            "rankingOrder": 2
        }
    ]
}
```

## Response Sample  

If the request has been successfully processed, a 200 OK response will be returned along with the ID of the applying baselines to tenant job displayed in the response body. For more details on the HTTP status code, refer to [Http Status Code](../Use-AvePoint-Graph-API.md#http-status-code).

```json
{
    "jobId": "7f3b241b-****-****-****-3a1c395524t6" // The ID of the applying baselines to tenant job 
}
```