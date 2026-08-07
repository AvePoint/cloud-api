# Retrieve Azure Cost Issues

Use this API to retrieve Azure cost issues in a customer's tenant.

## Permission

The following permission is required to call the API.
You must register an app through Elements > API app registration to authenticate and authorize your access to Elements API. For details, refer to [App Registration](../register-app.md).

| API | Permission |
|-----------|-----------|
| `/partner/external/v3/acm/customers/{customerId}/tenants/{tenantId}/issues` |elements.cm.read.all|

## Request

This section outlines the HTTP method and endpoint used to retrieve the cost issues for a specific tenant.

| Method | Endpoint | Description |
|-----------|-----------|-----------|
| GET | `/partner/external/v3/acm/customers/{customerId}/tenants/{tenantId}/issues` | Retrieves cost issues for a specific tenant. |

## URL Parameters

This section outlines the parameters required to specify which tenant's cost issues you want to retrieve.

| Parameter | Description | Type | Required |
| --- | --- | --- | --- |
| customerId | The customer ID. | string | Yes |
| tenantId | The tenant ID of the customer. | string | Yes |

## Query Parameters

This section outlines the query parameters that allow users to specify pagination.

| Parameter | Description | Type | Required |
| --- | --- | --- | --- |
| pageIndex | The starting number of the page to retrieve the cost issues. The default value is 1. | integer | No |
| pageSize | The number of cost issues to display on one page. The default value is 50 and the maximum value allowed is 100. | integer | No |

## Response

If the request has been successfully processed, a 200 OK response will be returned along with the requested information displayed in the response body.

| Response | Description | Type |
| --- | --- | --- |
| hasNextPage | Indicates whether there is another page of results. | boolean |
| totalCount | The total number of issues in the customer's tenant. | integer |
| costIssueItemModels | The list of cost issues. | array |

**costIssueItemModels**

| Response | Description | Type |
| --- | --- | --- |
| ruleId | The ID of the cost rule. | string |
| ruleName | The name of the cost rule. | string |
| policy | The name of the cost policy. | string |
| severity | The severity of the cost issue. | enum (string) |
| affectedResources | The number of affected resources. | integer |
| recommendation | The recommended action. | enum (string) |
| potentialCostSaving | The estimated annual cost savings. | integer |
| description | The description of the issue. | string |
| recommendationTypeId | The ID of the recommendation type. | string |

### severity

| Name | Value |
| --- | --- |
| Low | 0 |
| Medium | 1 |
| High | 2 |
| Critical | 3 |

### recommendation

| Name | Value |
| --- | --- |
| None | 0 |
| RightSize | 1 |
| DeleteIdleResource | 2 |
| PurchaseSavingsPlan | 3 |
| PurchaseReservation | 4 |
| Autoscale | 5 |
| PricingTierReview | 6 |
| AksEnableCostAnalysis | 7 |
| AksEnableAutoscaler | 8 |
| AksSpotNodePool | 10 |
| ReduceCachePolicy | 11 |
| CommitmentPlan | 12 |
| CosmosDBEnableFabricMirroring | 13 |
| PurchaseCapacity | 14 |
| ShutdownIdle | 15 |
| AutoPause | 16 |
| AnomalyAlerting | 17 |
| BackupOptimization | 18 |
| MigrateTier | 19 |


## Request Sample

To use this API, send a GET request to the specified endpoint.

```json
https://graph.avepointonlineservices.com/partner/external/v3/acm/customers/966f35cc-****-4070-****-25cd****2a07/tenants/0c7715b3-****-4c4c-****-f363****acec/issues?pageIndex=1&pageSize=100
```

## Response Sample

If the request has been successfully processed, a 200 OK response will be returned along with the requested information displayed in the response body. 
For more details on the HTTP status code, refer to [Http Status Code](../Use-AvePoint-Graph-API.md#http-status-code).

```json
{
    "hasNextPage": false,
    "totalCount": 2,
    "costIssueItemModels": [
        {
            "ruleId": "a836e4fc-****-4c64-****-b5d1****4a09", //The ID of the cost rule.
            "ruleName": "Stop idle virtual machine", //The name of the cost rule.
            "policy": "Default Cost Policy", //The name of the cost policy.
            "severity": "High", //The severity of the cost issue.
            "affectedResources": 8, //The number of affected resources.
            "recommendation": "ShutdownIdle", //The recommended action.
            "potentialCostSaving": 1200, //The estimated annual cost savings.
            "description": "Stop idle virtual machines to reduce costs.", //The description of the issue.
            "recommendationTypeId": "shutdown-idle-resource" //The recommendation type.
        },
        {
            "ruleId": "f2ddf741-****-4a82-****-aa5f****da12",
            "ruleName": "Purchase reservation",
            "policy": "Default Cost Policy",
            "severity": "Medium",
            "affectedResources": 3,
            "recommendation": "PurchaseReservation",
            "potentialCostSaving": 3000,
            "description": "Purchase reservation for stable workloads.",
            "recommendationTypeId": "purchase-reservation"
        }
    ]
}
```
