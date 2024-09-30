# Overview of AvePoint Graph Modern API

The AvePoint Graph Modern API is a robust suite of tools designed to streamline integration and enhance functionalities for managing your digital collaboration environment. This API allows developers to interact programmatically with AvePoint's solutions, facilitating automation, data integration, and enhanced operational capabilities.  

## Available APIs  

### Modern API  
- Offers advanced authentication methods, including client secret and certificate authentication.  
- Provides a single endpoint at https://graph.avepointonlineservices.com for accessing AvePoint services data. Note that it differs upon the data center you want to access. For details, refer to [Endpoints Upon Data Centers](#endpoints-upon-data-center).

### Legacy API  
- Enables actions such as retrieving audit records, importing objects, registering a partner's customer, and obtaining Cloud Backup for Microsoft 365 job information.  
- For details, refer to [AvePoint Online Services Web API Help](https://avepointcdn.azureedge.net/assets/webhelp/avepoint-online-services-api/index.htm). 
- Note that AvePoint plans to deprecate these legacy APIs following the December release. It is recommended to transit to the modern APIs to ensure continued functionality and support.  

By leveraging these APIs, you can efficiently manage and interact with your cloud data in AvePoint Confidence Platform, ensuring seamless integration and enhanced productivity.  

## What's in AvePoint Graph Modern API

AvePoint Graph Modern API offers a unified endpoint to rovide access to AvePoint services data.

### Introduction

Using advanced authentication methods, this API ensures secure and efficient access to a wide range of functionalities. These include retrieving audit records from AvePoint Online Services, managing partners via the Elements platform, and obtaining detailed job information from AvePoint's Cloud Backup solutions for Microsoft 365, Microsoft Azure, AWS, and Dynamics 365. It is tailored to meet the needs of IT professionals seeking robust and scalable solutions for their data management and backup monitoring.  

### Key Features

- Advanced Authentication Method: Secure access using client secret and certificate authentication.  

- Audit Records Retrieval: Comprehensive monitoring and tracking of user activities to ensure compliance and security.  

- Partner Management via Elements: Efficient partner operations and integration management.

- Job Information Retrieval: Detailed insights into Cloud Backup operations to ensure data integrity and availability.  

### Endpoints Upon Data Center

| Region                    | URL                                 |
|------------------------------|---------------------------------|
| APAC - Australia          | [https://graph-au.avepointonlineservices.com/](https://graph-au.avepointonlineservices.com/) |
| APAC - Singapore                    | [https://graph-sg.avepointonlineservices.com/](https://graph-sg.avepointonlineservices.com/) |
| Canada Central (Toronto)            | [https://graph-ca.avepointonlineservices.com/](https://graph-ca.avepointonlineservices.com/) |
| EMEA - Ireland                      | [https://graph-ne.avepointonlineservices.com/](https://graph-ne.avepointonlineservices.com/) |
| EMEA - Netherlands                  | [https://graph-we.avepointonlineservices.com/](https://graph-we.avepointonlineservices.com/) |
| France Central (Paris)              | [https://graph-fr.avepointonlineservices.com/](https://graph-fr.avepointonlineservices.com/ ) |
| Germany West Central (Frankfurt)    | [https://graph-de.avepointonlineservices.com/ ](https://graph-de.avepointonlineservices.com/ ) |
| Japan West - Osaka                  | [https://graph-jp.avepointonlineservices.com/ ](https://graph-jp.avepointonlineservices.com/ ) |
| Korea Central (Seoul)               | [https://graph-kr.avepointonlineservices.com/ ](https://graph-kr.avepointonlineservices.com/ ) |
| Switzerland North (Zurich)          | [https://graph-ch.avepointonlineservices.com/ ](https://graph-ch.avepointonlineservices.com/ ) |
| UK South (London)                   | [https://graph-uk.avepointonlineservices.com/ ](https://graph-uk.avepointonlineservices.com/ ) |
| US - East                           | [https://graph-us.avepointonlineservices.com/ ](https://graph-us.avepointonlineservices.com/ ) |