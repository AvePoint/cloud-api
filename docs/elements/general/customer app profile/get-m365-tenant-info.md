# Retrieve Microsoft 365 Tenant Information

Use this API to retrieve information of a Microsoft 365 tenant.

## Permissions

The following permission is required to call the API.  
You must register an app through Elements > API app registration to authenticate and authorize your access to Elements API. For details, refer to [App Registration](../../../elements/register-app.md).  

| API | Permission |
| ------------ | ------------ |
| `partner/external/v3/general/customers/{customerId}/tenants/{tenantId}` | elements.customers.read.all, partnerapi.customers.read.all |

## Request

This section outlines the details of the HTTP method and endpoint used by this API.

| Method | Endpoint | Description |
| ------ | ------------------------------------------ | --------------------------------------- |
| GET | `partner/external/v3/general/customers/{customerId}/tenants/{tenantId}` | Retrieves information of a Microsoft 365 tenant. |

## URL Parameters

This section describes the query parameters that can be added to the URL when sending a GET request.

| Parameter  | Description   | Type  | Required |
| ---------- | ----------------------------------------- | ------ | -------- |
| customerId | The ID of the customer. | string | Yes |
| tenantId   | The ID of the Microsoft 365 tenant. | string | Yes |

## Response

If the request has been successfully processed, a 200 OK response will be returned along with the requested information displayed in the response body.

| Field | Description | Type |
| ----- | -------------- | ------------------- |
| id   | The tenant ID. | string |
| name   | The tenant name. | string |
| aadEnvironment   | An enumeration value that specifies the Azure Active Directory (AAD) environment type associated with the tenant. For a complete list of valid values, refer to [AAD Environment Types](./aad-environment-types.md).| int |
| platformEnvironmentType   | An enumeration value that specifies the platform environment type associated with the tenant. For a complete list of valid values, refer to [Platform Environment Types](./platform-environment-types.md).| int |

## Request Sample

To use this API, send a GET request to the specified endpoint, including necessary parameters as defined in the references.

```json
https://graph.avepointonlineservices.com/partner/external/v3/general/customers/caf9****-2cc6-****-b04b-794c****5ea3/tenants/f04d7aee-****-5f92-****-6521****e596
```

## Response Sample

If the request has been successfully processed, a 200 OK response will be returned along with the requested information displayed in the response body.

For more details on the HTTP status code, refer to [Http Status Code](https://learn.avepoint.com/docs/Use-AvePoint-Graph-API.html#http-status-code).

```json
{
  "id": "d49c625b-****-****-****-77c8cbca3773", // The tenant ID
  "name": "ym1w5", // The tenant name
  "aadEnvironment": 0, // An enumeration value that specifies the Azure Active Directory (AAD) environment type associated with the tenant
  "platformEnvironmentType": 1 // An enumeration value that specifies the platform environment type associated with the tenant
}
```
