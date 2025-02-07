# Change Log

This document provides a detailed log of changes, updates, and enhancements made to the API. It includes information on newly introduced features, improvements to existing functionalities, and any fixes applied. Stay up-to-date with the latest modifications to ensure optimal integration and utilization of the API.

## February 2025

### Added
- Introduced new endpoints for Cloud Backup for Google Workspace, AvePoint Opus, Insights for Microsoft 365, and EnPower.   
- Implemented new API for retrieving unusual activities or potential ransomware attacks for Microsoft 365 environment in the `/backup/m365/cloudbackup/unusualactivitydata` endpoint. 

### Changed
- Enhanced the `/aos/audit` endpoint to support filtering for Cloud Backup for Google Workspace.  

<!---## January 2025 hotfix

### Fixed
- Resolved the issue with the `Dynamics.ReadWrite.All` scope where the API does not work when using it with the other scopes.  -->


## December 2024

### Added

- Initial release of the AvePoint Graph Modern API.
- Introduced endpoints for retrieving audit records, managing partner operations, and accessing job information from AvePoint Cloud Backup solutions.

### Deprecated
- Marked the legacy API for deprecation after the December 2024 release. Transition to the modern API is recommended.