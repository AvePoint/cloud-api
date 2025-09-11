# Retrieve specific rule detail hit items

Use this API to retrieve all records for a specific risk rule for a specific tenant in AvePoint Online Services.  

## Permissions  

The following permission is required to call the API.  
You must register an app through Elements > API app registration to authenticate and authorize your access to AvePoint Graph API. For details, refer to [App Registration](https://cdn.avepoint.com/assets/apelements-webhelp/avepoint-elements-for-partners/index.htm#!Documents/appregistration.htm).

| API | Permission |
|-----------|-----------|
| `/partner/external/rm/customers/{customerId}/tenants/{tenantId}/detection/rules/{ruleId}/hit-items` | partner.rm.read.all |  


## Request

This section outlines the HTTP method and endpoint used to retrieve your customer's information for all scan profiles configured in AvePoint Online Services.

| Method | Endpoint | Description |
|-----------|-----------|-----------|
|GET|`/partner/external/rm/customers/{customerId}/tenants/{tenantId}/detection/rules/{ruleId}/hit-items`|Retrieves all records for a specific risk rule for a specific tenant in AvePoint Online Services.|

## Query Parameters

This section outlines the parameters required to specify which tenant's risk rule detail records you want to retrieve.

| Parameter | Description | Type | Required |
| --- | --- | --- | --- |
| CustomerId | The customer's ID. | string | Yes |
| TenantId | The customer tenant's ID. | string | Yes |
| RuleId | The ID of the risk rule. | string | Yes |
| PageIndex | The page you want to navigate to. | integer | No |
| PageSize | The number of records in each response. | integer | No |


## Response

If the request has been successfully processed, a 200 OK response will be returned along with the requested information displayed in the response body.

| Response | Description | Type |
| --- | --- | --- |
| pageSize | The number of data items displayed per page. | integer |
| totalNumber | The total number of items that meet the criteria. | integer |
| totalPage | The total number of pages that meet the criteria.  | integer |
| jumpPage | The page we need to jump to. | integer |
| currentPage | The current display page  | integer |
| id | The record's id | integer |
| objectId | The object's id | integer |
| tenantId | The tenant's id | integer |
| customerId | The customer's id | integer |
| workspace | The record's workspace <ul><li>**1** - Mailbox (Exchange)</li><li>**2** - M365 Group</li><li>**3** - Teams</li><li>**4** - Sharepoint</li><li>**5** - Onedrive</li></ul>| integer |
| detail | The detail information of the record | object |


## Request Sample

To use this API, send a GET request to the specified endpoint, including necessary parameters as defined in the references.

```json
https://graph-us.avepointonlineservices.com/partner/customers/d926b068-47cd-4830-a082-fd2a1eb64e99/tenants/0eaab044-c775-4a92-b40d-93c6e237711e/detection/rules/00000002-9E63-4A52-9946-00000036/hit-items
```

## Response Sample

If the request has been successfully processed, a 200 OK response will be returned along with the requested information displayed in the response body. For more details on the HTTP status code, refer to [Http Status Code](https://learn.avepoint.com/docs/Use-AvePoint-Graph-API.html#http-status-code).

```json 
{
    "pageSize": 50,
    "totalNumber": 37,
    "totalPage": 1,
    "jumpPage": 1,
    "currentPage": 1,
    "result": [
        {
            "detail": {
                "groupName": "20240820 teamsite",
                "groupEmailAddress": "20***********site@*****.onmicrosoft.com",
                "createdBy": "",
                "groupType": 1,
                "owners": "",
                "ownerCount": 1,
                "memberCount": 4,
                "createDate": 638597481290000000,
                "lastActivityDate": 638877024000000000,
                "ownerIds": "17cbcd9e-****-****-****-fec514a79c64",
                "memberIds": "",
                "mark": 0,
                "sourceType": 1
            }
        }
    ]
}