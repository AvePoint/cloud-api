# Get a scan profile information configured in Avepoint Online Services for a customer

Use this API to get a scan profile information configured in Avepoint Online Services for a customer. 

 ## Permissions

The following permission is required to call the API.  
You must register an app through Elements > API app registration to authenticate and authorize your access to AvePoint Graph API. For details, refer to [App Registration](../../../elements/register-app.md).

| API | Permission  |
|-----------|--------|
| `partner/external/v3/general/customers/{customerId}/scan-profiles/{scanProfileId}/detail`|elements.scanprofiles.read.all|  

## Request

This section outlines the details of the HTTP method and endpoint used to get a scan profile information configured in Avepoint Online Services for a customer.

| Method | Endpoint | Description |
|-----------|--------|------------|
| GET | `partner/external/v3/general/customers/{customerId}/scan-profiles/{scanProfileId}/detail` | Get a scan profile information configured in Avepoint Online Services for a customer.|

## Response

If the request has been successfully processed, a 200 OK response will be returned along with the requested information displayed in the response body.
 
| Field | Description | Type |
| --- | --- | --- |
| profileName               | The profile name of the profile.                 | string |
| profileId     | The profile id of the profile.       | string |
| description       | The description of the profile.      | string |
| tenantId | The tenant id of the profile. | string |
| tenantDomain | The tenant domain of the profile. | string |
| scanMode | The scan mode of the profile. | integer |
| modifiedTime | The modify time of the profile. | string |
| createdTime | The create time of the profile. | string |
| lastUpdateTime | The last update time of the profile. | string |
| impersonationAccount | The impersonation account of the profile. | string |
| scanInplaceArchivedMailboxes | The scan inplace archive mailboxes of the profile. | boolean |
| ignoreTheLockedObjectsWhenUpdatingTheJobStatus | The ignore lock object status of the profile. | bool |
| isIgnoreLockedSiteEnabled | The ignore lock site of the profile. | boolean |
| enableDailyScan | The enable daily scan of the profile. | string |
| isSendOutOfPolicyNotification | The send oop notification status of the profile. | boolean |
| containers | The container information of the container. | list |

### The container information:
| Field | Description | Type |
| --- | --- | --- |
| containersName | The container name of the container. | string |
| objectType | The object type of the container. | integer |





## Request Sample
To use this API, send a GET request to the specified endpoint, including necessary parameters as defined in the references.
```json
https://graph.avepointonlineservices.com/partner/external/v3/general/customers/{customerId}/scan-profiles/{scanProfileId}/detail
```
 
## Response Sample
If the request has been successfully processed, a 200 OK response will be returned along with the requested information displayed in the response body.
For more details on the HTTP status code, refer to [Http Status Code](https://learn.avepoint.com/docs/Use-AvePoint-Graph-API.html#http-status-code).
```json
{
    "profileId": "47dba9a1-1004-4c2d-b2ce-8f5e66f5842d",
    "profileName": "Default Microsoft 365 Scan Profile",
    "description": "This is a partner-configured scan profile.",
    "tenantId": "c2350b99-c7a2-4605-b7d4-79e8646f66c3",
    "tenantDomain": "v0s40",
    "scanMode": 0,
    "modifiedTime": "2025-09-11T03:19:14Z",
    "createdTime": "2025-09-11T03:19:14Z",
    "lastUpdateTime": "2025-09-11T03:19:14Z",
    "scanInplaceArchivedMailboxes": false,
    "ignoreTheLockedObjectsWhenUpdatingTheJobStatus": false,
    "isIgnoreLockedSiteEnabled": false,
    "enableDailyScan": "15:19",
    "isSendOutOfPolicyNotification": false,
    "containers": [
        {
            "containersName": "Default_ProjectOnline_Sites_Group",
            "objectType": 6
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