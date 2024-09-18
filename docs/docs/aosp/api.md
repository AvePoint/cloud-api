# Elements Open API

Elements provides APIs to retrieve information of your customers, including services, job details, and scan profiles.

## Path Table

| Method | Path | Description |
| --- | --- | --- |
| GET | [/Customers](#getapiv11customers) |Get the general information of all customers that you manage.  |
| GET | [/Customers/{id}](#getapiv11customersid) |Get the general information of a specific customer that you manage.  |
| GET | [/Customers/{Id}/Jobs](#getapiv11customersidjobs) | Get your customer's job details for the backup services.<br>Note that only the job details for the backup services that the customer has the subscription for are supported. |
| GET | [/Customers/{Id}/Jobs/JobType/{JobType}/JobModule/{JobModule}](#getapiv11customersidjobsjobtypejobtypejobmodulejobmodule) |Get your customer's job details for a specific job type and module of the backup services.<br>Note that only the job details for the backup services that the cusotmer has the subscription for are supported.  |
| GET | [/Customers/{id}/Protected](#getapiv11customersidprotected) | Get your cusomter's protected data information of Cloud Backup for Microsoft 365.<br>Note that only the customers that have the Cloud Backup for Microsoft 365 subscription are supported.|
| GET | [/Customers/{id}/ScanProfiles](#getapiv11customersidscanprofiles) | Get your customer's information for all scan profiles configured in AvePoint Online Services. |
| GET | [/Customers/{id}/ScanProfilesDailyNew/ProfileId/{ProfileId}](#getapiv11customersidscanprofilesdailynewprofileidprofileid) |Get your cusomter's daily scan profile changes in AvePoint Online Services.|
| GET | [/Customers/{id}/ScanProfilesDailyNewDetail/ProfileId/{ProfileId}](#getapiv11customersidscanprofilesdailynewdetailprofileidprofileid) |Get your customer's daily scan profile change details in AvePoint Online Services.  |
| GET | [/Customers/{id}/ScanProfilesDetails/ProfileId/{ProfileId}](#getapiv11customersidscanprofilesdetailsprofileidprofileid) | Get your cusotmer's information for a specific scan profile configured in AvePoint Online Services.  |
| GET | [/Services](#getapiv11services) |Get the service subscription details of all customers that you manage.|
| GET | [/Services/{id}](#getapiv11servicesid) | Get the service subscription details of a specific customer that you manage. |

## Path Details

### [GET]/Customers

Get the general information of all customers that you manage.

#### Responses

If the request has been successfully processed, a 200 OK response will be returned, along with the requested information displayed in the response body.

| Response | Description | Type |
| --- | --- | --- |
| Id | The tenant owner ID of the customer. | String |
| Organization | The organization name of the customer. | String |
| OwnerEmail | The tenant owner email address of the customer. | String |
| JobStatus | The status of the customer’s tenant. | String |
| CountryOrRegion | The country or region name of the customer. | String |

***

### [GET]/Customers/{id}

Get the general information of a specific customer that you manage.

#### Parameters (Query)
| Parameter | Description | Type |
| --- | --- | --- |
| Id | The tenant owner ID of the customer. | String |

#### Responses

If the request has been successfully processed, a 200 OK response will be returned, along with the requested information displayed in the response body.

| Response | Description | Type |
| --- | --- | --- |
| Id | The tenant owner ID of the customer. | String |
| Organization | The organization name of the customer. | String |
| OwnerEmail | The tenant owner email address of the customer. | String |
| JobStatus | The status of the customer’s tenant. | String |
| CountryOrRegion | The country or region name of the customer. | String |

***

### [GET]/Customers/{Id}/Jobs

Get your customer's job details for the backup services.<br>Note that only the job details for the backup services that the cusotmer has the subscription for are supported. 

#### Parameters (Query)
| Parameter | Description | Type |
| --- | --- | --- |
| Id | The tenant owner ID of the customer. | String |

#### Responses

If the request has been successfully processed, a 200 OK response will be returned, along with the requested information displayed in the response body.

| Response | Description | Type |
| --- | --- | --- |
| JobType | The service type of the job. | String |
| JobModule | The service module of the job. | String |
| Status | The job status. | String |
| JobId | The job ID. | String |
| Name | The job name. | String |
| TotalCount | The count of the objects that have been processed by the job. | Int |
| FailedCount | The count of the failed objects. | Int |
| SuccessfulCount | The count of the successful objects. | Int |
| SkippedCount | The count of the skipped objects. | Int |
| WarningCount | The count of the warning objects. | Int |
| BackupSize | The size of the backed-up objects. | String |
| StartTime | The start time of the job. | DateTime |
| EndTime | The end time of the job. | DateTime |
| JobDuration | The job duration. | String |
| LastModifyTime | The last modified time of the job. | DateTime |

***

### [GET]/Customers/{Id}/Jobs/JobType/{JobType}/JobModule/{JobModule}

Get your customer's job details for a specific job type and module of the backup services.<br>Note that only the job details for the backup services that the customer has the subscription for are supported.

#### Parameters (Query)
| Parameter | Description | Type |
| --- | --- | --- |
| Id | The tenant owner ID of the customer. | String |
| JobType | The service type of the job. | String |
| JobModule | The service module of the job. | String |

#### Responses

If the request has been successfully processed, a 200 OK response will be returned, along with the requested information displayed in the response body.

| Response | Description | Type |
| --- | --- | --- |
| JobType | The service type of the job. | String |
| JobModule | The service module of the job. | String |
| Status | The job status. | String |
| JobId | The job ID. | String |
| Name | The job name. | String |
| TotalCount | The count of the objects that have been processed by the job. | Int |
| FailedCount | The count of the failed objects. | Int |
| SuccessfulCount | The count of the successful objects. | Int |
| SkippedCount | The count of the skipped objects. | Int |
| WarningCount | The count of the warning objects. | Int |
| BackupSize | The size of the backed-up objects. | String |
| StartTime | The start time of the job. | DateTime |
| EndTime | The end time of the job. | DateTime |
| JobDuration | The job duration. | String |
| LastModifyTime | The last modified time of the job. | DateTime |

***

### [GET]/Customers/{id}/Protected

Get your customer's protected data information of Cloud Backup for Microsoft 365.<br>Note that only the customers that have the Cloud Backup for Microsoft 365 subscription are supported.

#### Parameters (Query)
| Parameter | Description | Type |
| --- | --- | --- |
| Id | The tenant owner ID of the customer. | String |

#### Responses

If the request has been successfully processed, a 200 OK response will be returned, along with the requested information displayed in the response body.

| Response | Description | Type |
| --- | --- | --- |
| CustomerId | The tenant owner ID of the customer. | String |
| Customer | The tenant owner email address of the customer. | String |
| ServiceType | The Cloud Backup for Microsoft 365 service that the customer has the subscription for. | String |
| ServiceModule | The module of the customer’s Cloud Backup for Microsoft 365 service. | String |
| TotalScannedObjects | The number of the scanned objects. | Int |
| TotalProtectedObjects | The number of the backed-up objects. | Int |
| DataSizeStoredInAvePoint | The size of the backed-up objects stored in the AvePoint storage. | Int |
| DataSizeStoredInBYOS | The size of the backed-up objects stored in BYOS. | Int |

***

### [GET]/Customers/{id}/ScanProfiles

Get your cusomter's information for all scan profiles configured in AvePoint Online Services.

#### Parameters (Query)
| Parameter | Description | Type |
| --- | --- | --- |
| Id | The tenant owner ID of the customer. | String |

#### Responses

If the request has been successfully processed, a 200 OK response will be returned, along with the requested information displayed in the response body.

| Response | Description | Type |
| --- | --- | --- |
| ProfileName | The name of the scan profile. | String |
| ProfileId | The ID of the scan profile. | String |
| ScanMode | The scan mode of the scan profile:<br> <ul><li> **0** represents **Express mode**</li><li> **1** represents **Advanced mode** | Int |
| ModifiedTime | The last modified time of the scan profile. | String |

***

### [GET]/Customers/{id}/ScanProfilesDailyNew/ProfileId/{ProfileId}

Get your cusomter's daily scan profile changes in AvePoint Online Services.

#### Parameters (Query)
| Parameter | Description | Type |
| --- | --- | --- |
| Id | The tenant owner ID of the customer. | String |
| ProfileId | The ID of the scan profile. | String |

#### Responses

If the request has been successfully processed, a 200 OK response will be returned, along with the requested information displayed in the response body.

| Response | Description | Type |
| --- | --- | --- |
| ProfileName | The name of the scan profile. | String |
| ProfileId | The ID of the scan profile. | String |
| TenantDomain | The tenant domain of the scan profile. | String |
| TenantId | The tenant ID the scan profile. | String |
| Description | The description of the scan profile. | String |
| ScanMode | The scan mode of the scan profile:<br> <ul><li>**0** represents **Express mode**<li>**1** represents **Advanced mode**| Int |
| ModifiedTime | The last modified time of the scan profile. | String |
| LastUpdateTime | The time of generating the daily report for the scan profile. If no daily report has been generated, the time will be the last modified time of the scan profile. | String |
| LastScanStatus | The last scan job status of the scan profile:<br><ul><li>**2** represents **Finished**<li>**3** represents **Failed**<li>**4** represents **Finished with exception**<li>**5** represents **Skipped**<li>**10** represents **Stopped** | Int |
| NewRegistedContentCount | The number of newly registered objects in the daily report of the scan profile. | Int |
| MovedToAnotherContainer | The number of objects moved to another container in the daily report of the scan profile. | Int |
| RemovedFromMicrosoft365OrOutofPolicy | The number of objects removed from Microsoft 365 or out of policy in the daily report of the scan profile. | Int |

***

### [GET]/Customers/{id}/ScanProfilesDailyNewDetail/ProfileId/{ProfileId}

Get your customer's daily scan profile change details in AvePoint Online Services.

#### Parameters (Query)
| Parameter | Description | Type |
| --- | --- | --- |
| Id | The tenant owner ID of the customer. | String |
| ProfileId | The ID of the scan profile. | String |

#### Responses

If the request has been successfully processed, a 200 OK response will be returned, along with the requested information displayed in the response body.

| Response | Description | Type |
| --- | --- | --- |
| ProfileName | The name of the scan profile. | String |
| ProfileId | The ID of the scan profile. | String |
| TenantDomain | The tenant domain of the scan profile. | String |
| TenantId | The tenant ID the scan profile. | String |
| LastUpdateTime | The time of generating the daily report for the scan profile. If no daily report has been generated, the time will be the last modified time of the scan profile. | String |
| NewRegistedContent | The details of newly registered objects in the daily report of the scan profile. | String |
| RemovedFromMicrosoft365OrOutOfPolicyObjects | The details of objects moved to another container in the daily report of the scan profile. | String |
| MovedToAnotherContainerObjects | The details of objects removed from Microsoft 365 or out of policy in the daily report of the scan profile. | String |

***

### [GET]/Customers/{id}/ScanProfilesDetails/ProfileId/{ProfileId}

Get your customer's information for a specific scan profile configured in AvePoint Online Services.

#### Parameters (Query)
| Parameter | Description | Type |
| --- | --- | --- |
| Id | The tenant owner ID of the customer. | String |
| ProfileId | The ID of the scan profile. | String |

#### Responses

If the request has been successfully processed, a 200 OK response will be returned, along with the requested information displayed in the response body.

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
| IgnoreTheLockedObjectsWhenUpdatingTheJobStatus | Whether the **Ignore the locked objects when updating the job status** setting is enabled in the scan profile:<br><ul><li>**True** represents **Enabled**<li>**False** represents **Disabled** | Boolean |
| EnableDailyScan | Whether the **Enable daily scan** setting is enabled in the scan profile:<br><ul><li>**No** represents  **Disabled**<li>**hh:mm** represents the time of the daily scan, for example, 01:59 | String |
| SendAnemailNotificationToTheFollowIngRecipientsWhenObjectsAreMovedTooTherContainerOrRemovedFromAnyContainers | Whether the **Send an email notification to the following recipients when objects are moved to other containers or removed from any containers** setting is enabled in the scan profile:<br><ul><li>**True** represents **Enabled**<li>**False** represents **Disabled** | Boolean |
| Containers | The container details of the scan profile. | String |

***

### [GET]/Services

Get the service subscription details for the customers that you manage.


#### Responses

If the request has been successfully processed, a 200 OK response will be returned, along with the requested information displayed in the response body.

| Response | Description | Type |
| --- | --- | --- |
| CustomerId | The tenant owner ID of the customer. | String |
| Organization | The organization name of the customer. | String |
| Customer | The tenant owner email address of the customer. | String |
| TenantId | The tenant ID of the customer. | String |
| Service | The service that the customer has subscriptions for. | String |
| SubscriptionModel | The subscription model of the customer’s service. | String |
| PurchasedUserSeats | The number of purchased user seats of the customer. | String |
| MicrosoftLicenseAssigned | The number of assigned Microsoft licenses of the customer. | String |
| MicrosoftLicenseAvailable | The number of available Microsoft licenses of the customer. | String |
| PurchasedCapacity | The purchased capacity of the customer. | String |
| Storage | The storage type of the customer. | String |
| Retention | The data retention period of the customer. | String |
| ConsumedStorage | The consumed storage size of the customer. | String |
| expirationDate | The expiration date of the customer’s service. | String |
| Change | The user seats changes in the pooled license compared with the first day of the current month. | String |

***

### [GET]/Services/{id}

Get the service subscription details for a specific customer that you manage.

#### Parameters (Query)
| Parameter | Description | Type |
| --- | --- | --- |
| Id | The tenant owner ID of the customer. | String |

#### Responses

If the request has been successfully processed, a 200 OK response will be returned, along with the requested information displayed in the response body.

| Response | Description | Type |
| --- | --- | --- |
| CustomerId | The tenant owner ID of the customer. | String |
| Organization | The organization name of the customer. | String |
| Customer | The tenant owner email address of the customer. | String |
| TenantId | The tenant ID of the customer. | String |
| Service | The service that the customer has subscriptions for. | String |
| SubscriptionModel | The subscription model of the customer’s service. | String |
| PurchasedUserSeats | The number of purchased user seats of the customer. | String |
| MicrosoftLicenseAssigned | The number of assigned Microsoft licenses of the customer. | String |
| MicrosoftLicenseAvailable | The number of available Microsoft licenses of the customer. | String |
| PurchasedCapacity | The purchased capacity of the customer. | String |
| Storage | The storage type of the customer. | String |
| Retention | The data retention period of the customer. | String |
| ConsumedStorage | The consumed storage size of the customer. | String |
| ExpirationDate | The expiration date of the customer’s service. | String |