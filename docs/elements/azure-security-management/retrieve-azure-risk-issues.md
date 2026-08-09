# Retrieve Azure Risk Issues

Use this API to retrieve Azure risk issues in a customer's tenant.

## Permission

The following permission is required to call the API.
You must register an app through Elements > API app registration to authenticate and authorize your access to Elements API. For details, refer to [App Registration](../register-app.md).

| API | Permission |
|-----------|-----------|
| `/partner/external/v3/asm/customers/{customerId}/tenants/{tenantId}/issues` |elements.sm.read.all|

## Request

This section outlines the HTTP method and endpoint used to retrieve the risk issues for a specific tenant.

| Method | Endpoint | Description |
|-----------|-----------|-----------|
| GET | `/partner/external/v3/asm/customers/{customerId}/tenants/{tenantId}/issues` | Retrieves risk issues for a specific tenant. |

## URL Parameters

This section outlines the parameters required to specify which tenant's risk issues you want to retrieve.

| Parameter | Description | Type | Required |
| --- | --- | --- | --- |
| customerId | The customer ID. | string | Yes |
| tenantId | The tenant ID of the customer. | string | Yes |

## Query Parameters

This section outlines the query parameters that allow users to specify pagination.

| Parameter | Description | Type | Required |
| --- | --- | --- | --- |
| pageIndex | The starting number of the page to retrieve the risk issues. The default is 1. | integer | No |
| pageSize | The number of risk issues to display on one page. The default value is 50 and the maximum value allowed is 100. | integer | No |

## Response

If the request has been successfully processed, a 200 OK response will be returned along with the requested information displayed in the response body.

| Response | Description | Type |
| --- | --- | --- |
| hasNextPage | Indicates whether there is another page of results. | boolean |
| totalCount | The total number of issues in the customer's tenant. | integer |
| securityManagementIssueModels | The list of risk issues. | array |

**securityManagementIssueModels**

| Response | Description | Type |
| --- | --- | --- |
| issueId | The ID of the risk issue. | string |
| ruleId | The ID of the risk rule. | string |
| policyId | The ID of the risk policy. | string |
| resourceId | The ID of the resource. | string |
| issueName | The display name of the risk issue. | string |
| description | The description of the risk rule. | string |
| policy | The name of the risk policy. | string |
| severity | The severity of the risk issue. | enum (string) |
| status | The issue status. | enum (string) |
| resource | The resource name. | string |
| resourceType | The resource type. | enum (integer) |
| resourceGroup | The resource group name. | string |
| subscriptionId | The ID of the subscription. | string |
| subscription | The name of the subscription. | string |
| tags | The tags of the resource. | array |
| detectedDate | The detected time of the risk issue in ISO 8601 format. | string (date-time) |
| firstDetectedDate | The first detected time of the risk issue in ISO 8601 format. | string (date-time) |

### severity

| Name | Value |
| --- | --- |
| Low | 0 |
| Medium | 1 |
| High | 2 |
| Critical | 3 |

### status

| Name | Value |
| --- | --- |
| None | 0 |
| Pending | 1 |
| Viewed | 2 |
| Fixed | 3 |
| Ignored | 4 |

### resourceType

| Name | Value |
| --- | --- |
| None | 0 |
| VirtualMachine | 1 |
| VirtualMachineScaleSet | 2 |
| KubernetesService | 6 |
| BatchAccount | 7 |
| ServiceFabric | 8 |
| OneesHostedPools | 9 |
| ManagedEnvironment | 10 |
| AzureComputeGallery | 11 |
| BareMetalInstance | 12 |
| CloudService | 13 |
| CommunityImage | 14 |
| ComputeFleet | 15 |
| AvailabilitySet | 16 |
| HostGroup | 17 |
| ImageTemplate | 18 |
| Image | 19 |
| LabAccount | 20 |
| ProximityPlacementGroup | 21 |
| QuantumWorkspace | 22 |
| RestorePointCollection | 23 |
| SapHanaOnAzure | 24 |
| SshPublicKey | 25 |
| VmApplicationDefinition | 26 |
| VmApplicationVersion | 27 |
| VmImageDefinition | 28 |
| VmImageVersion | 29 |
| VirtualNetwork | 100 |
| Subnet | 101 |
| NetworkInterface | 102 |
| PublicIPAddress | 103 |
| LoadBalancer | 104 |
| ApplicationGateway | 105 |
| NetworkSecurityGroup | 106 |
| VirtualNetworkGateway | 107 |
| ExpressRouteCircuit | 108 |
| PrivateEndpoint | 109 |
| TrafficManager | 110 |
| FrontDoor | 111 |
| NetworkWatcher | 112 |
| Bastions | 113 |
| Connections | 114 |
| CustomIPPrefixes | 115 |
| DnsPrivateResolvers | 116 |
| DnsZones | 117 |
| ExpressrouteTrafficCollectors | 119 |
| IPGroups | 121 |
| LocalNetworkGateways | 123 |
| MicrosoftConnectedCacheForInternetServiceProviders | 124 |
| NatGateways | 125 |
| NetworkManagers | 127 |
| Nginxaas | 129 |
| PeeringServices | 130 |
| Peerings | 131 |
| PrivateDnsZones | 132 |
| PublicIPPrefixes | 134 |
| RouteTables | 135 |
| VirtualWans | 137 |
| NetConnections | 138 |
| StorageAccount | 200 |
| BlobContainer | 201 |
| FileShare | 202 |
| Queue | 203 |
| Table | 204 |
| ManagedDisk | 205 |
| AzureStackHCI | 206 |
| Disk | 207 |
| AzureDataBox | 208 |
| AzureManagedLustre | 209 |
| AzureNativePureStorageCloudService | 210 |
| AzureNativeQumuloScalableFileService | 211 |
| AzureNetappFiles | 212 |
| AzureStackEdgeDataBoxGateway | 213 |
| DataLakeStorageGen1 | 214 |
| DiskAccesses | 215 |
| DiskEncryptionSets | 216 |
| ElasticSans | 218 |
| HpcCaches | 219 |
| Snapshots | 220 |
| StorageMovers | 222 |
| StorageSyncServices | 223 |
| SqlDatabase | 300 |
| SqlServer | 301 |
| CosmosDbAccount | 302 |
| MySqlServer | 303 |
| PostgreSqlServer | 304 |
| RedisCache | 305 |
| SqlManagedInstance | 306 |
| DocumentDB | 307 |
| SqlServerOnVirtualMachine | 308 |
| PostgreSQLFlexibleServer | 309 |
| MySQLFlexibleServer | 310 |
| PostgreSQLFlexibleServerVirtualEndpoint | 311 |
| AzureManagedInstanceForApacheCassandra | 315 |
| AzureManagedRedis | 316 |
| ElasticJobAgents | 317 |
| ManagedDatabases | 318 |
| MongodbAtlas | 319 |
| SynapseWorkspace | 400 |
| DataFactory | 401 |
| DataLakeStore | 402 |
| EventHub | 403 |
| StreamAnalytics | 404 |
| HDInsight | 405 |
| Databricks | 406 |
| AnalysisServices | 407 |
| AzureSynapseAnalyticsPrivateLinkHubs | 409 |
| DataShares | 411 |
| ExperimentWorkspaces | 412 |
| InformaticaIntelligentDataManagementCloudANAzureNativeIsvService | 414 |
| PowerBIEmbedded | 415 |
| StreamAnalyticsClusters | 416 |
| KeyVault | 500 |
| SecurityCenter | 501 |
| Sentinel | 502 |
| AzureFirewall | 503 |
| ApplicationSecurityGroups | 505 |
| ArtifactSigningAccounts | 506 |
| AttestationProviders | 507 |
| AzureCloudHsms | 508 |
| AzureKeyVaultManagedHsms | 509 |
| ConfidentialLedgers | 510 |
| DdosProtectionPlans | 511 |
| MicrosoftDefenderEasm | 516 |
| MicrosoftEntraDomainServices | 517 |
| NetworkSecurityPerimeters | 518 |
| WebApplicationFirewallPoliciesWaf | 520 |
| NetworkFrontdoors | 521 |
| ActiveDirectory | 600 |
| ManagedIdentity | 601 |
| AccessConnectorForAzureDatabricks | 602 |
| B2CTenants | 603 |
| ExternalConfigurationTenant | 604 |
| GuestUsages | 605 |
| LogAnalyticsWorkspace | 700 |
| ApplicationInsights | 701 |
| Monitor | 702 |
| AlertRule | 703 |
| DiagnosticSetting | 704 |
| AzureMonitorWorkspaces | 705 |
| AzureMonitorsForSapSolutions | 706 |
| AzureNativeDynatraceService | 707 |
| AzureNativeNewRelicService | 708 |
| AzureWorkbooks | 709 |
| DataCollectionEndpoints | 710 |
| DataCollectionRules | 711 |
| DatabaseWatchers | 712 |
| DatadogANAzureNativeIsvService | 713 |
| ElasticCloudElasticsearch | 714 |
| LogAnalyticsDedicatedClusters | 715 |
| LogAnalyticsQueryPacks | 716 |
| AzureManagedGrafana | 717 |
| ResourceGroup | 800 |
| Subscription | 801 |
| ManagementGroup | 802 |
| Policy | 803 |
| Blueprint | 804 |
| AutomationAccount | 805 |
| AzureLighthouse | 807 |
| BackupVaults | 808 |
| CapacityReservationGroups | 809 |
| Copilot | 810 |
| DeploymentScripts | 811 |
| MachinesAzureArc | 812 |
| MicrosoftPurviewAccounts | 813 |
| ResourceGraphQueries | 814 |
| ServiceGroups | 816 |
| Solutions | 817 |
| VirtualInstancesForSapSolutions | 818 |
| DataProtectionBackupVaults | 819 |
| ResourceGroupDeployments | 820 |
| ServiceBus | 900 |
| ApiManagement | 901 |
| LogicApp | 902 |
| EventGrid | 903 |
| EventGridDomain | 904 |
| ApiManagementOperations | 905 |
| EventGridTopic | 906 |
| EventHubsClusters | 907 |
| FhirService | 908 |
| HealthDataServicesWorkspace | 909 |
| IntegrationAccounts | 910 |
| LogicAppsCustomConnector | 911 |
| Relays | 912 |
| ApacheKafkaApacheFlinkONConfluentCloudANAzureNativeIsvService | 913 |
| AzureApiForFhir | 914 |
| CognitiveServices | 1000 |
| MachineLearningWorkspace | 1001 |
| BotService | 1002 |
| ComputerVision | 1003 |
| SpeechService | 1004 |
| ContentModerator | 1005 |
| FaceAPI | 1006 |
| OpenAI | 1007 |
| Language | 1008 |
| Personalizer | 1009 |
| CustomVision | 1010 |
| Translator | 1011 |
| AnomalyDetector | 1012 |
| DocumentIntelligence | 1013 |
| ImmersiveReader | 1014 |
| IntelligentRecommendation | 1015 |
| MetricsAdvisor | 1016 |
| AIVideoIndexer | 1017 |
| CustomVisionPrediction | 1018 |
| AzureNativeArizeAICloudService | 1019 |
| AzureSREAgent | 1020 |
| IoTHub | 1100 |
| IoTCentral | 1101 |
| SynapseAnalytic | 1102 |
| AzureDataExplorerClusters | 1104 |
| AzureDigitalTwins | 1105 |
| AzureIoTHubDeviceProvisioningServices | 1106 |
| AzureMapsAccounts | 1108 |
| DeviceUpdateForIoTHubs | 1110 |
| IoTCentralApplications | 1113 |
| ContainerRegistry | 1200 |
| ContainerInstance | 1201 |
| AzureRedHatOpenshiftClusters | 1202 |
| ContainerAppJobs | 1203 |
| KubernetesFleetManager | 1206 |
| ServiceFabricManagedClusters | 1209 |
| AppConfiguration | 1300 |
| AISearch | 1301 |
| WebPubSubService | 1302 |
| SpringApps | 1303 |
| SignalR | 1304 |
| AppService | 1305 |
| AppServiceApiApp | 1306 |
| AppServiceWebApp | 1307 |
| FunctionApp | 1308 |
| ContainerApps | 1309 |
| AppServicePlan | 1310 |
| ApiConnections | 1311 |
| AppServiceCertificates | 1313 |
| AppServiceDomains | 1314 |
| AppServiceEnvironments | 1315 |
| FluidRelay | 1320 |
| NotificationHubs | 1322 |
| StaticWebApps | 1323 |
| DevopsOrganization | 1400 |
| AzureLoadTesting | 1401 |
| AzureNativeLambdatestHyperexecuteCloudService | 1402 |
| DevCenters | 1403 |
| DevtestLabs | 1404 |
| ManagedDevopsPools | 1405 |
| NetworkConnections | 1406 |
| PlaywrightTestingClassic | 1407 |
| Projects | 1408 |
| RoleDefinitions | 1500 |
| RoleAssignments | 1501 |
| AIFoundry | 1502 |
| AIFoundryProject | 1503 |
| AIFoundryAgent | 1504 |
| AIFoundryModel | 1505 |
| PolicyAssignment | 1506 |
| PolicyDefinition | 1507 |
| PolicyInitiativeDefinition | 1508 |
| VirtualApplicationGroup | 1600 |
| VirtualApplication | 1601 |
| VirtualDesktop | 1602 |
| DesktopVirtualizationStartMenuItem | 1603 |
| SharedDashboards | 1604 |
| HostPool | 1700 |
| SessionHost | 1701 |
| UserSession | 1702 |
| MsixPackage | 1703 |
| AzureArcPrivateLinkScopes | 1704 |
| AzureNetworkFunctionManagerDevices | 1705 |
| AzureVmwareSolution | 1706 |
| CustomLocations | 1707 |
| ResourceBridges | 1708 |
| ScvmmManagementServers | 1709 |
| SQLManagedInstancesAzureArc | 1710 |
| SQLServerDatabases | 1711 |
| SQLServerInstances | 1712 |
| VmwareVcenters | 1713 |
| AzureArcDataControllers | 1714 |
| VirtualWorkspace | 1750 |
| GuestConfigurationAssignment | 1800 |
| RecoveryServicesVaults | 1801 |
| SecurityAssessment | 1900 |
| OneesImages | 1901 |
| AccessControlListsOperatorNexus | 1902 |
| ActionGroups | 1903 |
| ActiveDirectoryConfig | 1904 |
| ActivityLogAlertRules | 1905 |
| AdrAssetEndpointProfiles | 1906 |
| AdrAssets | 1907 |
| AdrAssetsClassic | 1908 |
| AdrCredentialResources | 1909 |
| AdrDevices | 1910 |
| AdrNamespaces | 1911 |
| AdrSchemaRegistries | 1912 |
| AgentPoolsOperatorNexus | 1913 |
| AgentPrivateAccesses | 1914 |
| AgenticWebApps | 1915 |
| AlertProcessingRules | 1916 |
| Analyses | 1917 |
| AnyscaleCloudResources | 1918 |
| AnyscaleClouds | 1919 |
| ApacheAirflowONAstroANAzureNativeIsvService | 1920 |
| ApacheSparkPools | 1921 |
| ApiCenters | 1922 |
| AppAttachPackages | 1923 |
| AppServerInstancesForSapSolutions | 1924 |
| AppServiceSlots | 1925 |
| AppServiceKubernetesEnvironments | 1926 |
| ApplicationGatewayForContainers | 1927 |
| ApplicationGatewayWafPolicies | 1928 |
| AszlabhardwareLabServers | 1930 |
| AszlabhardwareReservations | 1931 |
| AszlabhardwareServers | 1932 |
| AutomationProjects | 1933 |
| AutonomousAIDatabases | 1934 |
| AvailabilityTests | 1935 |
| AzureArcGateways | 1936 |
| AzureCosmosDBFleets | 1937 |
| AzureCosmosDBForPostgresqlCluster | 1938 |
| AzureCosmosDBGarnetCache | 1939 |
| AzureDataExplorerDatabases | 1940 |
| AzureDataManagerForEnergy | 1941 |
| AzureDatabaseForMariadbServers | 1942 |
| AzureDatabaseMigrationProjects | 1945 |
| AzureDatabaseMigrationServices | 1946 |
| AzureEdgeHardwareCenter | 1948 |
| AzureEdgeHardwareCenterAddress | 1949 |
| AzureHorizondbPreview | 1950 |
| AzureHorizondbPreviewParameterGroups | 1951 |
| AzureIoTOperations | 1952 |
| AzureLargeInstances | 1953 |
| AzureLocal | 1954 |
| AzureLocalDisconnectedOperations | 1955 |
| AzureLocalDisksAzureArc | 1956 |
| AzureLocalGalleryImages | 1957 |
| AzureLocalLogicalNetworks | 1958 |
| AzureLocalMarketplaceGalleryImages | 1959 |
| AzureLocalNetworkSecurityGroups | 1960 |
| AzureLocalStoragePaths | 1961 |
| AzureLocalVirtualMachineAzureArc | 1962 |
| AzureLocalVMNetworkInterfaces | 1963 |
| AzureMachineLearningRegistries | 1964 |
| AzureMigrate | 1965 |
| AzureMonitorDashboardsWithGrafana | 1966 |
| AzureMonitorPipelines | 1967 |
| AzureMonitorPrivateLinkScopes | 1968 |
| AzureNativeLiftrliteSampleRPANAzureNativeSampleRPCloudService | 1969 |
| AzureNativePineconeCloudService | 1970 |
| AzureNativeWeightsBiasesCloudService | 1971 |
| AzureNetworkFunctionManagerNetworkFunctions | 1972 |
| AzureSphere | 1973 |
| AzureStackPreview | 1974 |
| AzureStorageActions | 1975 |
| AzureVirtualNetworkRoutingAppliances | 1976 |
| AzureWorkbookTemplates | 1977 |
| BackupItems | 1978 |
| BackupPolicies | 1979 |
| BareMetalMachinesOperatorNexus | 1981 |
| BaseDatabases | 1982 |
| BingResources | 1983 |
| BusinessProcessTracking | 1984 |
| CapacityPools | 1985 |
| Catalogs | 1986 |
| CentralServiceInstancesForSapSolutions | 1987 |
| ChangeRecords | 1988 |
| ChaosExperiments | 1989 |
| ChatModelDeployments | 1990 |
| CloudNgfwsBYPaloAltoNetworks | 1991 |
| CloudServicesClassic | 1992 |
| CloudServicesNetworksOperatorNexus | 1993 |
| CloudtestAccounts | 1994 |
| CloudtestPools | 1995 |
| ClusterBareMetalMachineKeySetsOperatorNexus | 1996 |
| ClusterBaseboardManagementControllerKeySetsOperatorNexus | 1997 |
| ClusterManagersOperatorNexus | 1998 |
| ClusterMetricsConfigurationsOperatorNexus | 1999 |
| AdvisorRecommendation | 2000 |
| Communities | 2001 |
| CommunityEndpoints | 2002 |
| CommvaultCloudAccounts | 2003 |
| ComputeRacksOperatorNexus | 2004 |
| ConditionalCredits | 2005 |
| ConfigurationGroupSchemas | 2006 |
| ConfigurationGroupValues | 2007 |
| ConnectedCachesForEnterpriseEducation | 2008 |
| ConnectorNamespacePreview | 2010 |
| ContainerAppSessionPools | 2011 |
| ContainerAppsConnectedEnvironments | 2012 |
| ContainerGroupProfiles | 2013 |
| ContainerInstancesStandbyPools | 2014 |
| ContainerRegistryReplications | 2015 |
| ContainerRegistryWebhooks | 2016 |
| ContainerStorages | 2017 |
| ContentDeliveryNetworkWafPolicies | 2018 |
| CosmicEnvironments | 2019 |
| CosmicNamespaces | 2020 |
| Createconnectedregistryarcresource | 2021 |
| Credits | 2022 |
| DataExplorerPoolsPreview | 2023 |
| DataReplicationVaults | 2025 |
| DatabasesForSapSolutions | 2026 |
| DdosCustomPolicies | 2027 |
| DEIdentificationServices | 2028 |
| DedicatedHubs | 2029 |
| DedicatedSQLPools | 2030 |
| DellPowerscale | 2031 |
| DeploymentStacks | 2032 |
| DevBoxDefinitions | 2033 |
| DevTunnelDomains | 2034 |
| DeviceUpdateAccounts | 2035 |
| DeviceUpdateActiveDeployments | 2036 |
| DeviceUpdateAgents | 2037 |
| DeviceUpdateDeployments | 2038 |
| DeviceUpdateDeviceClasses | 2039 |
| DeviceUpdates | 2040 |
| DevtestLabsVirtualMachines | 2041 |
| DicomService | 2042 |
| Discounts | 2043 |
| DnsDomainLists | 2044 |
| DnsForwardingRulesets | 2045 |
| DnsSecurityPolicies | 2046 |
| DurableTaskScheduler | 2047 |
| EdgeActions | 2048 |
| EdgeSites | 2049 |
| ElasticBackupPolicies | 2050 |
| ElasticBackupVaults | 2051 |
| ElasticCapacityPools | 2052 |
| ElasticSnapshotPolicies | 2053 |
| ElasticVolumes | 2054 |
| EnclaveConnections | 2055 |
| EnclaveEndpoints | 2056 |
| Enclaves | 2057 |
| Endpoints | 2058 |
| EngageCenterConnectors | 2059 |
| EsrpScan | 2060 |
| EventGridPartnerConfigurations | 2063 |
| EventGridPartnerDestinations | 2064 |
| EventGridPartnerNamespaces | 2065 |
| EventGridPartnerRegistrations | 2066 |
| EventGridPartnerTopics | 2067 |
| EventGridSystemTopics | 2068 |
| ExpressrouteDirect | 2070 |
| ExpressrouteGateways | 2071 |
| ExpressrouteLinkGroups | 2072 |
| ExtendedSecurityUpdates | 2073 |
| ExtensionDeployments | 2074 |
| ExtensionSlots | 2075 |
| ExtensionVersions | 2076 |
| FirewallPolicies | 2078 |
| FirmwareAnalysisWorkspaces | 2079 |
| FlowLogs | 2080 |
| FlowProfiles | 2081 |
| Flows | 2082 |
| FoundryProject | 2083 |
| Gateways | 2084 |
| Geocatalogs | 2085 |
| GroundStations | 2086 |
| HealthModels | 2087 |
| HealthModelsPreview | 2088 |
| HealthcareAgentService | 2089 |
| Hosts | 2091 |
| ImpactReportingConnectors | 2092 |
| IncentiveSchedules | 2093 |
| InfrastructureASCodeAutomation | 2094 |
| InstancePools | 2095 |
| IntegrationEnvironments | 2096 |
| InternetGatewayRulesOperatorNexus | 2097 |
| InternetGatewaysOperatorNexus | 2098 |
| IPAddressPools | 2099 |
| BillingAccount | 2100 |
| BillingSubscription | 2101 |
| IPPrefixesOperatorNexus | 2102 |
| Issues | 2103 |
| KubernetesAzureArc | 2104 |
| KubernetesClusterFeaturesOperatorNexus | 2105 |
| KubernetesClustersOperatorNexus | 2106 |
| L2Connections | 2107 |
| LabPlans | 2108 |
| Labs | 2109 |
| LandingZoneAccount | 2110 |
| Layer2IsolationDomainsOperatorNexus | 2111 |
| Layer2NetworksOperatorNexus | 2112 |
| Layer3IsolationDomainsOperatorNexus | 2113 |
| Layer3NetworksOperatorNexus | 2114 |
| Libraries | 2115 |
| LocalRulestacksForCloudNgfwBYPaloAltoNetworks | 2116 |
| LogSearchAlertRules | 2117 |
| LogicAppsTemplates | 2118 |
| MachineLearningOnlineDeployments | 2119 |
| MachineLearningOnlineEndpoints | 2120 |
| MaintenanceConfigurations | 2121 |
| ManagedApplications | 2122 |
| ManagedCcfApps | 2123 |
| ManagedConnector | 2124 |
| ManagedFleetNamespaces | 2125 |
| ManagedNamespaces | 2126 |
| MccCachenodesForEnterprise | 2127 |
| MedtechService | 2128 |
| MeshVpns | 2129 |
| MetricAlertRules | 2130 |
| MicrosoftAzureConsumptionCommitments | 2131 |
| MicrosoftDiscoveryBookshelves | 2132 |
| MicrosoftDiscoveryProjects | 2133 |
| MicrosoftDiscoverySupercomputers | 2135 |
| MicrosoftDiscoveryTools | 2136 |
| MicrosoftDiscoveryWorkspaces | 2137 |
| MicrosoftFabric | 2138 |
| MicrosoftSecurityComputeCapacities | 2139 |
| MicrosoftNetworkNetworkVirtualAppliances | 2140 |
| MicrosoftNetworkVirtualhubs | 2141 |
| MicrosoftWorkloadsInsights | 2142 |
| MigrationProjects | 2143 |
| MoveProjects | 2144 |
| MulticloudConnectors | 2145 |
| MYEngagehubPortal | 2146 |
| MYResources | 2147 |
| NapsterCompanionApiANAzureNativeIsvService | 2148 |
| NeighborGroupsOperatorNexus | 2149 |
| NetappElasticAccounts | 2150 |
| NetworkAnchors | 2151 |
| NetworkDevicesOperatorNexus | 2152 |
| NetworkFabricControllersOperatorNexus | 2153 |
| NetworkFabricsOperatorNexus | 2154 |
| NetworkFunctionDefinitionVersions | 2155 |
| NetworkFunctionDefinitions | 2156 |
| ConnectivityConfigurations | 2157 |
| NetworkMonitorsOperatorNexus | 2158 |
| NetworkPacketBrokersOperatorNexus | 2159 |
| NetworkRacksOperatorNexus | 2160 |
| NetworkServiceDesignVersions | 2161 |
| NetworkServiceDesigns | 2162 |
| NetworkTapRulesOperatorNexus | 2163 |
| NetworkTapsOperatorNexus | 2164 |
| Nodepools | 2166 |
| NotificationHubNamespaces | 2167 |
| ONPremisesDataGateways | 2168 |
| OnlineExperimentationWorkspaces | 2169 |
| OracleExadataInfrastructures | 2170 |
| OracleExadataVMClusters | 2171 |
| OracleExascaleVMClusters | 2172 |
| PilotANAzureNativeIsvService | 2173 |
| Pipelines | 2174 |
| PlaywrightWorkspaces | 2175 |
| Pools | 2176 |
| PortalExtensions | 2177 |
| PostgresqlServersAzureArc | 2178 |
| PreviewFeatures | 2179 |
| PrivateLinkForMicrosoftEntraID | 2181 |
| PrivateLinkServices | 2182 |
| ProfessionalServices | 2183 |
| Profiles | 2184 |
| PrometheusRuleGroups | 2185 |
| ProvisionedMachines | 2186 |
| PublisherArtifactManifests | 2187 |
| PublisherArtifactStores | 2188 |
| Publishers | 2189 |
| QuantumProviderAccounts | 2190 |
| ResourceAnchors | 2191 |
| ResourceGuards | 2192 |
| ResourceManagementPrivateLinks | 2193 |
| RouteFilters | 2194 |
| RoutePoliciesOperatorNexus | 2195 |
| Runbook | 2196 |
| Saas | 2197 |
| Samples | 2198 |
| ScalingPlans | 2199 |
| ScheduledActionsPreview | 2200 |
| ScomManagedInstances | 2201 |
| ScvmmClouds | 2202 |
| ScvmmVirtualMachineAzureArc | 2203 |
| ScvmmVirtualMachineTemplates | 2204 |
| ScvmmVirtualNetworks | 2205 |
| SecurityAlerts | 2206 |
| SecurityDetonationChambers | 2207 |
| SecurityPrivateLinks | 2208 |
| SegmentationManagers | 2209 |
| ServiceCatalogManagedApplicationDefinitions | 2210 |
| ServiceEndpointPolicies | 2211 |
| SignalrReplicas | 2212 |
| SiteConfigurations | 2213 |
| SiteKeys | 2214 |
| SiteNetworkServices | 2215 |
| Sites | 2216 |
| SmartDetectorAlertRules | 2217 |
| SnapshotPolicies | 2218 |
| SoftwareASAServiceClassic | 2219 |
| SovereignViews | 2220 |
| SQLElasticPools | 2221 |
| SQLServerEsuLicenses | 2222 |
| SQLServerLicenses | 2223 |
| SREAgentSpaces | 2225 |
| StageMaps | 2226 |
| StageProgressions | 2227 |
| StorageAccountsClassic | 2228 |
| StorageAppliancesOperatorNexus | 2229 |
| StorageAssets | 2230 |
| StorageDiscoveryWorkspaces | 2231 |
| StoragePools | 2232 |
| TemplateSpecs | 2234 |
| TrafficManagerProfiles | 2235 |
| TransitHubs | 2236 |
| TrunkedNetworksOperatorNexus | 2237 |
| UpdateRules | 2238 |
| UsagebillingAccounts | 2239 |
| Validations | 2240 |
| VerifierWorkspaces | 2241 |
| VirtualClusters | 2242 |
| VirtualMachineConsolesOperatorNexus | 2243 |
| VirtualMachinesClassic | 2244 |
| VirtualMachinesOperatorNexus | 2245 |
| VirtualNetworkLinks | 2246 |
| VirtualNetworkTerminalAccessPoints | 2247 |
| VisualStudioOnlinePlans | 2248 |
| VmwareAvsVirtualMachines | 2249 |
| VmwareClusters | 2250 |
| VmwareDatastores | 2251 |
| VmwareHosts | 2252 |
| VmwareResourcePools | 2253 |
| VmwareVirtualMachineTemplates | 2254 |
| VmwareVirtualNetworks | 2255 |
| Volumes | 2256 |
| VolumesOperatorNexus | 2257 |
| VpnGateways | 2258 |
| WebPubsubServiceReplicas | 2259 |
| WorkloadComponents | 2260 |
| WorkloadVirtualInstances | 2261 |
| Workloads | 2262 |
| Workspaces | 2263 |
| OneesBuildCaches | 2264 |
| ClustersOperatorNexus | 2265 |
| IPCommunitiesOperatorNexus | 2266 |
| IPExtendedCommunitiesOperatorNexus | 2267 |
| FileShares | 2268 |
| MicrosoftDiscoveryStorageContainers | 2269 |
| KeyVaultKey | 10000 |
| KeyVaultSecret | 10001 |
| KeyVaultCertificate | 10002 |
| FrontDoorStandard | 10500 |
| KustoCluster | 10501 |
| OperationalInsightsWorkspace | 10502 |
| RecoveryServicesVault | 10503 |
| ComputeDisk | 10504 |
| ComputeSnapshot | 10505 |
| Subscriptions | 10506 |
| AllResources | 2147483647 |


## Request Sample

To use this API, send a GET request to the specified endpoint.

```json
https://graph.avepointonlineservices.com/partner/external/v3/asm/customers/966f35cc-****-4070-****-25cd****2a07/tenants/0c7715b3-****-4c4c-****-f363****acec/issues?pageIndex=1&pageSize=100
```

## Response Sample

If the request has been successfully processed, a 200 OK response will be returned along with the requested information displayed in the response body. For more details on the HTTP status code, refer to [Http Status Code](../Use-AvePoint-Graph-API.md#http-status-code).

```json
{
    "hasNextPage": false,
    "totalCount": 2,
    "securityManagementIssueModels": [
        {
            "issueId": "8A40E648-****-4FBA-****-66AD1A8BE89A", //The ID of the risk issue.
            "ruleId": "00000002-****-4A52-****-00000019", //The ID of the risk rule.
            "policyId": "4f7c5d43-****-4c7a-****-8071c4a9e5f1", //The ID of the risk policy.
            "resourceId": "/subscriptions/****/resourceGroups/rg-01/providers/Microsoft.Compute/virtualMachines/vm-01", //The ID of the resource.
            "issueName": "Public IP without NSG", //The display name of the risk issue.
            "description": "A public IP is exposed without network security group protection.", //The description of the risk rule.
            "policy": "Default Security Policy", //The name of the risk policy.
            "severity": "High", //The severity of the risk issue.
            "status": "Pending", //The issue status.
            "resource": "vm-01", //The resource name.
            "resourceType": 1, //The resource type; 1 represents VirtualMachine.
            "resourceGroup": "rg-01", //The resource group name.
            "subscriptionId": "****-****-****-****", //The ID of the subscription.
            "subscription": "Production Subscription", //The subscription name.
            "tags": [
                {
                    "key": "environment", //The tag key of the resource.
                    "value": "prod" //The tag value of the resource.
                }
            ],
            "detectedDate": "2026-07-01T00:00:00Z", //The detected time of the risk issue in ISO 8601 format.
            "firstDetectedDate": "2026-06-30T00:00:00Z" //The first detected time of the risk issue in ISO 8601 format.
        },
        {
            "issueId": "0E1794A2-****-41EF-****-D4EB4265E538",
            "ruleId": "00000002-****-4A52-****-00000020",
            "policyId": "4f7c5d43-****-4c7a-****-8071c4a9e5f1",
            "resourceId": "/subscriptions/****/resourceGroups/rg-02/providers/Microsoft.Storage/storageAccounts/resource01",
            "issueName": "Storage account allows public access",
            "description": "Blob public access is enabled on a storage account.", 
            "policy": "Default Security Policy", 
            "severity": "Medium", 
            "status": "Viewed", 
            "resource": "resource01",
            "resourceType": 5,
            "resourceGroup": "rg-02",
            "subscriptionId": "****-****-****-****",
            "subscription": "Production Subscription",
            "tags": [],
            "detectedDate": "2026-07-01T00:00:00Z",
            "firstDetectedDate": "2026-06-29T00:00:00Z"
        }
    ]
}
```

