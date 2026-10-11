# Retrieve Storage Profiles
Use this API to retrieve storage profiles.

## Permissions
The following permission is required to call the API.
You must register an app through Elements > API app registration to authenticate and authorize your access to Elements API. For details, refer to [App Registration](../../../elements/register-app.md).

| API | Permission |
|-----------|--------|
| `/external/v3/general/partners/storage-profile/batch` | elements.license.read.all |

## Request
This section outlines the details of the HTTP method and endpoint used to retrieve storage profiles.
| Method | Endpoint | Description |
|-----------|--------|------------|
| POST | `/external/v3/general/partners/storage-profile/batch` | Retrieves storage profiles. |

### Query Parameters
This section outlines the optional paging parameters.
| Parameter | Description | Type | Required |
| --- | --- | --- | --- |
| pageIndex | Page number. The default value is 1. | integer | No |
| pageSize | Number of records per page. The default value is 100. | integer | No |

### Request Body Parameters
|Parameter|Description | Type|Required?|
|---|---|---|---|
|ProfileIds|Use this if you want to filter storage profiles by ID. Without indicating it, all storage profiles will be returned.|`List<string>`|No|

## Response
If the request has been successfully processed, a 200 OK response will be returned along with the requested information displayed in the response body.
| Field | Description | Type |
|---|---|---|
| data | The information of the storage profile. | `List<StorageProfile>` |
| metadata.pageIndex | The page index of the result. | integer |
| metadata.pageSize | The page size of the result. | integer |
| metadata.totalCount | The total number of the storage profiles returned. | integer |

**Storage Profile Information**

| Field | Description | Type |
| --- | --- | --- |
| id | The ID of the storage profile. | string |
| name | The name of the storage profile. | string |
| deviceType | The device type of the storage profile: <ul><li>**1** - FTP</li><li>**12** - SFTP</li><li>**301** - IBM Storage Protect - S3</li><li>**302** - IBM Cloud Object Storage</li><li>**401** - Amazon Storage</li><li>**403** - Microsoft Azure Storage</li><li>**601** - Amazon Storage-Compatible Storage</li><li>**701** - Google Cloud Storage</li></ul> | integer |
| modifyTime | The modified time of the storage profile in ISO 8601 format. | string |
| extension | The extension of the storage profile. | `StorageProfileExtension` |

**Extension Basic Information**

| Field | Description | Type |
| --- | --- | --- |
| description | The description of the extension. | string |
| advanced | Indicates whether there are extended parameters. | bool |
| extendedParameters | The extended parameters of the extension. | string |
| retentionInterval | The retention interval of the extension. | integer |

**FTP Storage Extension Information**

| Field | Description | Type |
| --- | --- | --- |
| host | The host of the Azure storage extension. | string |
| port | The port of the Azure storage extension. | integer |
| folder | The folder of the Azure storage extension. | string |
| userName | The user name of the Azure storage extension. | string |
| password | The password of the Azure storage extension. | string |

**Azure Storage Extension Information**

| Field | Description | Type |
| --- | --- | --- |
| accessPoint | The access point of the Azure storage extension. | string |
| containerName | The container name of the Azure storage extension. | string |
| accountName | The account name of the Azure storage extension. | string |
| accountKey | The account key of the Azure storage extension. | string |

**Amazon Storage Extension Information**

| Field | Description | Type |
| --- | --- | --- |
| bucketName | The bucket name of the Amazon storage extension. | string |
| accessKeyId | The access key id of the Amazon storage extension. | string |
| secretAccessKey | The secret access key of the Amazon storage extension. | string |
| region | The region of the Amazon storage extension. <ul><li>**0** - US Standard</li><li>**1** - US West (Northern California)</li><li>**2** - US West (Oregon)</li><li>**3** - US East (Ohio)</li><li>**4** - Canada Central</li><li>**5** - EU (Ireland)</li><li>**6** - EU (Frankfurt)</li><li>**7** - EU (London)</li><li>**8** - Asia Pacific (Singapore)</li><li>**9** - Asia Pacific (Tokyo)</li><li>**10** - Asia Pacific (Sydney)</li><li>**11** - Asia (Seoul)</li><li>**12** - Asia (Mumbai)</li><li>**13** - South America (Sao Paulo)</li></ul> | integer |

**Amazon-Compatible Storage Extension Information**

| Field | Description | Type |
| --- | --- | --- |
| bucketName | The bucket name of the Amazon-Compatible storage extension. | string |
| accessKeyId | The access key id of the Amazon-Compatible storage extension. | string |
| secretAccessKey | The secret access key of the Amazon-Compatible storage extension. | string |
| endpoint | The end point of the Amazon-Compatible storage extension. | string |
| signatureVersionKey | The signature version key of the Amazon-Compatible storage extension. | string |

**IBM Project-S3 Storage Extension Information**

| Field | Description | Type |
| --- | --- | --- |
| bucketName | The bucket name of the IBM Project-S3 storage extension | string |
| accessKeyId | The access key ID of the IBM Project-S3 storage extension | string |
| secretAccessKey | The secret access key of the IBM Project-S3 storage extension | string |
| endpoint | The end point of the IBM Project-S3 storage extension | string |
| signatureVersionKey | The signature version key of the IBM Project-S3 storage extension | string |
| allowInsecureSsl | The allow insecure SSL setting of the IBM Project-S3 storage extension | string |
| certThumbprint | The cert thumbprint of the IBM Project-S3 storage extension | string |

**IBM Cloud Object Storage Extension Information**

| Field | Description | Type |
| --- | --- | --- |
| bucketName | The bucket name of the IBM Cloud Object storage extension. | string |
| accessKeyId | The access key ID of the IBM Cloud Object storage extension | string |
| secretAccessKey | The secret access key of the IBM Cloud Object storage extension | string |
| endpoint | The end point of the IBM Cloud Object storage extension | string |
| signatureVersionKey | The signature version key of the IBM Cloud Object storage extension | string |

**Google Cloud Storage Extension Information**

| Field | Description | Type |
| --- | --- | --- |
| bucketName | The bucket name of the Google Cloud storage extension | string |
| clientEmail | The client email of the Google Cloud storage extension | string |
| privateId | The private ID of the Google Cloud storage extension | string |
| projectId | The project ID of the Google Cloud storage extension | string |

## Request Sample
To use this API, send a POST request to the specified endpoint, including necessary parameters as defined in the references.
```json
https://graph.avepointonlineservices.com/partner/external/v3/general/partners/storage-profile/batch?pageIndex=1&pageSize=50
```

## Response Sample
If the request has been successfully processed, a 200 OK response will be returned along with the requested information displayed in the response body.
For more details on the HTTP status code, refer to [Http Status Code](https://learn.avepoint.com/docs/Use-AvePoint-Graph-API.html#http-status-code).
```json
{
    "data": [
        {
            "id": "eecfe2d6-xxxx-xxxx-xxxx-a18f141e839d", // The ID of the storage profile
            "name": "test03", // The name of the storage profile
            "deviceType": 403, // The device type of the storage profile
            "modifyTime": "03-26-2026T12:00:00Z", // The modified time of the storage profile
            "extension": {
                "AccessPoint": "https://blob.core.windows.net", // The access point of the storage profile
                "ContainerName": "{$CustomerName}", // The container name of the storage profile
                "AccountName": "aospazure", // The account name of the storage profile
                "AccountKey": "", // The account key of the storage profile
                "Description": "N/A", // The description of the storage profile
                "Advanced": false, // The advanced setting of the storage profile
                "ExtendedParameters": "", // The extended parameters of the storage profile
                "RetentionInterval": 2 // The retention interval of the storage profile
            }
        }
    ],
    "metadata": {
        "pageIndex": 1, // The current page index of the response
        "pageSize": 50, // The number of storage profiles returned per page
        "totalCount": 1 // The total count of storage profiles available
    }
}

```
