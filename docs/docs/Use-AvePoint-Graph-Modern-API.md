# Use AvePoint Graph Modern API <!-- omit in toc -->

**In this article**

<!-- TOC -->

- [Authentication and Authorization](#authentication-and-authorization)
- [Call an API Method](#call-an-api-method)
  - [Request Components](#request-components)
  - [Response Components](#response-components)
- [HTTP Methods](#http-methods)
- [HTTP Status Code](#http-status-code)
- [Resource](#resource)

<!-- /TOC -->

Welcome to the AvePoint Graph Modern API, your gateway to accessing and managing the AvePoint Confidence Platform with efficiency and security. This API is designed to streamline your data management and backup monitoring processes, providing IT professionals with robust tools and insights.  

## Authentication and Authorization

To access the resources of AvePoint Cloud Services via the AvePoint Graph Modern API, you must configure the app registration and grant the necessary permissions. This process involves:  

- **Registering an app**: Set up your app in AvePoint Online Services.  
- **Permissions**: Assign the appropriate permissions for your app.
- **Authentication**: Use the generated application (client) ID for secure access.  

For a step-by-step guide on creating an app registration for API authentication, refer to the [Register an App for Modern API](register-app.md) section in the AvePoint Online Services User Guide.  

>[!NOTE]  
> For partner operations, go to Elements for Partner for app registration. See [App Registration in Elements for Partners guide](https://cdn.avepoint.com/assets/apelements-webhelp/avepoint-elements-for-partners/index.htm#!Documents/appregistration.htm).

## Call an API Method

To interact with resources, construct a request as follows:  

    {HTTP method} https://graph-{dc}.avepointonlineservices.com/{resource}?{query-parameters}  

### Request Components

- {HTTP method} – The HTTP method used for the request.
- {resource} – The referenced resource.
- {query-parameters} – Optional parameters to customize the response.

### Response Components

After making a request, a response is returned that includes:

- Status code – An HTTP status code that indicates success or failure.  
- Response message – The data that you requested or the result of the operation. The response message can be empty for some operations.  
- nextLink – If your request returns a lot of data, you need to page through it by using the URL returned in nextLink.

- Response headers – Additional information about the response, such as the type of content returned and the request-id that you can use to correlate the response to the request.  

## HTTP Methods

The Modern API uses the HTTP methods to specify the action being performed on a request. Currently, the API documented here only supports:  

| Method | Description |  
|------|------|  
|GET|Read data from a resource.|  

## HTTP Status Code

HTTP status codes indicate the outcome of a request. Common codes include:

| Code | Description |
| ---- | ----------- |
| 200 | OK – The request was successful, and hte response contains the requested data. |
| 400 | Bad Request – The request could not be processed due to invalid parameters. |
| 500 | Internal Server Error – An unexpected server error occurred. |

## Resource  

A resource can be an entity or complex type, commonly defined with properties.  Your URL will include the resource you are interacting with in the request, such as `customers`, `services`, and `jobs`. Methods can also be used to perform operations on these resources.  
