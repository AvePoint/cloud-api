# Overview

The Cloud Backup for Microsoft 365 Public APIs provide programmatic access to your backup environment, enabling you to retrieve job details, monitor subscription consumption, review retention policies, check backup frequency settings, and detect unusual activity. Use these APIs to build custom reports, automate audits, or integrate your data protection status with third-party platforms and services.

## APIs

| Method | Endpoint | Permission | Documentation |
| --- | --- | --- | --- |
| GET | `/backup/m365/cloudbackupjobs` | microsoft365backup.jobInfo.read.all | [List Jobs](./jobs/list-jobs.md) |
| GET | `/backup/m365/cloudbackupjobs/{jobId}` | microsoft365backup.jobInfo.read.all | [Retrieve Job Details](./jobs/retrieve-job-details.md) |
| POST | `/backup/m365/restore/jobs` | microsoft365backup.restore.readwrite.all | [Perform Restore Job](./jobs/perform-restore-job.md) |
| GET | `/backup/m365/cloudbackuplicenseconsumption` | microsoft365backup.subscriptionInfo.read.all | [Subscriptions](./subscription.md) |
| GET | `/backup/m365/cloudbackupunusualactivitydata` | microsoft365backup.unusualActivity.read.all | [Unusual Activities](./unusual-activities.md) |
| GET | `/backup/m365/settings/backup/frequency` | microsoft365backup.settings.read.all | [Backup Frequency](./backup-frequency.md) |
| GET | `/backup/m365/settings/retention-policy` | microsoft365backup.settings.read.all | [Retention Policy](./retention-policy.md) |

## Common Parameters and Attributes

This section provides shared references used by multiple Cloud Backup for Microsoft 365 APIs.

### Parameter: location

Some APIs support the `location` query parameter to scope results to a specific geographic region in Multi-Geo tenant environments. The following values are supported:

| Value | Geography |
| --- | --- |
| PrimaryGeoLocation | Central AOS location |
| NAM | North America |
| EUR | Europe/Middle East/Africa |
| GBR | United Kingdom |
| JPN | Japan |
| APC | Asia-Pacific |
| AUS | Australia |
| CAN | Canada |
| IND | India |
| FRA | France |
| ARE | United Arab Emirates |
| ZAF | South Africa |
| CHE | Switzerland |
| KOR | Korea |
| DEU | Germany |
| BRA | Brazil |
| NOR | Norway |
| SWE | Sweden |
| QAT | Qatar |
| POL | Poland |
| ITA | Italy |
| ISR | Israel |
| MEX | Mexico |
| NZL | New Zealand |
| ESP | Spain |
| TWN | Taiwan |

### Attribute: serviceType

Several APIs return a `serviceType` value that identifies the Microsoft 365 service. The following values are valid:

| Value | Service |
| --- | --- |
| 0 | Exchange Online |
| 1 | SharePoint Online |
| 2 | OneDrive |
| 3 | Microsoft 365 Groups |
| 4 | Project Online |
| 5 | Public Folder |
| 6 | Teams |
| 7 | Public Folder Metadata |
| 8 | Private Channel |
| 9 | Yammer Group |
| 10 | Personal Chat |
| 11 | Power BI |
| 12 | Power Automate |
| 13 | Shared Channel |
| 14 | Power Apps |
