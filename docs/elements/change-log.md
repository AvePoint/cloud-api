# Change Log

This document provides a detailed log of changes, updates, and enhancements made to the AvePoint Graph API for Elements. It includes information on newly introduced features, improvements to existing functionalities, and any fixes applied. Stay up-to-date with the latest modifications to ensure optimal integration and utilization of the API.

## October 2025

### Added  

  - Introduced new endpoints for common features. 
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
