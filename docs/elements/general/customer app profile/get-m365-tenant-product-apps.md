# Retrieve Status of Service Apps

Use this API to retrieve status of service apps. Currently, only baseline management and other premium services are supported. For a complete list of services, refer to [Services](./services.md).

## Permissions

The following permission is required to call the API.  
You must register an app through Elements > API app registration to authenticate and authorize your access to Elements API. For details, refer to [App Registration](../../../elements/register-app.md).  

| API | Permission |
| ------------------------------------ | ---------------------------------------------------------- |
| `partner/external/v3/general/customers/{customerId}/tenants/{tenantId}/product/{productName}/apps` | elements.customers.read.all, partnerapi.customers.read.all |

## Request

This section outlines the details of the HTTP method and endpoint used by this API.

| Method | Endpoint | Description  |
| ------ | -------------------------------------- | -------------------------------------- |
| GET    | `partner/external/v3/general/customers/{customerId}/tenants/{tenantId}/product/{productName}/apps` | Retrieves status of service apps. |

## URL Parameters

This section describes the query parameters that can be added to the URL when sending a GET request.

| Parameter | Description | Type  | Required |
| ----------- | ---------------------------- | ------ | -------- |
| customerId  | The customer ID. | string | Yes |
| tenantId    | The Microsoft 365 tenant ID. | string | Yes |
| productName | Services whose app status you want to retrieve. <ul><li>**PartnerTenantSettingManagement** - Baseline management</li><li>**PartnerWorkspaceOnboarding** - Other premium services</li></ul> | string | Yes |

## Response

If the request has been successfully processed, a 200 OK response will be returned along with the requested information displayed in the response body.

| Field | Description | Type |
| ------------------------- | -------------------------- | ----- |
| isConsent | Indicates whether service apps have been authorized. <ul><li>**false** - Service apps do not exist</li><li>**true** - Service apps have already been authorized</li></ul> | bool |

## Request Sample

To use this API, send a GET request to the specified endpoint, including necessary parameters as defined in the references.

```json
https://graph.avepointonlineservices.com/partner/external/v3/general/customers/caf9****-2cc6-****-b04b-794c****5ea3/tenants/f04d7aee-****-5f92-****-6521****e596/product/PartnerWorkspaceOnboarding/apps
```

## Response Sample

If the request has been successfully processed, a 200 OK response will be returned along with the requested information displayed in the response body.

For more details on the HTTP status code, refer to [Http Status Code](https://learn.avepoint.com/docs/Use-AvePoint-Graph-API.html#http-status-code).

```json
[
  {
    "isConsent": false // Indicates whether service apps have been authorized
  }
]
```
