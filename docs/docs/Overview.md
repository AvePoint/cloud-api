# Overview

The AvePoint Graph API is a robust suite of tools designed to streamline integration and enhance functionality for managing your digital collaboration environment. It allows developers to interact programmatically with AvePoint's solutions, facilitating automation, data integration, and enhanced operational capabilities.  

The API provides advanced features to optimize integration and security:  

- Authentication methods: Supports client secret and certificate authentication for secure and efficient access control. This flexibility allows developers to choose the most suitable authentication method for their needs.  
- Unified endpoint: The API can be accessed via a unified endpoint format `https://graph-{dc}.avepointonlineservices.com`. Note that the endpoint differs based upon the data center you want to access. For details, refer to [Endpoints Upon Data Centers](#endpoints-upon-data-center). 
  > [!NOTE]
  > For users of the Elements API, there is an added convenience. The Elements API supports a single endpoint (`https://graph.avepointonlineservices.com`), meaning you do not need to adjust the endpoint based on the data center. This can simplify your integration process and reduce configuration overhead.

- Comprehensive functionality: Enables seamless interaction with AvePoint services, supporting tasks like data management, reporting, and configuration.  
- Scalability and performance: Designed to handle large-scale operations, ensuring reliability and speed in various enterprise scenarios.  

## Legacy API  

The legacy API offers essential capabilities but is slated for deprecation:  

- Functionalities:  
  - Retrieve audit records for compliance and monitoring.  
  - Import objects into AvePoint Online Services for streamlined data management.  
  - Register partner customers to facilitate partner integrations.  
  - Access Cloud Backup for Microsoft 365 job information for backup management.  

- **Deprecation Notice**: This API has been deprecated after the December 2024 release. Transitioning to the current API is highly recommended to ensure continued support and access to the latest features.  
- Documentation: For additional details on the legacy API, refer to [AvePoint Online Services Web API Help](https://avepointcdn.azureedge.net/assets/webhelp/avepoint-online-services-api/index.htm).  

## What's in the current AvePoint Graph API

AvePoint Graph API provides a unified endpoint to accessing AvePoint services data, designed to cater to IT professionals seeking robust data management, data insights, and backup monitoring solutions.  

### Introduction

The AvePoint Graph API employs advanced authentication methods to ensure secure and efficient access to a wide range of functionalities. These include:  

- Retrieve audit records: Access comprehensive records from AvePoint Online Services.  
- Streamline partner operations on customer management: Enhance efficiency in handling customer data and interactions through the Elements platform.  
- Job information retrieval: Obtain detailed job data from AvePoint's Cloud Backup solutions for Microsoft 365, Microsoft Azure, AWS, Dynamics 365, and Google Workspace.  
- EnPower data retrieval: Access and manage Exchange mailboxes and Power Platform data.  
- Insights data retrieval: Access detailed reports and data insights from Insights for Microsoft 365.  
- AvePoint Opus data management: Submit records to AvePoint Opus, retrieve due records, and destroy records.  

### Key Features

- Advanced Authentication Methods: Secure access using client secret and certificate authentication.  

- Audit Records Retrieval: Comprehensive monitoring and tracking of user activities to ensure compliance and security.  

- Partner Management via Elements: Efficient partner operations and integration management.

- Job Information Retrieval: Detailed insights into Cloud Backup operations to ensure data integrity and availability.  

- EnPower Data Retrieval: Manage and retrieve data for Exchange mailboxes and Power Platform environments, connections, Power Apps, Power Automate Cloud Flows, and Power BI artifacts.  

- Insights Data Retrieval: Export and retrieve detailed reports and data insights for Microsoft 365.  

- AvePoint Opus Data Management: Submit, retrieve, or destroy records to ensure the records are managed according to their lifecycle and compliance requirements.  


For more features and use cases, visit the [Use Cases](Use-Cases.md).  

### Endpoints Upon Data Center

>[!NOTE]
>Effective April 2025 release, AvePoint Online Services commercial production environment now supports the following **Google Cloud Platform (GCP) data centers**: 
> - GCP for Australia Southeast (Sydney) 
> - GCP for Japan (Tokyo) 
> - GCP for East US (Moncks Corner) 
> - GCP for West Europe (Eemshaven, Netherlands) 
> 
> These GCP data centers are currently deployed with the following AvePoint services:
> - AvePoint Online Services
> - Cloud Backup for Microsoft 365
> - Cloud Backup for Google Workspace
> - AvePoint Opus
> - Insights
> 
> In addition to the core deployments, the **public APIs** for these products now fully support **GCP data center endpoints**.  

Refer to the data center endpoints in the table below: 

|Infrastructure | Region                    | URL                                 |
|---|------------------------------|---------------------------------|
|Microsoft Azure | APAC - Australia          | `https://graph-au.avepointonlineservices.com/`|
|| APAC - Singapore                    | `https://graph-sg.avepointonlineservices.com/`|
|| Canada Central (Toronto)            | `https://graph-ca.avepointonlineservices.com/`|
|| EMEA - Ireland                      | `https://graph-ne.avepointonlineservices.com/` |
|| EMEA - Netherlands                  | `https://graph-we.avepointonlineservices.com/` |
|| France Central (Paris)              | `https://graph-fr.avepointonlineservices.com/` |
|| Germany West Central (Frankfurt)    | `https://graph-de.avepointonlineservices.com/` |
|| Japan West - Osaka                  | `https://graph-jp.avepointonlineservices.com/` |
|| Korea Central (Seoul)               | `https://graph-kr.avepointonlineservices.com/` |
|| Switzerland North (Zurich)          | `https://graph-ch.avepointonlineservices.com/` |
||UK South (London)                   | `https://graph-uk.avepointonlineservices.com/` |
|| US - East                           | `https://graph-us.avepointonlineservices.com/`|
|| AOS-US Gov                           |`https://graph-gov.avepointonlineservices.com/`|
|Google Cloud Platform| Australia Southeast (Sydney): **australia-southeast1**|`https://graph-gcp-au.avepointonlineservices.com/`|
||Japan (Tokyo): **asia-northeast1**|`https://graph-gcp-jp.avepointonlineservices.com/`|
||East US (Moncks Corner): **us-east1**|`https://graph-gcp-us.avepointonlineservices.com/`|
||West Europe (Eemshaven, Netherlands): **europe-west4**|`https://graph-gcp-we.avepointonlineservices.com/`|
||South Korea (Seoul): **asia-northeast3** |`https://graph-gcp-kr.avepointonlineservices.com/`|

