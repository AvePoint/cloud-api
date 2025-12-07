# Retrieve Matched Objects of Specific Risk Rule

Use this API to retrieve the objects that violate a specific risk rule within a specific tenant in Elements.  

## Permission  

The following permission is required to call the API.  
You must register an app through Elements > API app registration to authenticate and authorize your access to Elements API. For details, refer to [App Registration](../register-app.md).

| API | Permission |
|-----------|-----------|
| `/partner/external/v3/rm/customers/{customerId}/tenants/{tenantId}/detection/rules/{ruleId}/hit-items` | elements.rm.read.all |  


## Request

This section outlines the HTTP method and endpoint used to retrieve the violated objects for a speific risk rule within a tenant.

| Method | Endpoint | Description |
|-----------|-----------|-----------|
|GET|`/partner/external/v3/rm/customers/{customerId}/tenants/{tenantId}/detection/rules/{ruleId}/hit-items`|Retrieves all violated objects of a specific risk rule.|


## URL Parameters

This section outlines the parameters required to specify which risk rule's detection details you want to retrieve.

| Parameter | Description | Type | Required |
| --- | --- | --- | --- |
| customerId | The customer ID | string | Yes |
| tenantId | The tenant ID of the customer| string | Yes |
| ruleId | The ID of the risk rule| string | Yes |


## Query Parameters

This section outlines the parameters that allow users to specify pagination.

| Parameter | Description | Type | Required |
| --- | --- | --- | --- |
| pageIndex | The starting number of the page to get the violated objects. The default value is 1. | integer | No |
| pageSize | The number of objects to display on one page. The default value is 50 and the maximum value allowed is 100. | integer | No |


## Response

If the request has been successfully processed, a 200 OK response will be returned along with the requested information displayed in the response body.

| Elements | Description | Type |
| --- | --- | --- |
| metaData | The response's metadata. | object |
| pageIndex | The current display page. | integer |
| pageSize | The number of objects on the display page.  | integer |
| totalCount | The total number of objects matching the query parameters. | integer |
| id | The record ID. | string |
| objectId | The object ID. | string |
| tenantId | The tenant ID. | string |
| customerId | The customer ID.| string |
| dataSource | The object's data source. <ul><li>**1** - Exchange</li><li>**2** - Groups</li><li>**3** - Teams</li><li>**4** - SharePoint</li><li>**5** - OneDrive</li><li>**6** - Users</li><li>**8** - Environments</li><li>**9** - Connections</li><li>**10** - Power Apps</li><li>**11** - Power Automate</li><li>**12** - Power BI</li></ul>| integer |
| detail | The detailed information of the object. | object |


**Exchange mailbox details**

| Property | Description | Type |
| --- | --- | --- |
| mailboxName | The display name of the mailbox. | string |
| mailboxEmailAddress | The email address. | string |
| storageUsed | The used storage of the mailbox. The unit is MB. | integer |
| prohibitSendReceiveQuota | The prohibit send and recieve quota of the mailbox. The unit is MB.| integer |
| recipientType | The recipient type of the mailbox. <ul><li>**1** - User mailbox</li><li>**2** - Shared mailbox</li><li>**4** - Room mailbox</li><li>**8** - Equipment mailbox</li><li>**16** - Mail contact</li><li>**32** - Mail user</li><li>**64** - Guest mail user</li><li>**128** - Discovery mailbox</li><li>**256** - Legacy mailbox</li><li>**512** - Linked mailbox</li><li>**1024** - Linked room mailbox</li><li>**2048** - Team mailbox</li><li>**4096** - Dynamic distribution group</li><li>**8192** - Group mailbox</li><li>**16384** - Mail forest contact</li><li>**32768** - Mail-enabled non-universal group</li><li>**65536** - Universal distribution group</li><li>**131072** - Universal security group</li><li>**262144** - Public folder</li><li>**524288** - Public folder mailbox</li><li>**1048576** - Remote equipment mailbox</li><li>**2097152** - Remote room mailbox</li><li>**4194304** - Remote shared mailbox</li><li>**8388608** - Remote Team mailbox</li><li>**16777216** - Remote user mailbox</li><li>**33554432** - Room list</li><li>**67108864** - Scheduling mailbox</li></ul> | integer |
| createdDate | The created date and time of the mailbox in ISO 8601 format. | string |
| lastActivityDate | The date and time of the mailbox's last activity in ISO 8601 format. | string |
| prohibitSendQuota | The prohibit send quota of the mailbox. The unit is MB.| integer |
| mark | The status of the mailbox whether it is marked as fixed. <ul><li>**0** - No</li><li>**1** - Yes</li></ul> | integer |


**Group details**

| Response | Description | Type |
| --- | --- | --- |
| groupName | The display name of the group. | string |
| groupEmailAddress | The email address of the group. | string |
| createdBy | The creator name of the group.  | string |
| groupType | The type of group. <ul><li>**1** - Microsoft 365 Group</li><li>**2** - Security group</li><li>**4** - Distribution group</li><li>**8** - Mail-enabled security group</li><li>**-1** - Unknown</li></ul> | integer |
| ownerCount | The number of owners in the group. | integer |
| memberCount | The number of members in the group. | integer |
| createdDate | The created date and time of the group in ISO 8601 format. | string |
| lastActivityDate | The date and tiem of the group's last activity in ISO 8601 format. | string |
| mark | The status of the group whether it is marked as fixed. <ul><li>**0** - No</li><li>**1** - Yes</li></ul> | integer |
| sourceType | The source type of the group. <ul><li>**0** - None</li><li>**1** - Cloud</li><li>**2** - On-premises</li><li>**4** - Hybrid</li></ul> | integer |


**Team details**

| Response | Description | Type |
| --- | --- | --- |
| teamsName | The display name of the Team. | string |
| teamsUrl | The URL of the Team site. | string |
| createdBy | The creator name of the Team. | string |
| ownerCount | The number of owners in the Team. | integer |
| memberCount | The number of members in the Team. | integer |
| lastActivityDate | The date and time of the Team's last activity in ISO 8601 format. | string |
| mark | The status of the Team whether it is marked as fixed. <ul><li>**0** - No</li><li>**1** - Yes</li></ul> | integer |
| latestCampaignInfo | The detailed information about the Team's campaign. | string |


**Site details**

| Response | Description | Type |
| --- | --- | --- |
| siteName | The display name of the site. | string |
| siteUrl | The site URL. | string |
| createdBy | The creator name of the site. | string |
| storageUsed | The used storage of the site. The unit is MB.| integer |
| ownerCount | The number of owners in the site. | integer |
| memberCount | The number of members in the site. | integer |
| createdDate | The created date and time of the site in ISO 8601 format. | string |
| lastActivityDate | The date and time of the site's last activity in ISO 8601 format. | string |
| mark | The status of the site whether it is marked as fixed.  <ul><li>**0** - No</li><li>**1** - Yes</li></ul> | integer |
| latestCampaignInfo | The detailed information about the site's campaign. | string |
| lockState | The lock status of the site. <ul><li>**0** - Unknown</li><li>**1** - Unlocked</li><li>**2** - Read only</li><li>**3** - No access</li></ul> | integer |


**OneDrive details:**

| Response | Description | Type |
| --- | --- | --- |
| displayName | The display name of the OneDrive. | string |
| url | The OneDrive URL. | string |
| adminCount | The number of admins. | integer |
| storageUsed | The used storage of the OneDrive. The unit is MB. | integer |
| storageLimit | The storage limit of the OneDrive. The unit is MB.| integer |
| changeFileCount | The number of file modifications. | integer |
| guestsCount | The number of guests in the OneDrive. | integer |
| mark | The status of the OneDrive whether it is marked as fixed.  <ul><li>**0** - No</li><li>**1** - Yes</li></ul> | integer |


**Environment details:**

| Response | Description | Type |
| --- | --- | --- |
| environmentName | The display name of the environment. | string |
| environmentMakerCount | The number of environment makers. | integer |
| region | The environment's region. <ul><li>**-1** - None</li><li>**0** - United States</li><li>**1** - Europe</li><li>**2** - Asia</li><li>**3** - Australia</li><li>**4** - India</li><li>**5** - Japan</li><li>**6** - Canada</li><li>**7** - United Kingdom</li><li>**8** - United States</li><li>**9** - South America</li><li>**10** - France</li><li>**11** - Switzerland</li><li>**12** - Germany</li><li>**13** - Korea</li><li>**14** - Norway</li><li>**15** - United Arab Emirates</li><li>**16** - US Gov</li><li>**17** - South Africa</li><li>**18** - Sweden</li><li>**19** - US Gov High</li></ul> | integer |
| type | The environment type. <ul><li>**1** - Default</li><li>**2** - Trial</li><li>**4** - Sandbox</li><li>**8** - Production</li><li>**16** - Teams</li><li>**32** - Trial (subscription-based)</li><li>**64** - Developer</li></ul> | integer |
| createdDate | The created date and time of the environment in ISO 8601 format. | string |
| lastActivityDate | The date and time of the environment's last activity in ISO 8601 format. | string |
| totalUsage | The environment's total usage. The unit is Bytes. | integer |
| mark |  The status of the environment whether it is marked as fixed. <ul><li>**0** - No</li><li>**1** - Yes</li></ul> | integer |
| creatorName | The creator name of the environment. | string |
| creatorEmail | The email address of the creator. | string |
| adminCount | The number of admins in the environment.| integer |
| guestUserCount | The number of guest users in the environment.| integer |


**Connection details:**

| Response | Description | Type |
| --- | --- | --- |
| connectionName | The display name of the connection. | string |
| parentEnvironment | The parent environment of the connection. | string |
| createdBy | The creator name of the connection | string |
| createdDate | The created date and time of the connection in ISO 8601 format. | string |
| mark | The status of the connection whether it is marked as fixed. <ul><li>**0** - No</li><li>**1** - Yes</li></ul> | integer |


**Power App details:**

| Response | Description | Type |
| --- | --- | --- |
| appName | The display name of the Power App. | string |
| environment | The environment of the Power App. | string |
| createdBy | The creator name of the Power App. | string |
| guestUserCount | The number of guest users in the Power App. | integer |
| includedInSolutions | The status whether the Power App is included in a solution. <ul><li>**0** - No</li><li>**1** - Yes</li></ul> | integer |
| coOwnerCount | The number of co-owners in the app. | integer |
| lastSignIn | The time when users last signed in to the app in ISO 8601 format. | string |
| lastLaunchTime | The time when users last launched the app in ISO 8601 format. | string |
| createdDate | The created date and time of the app in ISO 8601 format. | string |
| mark | The status of the app whether it is marked as fixed. <ul><li>**0** - No</li><li>**1** - Yes</li></ul> | integer |


**Flow details:**

| Response | Description | Type |
| --- | --- | --- |
| flowName | The display name of flow. | string |
| environment | The environment of the flow. | string |
| guestsCount | The number of guests in the flow. | integer |
| creatorName | The creator name of the flow. | string |
| type | The flow type. <ul><li>**0** - Unknown</li><li>**1** - Instant</li><li>**2** - Automated</li><li>**4** - Scheduled</li><li>**8** - Desktop flow</li></ul> | integer |
| includedInSolutions |The status whether the flow is included in a solution. <ul><li>**0** - No</li><li>**1** - Yes</li></ul> | integer |
| coOwnerCount | The number of co-owners in the flow. | integer |
| createdDate | The created date and time of the flow in ISO 8601 format. | string |
| lastActivityDate | The date and time of the flow's last activity in ISO 8601 format. | string |
| lastSignIn | The time when users last signed in to the flow. | string |
| mark | The status of the flow whether it is marked as fixed. <ul><li>**0** - No</li><li>**1** - Yes</li></ul> | integer |


**Power BI details:**

| Response | Description | Type |
| --- | --- | --- |
| workspaceName | The display name of the Power BI workspace/report. | string |
| capacityName | The capacity name of the Power BI workspace.| string |
| artifactName | The artifact name. | string |
| workspace | The parent workspace name. | string |
| sensitivity | The sensitivity level of the Power BI workspace/report. | string |
| adminCount | The number of admins. | integer |
| lastActivityDate | The date and time of the last activity in the Power BI workspace/report in ISO 8601 format. | string |
| createdDate | The created date and time of the Power BI workspace/report in ISO 8601 format. | string |
| guestUserCount | The number of guest users. | integer |
| reportCount | The number of Power BI reports. | integer |
| mark | The status of the workspace/report whether it is marked as fixed. <ul><li>**0** - No</li><li>**1** - Yes</li></ul> | integer |
| userCount | The number of users in the Power BI workspace/report. | integer |



**User details:**

| Response | Description | Type |
| --- | --- | --- |
| userName | The user's display name. | string |
| userEmailAddress | The user's email address. | string |
| userRoles | The user role. | string |
| upn | The User Principal Name of the user. | string |
| userType | The user type. <ul><li>**1** - Guest</li><li>**2** - Member</li></ul> | integer |
| MFAControlledViaCap | The user's MFA status. | bool |
| lastSignIn | The time when the user last signed in to Microsoft 365 in ISO 8601 format. | string |
| lastActivityDate | The date and time of the user's last activity in ISO 8601 format. | string |
| createdDate | The created date and time of the user in ISO 8601 format. | string |
| signInCount | The number of the user's sign-ins. | integer |
| mark | The status of the user whether it is marked as fixed. <ul><li>**0** - No</li><li>**1** - Yes</li></ul> | integer |
| sourceType | The source type of the user. <ul><li>**0** - None</li><li>**1** - Cloud</li><li>**2** - On-premises</li><li>**4** - Hybrid</li></ul> | integer |

**License details:**

| Response | Description | Type |
| --- | --- | --- |
| licenseCount | The license count. | integer |
| licenseDisplayName | The license display name. | string |
| licenseKeyName | The license key name. | string |
| mark | The status of the license whether it is marked as fixed. <ul><li>**0** - No</li><li>**1** - Yes</li></ul> | integer |

## Request Sample

To use this API, send a GET request to the specified endpoint, including necessary parameters as defined in the references.

```json
https://graph-us.avepointonlineservices.com/partner/external/v3/rm/customers/d926b068-****-4830-****-fd2a****4e99/tenants/0eaab044-****-4a92-****-93c6****711e/detection/rules/00000002-9E63-4A52-9946-00000036/hit-items
```

## Response Sample

If the request has been successfully processed, a 200 OK response will be returned along with the requested information displayed in the response body. For more details on the HTTP status code, refer to [Http Status Code](../Use-AvePoint-Graph-API.md#http-status-code).

```json 
{
    "data": [
        {
            "detail": {
                "groupName": "20240820 teamsite", // The display name of the group
                "groupEmailAddress": "2024****@****.onmicrosoft.com", // The email address of the group
                "createdBy": "", // The creator of the group
                "groupType": 1, // The type of group, Microsoft 365 Group
                "ownerCount": 1, // The number of owners in the group
                "memberCount": 4, // The number of members in the group
                "createDate": "2024-08-20T10:55:29.0000000Z", // The created date and time of the group
                "lastActivityDate": "2025-07-10T00:00:00.0000000Z", // The date and time of the group's last activity
                "mark": 0, // The status of the group whether it is marked as fixed, not fixed
                "sourceType": 1 // The source type of the group, Cloud
            },
            "id": "5824e186-****-9a60-****-e2aa****ac16", // The record ID
            "objectid": "e6950ad1-****-1a06-****-151a****0d1f", // The object ID
            "ruleId": "00000002-****-4A52-****-00000036", // The ID of the risk rule
            "tenantId": "0eaab044-****-4a92-****-93c6****711e", // The tenant ID
            "customerId": "d926b068-****-4830-****-fd2a****4e99", // The customer ID
            "dataSource": 2 // The object's data source, Groups
        }
    ],
    "metaData": {
        "pageIndex": 1, // The current display page
        "pageSize": 50, // The number of objects on the display page
        "totalCount": 1 // The total number of objects matching the query parameters
    }
}