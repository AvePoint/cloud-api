# Elements API

The `/partner/customers/{id}/protected` API is designed to retrieve detailed information about a customer's protected data within Cloud Backup for Microsoft 365. This API is specifically for customers who have subscribed to the Cloud Backup for Microsoft 365 service.

## Permissions  

The following permission is required to call the APIs.  
You must register an app through Elements for Partners > App Registration to authenticate and authorize your access to AvePoint Graph Modern API. For details, refer to [App Registration](https://cdn.avepoint.com/assets/apelements-webhelp/avepoint-elements-for-partners/index.htm#!Documents/appregistration.htm)  

| API | Permission  |
|-----------|-------|
| `/partner/customers/{id}/protected` |partner.cbprotected.read.all |  

## Query Parameters  

This section outlines the necessary parameters required to specify the customer's protected data you want to access.  

| Parameter | Description | Type |
| --- | --- | --- |
| Id | The tenant owner ID of the customer. | String |

## Responses

If the request has been successfully processed, a 200 OK response will be returned, along with the requested information displayed in the response body.

| Response | Description | Type |
| --- | --- | --- |
| CustomerId | The tenant owner ID of the customer. | String |
| Customer | The tenant owner email address of the customer. | String |
| ServiceType | The Cloud Backup for Microsoft 365 service that the customer has the subscription for. | String |
| ServiceModule | The module of the customer’s Cloud Backup for Microsoft 365 service. | String |
| TotalScannedObjects | The number of the scanned objects. | Int |
| TotalProtectedObjects | The number of the backed-up objects. | Int |
| DataSizeStoredInAvePoint | The size of the backed-up objects stored in the AvePoint storage. | Int |
| DataSizeStoredInBYOS | The size of the backed-up objects stored in BYOS. | Int |

## Request Example  



## Response Example  


