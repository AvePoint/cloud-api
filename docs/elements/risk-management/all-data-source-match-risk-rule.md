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
| dataSources | The specific data sources to narrow down the results. <ul><li>**1** - Mailbox (Exchange)</li><li>**2** - M365 Group</li><li>**3** - Teams</li><li>**4** - Sharepoint</li><li>**5** - Onedrive</li><li>**6** - User</li><li>**8** - Power Platform Environment</li><li>**9** - Power Platform Connection</li><li>**10** - Power App</li><li>**11** - Power Automate</li><li>**12** - PowerBI</li></ul>| integer[] | No |
| status | The status of risk rules to filter. <ul><li>**0** - Disabled</li><li>**1** - Enabled</li></ul>| integer | No |


## Response

If the request has been successfully processed, a 200 OK response will be returned along with the requested information displayed in the response body.

| Response | Description | Type |
| --- | --- | --- |
| ruleId | The ID of the rule. | string |
| ruleName | The display name of the rule. | string |
| setting | The paramerter in the name of the rule.  | string |
| tenantId | The tenant's id. | integer |
| customerId | The customer's id. | integer |
| dataSource | The record's data source. <ul><li>**1** - Mailbox (Exchange)</li><li>**2** - M365 Group</li><li>**3** - Teams</li><li>**4** - Sharepoint</li><li>**5** - Onedrive</li><li>**6** - User</li><li>**8** - Power Platform Environment</li><li>**9** - Power Platform Connection</li><li>**10** - Power App</li><li>**11** - Power Automate</li><li>**12** - PowerBI</li></ul>| integer |
| hitItemCount | The number of objects that have the rule. | integer |


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
            "ruleId": "00000002-****-****-****-0000001A",
            "ruleName": "Users without MFA enabled",
            "setting": null,
            "tenantId": "be4cdf40-****-****-****-ab967eb78246",
            "customerId": "292b68c5-****-****-****-28650d407eaf",
            "dataSource": 6,
            "hitItemCount": 161
        },
        {
            "ruleId": "00000002-****-****-****-00000023",
            "ruleName": "Global administrator without a password expiration date",
            "setting": null,
            "tenantId": "be4cdf40-****-****-****-ab967eb78246",
            "customerId": "292b68c5-****-****-****-28650d407eaf",
            "dataSource": 6,
            "hitItemCount": 1
        }
    ]
}