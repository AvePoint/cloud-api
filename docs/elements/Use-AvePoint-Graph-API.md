# Use Elements API <!-- omit in toc -->

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

Welcome to the Elements API, your gateway to accessing and managing the Elements Platform with efficiency and security. This API is designed to streamline your data management and monitoring processes, providing IT professionals with robust tools and insights.  

## Authentication and Authorization

To access the resources of Elements services via the Elements API, you must configure the app registration and grant the necessary permissions. This process involves:  

- **Registering an app**: Set up your app in Elements.  
- **Permissions**: Assign the appropriate permissions for your app.
- **Authentication**: Use the generated application (client) ID for secure access.  

For a step-by-step guide on creating an app registration for API authentication, refer to [Register an App](register-app.md).  


## Call an API Method

To interact with resources, construct a request as follows:  

    {HTTP method} https://graph.avepointonlineservices.com/{resource}?{query-parameters}  

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

The API uses the HTTP methods to specify the action being performed on a request. Currently, the API documented here only supports:  

| Method | Description |  
|------|------|  
|GET|Read data from a resource.|  
|POST| Create data in a resource. |
|PUT| Update data in a resource. | 

## HTTP Status Code

HTTP status codes indicate the outcome of a request. Common codes include:

| Code | Description |
| ---- | ----------- |
| 200 | OK – The request was successful, and the response contains the requested data. |
| 201 | Created – The request was successful and a new resource was created as a result.  |
| 204 | No Content – The request was successful, but the response body contains no content. |
| 400 | Bad Request – The request could not be processed due to invalid parameters. |
| 401 | Unauthorized – The request requires user authentication.  |
| 403 | Forbidden – The server understood the request but refuses to authorize it.  |
| 404 | Not Found – The requested resource could not be found on the server.  |
| 429 | Too Many Requests – The client has exceeded the rate limit defined by the server.  |
| 500 | Internal Server Error – An unexpected server error occurred. |
| 503 | Service Unavailable – The server is temporarily unable to handle the request due to maintenance or overload. |

## Resource  

A resource can be an entity or complex type, commonly defined with properties.  Your URL will include the resource you are interacting with in the request, such as `customers`, `tenatns`, and `services`. Methods can also be used to perform operations on these resources.
