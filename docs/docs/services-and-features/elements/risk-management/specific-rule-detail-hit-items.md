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
| currentPage | The current display page.  | integer |
| id | The record's id. | integer |
| objectId | The object's id. | integer |
| tenantId | The tenant's id. | integer |
| customerId | The customer's id | integer |
| workspace | The record's workspace. <ul><li>**1** - Mailbox (Exchange)</li><li>**2** - M365 Group</li><li>**3** - Teams</li><li>**4** - Sharepoint</li><li>**5** - Onedrive</li><li>**6** - User</li><li>**8** - Power Platform Environment</li><li>**9** - Power Platform Connection</li><li>**10** - Power App</li><li>**11** - Power Automate</li><li>**12** - PowerBI</li></ul>| integer |
| detail | The detail information of the record. | object |


## Detail's enumerations

Based on the workspace, there are enumerations that stands for a specific type of the record.

| Response | Description | Type |
| --- | --- | --- |
| groupType | The type of group. <ul><li>**1** - Microsoft365</li><li>**2** - Security</li><li>**4** - Distribution</li><li>**8** - MailEnabledSecurity</li><li>**-1** - Unknown</li></ul> | integer |
| sourceType | The source type of the record. <ul><li>**0** - None</li><li>**1** - Cloud</li><li>**2** - OnPremise</li><li>**4** - Hybrid</li></ul> | integer |
| userType | The user's type. <ul><li>**1** - Guest</li><li>**2** - Member</li></ul> | integer |
| archiveStatus | The record's archive status. <ul><li>**0** - Archive</li><li>**1** - UnArchive</li></ul> | integer |
| lockState | The record's lock state. <ul><li>**0** - Unknown</li><li>**1** - Unlock</li><li>**2** - ReadOnly</li><li>**3** - NoAccess</li></ul> | integer |
| includedInSolutions | The record's id. | integer |
| type(1) | The Power Automate's flow type. <ul><li>**0** - Unknown</li><li>**1** - Instant</li><li>**2** - Automated</li><li>**4** - Scheduled</li><li>**8** - DesktopFlow</li></ul> | integer |
| type(2) | The Power Platform Environment's environment type. <ul><li>**1** - Default</li><li>**2** - Trial</li><li>**4** - Sandbox</li><li>**8** - Production</li><li>**16** - Teams</li><li>**32** - Subscription Based Trial</li><li>**64** - Developer</li></ul> | integer |
| region | The Power Platform Environment's region. <ul><li>**-1** - none</li><li>**0** - unitedstates</li><li>**1** - europe</li><li>**2** - asia</li><li>**3** - australia</li><li>**4** - india</li><li>**5** - japan</li><li>**6** - canada</li><li>**7** - unitedkingdom</li><li>**8** - unitedstatesfirstrelease</li><li>**9** - southamerica</li><li>**10** - france</li><li>**11** - switzerland</li><li>**12** - germany</li><li>**13** - korea</li><li>**14** - norway</li><li>**15** - unitedarabemirates</li><li>**16** - usgov</li><li>**17** - southafrica</li><li>**18** - sweden</li><li>**19** - usgovhigh</li></ul> | integer |


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