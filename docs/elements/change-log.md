# Change Log

This document provides a detailed log of changes, updates, and enhancements made to the Elements API. It includes information on newly introduced features, improvements to existing functionalities, and any fixes applied. Stay up-to-date with the latest modifications to ensure optimal integration and utilization of the API.

## October 2025

### Added  

  - Introduced new endpoints for common features. 
    - `/partner/external/v3/general/customers/batch` for retrieving the information of all customers managed by the current partner.
    - `/partner/external/v3/general/customers` for onboarding a customer to the current partner.
    - `/partner/external/v3/general/customers/{customerId}/services` for adding a service for a customer.
    - `/partner/external/v3/general/customers/services/batch` for retrieving the services of customers managed by the current partner.
    - `/partner/external/v3/general/customers/{customerId}/3rd-party-products/type/{type}/tenants/batch` for retrieving the numbers of assigned and available user seats of customer's tenant.
    - `/partner/external/v3/general/customers/{customerId}/avpt-products/type/{productType}/overview` for retrieving the purchased user seats for AvePoint products of the customer.
    - `/partner/external/v3/general/customers/{customerId}/tenants/{tenantId}/cloud-backup-m365/users/batch` for retrieving the protected status of users in the customer's tenant by Cloud Backup for Microsoft 365.
    - `/partner/external/v3/general/customers/{customerId}/cloud-backup-m365/overview` for retrieving the customer's protected data information of Cloud Backup for Microsoft 365.
    - `/partner/external/v3/general/customers/{customerId}/avpt-products/jobs/batch` for retrieving the job details of the backup services for a specific customer.
    - `/partner/external/v3/general/customers/{customerId}/scan-profiles/batch` for retrieving all scan profiles configured for a specific customer in AvePoint Online Services.
    - `/partner/external/v3/general/customers/{customerId}/scan-profiles/{scanProfileId}` for retrieving the details of a specific scan profile configured in AvePoint Online Services for a customer.
    - `/partner/external/v3/general/customers/{customerId}/scan-profiles/{scanProfileId}/changes` for retrieving the daily scan profile changes in AvePoint Online Services for a customer.
  - Introduced new endpoints for baseline management.  
    - `/partner/external/v3/bm/baselines` for creating a baseline from a tenant to establish benchmarks for tenant configurations.
    - `/partner/external/v3/bm/baselines/batch` for retrieving the general information of baselines.
    - `/partner/external/v3/bm/baselines/{baselineId}/reports` for retrieving the report details of a baseline creation job.
    - `/partner/external/v3/bm/customers/{customerId}/tenants/{tenantId}/process-center/jobs/batch` for retrieving job information from the Process center page.
     - `/partner/external/v3/bm/tenants/batch` for retrieving the general information of tenants added to the Baseline Management module.
     - `/partner/external/v3/bm/customers/{customerId}/tenants/{tenantId}/actions` for monitoring a tenant by performing specific actions to the tenant.
  - Introduced new endpoints for risk management.
    - `/partner/external/v3/rm/customers/{customerId}/tenants/{tenantId}/detection/rules` for retrieving all matched risk rules for a specific tenant.
    - `/partner/external/v3/rm/customers/{customerId}/tenants/{tenantId}/detection/rules/{ruleId}/hit-items` for retrieving the objects that violate a specific risk rule.
  - Introduced new endpoints for user management.
    - `/partner/external/v3/um/customers/{customerId}/tenants/{tenantId}/overview/security/users` for retrieving information of security users in a customer's tenant.
    - `/partner/external/v3/um/customers/{customerId}/tenants/{tenantId}/users/{userId}` for retrieving information of a specific user in a customer's tenant.
    - `/partner/external/v3/um/customers/{customerId}/tenants/{tenantId}/users/batch` for retrieving information of multiple users in a customer's tenant.
    - `/partner/external/v3/um/customers/{customerId}/tenants/{tenantId}/users/{userId}/account-information` for updating information of a specific user in a customer's tenant.
    - `/partner/external/v3/um/customers/{customerId}/tenants/{tenantId}/users/{userId}/birthday` for updating the birthday of a specific user in a customer's tenant.
    - `/partner/external/v3/um/customers/{customerId}/tenants/{tenantId}/users/{userId}/contact-information` for updating the contact information of a specific user in a customer's tenant.
    - `/partner/external/v3/um/customers/{customerId}/tenants/{tenantId}/users/{userId}/alternate-email-address` for updating the alternate email address of a specific user in a customer's tenant.
    - `/partner/external/v3/um/customers/{customerId}/tenants/{tenantId}/users/{userId}/general-information` for updating the general information of a specific user in a customer's tenant.
    - `/partner/external/v3/um/customers/{customerId}/tenants/{tenantId}/users/{userId}/istest` for updating the test user property of a specific user in a customer's tenant.
    - `/partner/external/v3/um/customers/{customerId}/tenants/{tenantId}/users/{userId}/manager` for updating the manager of a specific user in a customer's tenant.
    - `/partner/external/v3/um/customers/{customerId}/tenants/{tenantId}/users/{userId}/office` for updating the office information of a specific user in a customer's tenant.
    - `/partner/external/v3/um/customers/{customerId}/tenants/{tenantId}/users/{userId}/office-information` for updating the office location information of a specific user in a customer's tenant.
    - `/partner/external/v3/um/customers/{customerId}/tenants/{tenantId}/users/{userId}/password-setting` for updating the password setting of a specific user in a customer's tenant.
    - `/partner/external/v3/um/customers/{customerId}/tenants/{tenantId}/overview/security/compliances/workflows` for retrieving information of workflows in a customer's tenant.
    - `/partner/external/v3/um/customers/{customerId}/tenants/{tenantId}/overview/security/compliances/actions` for retrieving the risky action count in a customer's tenant.
    - `/partner/external/v3/um/customers/{customerId}/tenants/{tenantId}/overview/security/compliances/workflows/{workflowId}` for retrieving compliance information of a specific workflow in a customer's tenant. 
    - `/partner/external/v3/um/customers/{customerId}/tenants/{tenantId}/overview/security/compliances/signins` for retrieving users' sign-in information in a customer's tenant.
  - Introduced new endpoints for workspace management.
    - `/partner/external/wm/customers/{customerId}/tenants/{tenantId}/overview/workspace`	for retrieving the workspace overview statistics of a specific tenant.
    - `/partner/external/wm/customers/{customerId}/tenants/{tenantId}/overview/data-protection/compliance-rate` for retrieving the compliance statistics of workspaces for a specific tenant.
    - `/partner/external/wm/customers/{customerId}/tenants/{tenantId}/overview/dspm/insights` for retrieving the data security posture statistics of a specific tenant.
    - `/partner/external/wm/customers/{customerId}/tenants/{tenantId}/overview/data-protection/ransomware-detection` for retrieving the data protection statistics of a specific tenant.
