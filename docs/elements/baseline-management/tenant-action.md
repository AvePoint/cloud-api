# Tenant baseline action

Use this API to execute tenant actions.

## Permissions  

The following permission is required to call the API.  
You must register an app through Elements > API app registration to authenticate and authorize your access to AvePoint Graph API. For details, refer to [App Registration](https://cdn.avepoint.com/assets/apelements-webhelp/avepoint-elements-for-partners/index.htm#!Documents/appregistration.htm).  

| API  | Permission  |
|-----------|--------|
| `/partner/external/v3/bm/customers/{customerId}}/tenants/{tenantId}}/actions` | elements.bm.tenant.readwrite.all|  

## Request

This section provides details on the HTTP method and endpoint used to execute tenant action.

| Method | Endpoint | Description |
| --- | --- | --- |
| POST | `/partner/external/v3/bm/customers/{customerId}}/tenants/{tenantId}}/actions` | Execute tenant action. |

## Request Body Parameters

You can provide a object about the action.

|Parameter|Description | Type|Required?|
|---|---|---|---|
|actionType| The tenant action type. <ul><li>**1** - Apply Baseline</li></ul> |int|Yes|
|data| The parameters of action <ul><li>**baselineId** - Apply Baseline Id (Apply Baseline action)</li><li>**order** - Apply baseline order (Apply Baseline action)</li></ul></li></ul> |object|Yes|

> [!NOTE]  
> Tenants in the following status cannot perform the "Apply Baseline" action.<ul><li>**3** - Deploying</li><li>**6** - Expired</li><li>**11** - Restoring</li><li>**12** Retrieving setting</li></ul>
> Baselines in the following status cannot be used for the "Apply Baseline" action.<ul><li>**1** - Retrieving settings</li><li>**4** - Settings retrieval failed</li><li>**6** - Draft</li></ul>

## Response

If the request has been successfully processed, a 200 OK response will be returned along with the action result in the response body.

| Response | Description | Type |
| --- | --- | --- |
| jobId | The job id of apply baseline job or export tenant configuration job. | string |

## Request Sample

To use this API, send a POST request to the specified endpoint.

```json
https://graph-us.avepointonlineservices.com/partner/external/v3/bm/customers/{customerId}}/tenants/{tenantId}}/actions

//Apply baseline action
{
    "actionType": "1",
    "data": 
    [
        {
            "baselineId": "e12922f4-****-****-****-3a1c162b4cf2",
            "order": 1
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