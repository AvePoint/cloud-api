# Monitor Tenants

Use this API to monitor tenants by performing actions to the tenants.

## Permissions  

The following permission is required to call the API.  
You must register an app through Elements > API app registration to authenticate and authorize your access to AvePoint Graph API. For details, refer to [App Registration](https://cdn.avepoint.com/assets/apelements-webhelp/avepoint-elements-for-partners/index.htm#!Documents/appregistration.htm).  

| API  | Permission  |
|-----------|--------|
| `/partner/external/v3/bm/customers/{customerId}/tenants/{tenantId}/actions` | elements.bm.tenant.readwrite.all|  

## Request

This section provides details on the HTTP method and endpoint used to monitor tenants by performing actions on the tenants.

| Method | Endpoint | Description |
| --- | --- | --- |
| POST | `/partner/external/v3/bm/customers/{customerId}/tenants/{tenantId}/actions` | Monitors tenants by performing actions on the tenants. |

## Request Body Parameters

You can provide a object about the action.

|Parameter|Description | Type|Required?|
|---|---|---|---|
|actionType| The action that you want to perform on the tenant. (More actions will be supported in the future) <ul><li>**1** - Apply baseline to tenant</li></ul> |integer|Yes|
|data| The parameters of the action. |object|Yes|

### Apply Action Data Parameters

For the "Apply baseline to tenant" action, the parameters of the data object are as follows.

|Parameter|Description | Type|Required?|
|---|---|---|---|
|baselineId| The ID of the baseline. |integer|Yes|
|order| The ranking order of the baseline among all applied baselines. |integer|Yes|


> [!NOTE]  
> Tenants in the following status cannot perform the "Apply baseline to tenant" action.<ul><li>**3** - Deploying</li><li>**6** - Expired</li><li>**11** - Restoring</li><li>**12** Retrieving setting</li></ul>
> Baselines in the following status cannot be used for the "Apply baseline to tenant" action.<ul><li>**1** - Retrieving settings</li><li>**4** - Settings retrieval failed</li><li>**6** - Draft</li></ul>

## Response

If the request has been successfully processed, a 200 OK response will be returned along with the action result in the response body.

| Response | Description | Type |
| --- | --- | --- |
| jobId | The ID of the job to apply baseline to tenant. | string |

## Request Sample

To use this API, send a POST request to the specified endpoint.

```json
https://graph-us.avepointonlineservices.com/partner/external/v3/bm/customers/38c6a73d-****-****-****-75b0f1959474/tenants/a2145aa5-****-****-****-7fffd6e0cc68/actions

//Apply baseline action
{
    "actionType": "1", // The action that you want to perform on the tenant. 1 represents "Apply baseline to tenant"
    "data": 
    [
        {
            "baselineId": "e12922f4-****-****-****-3a1c162b4cf2", // The ID of the baseline
            "order": 1 // The ranking order of the baseline among all applied baselines
        },
        {
            "baselineId": "b4c84bff-****-****-****-3a1c16243555",
            "order": 2
        }
    ]
}
```

## Response Sample  

If the request has been successfully processed, a 200 OK response will be returned along with the created baseline id displayed in the response body. For more details on the HTTP status code, refer to [HttpStatusCode](https://learn.avepoint.com/docs/Use-AvePoint-Graph-API.html#http-status-code).

```json
{
    "jobId": "7f3b241b-****-****-****-3a1c395524t6"
}
```