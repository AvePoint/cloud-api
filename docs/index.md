---
_layout: landing
---

# Overview of AvePoint Graph API

The AvePoint Graph API is a powerful suite of tools designed to provide seamless integration and robust functionalities for managing and optimizing your digital collaboration environment. This API allows developers to interact programmatically with AvePoint's solutions, facilitating automation, data integration, and enhanced operational capabilities.  

Below is a comprehensive overview of the available APIs:  

- Legacy API - Facilitates actions such as retrieving audit records, importing objects, registering a partner's customer, and obtaining Cloud Backup for Microsoft 365 job information. For details, refer to [AvePoint Online Services Web API Help](https://avepointcdn.azureedge.net/assets/webhelp/avepoint-online-services-api/index.htm).  
- Modern API - Offers advanced authentication methods, including client secret and certificate authentication. For details, refer to [What's in AvePoint Graph Modern API](#whats-in-avepoint-graph-modern-api)  
- Partner API - Designed for managing multiple customers under a single partner registration.  

By leveraging these APIs, you can efficiently manage and interact with your cloud data in AvePoint Confidence Platform, ensuring seamless integration and enhanced productivity.  

## What's in AvePoint Graph Modern API

AvePoint Graph Modern API offers a single endpoint, https://graph.avepointonlineservices.com, to provide access to AvePoint services data.

### Introduction

By leveraging advanced authentication methods, this API ensures secure and efficient access to a wide range of functionalities. These functionalities encompass retrieving audit records from AvePoint Online Services, managing partners via the Elements platform, and obtaining detailed job information from AvePoint's Cloud Backup solutions for Microsoft 365, Microsoft Azure, AWS, and Dynamics 365. AvePoint Graph Modern API is tailored to meet the needs of IT professionals seeking robust and scalable solutions for their data management and backup monitoring.  

### Key Features

- Advanced Authentication Method: Secure access using client secret and certificate authentication.  

- Audit Records Retrieval: Comprehensive monitoring and tracking of user activities to ensure compliance and security.  

- Partner Management via Elements: Efficient partner operations and integration management.

- Job Information Retrieval: Detailed insights into Cloud Backup operations to ensure data integrity and availability.  

### Use Cases  

By integrating the AvePoint Graph Modern API into the operations, organizations can achieve enhanced control, security, and efficiency in managing their data and IT services.  

#### Secure Data Access and Management  

Organizations can ensure that only authorized users can retrieve or manipulate data using robust authentication methods, ideal for enterprises with stringent security and compliance requirements.  

#### Compliance and Security Audits  

IT administrators can retrieve audit records from AvePoint Online Services to facilitate regular compliance checks and security audits, helping identify any unauthorized activities and maintaining a secure environment.  

#### Streamline Partner Operations  

Businesses can manage their partners more efficiently via the Elements platform, leveraging the API to integrate and automate partner-related workflows, and enhance collaboration and operational efficiency between the organization and its partners.  

#### Comprehensive Backup Management  

IT professionals can monitor backup status, performance, and issues by accessing detailed job information from various AvePoint Cloud Backup services.

## Use AvePoint Graph Modern API

### Namespace

### Authentication and Authorization

To access the resources of AvePoint Cloud Services via the AvePoint Graph Modern API, it's essential to correctly configure app registration and grant the necessary permissions. This process involves registering an app in AvePoint Online Services, setting up appropriate permissions, and using the generated application (client) ID for authentication.  

For detailed instructions on creating an app registration for API authentication, refer to [Configure App Registration](https://cdn.avepoint.com/assets/webhelp/avepoint-online-services/index.htm#!Documents/configureappregistrations.htm) section in AvePoint Online Services User Guide.

### Call an API Method

To read from or write to a resource such as a user or an email message, you construct a request that looks like the following:  

    {HTTP method} https://graph.avepointonlineservices.com/{version}/{resource}?{query-parameters}  

The components of a request include:

- {HTTP method} - The HTTP method used for the request.
- {version} - The API version.
- {resource} - The referenced resource.
- {query-parameters} - Optional parameters to customize the response.

After making a request, a response is returned that includes:

- Status code - An HTTP status code that indicates success or failure.  
- Response message - The data that you requested or the result of the operation. The response message can be empty for some operations.
- nextLink - If your request returns a lot of data, you need to page through it by using the URL returned in nextLink. For details, see Paging.--->
- Response headers - Additional information about the response, such as the type of content returned and the request-id that you can use to correlate the response to the request.  

### HTTP methods

AvePoint Graph Modern API uses the HTTP method on your request to determine what your request is doing. Depending on the resource, the API supports various operations including:  

| Method | Description |  
|------|------|  
|GET|Read data from a resource.|  
|POST|Create a new resource, or perform an action.|

- For the CRUD methods GET and DELETE, no request body is required.  
- The POST, PATCH, and PUT methods require a request body, usually specified in JSON format, that contains additional information, such as the values for properties of the resource.  

> [!IMPORTANT] Important  
> Write requests in the Microsoft Graph API have a size limit of 4 MB.  
> In some cases, the actual write request size limit is lower than 4 MB. For example, attaching a file to a user event by POST /me/events/{id}/attachments has a request size limit of 3 MB, because a file around 3.5 MB can become larger than 4 MB when encoded in base64.  
> Requests exceeding the size limit fail with the status code HTTP 413, and the error message "Request entity too large" or "Payload too large".

### Resource  

A resource can be an entity or complex type, commonly defined with properties.  Your URL will include the resource you are interacting with in the request, such as `customers`, `services`, and `job`. You can also interact with resources using methods; for example,  

Reference [Use the API > Overview](https://learn.microsoft.com/en-us/graph/use-the-api).  

https://developer.microsoft.com/en-us/graph/quick-start  

## API Changelog  
