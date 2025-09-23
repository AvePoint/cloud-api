# Process Center action

Use this API to execute process center action.

## Permissions  

The following permission is required to call the API.  
You must register an app through Elements > API app registration to authenticate and authorize your access to AvePoint Graph API. For details, refer to [App Registration](https://cdn.avepoint.com/assets/apelements-webhelp/avepoint-elements-for-partners/index.htm#!Documents/appregistration.htm).  

| API  | Permission  |
|-----------|--------|
| `/partner/external/v3/bm/customers/{customerId}}/tenants/{tenantId}}/process-center/actions` | elements.bm.tenant.read.all or elements.bm.tenant.readwrite.all|  

## Request

This section provides details on the HTTP method and endpoint used to execute process center action.

| Method | Endpoint | Description |
| --- | --- | --- |
| POST | `/partner/external/v3/bm/customers/{customerId}}/tenants/{tenantId}}/process-center/actions` | Execute process center action. |

## Request Body Parameters

You can provide a object about the action.

|Parameter|Description | Type|Required?|
|---|---|---|---|
|actionType| The tenant action type. <ul><li>**3** - Download</li></ul> |int|Yes|
|data| The parameters of action <ul><li>**jobId** - The job id of the job</li><li>**downloadFileType** - The file type of download<ul><li>**1** - Job file</li></ul></li></ul> | object |Yes|

## Response

If the request has been successfully processed, it will return a file stream.

## Request Sample

To use this API, send a POST request to the specified endpoint.

```json
https://graph-us.avepointonlineservices.com/partner/external/v3/bm/customers/{customerId}}/tenants/{tenantId}}/process-center/actions

{
    "actionType": "3",
    "data": 
    {
        "jobId": "e43f1e86-0000-0000-0000-5ae6ebd79a75",
        "downloadFileType": "1"
    }
}
```

## Response Sample  

If the request has been successfully processed, a 200 OK response will be returned. For more details on the HTTP status code, refer to [HttpStatusCode](https://learn.avepoint.com/docs/Use-AvePoint-Graph-API.html#http-status-code).

```json
//download action will return file stream