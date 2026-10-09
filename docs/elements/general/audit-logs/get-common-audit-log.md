# Retrieve Common Audit Log Records

Use this API to retrieve common audit log records.

## Permissions

The following permission is required to call the API.  
You must register an app through Elements > API app registration to authenticate and authorize your access to Elements API. For details, refer to [App Registration](../../../elements/register-app.md).  

| API | Permission |
| ------------ | ------------ |
| `/partner/external/v3/general/partners/report/auditlog/{date}` | elements.report.read.all |

## Request

This section outlines the details of the HTTP method and endpoint used by this API.

| Method | Endpoint | Description |
| ------ | ------------------------------------------ | --------------------------------------- |
| GET | `/partner/external/v3/general/partners/report/auditlog/{date}` | Retrieves audit log records. |

## URL Parameters

This section describes the query parameters that can be added to the URL when sending a GET request.

| Parameter  | Description   | Type  | Required |
| ---------- | ----------------------------------------- | ------ | -------- |
| date | The time. It should be less or equal to the current date. | string | Yes |
| pageSize   | The number of records per page, from 1 to 100. | integer | No |
| skipToken   | The token to query the next page. | string | No |

## Response

If the request has been successfully processed, a 200 OK response will be returned along with the requested information displayed in the response body.

| Field | Description | Type |
| ----- | -------------- | ------------------- |
| data   | The list of audit log records. | `list<string>` |
| metadata   | contain next link and skip token to request next page | `list<string>` |

**List of Audit Log Records**

| Field | Description | Type |
| ----- | -------------- | ------------------- |
| auditId   | The ID of the audit log. | string |
| operationTime   | The operation time. | string |
| operatedBy   | The name of the user who performed the action. | string |
| tenantId   | The ID of the tenant. | string |
| tenantName   | The name of the tenant. | string |
| customerId   | The ID of the customer. | string |
| customerName   | The name of the customer. | string |
| targetObjectId   | The ID of the target object. | string |
| targetObjectType   | The type of the target object. | string |
| targetObject   | The name of the target object. | string |
| category   | The category. | string |
| operation   | The operation. | string |
| organization   | The name of the organization who manages the user. | string |
| module   | The name of the module. | string |
| auditType   | The type of the audit log. | string |
| operationFrom   | The type of the operation. | string |
| propertyChanges   | The property changes. | list object |
| auditComments   | The comments added to the audit log. | list object |

**Property Changes**

| Field | Description | Type |
| ----- | -------------- | ------------------- |
| parameter   | The name of the property. | string |
| previousValue   | The property's old value. | string |
| currentValue   | The property's new value. | string |

**Comments**

| Field | Description | Type |
| ----- | -------------- | ------------------- |
| comment   | The comment. | string |
| addedBy   | The name of the user who added the comment. | string |
| addedTime   | The time when the comment was added.| string |

**Metadata**

| Field | Description | Type |
| ----- | -------------- | ------------------- |
| skipToken   | The token to request next page result. | string |
| totalCount   | The number of records. | integer |

## Request Sample

To use this API, send a GET request to the specified endpoint, including necessary parameters as defined in the references.

First time request

```json
https://graph.avepointonlineservices.com/partner/external/v3/general/partners/report/auditlog/202608?pageSize=50
```
Second time request
```json
https://graph.avepointonlineservices.com/partner/external/v3/general/partners/report/auditlog/202608?skipToken=****
```
## Response Sample

If the request has been successfully processed, a 200 OK response will be returned along with the requested information displayed in the response body.

For more details on the HTTP status code, refer to [Http Status Code](https://learn.avepoint.com/docs/Use-AvePoint-Graph-API.html#http-status-code).

```json
{
  "data": [
    {
      "auditId": "16ba8cae****", // The ID of the audit log
      "tenantId":"16ba8cae****", // The ID of the tenant
      "tenantName":"Hillary****", // The name of the tenant
      "customerId":"16ba8cae****", // The ID of the customer
      "customerName":"Hillary****", // The name of the customer
      "operationTime": "08/04/2026 09:35:11", // The operation time of the record
      "operatedBy": "Hillary****", // The user name of the user who performed the action
      "targetObjectId": "16ba8cae****", // The ID of the target object
      "targetObjectType": "DistributorAlso****", // The type of the target object
      "targetObject": "hi****", // The name of the target object
      "category": "Ro****", // The category
      "operation": "Ed****", // The operation
      "operatorOrganization": "Test****", // The name of the organization who manages the user
      "module": "Set****", // The name of the module
      "auditType": "Portal Partner", // The type of the audit
      "operationFrom": "Elements", // The type of the operation
      "propertyChanges": [
          {
            "parameter": "Name****", // The name of the property
            "previousValue": "hi****", // The property's old value
            "currentValue": "hi****", // The property's new value
          }
        ],
        "auditComments": [
          {
            "comment":"Hi****", // The comment
            "addedBy":"Luc****", // The name of the user who added the comment
            "addedTime":"08/04/2026 09:35:11" // The time when the comment was added
          }
        ]
    }
  ],
  "metadata": {
    "skipToken": "eyJwYWdlU2l6ZSI6NTAsImp1bXBQYWdlIjoyfQ==****", // The token to request next page result
    "totalCount": 100 // The number of records
  }
}
```
