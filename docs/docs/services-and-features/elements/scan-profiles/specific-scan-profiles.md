# Retrieve Specific Scan Profiles

Use this API to retrieve your customer's information for a specific scan profile configured in AvePoint Online Services.

## Permissions  

The following permission is required to call the API.  
You must register an app through Elements for Partners > API app registration to authenticate and authorize your access to AvePoint Graph API. For details, refer to [App Registration](https://cdn.avepoint.com/assets/apelements-webhelp/avepoint-elements-for-partners/index.htm#!Documents/appregistration.htm).

| API | Permission  |
|-----------|--------|
| `/partner/customers/{id}/scanProfiles/{ProfileId}`|partner.scanprofiles.read.all |  

## Request

This section outlines the details on the HTTP method and endpoint used to retrieve your customer's information for a specific scan profile configured in AvePoint Online Services.

| Method | Endpoint | Description |
|-----------|--------|------------|
| GET | `/partner/customers/{id}/scanProfiles/{ProfileId}` | Retrieves your customer's information for a specific scan profile configured in AvePoint Online Services.|

## Query Parameters

This section outlines the parameters required to specify which customer's specific scan profile in AvePoint Online Services you want to retrieve.

| Parameter | Description | Type | Required |
| --- | --- | --- |---|
| id | The tenant owner ID of the customer. | string | Yes |
| profileId | The ID of the scan profile. | string | Yes |

## Responses

If the request has been successfully processed, a 200 OK response will be returned along with the requested information displayed in the response body.

| Response | Description | Type |
| --- | --- | --- |
| profileId | The ID of the scan profile. | string |
| profileName | The name of the scan profile. | string |
| description | The description of the scan profile. | string |
| tenantId | The tenant ID of the scan profile. | string |
| tenantDomain | The tenant domain of the scan profile. | string |
| scanMode | The scan mode of the scan profile:<br><ul><li>**0** represents **Express mode**<li>**1** represents **Advanced mode** | integer |
| modifiedTime | The last modified time of the scan profile. | string |
| createdTime | The created time of the scan profile. | string |
| impersonationAccount | The impersonation account configured in the scan profile. | string |
| scanInplaceArchivedMailboxes | Whether the **Scan in-place archived mailboxes** setting is enabled in the scan profile:<br><ul><li>**True** represents **Enabled**<li>**False** represents **Disabled** | boolean |
| isIgnoreLockedSiteEnabled [1](#footnote1) | Whether the **Ignore the locked objects when updating the job status** setting is enabled in the scan profile:<br><ul><li>**True** represents **Enabled**<li>**False** represents **Disabled** | boolean |
| enableDailyScan | Whether the **Enable daily scan** setting is enabled in the scan profile:<br><ul><li>**No** represents  **Disabled**<li>**hh:mm** represents the time of the daily scan, for example, 01:59 | string |
| isSendOutOfPolicyNotification [2](#footnote2) | Whether the **Send an email notification to the following recipients when objects are moved to other containers or removed from any containers** setting is enabled in the scan profile:<br><ul><li>**True** represents **Enabled**<li>**False** represents **Disabled** | boolean |
| containers | The container details of the scan profile. | list |

>[!NOTE]
>To enhance user experience and improve integration, we have replaced the following properties with a shorter version. The original, longer properties have been deprecated.  
><a name="footnote1">1</a>: Replaced the `ignoreTheLockedObjectsWhenUpdatingTheJobStatus` property.  
><a name="footnote2">2</a>: Replaced the `SendAnemailNotificationToTheFollowIngRecipientsWhenObjectsAreMovedTooTherContainerOrRemovedFromAnyContainers` property.

## Request Sample

To use this API, send a GET request to the specified endpoint, including necessary parameters as defined in the references.

```json
https://graph.avepointonlineservices.com/partner/customers/caf94a75-2cc6-43aa-b04b-794cb9af5ea3/scanProfiles/0e5e156e-65cc-4206-9829-636ee72c88c3
```

## Response Sample

If the request has been successfully processed, a 200 OK response will be returned along with the requested information displayed in the response body. For more details on the HTTP status code, refer to [HTTP Status Code](https://learn.avepoint.com/docs/Use-AvePoint-Graph-API.html#http-status-code).

```json 
{
    "@odata.context": "https://graph.avepointonlineservices.com/partner/api/V1.1/$metadata#Portal.Api.Model.ProfileDetailInfo",
    "profileId": "0e5e152d-65cc-4206-9829-636ee72c88c3", // The ID of the scan profile
    "profileName": "test oop", // The name of the scan profile
    "description": "aa", // The description of the scan profile
    "tenantId": "c2350b99-c7a2-4605-b7d4-79e8646f66c3", // The tenant ID the scan profile
    "tenantDomain": "v0s40", // The tenant domain of the scan profile
    "scanMode": 0, // The scan mode of the scan profile: 0 represents Express mode
    "modifiedTime": "2024-12-27T17:08:24Z", // The last modified time of the scan profile
    "createdTime": "2024-10-27T17:08:24Z", // The created time of the scan profile
    "impersonationAccount": null, // The impersonation account configured in the scan profile
    "scanInplaceArchivedMailboxes": false, // Whether to scan in-place archived mailboxes configured in the scan profile: False represents Do not scan in-place archived mailbox
    "ignoreTheLockedObjectsWhenUpdatingTheJobStatus": false, // Deprecated. Indicates whether the Ignore the locked objects when updating the job status setting is enabled in the scan profile: False represents Disabled
    "IsIgnoreLockedSiteEnabled": false, // Indicates whether to ignore the locked sites in the scan profile: False represents Disabled
    "enableDailyScan": "No", // Whether the Enable daily scan setting is enabled in the scan profile
    "SendAnemailNotificationToTheFollowIngRecipientsWhenObjectsAreMovedTooTherContainerOrRemovedFromAnyContainers": false, // Deprecated. Indicates whether the Send an email notification to the following recipients when objects are moved to other containers or removed from any containers setting is enabled in the scan profile: False represents Disabled
    "IsSendOutOfPolicyNotification": false, // Indicates whether the Send an email notification to the following recipients when objects are moved to other containers or removed from any containers setting is enabled in the scan profile: False represents Disabled
    "containers": [
        {
            "ContainersName": "Default_ Mailbox_ Group", // The container name
            "ObjectType": "Mailbox" // The object type
        },
        {
            "ContainersName": "Default_ SharePoint Sites_ Group",
            "ObjectType": "SiteCollection"
        }
    ]
}