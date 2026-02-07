# Explore EnPower Public API

With EnPower Public API, you can access and retrieve your cloud objects details, including both their properties in Microsoft admin centers and in EnPower to form your own reports or audit your data by integrating with other platforms or services. 

The following sections provide detailed descriptions of each data retrieval method, including the required permissions, query parameters, and the structure of the responses. These methods are essential tools for administrators and developers who need to analyze their cloud objects managed by EnPower.


## API Methods for Power Platform Environment and Connection Data Retrieval

Currently, Power Platform environment and connection details can be retrieved via the following API Methods.

| API Method | Endpoint | Documentation | 
|--- | --- | --- |
| GET | `/smp/powerplatform/environments` | [Environments](../enpower/environments.md) |
| GET | `/smp/powerplatform/connections` | [Connections](../enpower/connections.md) |

## API Methods for Power Apps Data Retrieval


Currently, Power App details can be retrieved via the following API Methods.

| API Method | Endpoint | Documentation | 
|--- | --- | --- |
| GET | `/smp/powerplatform/powerapps` | [App Details](../enpower/powerapps/powerapps.md) |
| GET | `/smp/powerplatform/powerapps/{appId}/activities` | [Activities](../enpower/powerapps/activities.md) |
| GET | `/smp/powerplatform/powerapps/{appId}/launches` | [Launching History](../enpower/powerapps/applaunches.md) |
| GET | `/smp/powerplatform/powerapps/{appId}/launched-users` | [Launched Users](../enpower/powerapps/launchedusers.md) |

## API Methods for Power Automate Flows' Data Retrieval

Currently, Power Automate flows' details can be retrieved via the following API Methods.

| API Method | Endpoint | Documentation | 
|--- | --- | --- |
| GET | `/smp/powerplatform/powerautomate/cloudflows` | [Cloud Flow Details](../enpower/flows/cloudflows.md) |
| GET | `/smp/powerplatform/powerautomate/cloudflows/{flowId}/runs` | [Cloud Flow Running History](../enpower/flows/cloudrunhistories.md) |
| GET | `/smp/powerplatform/powerautomate/cloudflows/{flowId}/activities` | [Cloud Flow Activities](../enpower/flows/activities.md) |
| GET | `/smp/powerplatform/connectionusage/cloudflows` | [Cloud Flow Connection Usage](../enpower/flows/connectionusage.md) |
| GET | `/smp/powerplatform/powerautomate/desktopflows` | [Desktop Flow Details](../enpower/flows/desktopflows.md) |
| GET | `/smp/powerplatform/powerautomate/desktopflows/{flowId}/runs` | [Desktop Flow Running History](../enpower/flows/desktoprunhistories.md) |

## API Methods for Power BI Data Retrieval

Currently, Power BI details can be retrieved via the following API Methods.

| API Method | Endpoint | Documentation | 
|--- | --- | --- |
| GET  | `/smp/powerplatform/powerbi/workspaces` | [Workspaces](../enpower/powerbi/workspaces.md) |
| GET | `/smp/powerplatform/powerbi/artifacts` | [Artifacts](../enpower/powerbi/artifacts.md) |
| GET | `/smp/powerplatform/powerbi/datasourcecountbydatasourcetype` | [Data Source Counts](../enpower/powerbi/datasourcecount.md) |
| GET | `/smp/powerplatform/powerbi/datasourcedetails` | [Data Source Details](../enpower/powerbi/datasourcedetails.md) |
| GET | `/smp/powerplatform/powerbi/semanticemodeldetails` | [Semantic Model Details](../enpower/powerbi/semanticmodels.md) |
| GET | `/smp/powerplatform/powerbi/semanticmodelcountbydatasourcetype` | [Semantic Models by Data Sources](../enpower/powerbi/semanticmodelbydatasource.md) |
| GET | `/smp/powerplatform/powerbi/powerbiactiveusers` | [Active Users](../enpower/powerbi/activeusers.md) |

## API Methods for Copilot Studio Retrieval

Currently, details of agents in Copilot Studio can be retrieved via the following API Methods.

| API Method | Endpoint | Documentation | 
|--- | --- | --- |
| GET | `/smp/powerplatform/bot` | [Agent Details](../enpower/copilotstudio/agents.md) |
| GET | `/smp/powerplatform/bot/{botId}/activities` | [Agent Activities](../enpower/copilotstudio/activities.md) |

## API Methods for Power Pages Retrieval

Currently, details of Power Pages sites can be retrieved via the following API Methods.

| API Method | Endpoint | Documentation | 
|--- | --- | --- |
| GET | `/smp/powerplatform/powerpages` | [Site Details](../enpower/pages/details.md) |
| GET | `/smp/powerplatform/powerpages/{powerPageId}/activities` | [Site Activities](../enpower/pages/activities.md) |


## API Methods for Exchange Data Retrieval

With the following API Methods, data of your resource mailboxes, shared mailboxes, and user mailboxes can be retrieved.

| API Method | Endpoint | Documentation | 
|--- | --- | --- |
| GET | `/smp/exchange/resourcemailboxes` | [Resource Mailboxes](../enpower/exchange/resourcemailboxes.md) |
| GET | `/smp/exchange/mailboxes` | [User or Shared Mailboxes](../enpower/exchange/userandsharedmailboxes.md) |
