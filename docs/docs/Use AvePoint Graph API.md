# Use AvePoint Graph Modern API


## Authentication and Authorization

To access the resources of AvePoint Cloud Services via the AvePoint Graph Modern API, it's essential to correctly configure app registration and grant the necessary permissions. This process involves registering an app in AvePoint Online Services, setting up appropriate permissions, and using the generated application (client) ID for authentication.  

For detailed instructions on creating an app registration for API authentication, refer to [Configure App Registration](https://cdn.avepoint.com/assets/webhelp/avepoint-online-services/index.htm#!Documents/configureappregistrations.htm) section in AvePoint Online Services User Guide.

## Call an API Method

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

## HTTP methods

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

## Resource  

A resource can be an entity or complex type, commonly defined with properties.  Your URL will include the resource you are interacting with in the request, such as `customers`, `services`, and `job`. You can also interact with resources using methods; for example,  

Reference [Use the API > Overview](https://learn.microsoft.com/en-us/graph/use-the-api).  

https://developer.microsoft.com/en-us/graph/quick-start  
