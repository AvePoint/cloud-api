# Retrieve Customer Scan Profile Details

Use this API to retrieve the details of a specific scan profile configured in AvePoint Online Services for a customer. 

 ## Permissions

The following permission is required to call the API.  
You must register an app through Elements > API app registration to authenticate and authorize your access to Elements API. For details, refer to [App Registration](../../../elements/register-app.md).

| API | Permission  |
|-----------|--------|
| `/partner/external/v3/general/customers/{customerId}/scan-profiles/{scanProfileId}`|elements.scanprofiles.read.all|  

## Request

This section outlines the details of the HTTP method and endpoint used to retrieve the details of a specific scan profile configured in AvePoint Online Services for a customer.

| Method | Endpoint | Description |
|-----------|--------|------------|
| GET | `/partner/external/v3/general/customers/{customerId}/scan-profiles/{scanProfileId}` | Retrieve the details of a specific scan profile configured in AvePoint Online Services for a customer.|

## Response

If the request has been successfully processed, a 200 OK response will be returned along with the requested information displayed in the response body.
 
| Field | Description | Type |
| --- | --- | --- |
| profileName               | The name of the scan profile.                 | string |
| profileId     | The ID of the scan profile.       | string |
| description       | The description of the scan profile.      | string |
| tenantId | The tenant ID of the scan profile. | string |
| tenantDomain | The tenant domain of the scan profile. | string |
| scanMode | The scan mode of the scan profile. <ul><li>**0** - Express mode</li><li>**1** - Advanced mode</li></ul> | integer |
| modifiedTime | The last modified time of the scan profile in ISO 8601 format. | string |
| createdTime | The created time of the scan profile in ISO 8601 format. | string |
| impersonationAccount | The impersonation account configured in the scan profile. | string |
| scanInplaceArchivedMailboxes | Whether the **Scan in-place archived mailboxes** setting is enabled in the scan profile: <ul><li>**true** - Enabled</li><li>**false** - Disabled</li></ul> | boolean |
| isIgnoreLockedSiteEnabled | Whether the **Ignore the locked objects when updating the job status** setting is enabled in the scan profile: <ul><li>**true** - Enabled</li><li>**false** - Disabled</li></ul> | boolean |
| enableDailyScan | Whether the **Enable daily scan** setting is enabled in the scan profile: <ul><li>**No** - Disabled</li><li>**hh:mm** - The time of the daily scan, for example, 01:59</li></ul> | string |
| isSendOutOfPolicyNotification | Whether the **Send an email notification to the following recipients when objects are moved to other containers or removed from any containers** setting is enabled in the scan profile: <ul><li>**true** - Enabled</li><li>**false** - Disabled</li></ul>  | boolean |
| containers | The information of the containers. | list |

**Container information:**

| Field | Description | Type |
| --- | --- | --- |
| containersName | The name of the container. | string |
| objectType | The object type of the container.<ul><li>**0** - Site Collection</li><li>**1** - Mailbox</li><li>**2** - OneDrive</li><li>**5** - Microsoft 365 Group</li><li>**6** - Project Online</li><li>**7** - Public Folder</li><li>**9** - Channel</li><li>**10** - User</li><li>**11** - None Unified Group</li><li>**12** - Power Platform Environment</li><li>**13** - Power Platform Connection</li><li>**14** - Power Apps</li><li>**15** - Power Automate</li><li>**16** - Power BI Workspace</li><li>**17** - Active Directory Mailbox</li><li>**18** - Active Directory User</li><li>**19** - Active Directory Group</li><li>**20** - Power Platform Solution</li><li>**21** - Power Copilot Studio</li><li>**22** - Power Page</li><li>**23** - Loop Container</li><li>**24** - SharePoint Agent</li><li>**25** - Azure AI Foundry Agent</li><li>**100** - Google User</li><li>**101** - Google Shared Drive</li><li>**102** - Google Classroom</li><li>**103** - Google Mailbox</li><li>**104** - Google Group</li><li>**105** - Google Vault Matter</li></ul> | integer |



## Request Sample
To use this API, send a GET request to the specified endpoint, including necessary parameters as defined in the references.
```json
https://graph.avepointonlineservices.com/partner/external/v3/general/customers/caf9****-2cc6-****-b04b-794c****5ea3/scan-profiles/47db****-1004-****-b2ce-8f5e****842d
```
 
## Response Sample
If the request has been successfully processed, a 200 OK response will be returned along with the requested information displayed in the response body.
For more details on the HTTP status code, refer to [Http Status Code](../../Use-AvePoint-Graph-API.md#http-status-code).
```json
{
    "profileId": "47db****-1004-****-b2ce-8f5e****842d",// The ID of the scan profile
    "profileName": "Default Microsoft 365 Scan Profile", // The name of the scan profile
    "description": "This is a partner-configured scan profile.", // The description of the scan profile
    "tenantId": "c235****-c7a2-****-b7d4-79e8****66c3", // The tenant ID of the scan profile
    "tenantDomain": "domain", // The tenant domain of the scan profile
    "scanMode": 0, // The scan mode of the scan profile: 0 represents the Express mode
    "modifiedTime": "2025-09-11T03:19:14Z",  // The last modified time of the scan profile
    "createdTime": "2025-09-11T03:19:14Z", // The created time of the scan profile
    "impersonationAccount": "user@domain.com", // The impersonation account configured in the scan profile
    "scanInplaceArchivedMailboxes": false, // Whether to scan in-place archived mailboxes configured in the scan profile: False represents Do not scan in-place archived mailbox
    "isIgnoreLockedSiteEnabled": false, // Whether to ignore the locked sites in the scan profile: false represents Disabled
    "enableDailyScan": "15:19", // The time of the daily scan
    "isSendOutOfPolicyNotification": false, // Whether the Send an email notification to the following recipients when objects are moved to other containers or removed from any containers setting is enabled in the scan profile: false represents Disabled
    "containers": [
        {
            "containersName": "Default_ProjectOnline_Sites_Group", // The container name
            "objectType": 6 // The object type: 6 represents Project Online
        },
        {
            "containersName": "Default OneDrive for Business Group",
            "objectType": 2
        },
        {
            "containersName": "Default_ SharePoint Sites_ Group",
            "objectType": 0
        },
        {
            "containersName": "Default_ Mailbox_ Group",
            "objectType": 1
        },
        {
            "containersName": "Default_ User_ Group",
            "objectType": 10
        },
        {
            "containersName": "Default Office 365 Group Group",
            "objectType": 5
        }
    ]
}
```