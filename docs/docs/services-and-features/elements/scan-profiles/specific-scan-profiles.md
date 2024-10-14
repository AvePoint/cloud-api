# Elements API

Elements provides APIs to retrieve information of your customers, including services, job details, and scan profiles.

## Permissions  

The following permission is required to call the APIs.  
You must register an app through AvePoint Online Services > App registration to authenticate and authorize your access to AvePoint Graph Modern API. For details, refer to [Authentication and Authorization](/docs/docs/Use%20AvePoint%20Graph%20Modern%20API.md/#authentication-and-authorization)

| API |Method| Description | Permission Required |
|-----------|--------|-------|--------|
| [/Customers/{id}/ScanProfilesDetails/ProfileId/{ProfileId}](#getcustomersidscanprofilesdetailsprofileidprofileid)| GET  | Get your customer's information for a specific scan profile configured in AvePoint Online Services.  |partner.scanprofiles.read.all |  

## References


### [GET]/Customers/{id}/ScanProfilesDetails/ProfileId/{ProfileId}

Get your customer's information for a specific scan profile configured in AvePoint Online Services.

#### Parameters (Query)
| Parameter | Description | Type |
| --- | --- | --- |
| Id | The tenant owner ID of the customer. | String |
| ProfileId | The ID of the scan profile. | String |

#### Responses

If the request has been successfully processed, a 200 OK response will be returned along with the requested information displayed in the response body.

| Response | Description | Type |
| --- | --- | --- |
| ProfileId | The ID of the scan profile. | String |
| ProfileName | The name of the scan profile. | String |
| Description | The description of the scan profile. | String |
| TenantId | The tenant ID of the scan profile. | String |
| TenantDomain | The tenant domain of the scan profile. | String |
| ScanMode | The scan mode of the scan profile:<br><ul><li>**0** represents **Express mode**<li>**1** represents **Advanced mode** | Int |
| ModifiedTime | The last modified time of the scan profile. | String |
| CreatedTime | The created time of the scan profile. | String |
| ImpersonationAccount | The impersonation account configured in the scan profile. | String |
| ScanInplaceArchivedMailboxes | Whether the **Scan in-place archived mailboxes** setting is enabled in the scan profile:<br><ul><li>**True** represents **Enabled**<li>**False** represents **Disabled** | Boolean |
| IsIgnoreLockedSiteEnabled | Whether the **Ignore the locked objects when updating the job status** setting is enabled in the scan profile:<br><ul><li>**True** represents **Enabled**<li>**False** represents **Disabled** | Boolean |
| EnableDailyScan | Whether the **Enable daily scan** setting is enabled in the scan profile:<br><ul><li>**No** represents  **Disabled**<li>**hh:mm** represents the time of the daily scan, for example, 01:59 | String |
| IsSendOutOfPolicyNotification | Whether the **Send an email notification to the following recipients when objects are moved to other containers or removed from any containers** setting is enabled in the scan profile:<br><ul><li>**True** represents **Enabled**<li>**False** represents **Disabled** | Boolean |
| Containers | The container details of the scan profile. | String |

***

