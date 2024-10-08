# Use AvePoint Graph Modern API


## Authentication and Authorization

To access the resources of AvePoint Cloud Services via the AvePoint Graph Modern API, you must configure the app registration and grant the necessary permissions. This process involves:  
- **Registering an app**: Set up your app in AvePoint Online Services.
- **Permissions**: Assign the appropriate permissions for your app.
- **Authentication**: Use the generated application (client) ID for secure access.  

For a step-by-step guide on creating an app registration for API authentication, refer to the [Configure App Registration](https://cdn.avepoint.com/assets/webhelp/avepoint-online-services/index.htm#!Documents/configureappregistrations.htm) section in the AvePoint Online Services User Guide.

## Call an API Method

To interact with resources, construct a request as follows:  

    {HTTP method} https://graph-{dc}.avepointonlineservices.com/{resource}?{query-parameters}  

### Request Components

- {HTTP method} - The HTTP method used for the request.
- {resource} - The referenced resource.
- {query-parameters} - Optional parameters to customize the response.

### Response Components
After making a request, a response is returned that includes:

- Status code - An HTTP status code that indicates success or failure.  
- Response message - The data that you requested or the result of the operation. The response message can be empty for some operations.
- nextLink - If your request returns a lot of data, you need to page through it by using the URL returned in nextLink. For details, see Paging.--->
- Response headers - Additional information about the response, such as the type of content returned and the request-id that you can use to correlate the response to the request.  

## HTTP methods

The Modern API uses the HTTP method on your request to determine what your request is doing. Currently, it supports:  

| Method | Description |  
|------|------|  
|GET|Read data from a resource.|  


## Resource  

A resource can be an entity or complex type, commonly defined with properties.  Your URL will include the resource you are interacting with in the request, such as `customers`, `services`, and `job`. Methods can also be used to perform operations on these resources.  


