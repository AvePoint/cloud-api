# Change Log

This document provides a detailed log of changes, updates, and enhancements made to the AvePoint Graph API for Elements. It includes information on newly introduced features, improvements to existing functionalities, and any fixes applied. Stay up-to-date with the latest modifications to ensure optimal integration and utilization of the API.

## October 2025

### Added  

  - Introduced new endpoints for common features. 
    - `/partner/external/v3/general/customers/batch` for retrieving the information of all customers managed by the current partner.
    - `/partner/external/v3/general/customers` for onboarding a customer to the current partner.
    - `/partner/external/v3/general/customers/{customerId}/services` for adding a service for a customer.
    - `/partner/external/v3/general/customers/services/batch` for retrieving the services of customers managed by the current partner.
    - `/partner/external/v3/general/customers/{customerId}/3rd-party-products/type/{type}/users` for retrieving the numbers of assigned and available user seats of customer's tenant.
    - `/partner/external/v3/general/customers/{customerId}/avpt-products/type/{productType}/overview` for retrieving the purchased user seats for AvePoint products of the customer.
    - `/partner/external/v3/general/customers/{customerId}/tenants/{tenantId}/cloud-backup-m365/users/batch` for retrieving the protected status of users in the customer's tenant by Cloud Backup for Microsoft 365.
    - `/partner/external/v3/general/customers/{customerId}/cloud-backup-m365/overview` for retrieving the customer's protected data information of Cloud Backup for Microsoft 365.
    - `/partner/external/v3/general/customers/{customerId}/avpt-products/jobs/batch` for retrieving the job details of the backup services for a specific customer.
    - `/partner/external/v3/general/customers/{customerId}/scan-profiles/batch` for retrieving all scan profiles configured for a specific customer in AvePoint Online Services.
    - `/partner/external/v3/general/customers/{customerId}/scan-profiles/{scanProfileId}` for retrieving the details of a specific scan profile configured in AvePoint Online Services for a customer.
    - `/partner/external/v3/general/customers/{customerId}/scan-profiles/{scanProfileId}/changes` for retrieving the daily scan profile changes in AvePoint Online Services for a customer.
  - Introduced new endpoints for baseline management.  
  - Introduced new endpoints for risk management.
    - `/partner/external/v3/rm/customers/{customerId}/tenants/{tenantId}/detection/rules` for retrieving all matched risk rules for a specific tenant.
    - `/partner/external/v3/rm/customers/{customerId}/tenants/{tenantId}/detection/rules/{ruleId}/hit-items` for retrieving the objects that violate a specific risk rule.
  - Introduced new endpoints for user management.
  - Introduced new endpoints for workspace management.
    - `/partner/external/wm/customers/{customerId}/tenants/{tenantId}/overview/workspace`	for retrieving the workspace overview statistics of a specific tenant.
    - `/partner/external/wm/customers/{customerId}/tenants/{tenantId}/overview/data-protection/compliance-rate` for retrieving the compliance statistics of workspaces for a specific tenant.
    - `/partner/external/wm/customers/{customerId}/tenants/{tenantId}/overview/dspm/insights` for retrieving the data security posture statistics of a specific tenant.
    - `/partner/external/wm/customers/{customerId}/tenants/{tenantId}/overview/data-protection/ransomware-detetion` for retrieving the data protection statistics of a specific tenant.
