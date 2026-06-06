# Retention Policy

Get the retention policy (`/backup/m365/settings/retention-policy` navigation property) configured in Cloud Backup for Microsoft 365. By invoking the `/backup/m365/settings/retention-policy` endpoint, users can retrieve the current data retention configuration to know how long backup data is retained.

## Permission

The following permission is required to call this API.

You must register an app through AvePoint Online Services > App registration to authenticate and authorize your access to AvePoint Graph API. For details, refer to [Authentication and Authorization](https://learn.avepoint.com/docs/Use-AvePoint-Graph-API.html#authentication-and-authorization).

| API   | Permission |
|---|---|
|`/backup/m365/settings/retention-policy` | microsoft365backup.settings.read.all|

## Request

This section outlines the HTTP method and endpoint used to retrieve the retention policy. It provides a concise description of the action performed by the API call.  

| Method | Endpoint | Description |
| --- | --- | --- |
| GET | `/backup/m365/settings/retention-policy` | Gets the retention-policy of Cloud Backup for Microsoft 365. |

## Query Parameters

The API supports an optional query parameter to refine the location for Multi‑Geo tenants.

| Parameter | Description | Type | Required? |
| --- | --- | --- | --- |
| location | Available only for Multi-Geo tenants. If not specified, the retention policy is retrieved from the central AOS location. For supported values, refer to [Parameter: location](./overview.md#parameter-location). | string | No |

## Responses

The API response provides the data retention configuration.

**Retrieved result:**

| Elements | Description | Type |
| --- | --- | --- |
| statusCode | Http Response Status Code | integer |
| message | Error message | string |
| errors | API error | Array of ApiError |
| data | Retention policy | RetentionPolicy |
| requestId | API request ID | string |
| timestamp | API request time | string |
| traceId | API trace ID | string |

**Retention policy**

| Elements | Description | Type   |
| --- | --- | --- |
| enableDailyRetentionPolicy | Indicates whether daily retention is enabled | bool |
| enableCustomizedRetentionPolicy | Indicates whether the customized retention policy is enabled <br> If true, retention configuration for each service will be returned in ServicePolicies. | bool |
| retentionPeriod | Default retention period for all services | string |
| servicePolicies | Custom retention period for each service | Array of ServiceRetentionPolicy |

**Service retention policy**

| Elements | Description | Type   |
| --- | --- | --- |
| serviceType | Service type. For valid values, refer to [Attribute: serviceType](./overview.md#attribute-servicetype). | integer |
| containerPolicies  | Container‑level retention policy for the service | Array of ContainerPolicy |
| retentionPeriod | Customized retention period for the service | string |
| unassignedObjectRetentionPeriod | Custom retention period for objects that are currently not included in any containers for the service | string |

**Container-level retention policy**

| Elements | Description | Type   |
| --- | --- | --- |
| containerId | Container ID | string |
| containerName | Container name | string |
| retentionPeriod | Customized retention period for the container | string |

>[!NOTE]
> RetentionPeriod defines how long backup data is retained. Data older than this period becomes eligible for deletion. Before deletion occurs, retention notification emails will be sent to tenant administrators.

## Request Sample

To use this API, send a `GET` request to the specified endpoint, including necessary parameters as defined in the references. This will return the retention policy in a structured format, enabling easy integration with other systems or applications.

The following request is an API call to the Cloud Backup for Microsoft 365 environment.  

```json
https://graph-us.avepointonlineservices.com/backup/m365/settings/retention-policy
```

The following request is an API call to the Cloud Backup for Microsoft 365 environment for Multi-Geo tenant in the US - East region.  

```json
https://graph-us.avepointonlineservices.com/backup/m365/settings/retention-policy&Location=NAM
```

## Response Sample

If successful, this method returns a 200 OK response code and the retention policy in the response body.  

For details on the HTTP status code, refer to [HttpStatusCode](https://learn.avepoint.com/docs/Use-AvePoint-Graph-API.html#http-status-code).

```json
{
    "statusCode": 200, //Http Response Status Code
    "message": "", //Error message
    "data": {
        "enableDailyRetentionPolicy": false, //Whether daily retention is enabled
        "enableCustomizedRetentionPolicy": true, // Whether the customized retention policy is enabled
        "retentionPeriod": "1 years", //Default retention period for all services
        "servicePolicies": [
            {
                "serviceType": 0, //Service type
                "containerPolicies": [],
                "retentionPeriod": "2 years", //Custom retention period for this service
                "unassignedObjectRetentionPeriod": "2 years" //Custom retention period for objects that are currently not included in any containers for this service
            },
            {
                "serviceType": 3,
                "containerPolicies": [
                    {
                        "containerId": "5c8b139c-f380-4473-be2b-338d8cd938ce", //Container ID
                        "containerName": "Default Group Container", // Container Name
                        "retentionPeriod": "3 years" // Custom retention period for this container
                    },
                    {
                        "containerId": "438d1332-44bc-445b-9b1d-e9e3802694e8",
                        "containerName": "6vxjvq",
                        "retentionPeriod": "1 years"
                    },
                    {
                        "containerId": "6daffbb9-fc7b-491f-9dfe-aacd4e51e79f",
                        "containerName": "1418 group container",
                        "retentionPeriod": "1 years"
                    },
                    {
                        "containerId": "718ee8dc-ffbb-4a80-be2c-a4d4a3517911",
                        "containerName": "M365EDU751999",
                        "retentionPeriod": "1 years"
                    },
                    {
                        "containerId": "9b363096-5acb-4931-b919-c481387f3420",
                        "containerName": "vcb46",
                        "retentionPeriod": "1 years"
                    },
                    {
                        "containerId": "e338a57c-8e89-4a65-a0a0-61e9ecddd654",
                        "containerName": "2509ky",
                        "retentionPeriod": "1 years"
                    }
                ],
                "retentionPeriod": "1 years",
                "unassignedObjectRetentionPeriod": "1 years"
            },
            {
                "serviceType": 6,
                "containerPolicies": [
                    {
                        "containerId": "5c8b139c-f380-4473-be2b-338d8cd938ce",
                        "containerName": "Default Team Container",
                        "retentionPeriod": "1 years"
                    },
                    {
                        "containerId": "6daffbb9-fc7b-491f-9dfe-aacd4e51e79f",
                        "containerName": "1418 group container",
                        "retentionPeriod": "1 years"
                    },
                    {
                        "containerId": "e338a57c-8e89-4a65-a0a0-61e9ecddd654",
                        "containerName": "2509ky",
                        "retentionPeriod": "1 years"
                    },
                    {
                        "containerId": "438d1332-44bc-445b-9b1d-e9e3802694e8",
                        "containerName": "6vxjvq",
                        "retentionPeriod": "1 years"
                    },
                    {
                        "containerId": "718ee8dc-ffbb-4a80-be2c-a4d4a3517911",
                        "containerName": "M365EDU751999",
                        "retentionPeriod": "1 years"
                    },
                    {
                        "containerId": "9b363096-5acb-4931-b919-c481387f3420",
                        "containerName": "vcb46",
                        "retentionPeriod": "1 years"
                    }
                ],
                "retentionPeriod": "1 years",
                "unassignedObjectRetentionPeriod": "Unlimited"
            },
            {
                "serviceType": 2,
                "containerPolicies": [],
                "retentionPeriod": "Unlimited",
                "unassignedObjectRetentionPeriod": "Unlimited"
            },
            {
                "serviceType": 14,
                "containerPolicies": [],
                "retentionPeriod": "1 years",
                "unassignedObjectRetentionPeriod": "1 years"
            },
            {
                "serviceType": 12,
                "containerPolicies": [],
                "retentionPeriod": "1 years",
                "unassignedObjectRetentionPeriod": "1 years"
            },
            {
                "serviceType": 11,
                "containerPolicies": [],
                "retentionPeriod": "1 years",
                "unassignedObjectRetentionPeriod": "1 years"
            },
            {
                "serviceType": 4,
                "containerPolicies": [],
                "retentionPeriod": "1 years",
                "unassignedObjectRetentionPeriod": "1 years"
            },
            {
                "serviceType": 5,
                "containerPolicies": [],
                "retentionPeriod": "1 years",
                "unassignedObjectRetentionPeriod": "1 years"
            },
            {
                "serviceType": 1,
                "containerPolicies": [],
                "retentionPeriod": "1 years",
                "unassignedObjectRetentionPeriod": "1 years"
            },
            {
                "serviceType": 9,
                "containerPolicies": [],
                "retentionPeriod": "1 years",
                "unassignedObjectRetentionPeriod": "1 years"
            }
        ]
    },
    "requestId": "0HNK4NTH3RHLI:00000001", //API request ID 
    "timestamp": "2026-03-18T07:24:26.9295222Z", //API request time
    "traceId": "00-d04e271ae245e6c016fe25818edb4ce8-72157722b3cc8a3f-00" // API trace ID
}
```
