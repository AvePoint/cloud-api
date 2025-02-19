# Change Log

This document provides a detailed log of changes, updates, and enhancements made to the AvePoint Graph API. It includes information on newly introduced features, improvements to existing functionalities, and any fixes applied. Stay up-to-date with the latest modifications to ensure optimal integration and utilization of the API.

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
- Introduced endpoints for retrieving audit records, managing partner operations, and accessing job information from AvePoint Cloud Backup solutions.

### Deprecated
- Marked the legacy API for deprecation after the December 2024 release. Transition to the modern API is recommended.