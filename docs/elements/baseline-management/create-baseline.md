# Create Baseline

Use this API to create Baseline. 

## Permissions  

The following permission is required to call the API.  
You must register an app through Elements > API app registration to authenticate and authorize your access to AvePoint Graph API. For details, refer to [App Registration](https://cdn.avepoint.com/assets/apelements-webhelp/avepoint-elements-for-partners/index.htm#!Documents/appregistration.htm).  

| API  | Permission  |
|-----------|--------|
| `/partner/external/v3/bm/baselines` | elements.bm.baseline.readwrite.all|  

## Request

This section provides details on the HTTP method and endpoint used to create a baseline to establish benchmarks for tenant configurations.

| Method | Endpoint | Description |
| --- | --- | --- |
| POST | `/partner/external/v3/bm/baselines` | Create a baseline to establish benchmarks for tenant configurations. |

## Request Body Parameters

The API requires multiple parameters to create baseline.  

|Parameter|Description | Type|Required?|
|---|---|---|---|
|name|The ID of the baseline. |string|Yes|
|color|The color of the baseline.<ul><li><span style="display:inline-block; width:12px; height:12px; background:#94A6AF; margin-right:6px;" ></span> **0** </li><li><span style="display:inline-block; width:12px; height:12px; background:#DA1B3E; margin-right:6px;" ></span> **1** </li><li><span style="display:inline-block; width:12px; height:12px; background:#D95630; margin-right:6px;" ></span> **2** </li><li><span style="display:inline-block; width:12px; height:12px; background:#A45800; margin-right:6px;" ></span> **3** </li><li><span style="display:inline-block; width:12px; height:12px; background:#34A853; margin-right:6px;" ></span> **4** </li><li><span style="display:inline-block; width:12px; height:12px; background:#149EB0; margin-right:6px;" ></span> **5** </li><li><span style="display:inline-block; width:12px; height:12px; background:#0072D0; margin-right:6px;" ></span> **6** </li><li><span style="display:inline-block; width:12px; height:12px; background:#7626BB; margin-right:6px;" ></span> **7** </li><li><span style="display:inline-block; width:12px; height:12px; background:#344650; margin-right:6px;" ></span> **8** </li><li><span style="display:inline-block; width:12px; height:12px; background:#D01A83; margin-right:6px;" ></span> **9** </li><li><span style="display:inline-block; width:12px; height:12px; background:#990000; margin-right:6px;" ></span> **10** </li><li><span style="display:inline-block; width:12px; height:12px; background:#614051; margin-right:6px;" ></span> **11** </li><li><span style="display:inline-block; width:12px; height:12px; background:#046307; margin-right:6px;" ></span> **12** </li><li><span style="display:inline-block; width:12px; height:12px; background:#4747BA; margin-right:6px;" ></span> **13** </li><li><span style="display:inline-block; width:12px; height:12px; background:#8B008B; margin-right:6px;" ></span> **14** </li><li><span style="display:inline-block; width:12px; height:12px; background:#7D0552; margin-right:6px;" ></span> **15** </li></ul>|integer|Yes|
|description|The description of the baseline.|string|No|
|customerId|The id of the **Customer**.|string|Yes|
|tenantId|The id of the **Tenant**.|string|Yes|

> [!NOTE]  
> Tenants in the following status cannot be used to create baseline.<ul><li>**3** - Deploying</li><li>**6** - Expired</li><li>**11** - Restoring</li></ul>

## Response

If the request has been successfully processed, a 201 OK response will be returned along with the created baseline id displayed in the response body.

| Response | Description | Type |
| --- | --- | --- |
| baselineId | The Id of the new baseline. | string |

## Request Sample

To use this API, send a POST request to the specified endpoint.

```json
https://graph-us.avepointonlineservices.com/partner/external/v3/bm/baselines

{
    name: "baseline1",
    color:"0",
    description:"baseline1 description",
    customerId:"ce43e186-****-****-****-86b51b0aef92",
    tenantId:"af83b8e1-****-****-****-970f92192dc5"
}
```

## Response Sample  

If the request has been successfully processed, a 201 OK response will be returned along with the created baseline id displayed in the response body. For more details on the HTTP status code, refer to [HttpStatusCode](https://learn.avepoint.com/docs/Use-AvePoint-Graph-API.html#http-status-code).

```json
{
    "baselineId": "606f30c0-****-****-****-3a1c3a823ab5"
}