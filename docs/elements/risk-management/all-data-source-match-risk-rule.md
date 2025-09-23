# Retrieve all data source that match risk rules

Use this API to retrieve records for all risk rules that are match for a specific tenant in AvePoint Online Services.  

## Permissions  

The following permission is required to call the API.  
You must register an app through Elements > API app registration to authenticate and authorize your access to AvePoint Graph API. For details, refer to [App Registration](https://cdn.avepoint.com/assets/apelements-webhelp/avepoint-elements-for-partners/index.htm#!Documents/appregistration.htm).

| API | Permission |
|-----------|-----------|
| `/partner/external/v3/rm/customers/{customerId}/tenants/{tenantId}/detection/rules` | elements.rm.read.all |  


## Request

This section outlines the HTTP method and endpoint used to retrieve the matched workspaces of a specific risk rule.

| Method | Endpoint | Description |
|-----------|-----------|-----------|
|GET|`/partner/external/v3/rm/customers/{customerId}/tenants/{tenantId}/detection/rules`|Retrieves records for all risk rules that are match for a specific tenant in AvePoint Online Services.|

## Query Parameters

This section outlines the parameters required to specify which tenant's risk detection details you want to retrieve.

| Parameter | Description | Type | Required |
| --- | --- | --- | --- |
| customerId | The customer's ID. | string | Yes |
| tenantId | The tenant ID of the customer. | string | Yes |
| dataSources | The specific data sources to narrow down the results. | integer | No |
| status | The status of risk rules to filter. | integer | No |


## Response

If the request has been successfully processed, a 200 OK response will be returned along with the requested information displayed in the response body.

| Response | Description | Type |
| --- | --- | --- |
| ruleId | The ID of the risk rule. | string |
| ruleName | The display name of the risk rule. | string |
| setting | The paramerter value configured in the risk rule.  | string |
| tenantId | The tenant ID. | integer |
| customerId | The customer ID. | integer |
| dataSources | The record's workspace. <ul><li>**1** - Mailbox (Exchange)</li><li>**2** - Microsoft 365 Groups</li><li>**3** - Teams</li><li>**4** - SharePoint</li><li>**5** - OneDrive</li><li>**6** - Users</li><li>**8** - Environments</li><li>**9** - Connections</li><li>**10** - Power Apps</li><li>**11** - Power Automate</li><li>**12** - Power BI</li></ul>| integer |
| hitItemCount | The number of objects that match the risk rule. | integer |


## Request Sample

To use this API, send a GET request to the specified endpoint, including necessary parameters as defined in the references.

```json
https://graph-us.avepointonlineservices.com/partner/external/v3/rm/customers/d926b068-****-4830-a082-fd2a****4e99/tenants/0eaab044-****-4a92-b40d-93c6****711e/detection/rules
```

## Response Sample

If the request has been successfully processed, a 200 OK response will be returned along with the requested information displayed in the response body. For more details on the HTTP status code, refer to [Http Status Code](https://learn.avepoint.com/docs/Use-AvePoint-Graph-API.html#http-status-code).

```json 
{
    "result": [
        {
            "ruleId": "00000002-9E63-4A52-9946-00000016",
            "ruleName": "OneDrives that have reached 75% of the storage limits",
            "setting": "{\"param1\": 75}",
            "tenantId": "be4cdf40-****-****-****-ab967eb78246",
            "customerId": "292b68c5-****-****-****-28650d407eaf",
            "workspaces": 5,
            "hitItemCount": 0
        }
    ]
}