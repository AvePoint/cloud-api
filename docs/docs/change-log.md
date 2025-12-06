# Change Log

This document provides a detailed log of changes, updates, and enhancements made to the AvePoint Graph API. It includes information on newly introduced features, improvements to existing functionalities, and any fixes applied. Stay up-to-date with the latest modifications to ensure optimal integration and utilization of the API.

## December 2025

### Added

- **Cloud Backup for Salesforce®**
  - Introduced new endpoints to AvePoint Graph API for Cloud Backup for Salesforce®:
    - `/backup/sfbapi/jobs` for retrieving job-related information.
    - `/backup/sfbapi/monitor-alerts` for retrieving the basic information of alert records.
    - `/backup/sfbapi/unusual-activities` for retrieving the basic information of unusual activities.

    
- **EnPower**
  - Introduced the following new endpoints for Power Pages data retrieval:
    - `/smp/powerplatform/powerpages` for site details.
    - `/smp/powerplatform/powerpages/{powerPageId}/activities` for site activities.
  - Added the following properties to the response of the `/smp/powerplatform/powerapps` endpoint:
    - `lastActivityD30`
    - `lastActivityD90`
    - `lastActivityD180`
    - `appLaunchesLast7Days`
    - `appLaunchesLast30Days`
    - `appLaunchesLast90Days`
    - `appLaunchesLast180Days`
    - `launchedUsersLast7Days`
    - `launchedUsersLast30Days`
    - `launchedUsersLast90Days`
    - `launchedUsersLast180Days`
  - Added the following properties to the response of the `/smp/powerplatform/powerautomate/cloudflows` endpoint:
    - `runsLast7Days`
    - `runsLast30Days`
    - `runsLast90Days`
    - `runsLast180Days`
    - `activitiesLast30Days`
    - `activitiesLast90Days`
    - `activitiesLast180Days`
  - Added the following properties to the response of the `/smp/powerplatform/powerautomate/desktopflows` endpoint:
    - `runsLast7Days`
    - `runsLast30Days`
    - `runsLast90Days`
    - `runsLast180Days`
  - Added the following properties to the response of the `/smp/powerplatform/bot` endpoint:
    - `activityCountLast30D`
    - `activityCountLast90D`
    - `activityCountLast180D`
    - `instructions`
    - `useAIGeneralKnowledge`
    - `useGenAIOrchestration`
    - `knowledgeSourceCount`
    - `promptCount`
    - `skillCount`
    - `toolCount`
    - `restAPIToolCount`
    - `useWebSearch`
  - **User property** Cloud Governance metadata can now be retrieved via the following endpoints:
    - `/smp/powerplatform/environments`
    - `/smp/powerplatform/powerapps`
    - `/smp/powerplatform/powerbi/workspaces`
    - `/smp/powerplatform/powerautomate/cloudflows`
    - `/smp/exchange/mailboxes`
    - `/smp/exchange/resourcemailboxes`



- **Confide**
  - Introduced the following new endpoints for sharing privileged users import:
    - `/admin/shareSetting/import-users` for importing users to Confide share center and manage user permissions in bulk.
    - `/admin/shareSetting/import-users/{id}` for retrieving import users status.
    
### Changed

- **Insights**
   - Updated the `/insights/sharingLinks/{siteUrl}/summary` endpoint to `/insights/sharingLinks/summary`, updated the `HTTP Method` to `POST`, and improved the request sample.
   - Updated the `/insights/sites/{siteId}/detailRecords` endpoint to `/insights/sites/detailRecords`, updated the `HTTP Method` to `POST`, and improved the request sample.
   - Updated the `HTTP Method` of the `/insights/users/access` endpoint to `POST` and improved the request sample.
   - Updated the `HTTP Method` of the `/insights/sites/permission` endpoint to `POST` and improved the request sample.
   - Updated the `HTTP Method` of the `/insights/sites/overview` endpoint to `POST` and improved the request sample.

## October 2025

### Added  

- **Elements**
  - A new set of endpoints are now available for the Elements API, enhancing the existing common features and introducing new functionalities for premium services. [Explore Elements API](https://learn.avepoint.com/elements/Overview.html) for more details. 


- **Insights**
  - Introduced the new endpoint `/insights/google/activities/object/{id}/export` for exporting activities performed on a specific Google object.  
  - Introduced the new endpoint `/insights/google/users/{email}/activities/export` for exporting activity data for a specific Google user.  
  - Introduced the new endpoint `/insights/google/users/{email}/access/export` for exporting Google user access report.  <!--  -->
  - Introduced the new endpoint `/insights/google/groups/{groupId}/access/export` for exporting Google group access report.  
  - Introduced the new endpoint `/insights/google/drives/permission/export` for exporting Google drive permissions.  
  - Introduced the new endpoint `/insights/google/sharingLinks/export` for exporting permission related information for Google sharing links.  

- **EnPower**
  - Introduced the following new endpoints for Power App data retrieval:
    - `/smp/powerplatform/powerapps/{appId}/activities` for app activities.
    - `/smp/powerplatform/powerapps/{appId}/launches` for apps' launching history.
    - `/smp/powerplatform/powerapps/{appId}/launched-users` for users who launched apps.
  - Introduced the following new endpoints for Power Automate data retrieval:
    - `/smp/powerplatform/powerautomate/cloudflows/{flowId}/runs` for cloud flows' running history.
    - `/smp/powerplatform/powerautomate/cloudflows/{flowId}/activities` for cloud flow activities.
    - `/smp/powerplatform/connectionusage/cloudflows` for cloud flows' connection usage.
    - `/smp/powerplatform/powerautomate/desktopflows` for desktop flows' details.
    - `/smp/powerplatform/powerautomate/desktopflows/{flowId}/runs` for desktop flows' running history.
  - Introduced the following new endpoints for Power BI data retrieval:
    - `/smp/powerplatform/powerbi/datasourcecountbydatasourcetype` for data source counts.
    - `/smp/powerplatform/powerbi/datasourcedetails` for data source details.
    - `/smp/powerplatform/powerbi/semanticemodeldetails` for semantic model details.
    - `/smp/powerplatform/powerbi/semanticmodelcountbydatasourcetype` for semantic models by data sources.
    - `/smp/powerplatform/powerbi/powerbiactiveusers` for active Power BI users.
  - Introduced the following new endpoints for Copilot Studio data retrieval:
    - `/smp/powerplatform/bot` for Copilot Studio agent details.
    - `/smp/powerplatform/bot/{botId}/activities` for Copilot Studio agent activities.
  - Added the following properties to the response of the `/smp/powerplatform/powerapps` endpoint:
    - `creatorCountry`
    - `creatorId`
    - `creatorJobTitle`
    - `lastActivityDate`
  - Added the following properties to the response of the `/smp/powerplatform/powerautomate/cloudflows` endpoint:
    - `creatorCountry`
    - `creatorEmail`
    - `creatorId`
    - `creatorJobTitle`
    - `creatorUpn`
  - Added the following properties to the response of the `/smp/powerplatform/connections` endpoint:
    - `connectorCreatedTime`
    - `ownerCountry`
  - Added the following properties to the response of the `/smp/powerplatform/powerbi/artifacts` endpoint:
    - `lastRenewNotifyTime`
    - `creatorDisplayName`
    - `viewsOfLast7Days`
    - `uniqueViewersOfLast7Days`
    - `viewsOfLast30Days`
    - `uniqueViewersOfLast30Days`
    - `viewsOfLast90Days`
    - `uniqueViewersOfLast90Days`


### Changed

- **Cloud Backup for Microsoft 365**
  - Updated the `/backup/m365/jobs` endpoint to `/backup/m365/cloudbackupjobs` and improved the response structure.
  - Updated the `/backup/m365/licenseconsumption` endpoint to `/backup/m365/cloudbackuplicenseconsumption` and improved the response structure.
  - Updated the `/backup/m365/unusualactivitydata` endpoint to `/backup/m365/cloudbackupunusualactivitydata` and improved the response structure.

## August 2025

### Added

- Added the `phaseStartTime`, `renewalDueDate`, and `nextRenewalDate` properties to the response of the following endpoints:
  - `/smp/powerplatform/environments`
  - `/smp/powerplatform/powerapps`
  - `/smp/powerplatform/powerautomate/cloudflows`
  - `/smp/powerplatform/powerbi/workspaces`
  - `/smp/exchange/mailboxes`

### Changed

- **AvePoint Online Services**
  - Enhanced the `/aos/audit` endpoint to support filtering for Cloud Backup for Dynamics 365.
- **Cloud Backup for Google Workspace**
  - Enhanced the `/backup/google/admin/jobs` endpoint to support filtering for Google Directory (including users and groups) and Google Vault (including Gmail, Drive, and shared drives).
- **Cloud Backup for IaaS + PaaS**
  - Enhanced the `/backup/vm/jobs` endpoint to support filtering for Google VM backup and restore jobs.
- **EnPower**
  - Removed the following properties from the `/smp/exchange/resourcemailboxes` endpoint:
    - `lastRenewalTime`
    - `lastRenewalBy`
    - `renewProfileApplied`
    - `electionProfileApplied`
    - `phaseAssignees`
    - `renewProfile`
    - `electionProfile`
  - Updated the type of `recipientLimits` of the `/smp/exchange/mailboxes` endpoint to `string`.
- **Elements**
  - Enhanced the `/partner/customers/{id}/scanProfiles/{ProfileId}/dailyNewSummary` endpoint to support the last scan job status of **In progress**.

## June 2025

### Added  

- Introduced the new endpoint `/aos/jobs` to **AvePoint Online Services** for retrieving scan job information.
- Public APIs for **Elements** are now fully supported in GCC and GCC High tenants.  
- Introduced the new endpoint `/insights/sites/{siteId}/{objectUrl}/settag` to **Insights** for tagging objects.  
- Added the `webUrl` property to the response of the `/insights/sites/{siteId}/detailRecords` endpoint.

## April 2025

### Added  

- The public APIs for **AvePoint Online Services**, **Cloud Backup for Microsoft 365**, **Cloud Backup for Google Workspace**, **Insights**, and **AvePoint Opus**, now fully support **GCP data center endpoints**.
- Introduced new endpoints to EnPower for retrieving Exchange objects:
  - `/smp/exchange/resourcemailboxes`
  - `/smp/exchange/mailboxes`
- Added the `jobType` property to the response of the `backup/vm/jobs` endpoint.

### Changed

- **Cloud Backup for Microsoft 365**
  - Updated the `/backup/m365/cloudbackup/getjobs` endpoint to `/backup/m365/jobs`.
  - Updated the `/backup/m365/cloudbackup/licenseconsumption` endpoint to `/backup/m365/licenseconsumption`.
  - Updated the `/backup/m365/cloudbackup/unusualactivitydata` endpoint to `/backup/m365/unusualactivitydata`.
- **Elements**
  - Updated the `/partner/customers/{id}/scanProfilesDetails/profileId/{ProfileId}` endpoint to `/partner/customers/{id}/scanProfiles/{ProfileId}`.
  - Updated the `/partner/customers/{id}/scanProfilesDailyNew/profileId/{ProfileId}` endpoint to `/partner/customers/{id}/scanProfiles/{ProfileId}/dailyNewSummary`.
  - Updated the `/partner/customers/{id}/scanProfilesDailyNewDetail/profileId/{ProfileId}` endpoint to `/partner/customers/{id}/scanProfiles/{ProfileId}/dailyNewDetails`.
- **EnPower**
  - Removed the `ownerCount` and `userCount` properties from the response of the `/smp/powerplatform/powerapps` endpoint.

### Fixed

- Corrected the spelling mistake of the `conflictOption` property in the request of the `/records/connector/records` endpoint. It was previously misspelled as `confilictOption`.
- Corrected the following property types in the `/smp/powerplatform/environments` endpoint response:
  - Corrected the type of `phaseAssignees` to `Object`.
  - Corrected the type of `dlpPolicies` to `Integer`.
- Documented the `location` query parameter for the `/backup/m365/jobs` and `backup/m365/licenseconsumption` endpoints.

## February 2025

### Added

- Introduced new endpoints to AvePoint Graph API for:
  - Cloud Backup for Google Workspace
  - AvePoint Opus
  - Insights for Microsoft 365
  - EnPower  
- Implemented new API for retrieving unusual activities or potential ransomware attacks for Microsoft 365 environment in the `/backup/m365/cloudbackup/unusualactivitydata` endpoint.

### Changed

- Enhanced the `/aos/audit` endpoint to support filtering for Cloud Backup for Google Workspace.  
- Added `purchasedUnits`, `source`, `paymentType`, `subscriptionName`, `package`, and `contractEndDate` parameters to the `/partner/services` and `/partner/services/{id}` endpoints.
- Updated the type of the following parameters related to object count to `string` in the `/partner/customers/{id}/jobs` and `/partner/customers/{id}/jobs/jobType/{JobType}/jobModule/{JobModule}` endpoints:
  - `totalCount`
  - `failedCount`
  - `successfulCount`
  - `skippedCount`
  - `warningCount`
<!---## January 2025 hotfix

### Fixed
- Resolved the issue with the `Dynamics.ReadWrite.All` scope where the API does not work when using it with the other scopes.  -->

## December 2024

### Added

- Initial release of the AvePoint Graph API.
- Introduced endpoints for retrieving audit records, managing partner operations, and accessing job information and subscription consumption from AvePoint Cloud Backup solutions.

### Deprecated

- Marked the legacy API for deprecation after the December 2024 release. Transition to the current API is recommended.
