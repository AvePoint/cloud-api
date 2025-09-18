# Retrieve specific rule detail hit items

Use this API to retrieve all records for a specific risk rule for a specific tenant in AvePoint Online Services.  

## Permissions  

The following permission is required to call the API.  
You must register an app through Elements > API app registration to authenticate and authorize your access to AvePoint Graph API. For details, refer to [App Registration](https://cdn.avepoint.com/assets/apelements-webhelp/avepoint-elements-for-partners/index.htm#!Documents/appregistration.htm).

| API | Permission |
|-----------|-----------|
| `/partner/external/v3/rm/customers/{customerId}/tenants/{tenantId}/detection/rules/{ruleId}/hit-items` | elements.rm.read.all |  


## Request

This section outlines the HTTP method and endpoint used to retrieve your customer's information for all scan profiles configured in AvePoint Online Services.

| Method | Endpoint | Description |
|-----------|-----------|-----------|
|GET|`/partner/external/v3/rm/customers/{customerId}/tenants/{tenantId}/detection/rules/{ruleId}/hit-items`|Retrieves all records for a specific risk rule for a specific tenant in AvePoint Online Services.|

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
| recipientType | The recipient type of a Microsoft Exchange's mail. <ul><li>1 - UserMailbox</li><li>2 - SharedMailbox</li><li>4 - RoomMailbox</li><li>8 - EquipmentMailbox</li><li>16 - MailContact</li><li>32 - MailUser</li><li>64 - GuestMailUser</li><li>128 - DiscoveryMailbox</li><li>256 - LegacyMailbox</li><li>512 - LinkedMailbox</li><li>1024 - LinkedRoomMailbox</li><li>2048 - TeamMailbox</li><li>4096 - DynamicDistributionGroup</li><li>8192 - GroupMailbox</li><li>16384 - MailForestContact</li><li>32768 - MailNonUniversalGroup</li><li>65536 - MailUniversalDistributionGroup</li><li>131072 - MailUniversalSecurityGroup</li><li>262144 - PublicFolder</li><li>524288 - PublicFolderMailbox</li><li>1048576 - RemoteEquipmentMailbox</li><li>2097152 - RemoteRoomMailbox</li><li>4194304 - RemoteSharedMailbox</li><li>8388608 - RemoteTeamMailbox</li><li>16777216 - RemoteUserMailbox</li><li>33554432 - RoomList</li><li>67108864 - SchedulingMailbox</li></ul>
 | integer |
| Mark | Indicates whether the record is mark as fixed. <ul><li>**0** - No</li><li>**1** - Yes</li></ul> | string |
 

## Detail's fields

Depending on the workspace, there are fields that stands for a specific type of the record.

| Response | Description | Type |
| --- | --- | --- |
| MailboxName | The Microsoft Exchange's display name. | string |
| MailboxEmailAddress | The Microsoft Exchange's email address. | string |
| StorageUsed | The record's storage usage in Megabytes (MB). | int |
| ProhibitSendReceiveQuota | The record's prohibit send and recieve limit in Megabytes (MB). | int |
| ProhibitSendQuota | The record's prohibit send limit in Megabytes (MB). | int |
| CreateDate | The record's create date. | string |
| LastActivityDate | The record's last activity date. | string |
| EnabledDate | The time when the record was enabled for a user account. | string |
| EmailForwardingEnabledDate | The time when the record was enabled to forward mails to another recipient. | string |
| GroupName | The Microsoft 365 Group's display name. | string |
| GroupEmailAddress | The Microsoft 365 Group's email address | string |
| CreatedBy | The record's creator name | string |
| OwnerCount | The number of owners in the record. | int |
| MemberCount | The number of members in the record. | int |
| OwnerIds | The owners' Ids. | string |
| MemberIds | The members' Ids. | string |
| TeamsName | The Microsoft Teams's display name. | string |
| TeamsUrl | The Microsoft Teams's URL. | string |
| OwnersName | The record's owner display name. | string |
| OwnersEmail | The record's owner email. | string |
| Email | The Microsoft Teams's email. | string |
| SiteName | The Microsoft Sharepoint's display name. | string |
| SiteUrl | The Microsoft Sharepoint's URL. | string |
| DisplayName | The Microsoft OneDrive's display name. | string |
| URL | The Microsoft OneDrive's URL. | string |
| AdminName | The record's admin name. | string |
| EmailAddress | The record's email address. | string |
| OwnerDisplayName | The record's owner display name. | string |
| AdminCount | The record's admin count | string |
| StorageLimit | The record's storage limit in Megabytes (MB). | int |
| ChangeFileCount | The record's number of files changed. | int |
| GuestsCount | The record's number of guests. | int |
| EnvironmentName | The Microsoft Power Platform Environment's display name. | string |
| CreatorCount | The record's number of creators. | int |
| EnvironmentMakers | The Microsoft Power Platform Environment's environment makers. | string |
| EnvironmentMakerCount | The Microsoft Power Platform Environment's environment makers count. | int |
| GuestUserIds | The record guest users' ids. | string |
| GuestUserCount | The number of guest users in the record. | int |
| Permission | The Microsoft Power Platform Environment's permission. | string |
| DatabaseUsage | The Microsoft Power Platform Environment's Dataverse database usage in Bytes (B). | int |
| TotalUsage | The Microsoft Power Platform Environment's total usage in Bytes (B). | int |
| CreatorName | The record's creator name. | string |
| CreatorEmail | The record's creator email. | string |
| ConnectionName | The Microsoft Power Platform Environment's display name. | string |
| ParentEnvironment | The Microsoft Power Platform Environment's parent environment. | string |
| OwnerEmail | The record's owner email. | string |
| AppName | The Microsoft Power Platform App's display name. | string |
| Environment | The Microsoft Power Platform App/Flow's environment. | string |
| CoOwnerCount | The number of co-owners in the record. | int |
| LastSignIn | The time when users last sign in to the app/flow. | string |
| LastLaunchTime | The time when users last launch the app. | string |
| FlowName | The Microsoft Power Platform Flow's display name. | string |
| WorkspaceName | The Microsoft Power BI's workspace name. | string |
| CapacityName | The Microsoft Power BI's capacity name. | string |
| ArtifactName | The Microsoft Power BI's artifact name. | string |
| Workspace | The Microsoft Power BI's workspace. | string |
| Sensitivity | The Microsoft Power BI's sensitivity. | string |
| ReportCount | The Microsoft Power BI's number of reports. | int |
| UserCount | The record's number of users. | int |
| LicenseCount | The record's number of license pool count. | int |
| LicenseDisplayName | The license's display name. | string |
| LicenseKeyName | The license's key name. | string |
| UserName | The User's display name. | string |
| UserEmailAddress | The User's email address. | string |
| UserRoles | The User's user role. | string |
| CAP | The User's Conditional Access Policy. | string |
| UPN | The User's User Principal Name. | string |
| UserLoginLocation | The User's login location. | string |
| UserLoginIP | The User's display login IP address. | string |
| InvitedByUserName | The name of the User's inviter. | string |
| InvitedByEmailAddress | The email address of the User's inviter. | string |
| UserAccountCount | The User's number of user account. | int |
| MFAControlledViaCap | The User's MFA status. | bool |
| LoginTime | The User's login time. | string |
| ManagerId | The User's managerId. | string |
| SignInCount | The User's number of sign in. | int |
| ObjectUsers | The detail informations about users in the record. | string |


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
                "createdBy": "",
                "objectUsers": null,
                "groupType": 1,
                "ownerCount": 1,
                "memberCount": 4,
                "createDate": "2024-08-20T10:55:29.0000000Z",
                "lastActivityDate": "2025-07-10T00:00:00.0000000Z",
                "ownerIds": "17****-****-****-****-****79c64",
                "memberIds": "",
                "mark": 0,
                "sourceType": 1
            }
        }
    ]
}