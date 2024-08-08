---
_layout: landing
---

# AvePoint Graph API Overview  

The AvePoint Graph API is a powerful suite of tools designed to provide seamless integration and robust functionalities for managing and optimizing your digital collaboration environment. This API allows developers to interact programmatically with AvePoint's solutions, facilitating automation, data integration, and enhanced operational capabilities. The current version of the AvePoint Graph API encompasses two primary components: AvePoint Confidence Platform and Elements for Partners.  

## About AvePoint Graph API

### Introduction

### Key Features

### Use Cases

## Use AvePoint Graph API

### Namespace

The AvePoint Graph API defines most of its resources, methods, and enumerations in the OData namespace, `avepoint.graph`, in the AvePoint Graph metadata. A small number of API sets are defined in their sub-namespaces, such as the call records API which defines resources like callRecord in microsoft.graph.callRecords.

Unless explicitly specified in the corresponding topic, assume types, methods, and enumerations are part of the microsoft.graph namespace.

### Authentication and Authorization

### Call an AvePoint Graph API Method

To read from or write to a resource such as a user or an email message, you construct a request that looks like the following:  

    {HTTP method} https://graph.microsoft.com/{version}/{resource}?{query-parameters}  

The components of a request include:

- {HTTP method} - The HTTP method used on the request to Microsoft Graph.
- {version} - The version of the Microsoft Graph API your application is using.
- {resource} - The resource in Microsoft Graph that you're referencing.
- {query-parameters} - Optional OData query options or REST method parameters that customize the response.
- {headers} - Request headers that customize the request. Can be optional or required depending on the API.
After you make a request, a response is returned that includes:

- Status code - An HTTP status code that indicates success or failure. For details about HTTP error codes, see Errors.
- Response message - The data that you requested or the result of the operation. The response message can be empty for some operations.
<!---   @odata.nextLink - If your request returns a lot of data, you need to page through it by using the URL returned in @odata.nextLink. For details, see Paging.--->
- Response headers - Additional information about the response, such as the type of content returned and the request-id that you can use to correlate the response to the request.  


### HTTP methods

Microsoft Graph uses the HTTP method on your request to determine what your request is doing. Depending on the resource, the API may support operations including actions, functions, or CRUD operations described below.

| Method | Description |  
|------|------|  
|GET|Read data from a resource.|  
|POST|Create a new resource, or perform an action.|
|PATCH|Update a resource with new values, or upsert a resource (create if resource doesn't exist, update otherwise).|  
|PUT|Replace a resource with a new one.|  
|DELETE|Remove a resource.|  


For the CRUD methods GET and DELETE, no request body is required.
The POST, PATCH, and PUT methods require a request body, usually specified in JSON format, that contains additional information, such as the values for properties of the resource.
 Important

Write requests in the Microsoft Graph API have a size limit of 4 MB.

In some cases, the actual write request size limit is lower than 4 MB. For example, attaching a file to a user event by POST /me/events/{id}/attachments has a request size limit of 3 MB, because a file around 3.5 MB can become larger than 4 MB when encoded in base64.

Requests exceeding the size limit fail with the status code HTTP 413, and the error message "Request entity too large" or "Payload too large".

Reference [Use the API > Overview](https://learn.microsoft.com/en-us/graph/use-the-api).  