# Retrieve Power Platform Environment Details

Use this API to access and retrieve information of your Power Platform environments.  

## Permission

The following permission is required to call the API.
You must register the app through AvePoint Online Services > App registrations to authenticate and authorize your access to AvePoint Graph API.
For details, refer to [Authentication and Authorization](https://learn.avepoint.com/docs/Use-AvePoint-Graph-API.html#authentication-and-authorization).

| API   | Permission |
|-------------------|---------------|
|`/smp/powerplatform/environments` | enpower.data.read.all | 

## Request

This section provides details on the HTTP method and endpoint used to retrieve general information of your Power Platform environments.

| Method | Endpoint | Description | 
|--- | --- | --- |
| GET | `/smp/powerplatform/environments` | Retrieves your Environments' information | 

## Query Parameters

The API supports several query parameters to refine and customize the data retrieval process.

| Parameters | Description | Type | Required |
|--- | --- | --- | --- |
| top | The number of Environment records retrieved and returned each page. The default number is 100. You can enter a number from 1 to 1000. | integer | No |
| tenant | The tenant in which data of environments are retrieved. By default, environments of all tenants are retrieved. | string | No |

## Responses

The API response provides detailed information about the environments retrieved. Each environment in the response includes various attributes that describe its properties and status.

| Elements           | Description                                                           | Type   | 
|--------------------|-----------------------------------------------------------------------|--------|
| environments             | A list containing environments with detailed information. For the detailed list of responses, refer to [Environment Details](#environment-details).             | list  | 
| totalCount      | Total number of environments retrieved.                   | integer    | 
| nextLink | Reference to the next page of results | string |


### Environment Details

**Elements** | **Description** | **Type**
--- | --- | ---
id | The unique identifier of the environment. | string
name | The name of the environment. | string
dataverseInstanceUrl | The Dataverse instance URL of the environment. | string
displayName | The display name of the environment. | string
tenantId | The unique identifier of the tenant that the environment belongs to. | string
tenant | The display name of the tenant that the environment belongs to. | string
containerId | The unique identifier of the container that the environment belongs to. | string
container | The display name of container that the environment belongs to. | string
createdTime | The created time of the environment. | string
lastModifiedTime | The last modified time of the environment. | string
region | The region of the environment. | string
environmentType | The type of the environment. | string
| isDefault | Indicates whether this environment is the default environment for the tenant. <br> Valid values: <br> <ul><li> **true** for yes <br> </li><li> **false** for no <br> | boolean | 
enPowerPolicyId | The unique identifier of EnPower policy assigned to this environment. | string
enPowerPolicyName | The name of EnPower policy assigned to this environment. | string
enPowerPolicyStatus | The status of EnPower policy assigned to this environment. | string
environmentOwnerId | The unique identifier of environment owner. | string
environmentOwnerDisplayName | The display name of environment owner. | string
environmentOwnerDepartment | The department of environment owner. | string
environmentOwnerUserPrincipalName | The user principal name of environment owner. | string
environmentOwnerOffice | The office of environment owner. | string
| hasManaged | Indicates whether this environment has Managed Environment capabilities enabled. <br> Valid values: <br> <ul><li> **true** for yes <br> </li><li> **false** for no <br> | boolean | 
| ownerIsDisabled | Indicates whether the owner is disabled in environment. <br> Valid values: <br> <ul><li> **true** for yes <br> </li><li> **false** for no <br> | boolean |
totalNumberOfAppsAndFlows | The total number of both apps and flows in this environment. | integer
| hasDataverse | Indicates whether this environment is using Dataverse. <br> Valid values: <br> <ul><li> **true** for yes <br> </li><li> **false** for no <br> | boolean | 
| hasDlpPolicy | Indicates whether this environment has DKP policy assigned. <br> Valid values: <br> <ul><li> **true** for yes <br> </li><li> **false** for no <br> | boolean | 
| dlpPolicies | The number of DLP policies assigned to this environment. | integer
| hasPremiumConnection | Indicates whether this environment is using any premium tier connector. <br> Valid values: <br> <ul><li> **true** for yes <br> </li><li> **false** for no <br> | boolean |
ownerUserType | The user type of the environment owner. | string
numberOfAdmins | The number of admins in this environment. | integer
numberOfMakers | The number of makers in this environment. | integer
numberOfShadowUsers | The number of shadow users in this environment. | integer
numberOfApps | The number of apps in this environment. | integer
numberOfFlows | The number of flows in this environment. | integer
numberOfDesktopFlows | The number of desktop flows in this environment. | integer
numberOfConnections | The number of connections in this environment. | integer
numberOfGuestUsers | The number of guest users in this environment. | integer
numberOfUsers | The number of users in this environment. | integer
| hasSecurityGroup | Indicates whether this environment has any security groups. <br> Valid values: <br> <ul><li> **true** for yes <br> </li><li> **false** for no <br> | boolean |
| hasEnPowerPolicy | Indicates whether this environment has EnPower policy assigned. <br> Valid values: <br> <ul><li> **true** for yes <br> </li><li> **false** for no <br> | boolean |
securityGroupId | The unique identifier of the security group in this environment. | string
securityGroup | The security group information. For the detailed security group properties, refer to [Security Group Details](#security-group-details). | object
securityGroupType | The type of security group in this environment. | object
numberOfSecurityGroupOwners | The number of security group owners. | integer
numberOfSecurityGroupUsers | The number of users in the security group. | integer
totalUsage | The total usage of this environment. | string
usageOfDatabase | The usage of database in environment. | string
usageOfDatabasePercentage | The usage of database percentage of this environment. | string
usageOfFile | The usage of files in this environment. | string
usageOfFilePercentage | The usage of file percentage by this environment. | string
usageOfLog | The usage of log in environment. | string
usageOfLogPercentage | The usage of log percentage by this environment. | string
primaryContact | The Cloud Governance primary contact of this environment. For the detailed user properties, refer to [User Details](#user-details). | object
secondaryContact | The Cloud Governance secondary contact of this environment. For the detailed user properties, refer to [User Details](#user-details). | object
lastRenewalTime | The last renewal time of this environment. | string
phaseStartTime | The renewal start time of this environment. | string
renewalDueDate | The renewal due date of this environment. | string
nextRenewalDate | The next renewal date of this environment. | string
lastRenewalBy | The latest user who renewed this environment. For the detailed user properties, refer to [User Details](#user-details). | object
| renewalProfileApplied | Indicates whether Cloud Governance renewal profile has been applied to the environment. <br> Valid values: <br> <ul><li> **true** for yes <br> </li><li> **false** for no <br> | boolean |
Metadata | The Cloud Governance metadata of this environment. For the detailed metadata properties, refer to [Cloud Governance Metadata Details](#cloud-governance-metadata-details). | list
| electionProfileApplied | Indicates whether any Cloud Governance contact election profile has been applied to this environment. <br> Valid values: <br> <ul><li> **true** for yes <br> </li><li> **false** for no <br> | boolean |
| isRegistered | Indicates whether this environment has been imported to Cloud Governance. <br> Valid values: <br> <ul><li> **true** for yes <br> </li><li> **false** for no <br> | boolean | 
Phase | The Cloud Governance phase of this environment. | string
phaseAssignees | The current Cloud Governance phase’s assignee. | object
renewProfile | The renewal profile assigned to this environment. For the detailed profile properties, refer to [Cloud Governance Profile Details](#cloud-governance-profile-details). | object
electionProfile | The election profile assigned to this environment. For the detailed profile properties, refer to [Cloud Governance Profile Details](#cloud-governance-profile-details). | object
claimStatus | The Cloud Governance claim status of this environment. | string

### Security Group Details

| Elements                | Description                                                                 | Type    |
|-------------------------|-----------------------------------------------------------------------------|---------|
| id                      | The unique identifier for the group object.                                 | string  |
| tenantId                | The unique identifier for the tenant that the group object belongs to.      | string  |
| containerId             | The unique identifier for the container that the group object belongs to.   | string  |
| photo                   | The representation of the group object photo.                               | string  |
| displayName             | The display name of the group object.                                       | string  |
| realDisplayName         | The display name of the group object.                                | string  |
| userPrincipalName       | The user principal name of the group object.                                | string  |
| securityEnabled         | Indicates whether the group object has security enabled.                    | boolean |
| mailEnabled             | Indicates whether the group object is mail-enabled.                         | boolean |
| accountEnabled          | Indicates whether the group object account is enabled.                      | boolean |
| mailNickname            | The alias of the group object.                                              | string  |
| email                   | The email address of the group object.                                       | string  |
| type | The group object type. <br> Valid values: <br> <ul><li> **0** for user <br> </li><li> **1** for group <br></li><li> **2** for mailbox <br></li><li> **3** for user or shared mailbox <br></li><li> **4** for resource mailbox <br></li><li> **5** for mail user <br></li><li> **6** for mail contact <br></li><li> **7** for SharePoint <br></li><li> **8** for OneDrive for Business <br></li><li> **9** for recipient <br></li><li> **10** for none </li></ul> | integer | 
| userType                | The user type of the group object.                             | string  |
| groupTypes              | The types of the group object, represented as an enumerable collection.     | list    |
| officeLocation          | The office location of the group object.                                    | string  |
| jobTitle                | The job title of the group object.                                          | string  |
| exchangeRecipientType | The Exchange recipient type of the group object. <br> Valid values: <br> <ul><li> **1** for dynamic distribution group <br> </li><li> **2** for mail contact <br></li><li> **4** for mail non-universal group <br></li><li> **8** for mail universal distribution group <br></li><li> **16** for mail universal security group <br></li><li> **32** for mail user <br></li><li> **64** for public folder <br></li><li> **128** for user mailbox </li></ul> | integer | 
| groupType               | The group type of the group object.                                         | integer |
| membershipType          | The membership type of the group object.                                    | integer |

### User Details

| Elements                | Description                                                                 | Type    |
|-------------------------|-----------------------------------------------------------------------------|---------|
| id                      | The unique identifier for the user.                        | string  |
| displayName             | The display name associated with the user.                 | string  |
| email                   | The email address associated with the user.                | string  |
| tenantId                | The unique identifier for the tenant where the user belongs to. | string  |
| userPrincipalName       | The user principal name of the user.                       | string  |
| objectId                | The unique object ID for the user.                         | string  |
| jobTitle                | The job title associated with the user.                    | string  |
| department              | The department associated with the user.                   | string  |
| companyName             | The company name associated with the user.                 | string  |
| office                  | The office location associated with the user.              | string  |
| city                    | The city associated with the user.                         | string  |
| countryOrRegion         | The country or region associated with the user.                       | string  |

### Cloud Governance Metadata Details

| Elements                | Description                                                                 | Type    |
|-------------------------|-----------------------------------------------------------------------------|---------|
| metadataType | The type of metadata. <br> Valid values: <br> <ul><li> **0** for none <br> </li><li> **1** for single line of text <br></li><li> **2** for multiple lines of text <br></li><li> **3** for yes/no <br></li><li> **4** for choice <br></li><li> **5** for people picker filter profile <br></li><li> **6** for managed metadata <br></li><li> **7** for hyperlink <br></li><li> **8** for user profile property <br></li><li> **9** for Microsoft Entra property <br></li><li> **10** for lookup </li></ul> | integer | 
| value                   | The metadata value.                                                         | object  |
| id                      | The unique identifier for the metadata.                                     | string  |
| name                    | The metadata name.                                                          | string  |
| metadataSetting         | The custom metadata.                                                        | object  |

### Cloud Governance Profile Details

| Elements                | Description                                                                 | Type    |
|-------------------------|-----------------------------------------------------------------------------|---------|
| id                      | The unique identifier for the profile.                                      | string  |
| name                    | The name for the profile.                                                   | string  |

## Request Sample

To use this API, send a GET request to the specified endpoint, including necessary parameters as defined in the references. This will return the relevant object details in a structured format, enabling easy integration with other systems or applications. The following request is an API call to the EnPower environment in the US - East region.

```json
https://graph-us.avepointonlineservices.com/smp/powerplatform/environments
```

## Response Sample

If the request has been successfully processed, a 200 OK response will be returned along with the requested information displayed in the response body. For more details on the HTTP status code, refer to [HTTP Status Code](https://learn.avepoint.com/docs/Use-AvePoint-Graph-API.html#http-status-code).

```json
{
    "environments": [
        {
            "id": "32f8937b-64f4-e443-8dd5-06ed83f1bc82", // The unique identifier of the environment
            "name": "Environment name", // The name of the environment
            "dataverseInstanceUrl": "", // The Dataverse instance Url of the environment
            "displayName": "0613-Ci data02", // The display name of the environment
            "tenantId": "", // The unique identifier of the tenant that the environment belongs to
            "tenant": "Sample", // TThe display name of the tenant that the environment belongs to
            "containerId": "", // The unique identifier of the container that the environment belongs to
            "container": "Sample-Environments", // The display name of container that the environment belongs to
            "createdTime": "2024-06-13 03:31:12", // The created time of the environment
            "lastModifiedTime": "2024-12-30 01:05:36", // The last modified time of the environment
            "region": "Asia", // The region of the environment
            "environmentType": "Microsoft Teams", // The type of the environment
            "isDefault": false, // Indicates whether this environment is the default environment for the tenant
            "enPowerPolicyId": "00000000-0000-0000-0000-000000000000", // The unique identifier of EnPower policy assigned to this environment
            "enPowerPolicyName": null, // The name of EnPower policy assigned to this environment
            "enPowerPolicyStatus": "Not applied", // The status of EnPower policy assigned to this environment
            "environmentOwnerId": "", // The unique identifier of environment owner
            "environmentOwnerDisplayName": "Account Test", // The display name of environment owner
            "environmentOwnerDepartment": "Department Owner", // The department of environment owner
            "environmentOwnerUserPrincipalName": "", // The user principal name of environment owner
            "environmentOwnerOffice": null, // The office of environment owner
            "hasManaged": true, // Indicates whether this environment has Managed Environment capabilities enabled
            "ownerIsDisabled": false, // Indicates whether the owner is disabled in environment
            "totalNumberOfAppsAndFlows": 2, // The total number of both apps and flows in this environment
            "hasDataverse": true, // Indicates whether this environment is using Dataverse
            "hasDlpPolicy": true, // Indicates whether this environment has DLP policy assigned
            "dlpPolicies": 2, // The list of DLP policies assigned to this environment
            "hasPremiumConnection": false, // Indicates whether this environment is using any premium tier connector
            "ownerUserType": "Member", // The user type of the environment owner
            "numberOfAdmins": 0, // The number of admins in this environment
            "numberOfMakers": 0, // The number of makers in this environment
            "numberOfShadowUsers": 0, // The number of shadow users in this environment
            "numberOfApps": 0, // The number of apps in this environment
            "numberOfFlows": 0, // The number of flows in this environment
            "numberOfDesktopFlows": 2, // The number of desktop flows in this environment
            "numberOfConnections": 0, // The number of connections in this environment
            "numberOfGuestUsers": 0, // The number of guest users in this environment
            "numberOfUsers": 0, // The number of users in this environment
            "hasSecurityGroup": true, // Indicates whether this environment has any security groups
            "hasEnPowerPolicy": false, // Indicates whether this environment has EnPower policy assigned
            "securityGroupId": "", // The unique identifier of the security group in this environment
            "securityGroup": { // The security group information
                "id": "", // The unique identifier of the group member
                "enPowerObjId": null, // The unique identifier for the group member in EnPower
                "tenantId": "", // The unique identifier for the tenant that the group member belongs to
                "containerId": null, // The unique identifier for the container that the group member belongs to
                "photo": null, // The representation of the group member photo
                "displayName": "0613-Ci data02", // The display name of the group member
                "realDisplayName": null, // The display name of the group member
                "userPrincipalName": null, // The user principal name of the group member
                "securityEnabled": true, // Indicates whether the group member has security enabled
                "mailEnabled": true, // Indicates whether the group member is mail-enabled
                "accountEnabled": null, // Indicates whether the group member account is enabled
                "mailNickname": "0613-Cidata02", // The alias of the group member
                "email": "", // The email address of the group member
                "type": 0, // The group member type
                "userType": null, // The user type of the group member
                "groupTypes": null, // The types of the group member, represented as an enumerable collection
                "officeLocation": null, // The office location of the group member
                "jobTitle": null, // The job title of the group member
                "exchangeRecipientType": null, // The Exchange recipient type of the group member
                "groupType": 1, // The group type of the group member
                "membershipType": 1 // The membership type of the group member
            },
            "securityGroupType": "Microsoft 365 Group", // The type of security group in this environment
            "numberOfSecurityGroupOwners": 0, // The number of security group owners
            "numberOfSecurityGroupUsers": 0, // TThe number of users in the security group
            "totalUsage": "890.20 MB", // The total usage of this environment
            "usageOfDatabase": "890.20 MB", // The usage of database in environment.
            "usageOfDatabasePercentage": "100%", // The usage of database percentage of this environment
            "usageOfFile": "0 MB", // The usage of files in this environment
            "usageOfFilePercentage": "0%", // The usage of file percentage in environment
            "usageOfLog": "0 MB", // The usage of log of this environment
            "usageOfLogPercentage": "0%", // The usage of log percentage of this environment
            "primaryContact": null, // The Cloud Governance primary contact of this environment
            "secondaryContact": null, // The Cloud Governance secondary contact of this environment
            "lastRenewalTime": "", // The last renewal time of this environment
            "phaseStartTime": "", // The renewal start time of this environment
            "renewalDueDate": "", // The renewal due date of this environment
            "nextRenewalDate": "", // The next renewal date of this environment
            "lastRenewalBy": null, // The latest user who renewed this environment
            "renewProfileApplied": null, // Indicates whether Cloud Governance renewal profile has been applied for the tenant
            "metadata": [], // The Cloud Governance metadata of this environment
            "electionProfileApplied": null, // Indicates whether any Cloud Governance contact election profile has been applied to this tenant
            "isRegistered": false, // Indicates whether this environment has been imported to Cloud Governance
            "phase": "", // The Cloud Governance phase of this environment
            "phaseAssignees": "", // The current Cloud Governance phase’s assignee
            "renewProfile": "N/A", // The renewal profile assigned to this environment
            "electionProfile": "N/A", // The election profile assigned to this environment
            "claimStatus": "" // The Cloud Governance claim status of this environment
        }
    ],
    "totalCount": 1,
    "nextLink": ""
}