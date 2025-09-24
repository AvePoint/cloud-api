# Retrieve Hit Objects of Risk Rule

Use this API to retrieve all matched records of a specific risk rule for a specific tenant in Elements.  

## Permission  

The following permission is required to call the API.  
You must register an app through Elements > API app registration to authenticate and authorize your access to AvePoint Graph API. For details, refer to [App Registration](https://cdn.avepoint.com/assets/apelements-webhelp/avepoint-elements-for-partners/index.htm#!Documents/appregistration.htm).

| API | Permission |
|-----------|-----------|
| `/partner/external/v3/rm/customers/{customerId}/tenants/{tenantId}/detection/rules/{ruleId}/hit-items` | elements.rm.read.all |  


## Request

This section outlines the HTTP method and endpoint used to retrieve the matched objects of a speific risk rule within a tenant.

| Method | Endpoint | Description |
|-----------|-----------|-----------|
|GET|`/partner/external/v3/rm/customers/{customerId}/tenants/{tenantId}/detection/rules/{ruleId}/hit-items`|Retrieves all matched records of a specific risk rule.|

## Query Parameters

This section outlines the parameters required to specify which tenant's risk rule detail records you want to retrieve.

| Parameter | Description | Type | Required |
| --- | --- | --- | --- |
| customerId | The customer ID. | string | Yes |
| tenantId | The tenant ID of the customer. | string | Yes |
| ruleId | The ID of the risk rule. | string | Yes |
| pageIndex | The starting number of the page to get the hit objects. The default value is 1. | integer | No |
| pageSize | The number of objects to display on one page. The default value is 50. | integer | No |


## Response

If the request has been successfully processed, a 200 OK response will be returned along with the requested information displayed in the response body.

| Elements | Description | Type |
| --- | --- | --- |
| metaData | The response's metadata. | object |
| pageIndex | The current display page. | integer |
| pageSize | The number of objects on the display page.  | integer |
| totalCount | The total number of objects matching the query parameters. | integer |
| id | The record's id. | integer |
| objectId | The object ID. | integer |
| tenantId | The tenant ID. | integer |
| customerId | The customer ID.| integer |
| dataSource | The object's data source. <ul><li>**1** - Exchange</li><li>**2** - Groups</li><li>**3** - Teams</li><li>**4** - SharePoint</li><li>**5** - OneDrive</li><li>**6** - Users</li><li>**8** - Environments</li><li>**9** - Connections</li><li>**10** - Power Apps</li><li>**11** - Power Automate</li><li>**12** - Power BI</li></ul>| integer |
| detail | The detail information of the object. | object |


**Object details**

| Property | Description | Type |
| --- | --- | --- |
| mailboxName | The display name of the mailbox. | string |
| mailboxEmailAddress | The email address. | string |
| storageUsed | The storage usage of object in Megabytes (MB). | int |
| prohibitSendReceiveQuota | The record's prohibit send and recieve limit in Megabytes (MB). | int |
| prohibitSendQuota | The record's prohibit send limit in Megabytes (MB). | int |
| createDate | The record's create date. | string |
| lastActivityDate | The record's last activity date. | string |
| groupName | The Microsoft 365 Group's display name. | string |
| groupEmailAddress | The Microsoft 365 Group's email address | string |
| createdBy | The record's creator name | string |
| ownerCount | The number of owners in the record. | int |
| memberCount | The number of members in the record. | int |
| teamsName | The Microsoft Teams's display name. | string |
| teamsUrl | The Microsoft Teams's URL. | string |
| siteName | The Microsoft Sharepoint's display name. | string |
| siteUrl | The Microsoft Sharepoint's URL. | string |
| displayName | The Microsoft OneDrive's display name. | string |
| url | The Microsoft OneDrive's URL. | string |
| adminCount | The record's admin count | string |
| storageLimit | The record's storage limit in Megabytes (MB). | int |
| changeFileCount | The record's number of files changed. | int |
| guestsCount | The record's number of guests. | int |
| environmentName | The Microsoft Power Platform Environment's display name. | string |
| environmentMakerCount | The Microsoft Power Platform Environment's environment makers count. | int |
| totalUsage | The Microsoft Power Platform Environment's total usage in Bytes (B). | int |
| creatorName | The record's creator name. | string |
| creatorEmail | The record's creator email. | string |
| connectionName | The Microsoft Power Platform Environment's display name. | string |
| parentEnvironment | The Microsoft Power Platform Environment's parent environment. | string |
| appName | The Microsoft Power Platform App's display name. | string |
| environment | The Microsoft Power Platform App/Flow's environment. | string |
| coOwnerCount | The number of co-owners in the record. | int |
| lastSignIn | The time when users last sign in to the app/flow. | string |
| lastLaunchTime | The time when users last launch the app. | string |
| flowName | The Microsoft Power Platform Flow's display name. | string |
| workspaceName | The Microsoft Power BI's workspace name. | string |
| capacityName | The Microsoft Power BI's capacity name. | string |
| artifactName | The Microsoft Power BI's artifact name. | string |
| workspace | The Microsoft Power BI's workspace. | string |
| sensitivity | The Microsoft Power BI's sensitivity. | string |
| reportCount | The Microsoft Power BI's number of reports. | int |
| userCount | The record's number of users. | int |
| licenseCount | The record's number of license pool count. | int |
| licenseDisplayName | The license's display name. | string |
| licenseKeyName | The license's key name. | string |
| userName | The User's display name. | string |
| userEmailAddress | The User's email address. | string |
| userRoles | The User's user role. | string |
| upn | The User's User Principal Name. | string |
| MFAControlledViaCap | The User's MFA status. | bool |
| signInCount | The User's number of sign in. | int |
| latestCampaignInfo | The detail informations about record's campaign. | string |


## Detail's enumerations

Depending on the workspace, there are enumerations that stands for a specific type of the record.

| Response | Description | Type |
| --- | --- | --- |
| groupType | The type of group. <ul><li>**1** - Microsoft365 groups</li><li>**2** - Security groups</li><li>**4** - Distribution groups</li><li>**8** - Mail Enabled Security groups</li><li>**-1** - Unknown</li></ul> | integer |
| sourceType | The source type of the record. <ul><li>**0** - None</li><li>**1** - Cloud</li><li>**2** - On premise</li><li>**4** - Hybrid</li></ul> | integer |
| userType | The user's type. <ul><li>**1** - Guest</li><li>**2** - Member</li></ul> | integer |
| archiveStatus | The record's archive status. <ul><li>**1** - UnArchived</li><li>**2** - Archived</li></ul> | integer |
| lockState | The record's lock state. <ul><li>**0** - Unknown</li><li>**1** - Unlock</li><li>**2** - ReadOnly</li><li>**3** - NoAccess</li></ul> | integer |
| includedInSolutions | Indicates whether the Flow/App is included in a Power Platform solution. <ul><li>**0** - No</li><li>**1** - Yes</li></ul> | integer |
| type(1) | The Power Automate's flow type. <ul><li>**0** - Unknown</li><li>**1** - Instant</li><li>**2** - Automated</li><li>**4** - Scheduled</li><li>**8** - DesktopFlow</li></ul> | integer |
| type(2) | The Power Platform Environment's environment type. <ul><li>**1** - Default</li><li>**2** - Trial</li><li>**4** - Sandbox</li><li>**8** - Production</li><li>**16** - Teams</li><li>**32** - Subscription Based Trial</li><li>**64** - Developer</li></ul> | integer |
| region | The Power Platform Environment's region. <ul><li>**-1** - none</li><li>**0** - United States</li><li>**1** - Europe</li><li>**2** - Asia</li><li>**3** - Australia</li><li>**4** - India</li><li>**5** - Japan</li><li>**6** - Canada</li><li>**7** - United Kingdom</li><li>**8** - United States First Release</li><li>**9** - South America</li><li>**10** - France</li><li>**11** - Switzerland</li><li>**12** - Germany</li><li>**13** - Korea</li><li>**14** - Norway</li><li>**15** - United Arab Emirates</li><li>**16** - usgov</li><li>**17** - South Africa</li><li>**18** - Sweden</li><li>**19** - usgovhigh</li></ul> | integer |
| recipientType | The recipient type of a Microsoft Exchange's mail. <ul><li>1 - UserMailbox</li><li>2 - SharedMailbox</li><li>4 - RoomMailbox</li><li>8 - EquipmentMailbox</li><li>16 - MailContact</li><li>32 - MailUser</li><li>64 - GuestMailUser</li><li>128 - DiscoveryMailbox</li><li>256 - LegacyMailbox</li><li>512 - LinkedMailbox</li><li>1024 - LinkedRoomMailbox</li><li>2048 - TeamMailbox</li><li>4096 - DynamicDistributionGroup</li><li>8192 - GroupMailbox</li><li>16384 - MailForestContact</li><li>32768 - MailNonUniversalGroup</li><li>65536 - MailUniversalDistributionGroup</li><li>131072 - MailUniversalSecurityGroup</li><li>262144 - PublicFolder</li><li>524288 - PublicFolderMailbox</li><li>1048576 - RemoteEquipmentMailbox</li><li>2097152 - RemoteRoomMailbox</li><li>4194304 - RemoteSharedMailbox</li><li>8388608 - RemoteTeamMailbox</li><li>16777216 - RemoteUserMailbox</li><li>33554432 - RoomList</li><li>67108864 - SchedulingMailbox</li></ul> | integer |
| Mark | Indicates whether the record is mark as fixed. <ul><li>**0** - No</li><li>**1** - Yes</li></ul> | interger |
 



## Request Sample

To use this API, send a GET request to the specified endpoint, including necessary parameters as defined in the references.

```json
https://graph-us.avepointonlineservices.com/partner/external/v3/rm/customers/d926b068-47cd-4830-a082-fd2a1eb64e99/tenants/0eaab044-c775-4a92-b40d-93c6e237711e/detection/rules/00000002-9E63-4A52-9946-00000036/hit-items
```

## Response Sample

If the request has been successfully processed, a 200 OK response will be returned along with the requested information displayed in the response body. For more details on the HTTP status code, refer to [Http Status Code](https://learn.avepoint.com/docs/Use-AvePoint-Graph-API.html#http-status-code).

```json 
{
    "metaData": {
        "pageIndex": 1,
        "pageSize": 50,
        "totalCount": 37
    },
    "data": [
        {
            "detail": {
                "groupName": "20240820 teamsite",
                "groupEmailAddress": "2024********@vrmhv.onmicrosoft.com",
                "groupType": 1,
                "ownerCount": 1,
                "memberCount": 4,
                "createDate": "2024-08-20T10:55:29.0000000Z",
                "lastActivityDate": "2025-07-10T00:00:00.0000000Z",
                "mark": 0,
                "sourceType": 1
            },
            "id": "5824e186-****-****-****-e2aa9a60ac16",
            "objectid": "e6950ad1-****-****-****-151a1a060d1f",
            "ruleId": "00000002-****-****-****-00000007",
            "tenantId": "be4cdf40-****-****-****-ab967eb78246",
            "customerId": "292b68c5-****-****-****-28650d407eaf",
            "dataSource": 2
        }
    ]
}