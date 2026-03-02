# Azure Resource Naming Conventions

Recommended abbreviations for Azure resources based on the [Cloud Adoption Framework](https://learn.microsoft.com/en-us/azure/cloud-adoption-framework/ready/azure-best-practices/resource-abbreviations).

> **Note:** All endpoints require `https://` — it is omitted from examples below for brevity.

---

## AI + Machine Learning

| Resource                              | Abbreviation | API Endpoint Example |
| ------------------------------------- | ------------ | ---------------------------------------- |
| AI Search                             | `srch`       | `srch-app1.search.windows.net`           |
| Foundry Tools (multi-service account) | `ais`        | `ais-app1.cognitiveservices.azure.com`   |
| Foundry account                       | `aif`        | `aif-app1.cognitiveservices.azure.com`   |
| Foundry account project               | `proj`       | `proj-app1`                              |
| Foundry hub                           | `hub`        | `hub-app1`                               |
| Foundry hub project                   | `proj`       | `proj-app1`                              |
| Azure AI Video Indexer                | `avi`        | `avi-app1`                               |
| Azure Machine Learning workspace      | `mlw`        | `mlw-app1.api.azureml.ms`                |
| Azure OpenAI Service                  | `oai`        | `oai-app1.openai.azure.com`              |
| Bot service                           | `bot`        | `bot-app1`                               |
| Computer vision                       | `cv`         | `cv-app1.cognitiveservices.azure.com`    |
| Content moderator                     | `cm`         | `cm-app1.cognitiveservices.azure.com`    |
| Content safety                        | `cs`         | `cs-app1.cognitiveservices.azure.com`    |
| Custom vision (prediction)            | `cstv`       | `cstv-app1.cognitiveservices.azure.com`  |
| Custom vision (training)              | `cstvt`      | `cstvt-app1.cognitiveservices.azure.com` |
| Document intelligence                 | `di`         | `di-app1.cognitiveservices.azure.com`    |
| Face API                              | `face`       | `face-app1.cognitiveservices.azure.com`  |
| Health Insights                       | `hi`         | `hi-app1.cognitiveservices.azure.com`    |
| Immersive reader                      | `ir`         | `ir-app1.cognitiveservices.azure.com`    |
| Language service                      | `lang`       | `lang-app1.cognitiveservices.azure.com`  |
| Speech service                        | `spch`       | `spch-app1.cognitiveservices.azure.com`  |
| Translator                            | `trsl`       | `trsl-app1.cognitiveservices.azure.com`  |

## Analytics and IoT

| Resource                                   | Abbreviation | API Endpoint Example |
| ------------------------------------------ | ------------ | ---------------------------------------------- |
| Azure Analysis Services server             | `as`         | `asazure://eastus.asazure.windows.net/as-app1` |
| Azure Databricks Access Connector          | `dbac`       | `dbac-app1`                                    |
| Azure Databricks workspace                 | `dbw`        | `adb-dbw-app1.azuredatabricks.net`             |
| Azure Data Explorer cluster                | `dec`        | `dec-app1.eastus.kusto.windows.net`            |
| Azure Data Explorer cluster database       | `dedb`       | `dedb-app1`                                    |
| Azure Data Factory                         | `adf`        | `adf-app1.adf.azure.com`                       |
| Azure Digital Twin instance                | `dt`         | `dt-app1.api.eus.digitaltwins.azure.net`       |
| Azure Stream Analytics                     | `asa`        | `asa-app1`                                     |
| Azure Synapse Analytics private link hub   | `synplh`     | `synplh-app1`                                  |
| Azure Synapse Analytics SQL Dedicated Pool | `syndp`      | `syndp-app1`                                   |
| Azure Synapse Analytics Spark Pool         | `synsp`      | `synsp-app1`                                   |
| Azure Synapse Analytics workspaces         | `synw`       | `synw-app1.dev.azuresynapse.net`               |
| Data Lake Store account                    | `dls`        | `dls-app1.azuredatalakestore.net`              |
| Event Hubs namespace                       | `evhns`      | `evhns-app1.servicebus.windows.net`            |
| Event hub                                  | `evh`        | `evh-app1`                                     |
| Event Grid domain                          | `evgd`       | `evgd-app1`                                    |
| Event Grid namespace                       | `evgns`      | `evgns-app1`                                   |
| Event Grid subscriptions                   | `evgs`       | `evgs-app1`                                    |
| Event Grid topic                           | `evgt`       | `evgt-app1`                                    |
| Event Grid system topic                    | `egst`       | `egst-app1`                                    |
| Fabric Capacity                            | `fc`         | `fc-app1`                                      |
| HDInsight - Hadoop cluster                 | `hadoop`     | `hadoop-app1.azurehdinsight.net`               |
| HDInsight - HBase cluster                  | `hbase`      | `hbase-app1.azurehdinsight.net`                |
| HDInsight - Kafka cluster                  | `kafka`      | `kafka-app1.azurehdinsight.net`                |
| HDInsight - Spark cluster                  | `spark`      | `spark-app1.azurehdinsight.net`                |
| HDInsight - Storm cluster                  | `storm`      | `storm-app1.azurehdinsight.net`                |
| HDInsight - ML Services cluster            | `mls`        | `mls-app1.azurehdinsight.net`                  |
| IoT hub                                    | `iot`        | `iot-app1.azure-devices.net`                   |
| Provisioning services                      | `provs`      | `provs-app1.azure-devices-provisioning.net`    |
| Provisioning services certificate          | `pcert`      | `pcert-app1`                                   |
| Power BI Embedded                          | `pbi`        | `pbi-app1`                                     |
| Time Series Insights environment           | `tsi`        | `tsi-app1.env.timeseries.azure.com`            |

## Compute and Web

| Resource                                  | Abbreviation | API Endpoint Example |
| ----------------------------------------- | ------------ | ----------------------------------- |
| App Service environment                   | `ase`        | `ase-app1`                          |
| App Service plan                          | `asp`        | `asp-app1`                          |
| Azure Load Testing instance               | `lt`         | `lt-app1`                           |
| Availability set                          | `avail`      | `avail-app1`                        |
| Azure Arc enabled server                  | `arcs`       | `arcs-app1`                         |
| Azure Arc enabled Kubernetes cluster      | `arck`       | `arck-app1`                         |
| Azure Arc private link scope              | `pls`        | `pls-app1`                          |
| Azure Arc gateway                         | `arcgw`      | `arcgw-app1`                        |
| Batch accounts                            | `ba`         | `ba-app1.eastus.batch.azure.com`    |
| Cloud service                             | `cld`        | `cld-app1.cloudapp.net`             |
| Communication Services                    | `acs`        | `acs-app1`                          |
| Disk encryption set                       | `des`        | `des-app1`                          |
| Function app                              | `func`       | `func-app1.azurewebsites.net`       |
| Gallery                                   | `gal`        | `gal-app1`                          |
| Hosting environment                       | `host`       | `host-app1`                         |
| Image template                            | `it`         | `it-app1`                           |
| Managed disk (OS)                         | `osdisk`     | `osdisk-app1`                       |
| Managed disk (data)                       | `disk`       | `disk-app1`                         |
| Notification Hubs                         | `ntf`        | `ntf-app1`                          |
| Notification Hubs namespace               | `ntfns`      | `ntfns-app1.servicebus.windows.net` |
| Proximity placement group                 | `ppg`        | `ppg-app1`                          |
| Restore point collection                  | `rpc`        | `rpc-app1`                          |
| Snapshot                                  | `snap`       | `snap-app1`                         |
| Static web app                            | `stapp`      | `stapp-app1.azurestaticapps.net`    |
| Virtual machine                           | `vm`         | `vm-app1`                           |
| Virtual machine scale set                 | `vmss`       | `vmss-app1`                         |
| Virtual machine maintenance configuration | `mc`         | `mc-app1`                           |
| VM storage account                        | `stvm`       | `stvmapp1.blob.core.windows.net`    |
| Web app                                   | `app`        | `app-app1.azurewebsites.net`        |

## Containers

| Resource                       | Abbreviation | API Endpoint Example |
| ------------------------------ | ------------ | ---------------------------------------- |
| AKS cluster                    | `aks`        | `aks-app1`                               |
| AKS system node pool           | `npsystem`   | `npsystem`                               |
| AKS user node pool             | `np`         | `np-app1`                                |
| Container apps                 | `ca`         | `ca-app1.{region}.azurecontainerapps.io` |
| Container apps environment     | `cae`        | `cae-app1`                               |
| Container apps job             | `caj`        | `caj-app1`                               |
| Container registry             | `cr`         | `crapp1.azurecr.io`                      |
| Container instance             | `ci`         | `ci-app1`                                |
| Service Fabric cluster         | `sf`         | `sf-app1.eastus.cloudapp.azure.com`      |
| Service Fabric managed cluster | `sfmc`       | `sfmc-app1.eastus.cloudapp.azure.com`    |

## Databases

| Resource                                     | Abbreviation | API Endpoint Example |
| -------------------------------------------- | ------------ | ------------------------------------------ |
| Azure Cosmos DB database                     | `cosmos`     | `cosmos-app1`                              |
| Azure Cosmos DB for Apache Cassandra account | `coscas`     | `coscas-app1.cassandra.cosmos.azure.com`   |
| Azure Cosmos DB for MongoDB account          | `cosmon`     | `cosmon-app1.mongo.cosmos.azure.com`       |
| Azure Cosmos DB for NoSQL account            | `cosno`      | `cosno-app1.documents.azure.com:443/`      |
| Azure Cosmos DB for Table account            | `costab`     | `costab-app1.table.cosmos.azure.com`       |
| Azure Cosmos DB for Apache Gremlin account   | `cosgrm`     | `cosgrm-app1.gremlin.cosmos.azure.com`     |
| Azure Cosmos DB PostgreSQL cluster           | `cospos`     | `c-cospos-app1.postgres.cosmos.azure.com`  |
| Azure Cache for Redis instance               | `redis`      | `redis-app1.redis.cache.windows.net:6380`  |
| Azure Managed Redis                          | `amr`        | `amr-app1.redisenterprise.cache.azure.net` |
| Azure SQL Database server                    | `sql`        | `sql-app1.database.windows.net`            |
| Azure SQL database                           | `sqldb`      | `sqldb-app1`                               |
| Azure SQL Elastic Job agent                  | `sqlja`      | `sqlja-app1`                               |
| Azure SQL Elastic Pool                       | `sqlep`      | `sqlep-app1`                               |
| MySQL database                               | `mysql`      | `mysql-app1.mysql.database.azure.com`      |
| PostgreSQL database                          | `psql`       | `psql-app1.postgres.database.azure.com`    |
| SQL Managed Instance                         | `sqlmi`      | `sqlmi-app1.database.windows.net`          |

## Developer Tools

| Resource                | Abbreviation | API Endpoint Example |
| ----------------------- | ------------ | ------------------------------- |
| App Configuration store | `appcs`      | `appcs-app1.azconfig.io`        |
| Maps account            | `map`        | `map-app1`                      |
| SignalR                 | `sigr`       | `sigr-app1.service.signalr.net` |
| WebPubSub               | `wps`        | `wps-app1.webpubsub.azure.com`  |

## DevOps

| Resource              | Abbreviation | API Endpoint Example |
| --------------------- | ------------ | ---------------------------- |
| Azure Managed Grafana | `amg`        | `amg-app1.grafana.azure.com` |
| Managed DevOps Pools  | `mdp`        | `mdp-app1`                   |

## Integration

| Resource                        | Abbreviation | API Endpoint Example |
| ------------------------------- | ------------ | ---------------------------------- |
| API management service instance | `apim`       | `apim-app1.azure-api.net`          |
| Integration account             | `ia`         | `ia-app1`                          |
| Logic app                       | `logic`      | `logic-app1`                       |
| Service Bus namespace           | `sbns`       | `sbns-app1.servicebus.windows.net` |
| Service Bus queue               | `sbq`        | `sbq-app1`                         |
| Service Bus topic               | `sbt`        | `sbt-app1`                         |
| Service Bus topic subscription  | `sbts`       | `sbts-app1`                        |

## Management and Governance

| Resource                            | Abbreviation      | API Endpoint Example |
| ----------------------------------- | ----------------- | ------------------------------ |
| Automation account                  | `aa`              | `aa-app1`                      |
| Azure Policy definition             | *\<descriptive\>* | `policy-deny-public-ip`        |
| Application Insights                | `appi`            | `appi-app1`                    |
| Azure Monitor action group          | `ag`              | `ag-app1`                      |
| Azure Monitor data collection rule  | `dcr`             | `dcr-app1`                     |
| Azure Monitor alert processing rule | `apr`             | `apr-app1`                     |
| Data collection endpoint            | `dce`             | `dce-app1`                     |
| Diagnostic settings                 | `ds`              | `ds-app1`                      |
| Deployment scripts                  | `script`          | `script-app1`                  |
| Log Analytics workspace             | `log`             | `log-app1`                     |
| Log Analytics query packs           | `pack`            | `pack-app1`                    |
| Management group                    | `mg`              | `mg-app1`                      |
| Microsoft Purview instance          | `pview`           | `pview-app1.purview.azure.com` |
| Resource group                      | rg                | rg-app1                        |
| Template specs name                 | `ts`              | `ts-app1`                      |

## Migration

| Resource                            | Abbreviation | API Endpoint Example |
| ----------------------------------- | ------------ | ----------- |
| Azure Migrate project               | `migr`       | `migr-app1` |
| Database Migration Service instance | `dms`        | `dms-app1`  |
| Recovery Services vault             | `rsv`        | `rsv-app1`  |

## Networking

| Resource                                    | Abbreviation          | API Endpoint Example |
| ------------------------------------------- | --------------------- | ----------------------------------- |
| Application gateway                         | `agw`                 | `agw-app1`                          |
| Application security group (ASG)            | `asg`                 | `asg-app1`                          |
| CDN profile                                 | `cdnp`                | `cdnp-app1`                         |
| CDN endpoint                                | `cdne`                | `cdne-app1.azureedge.net`           |
| Connections                                 | `con`                 | `con-app1`                          |
| DNS                                         | *\<DNS domain name\>* | `contoso.com`                       |
| DNS forwarding ruleset                      | `dnsfrs`              | `dnsfrs-app1`                       |
| DNS private resolver                        | `dnspr`               | `dnspr-app1`                        |
| DNS private resolver inbound endpoint       | `in`                  | `in-app1`                           |
| DNS private resolver outbound endpoint      | `out`                 | `out-app1`                          |
| DNS zone                                    | *\<DNS domain name\>* | `privatelink.blob.core.windows.net` |
| Firewall                                    | `afw`                 | `afw-app1`                          |
| Firewall policy                             | `afwp`                | `afwp-app1`                         |
| ExpressRoute circuit                        | `erc`                 | `erc-app1`                          |
| ExpressRoute direct                         | `erd`                 | `erd-app1`                          |
| ExpressRoute gateway                        | `ergw`                | `ergw-app1`                         |
| Front Door (Standard/Premium) profile       | `afd`                 | `afd-app1`                          |
| Front Door (Standard/Premium) endpoint      | `fde`                 | `fde-app1.azurefd.net`              |
| Front Door firewall policy                  | `fdfp`                | `fdfp-app1`                         |
| Front Door (classic)                        | `afd`                 | `afd-app1.azurefd.net`              |
| IP group                                    | `ipg`                 | `ipg-app1`                          |
| Load balancer (internal)                    | `lbi`                 | `lbi-app1`                          |
| Load balancer (external)                    | `lbe`                 | `lbe-app1`                          |
| Load balancer rule                          | `rule`                | `rule-app1`                         |
| Local network gateway                       | `lgw`                 | `lgw-app1`                          |
| NAT gateway                                 | `ng`                  | `ng-app1`                           |
| Network interface (NIC)                     | `nic`                 | `nic-app1`                          |
| Network security perimeter                  | `nsp`                 | `nsp-app1`                          |
| Network security group (NSG)                | `nsg`                 | `nsg-app1`                          |
| Network security group (NSG) security rules | `nsgsr`               | `nsgsr-app1`                        |
| Network Watcher                             | `nw`                  | `nw-app1`                           |
| Private Link                                | `pl`                  | `pl-app1`                           |
| Private endpoint                            | `pe`                  | `pep-app1`                          |
| Public IP address                           | `pip`                 | `pip-app1`                          |
| Public IP address prefix                    | `ippre`               | `ippre-app1`                        |
| Route filter                                | `rf`                  | `rf-app1`                           |
| Route server                                | `rtserv`              | `rtserv-app1`                       |
| Route table                                 | `rt`                  | `rt-app1`                           |
| Service endpoint policy                     | `se`                  | `se-app1`                           |
| Traffic Manager profile                     | `traf`                | `traf-app1.trafficmanager.net`      |
| User defined route (UDR)                    | `udr`                 | `udr-app1`                          |
| Virtual network                             | `vnet`                | `vnet-app1`                         |
| Virtual network gateway                     | `vgw`                 | `vgw-app1`                          |
| Virtual network manager                     | `vnm`                 | `vnm-app1`                          |
| Virtual network peering                     | `peer`                | `peer-app1`                         |
| Virtual network subnet                      | `snet`                | `snet-app1`                         |
| Virtual WAN                                 | `vwan`                | `vwan-app1`                         |
| Virtual WAN Hub                             | `vhub`                | `vhub-app1`                         |

## Security

| Resource                                         | Abbreviation | API Endpoint Example |
| ------------------------------------------------ | ------------ | ---------------------------------- |
| Azure Bastion                                    | `bas`        | `bas-app1`                         |
| Key vault                                        | `kv`         | `kv-app1.vault.azure.net`          |
| Key Vault Managed HSM                            | `kvmhsm`     | `kvmhsm-app1.managedhsm.azure.net` |
| Managed identity                                 | `id`         | `id-app1`                          |
| SSH key                                          | `sshkey`     | `sshkey-app1`                      |
| VPN Gateway                                      | `vpng`       | `vpng-app1`                        |
| VPN connection                                   | `vcn`        | `vcn-app1`                         |
| VPN site                                         | `vst`        | `vst-app1`                         |
| Web Application Firewall (WAF) policy            | `waf`        | `waf-app1`                         |
| Web Application Firewall (WAF) policy rule group | `wafrg`      | `wafrg-app1`                       |

## Storage

| Resource                  | Abbreviation | API Endpoint Example |
| ------------------------- | ------------ | ------------------------------ |
| Backup Vault name         | `bvault`     | `bvault-app1`                  |
| Backup Vault policy       | `bkpol`      | `bkpol-app1`                   |
| File share                | `share`      | `share-app1`                   |
| Storage account           | `st`         | `stapp1.blob.core.windows.net` |
| Storage Sync Service name | `sss`        | `sss-app1`                     |

## Virtual Desktop Infrastructure

| Resource                          | Abbreviation | API Endpoint Example |
| --------------------------------- | ------------ | ---------------- |
| Virtual desktop host pool         | `vdpool`     | `vdpool-app1`    |
| Virtual desktop application group | `vdag`       | `vdag-app1`      |
| Virtual desktop workspace         | `vdws`       | `vdws-app1`      |
| Virtual desktop scaling plan      | `vdscaling`  | `vdscaling-app1` |

> **Disclaimer:** The API endpoint examples listed above are illustrative and may be inaccurate or outdated. Always refer to the [Azure documentation](https://learn.microsoft.com/en-us/azure) for the most current endpoint formats.

---

## Resource Provider Namespace Reference

Full namespace mappings for each resource listed above.

| Resource                                         | Abbreviation          | Resource Provider Namespace                                            |
| ------------------------------------------------ | --------------------- | ---------------------------------------------------------------------- |
| AI Search                                        | `srch`                | `Microsoft.Search/searchServices`                                      |
| Foundry Tools (multi-service account)            | `ais`                 | `Microsoft.CognitiveServices/accounts (kind: CognitiveServices)`       |
| Foundry account                                  | `aif`                 | `Microsoft.CognitiveServices/accounts (kind: AIServices)`              |
| Foundry account project                          | `proj`                | `Microsoft.CognitiveServices/accounts/projects`                        |
| Foundry hub                                      | `hub`                 | `Microsoft.MachineLearningServices/workspaces (kind: Hub)`             |
| Foundry hub project                              | `proj`                | `Microsoft.MachineLearningServices/workspaces (kind: Project)`         |
| Azure AI Video Indexer                           | `avi`                 | `Microsoft.VideoIndexer/accounts`                                      |
| Azure Machine Learning workspace                 | `mlw`                 | `Microsoft.MachineLearningServices/workspaces`                         |
| Azure OpenAI Service                             | `oai`                 | `Microsoft.CognitiveServices/accounts (kind: OpenAI)`                  |
| Bot service                                      | `bot`                 | `Microsoft.BotService/botServices (kind: azurebot)`                    |
| Computer vision                                  | `cv`                  | `Microsoft.CognitiveServices/accounts (kind: ComputerVision)`          |
| Content moderator                                | `cm`                  | `Microsoft.CognitiveServices/accounts (kind: ContentModerator)`        |
| Content safety                                   | `cs`                  | `Microsoft.CognitiveServices/accounts (kind: ContentSafety)`           |
| Custom vision (prediction)                       | `cstv`                | `Microsoft.CognitiveServices/accounts (kind: CustomVision.Prediction)` |
| Custom vision (training)                         | `cstvt`               | `Microsoft.CognitiveServices/accounts (kind: CustomVision.Training)`   |
| Document intelligence                            | `di`                  | `Microsoft.CognitiveServices/accounts (kind: FormRecognizer)`          |
| Face API                                         | `face`                | `Microsoft.CognitiveServices/accounts (kind: Face)`                    |
| Health Insights                                  | `hi`                  | `Microsoft.CognitiveServices/accounts (kind: HealthInsights)`          |
| Immersive reader                                 | `ir`                  | `Microsoft.CognitiveServices/accounts (kind: ImmersiveReader)`         |
| Language service                                 | `lang`                | `Microsoft.CognitiveServices/accounts (kind: TextAnalytics)`           |
| Speech service                                   | `spch`                | `Microsoft.CognitiveServices/accounts (kind: SpeechServices)`          |
| Translator                                       | `trsl`                | `Microsoft.CognitiveServices/accounts (kind: TextTranslation)`         |
| Azure Analysis Services server                   | `as`                  | `Microsoft.AnalysisServices/servers`                                   |
| Azure Databricks Access Connector                | `dbac`                | `Microsoft.Databricks/workspaces/accessConnectors`                     |
| Azure Databricks workspace                       | `dbw`                 | `Microsoft.Databricks/workspaces`                                      |
| Azure Data Explorer cluster                      | `dec`                 | `Microsoft.Kusto/clusters`                                             |
| Azure Data Explorer cluster database             | `dedb`                | `Microsoft.Kusto/clusters/databases`                                   |
| Azure Data Factory                               | `adf`                 | `Microsoft.DataFactory/factories`                                      |
| Azure Digital Twin instance                      | `dt`                  | `Microsoft.DigitalTwins/digitalTwinsInstances`                         |
| Azure Stream Analytics                           | `asa`                 | `Microsoft.StreamAnalytics/cluster`                                    |
| Azure Synapse Analytics private link hub         | `synplh`              | `Microsoft.Synapse/privateLinkHubs`                                    |
| Azure Synapse Analytics SQL Dedicated Pool       | `syndp`               | `Microsoft.Synapse/workspaces/sqlPools`                                |
| Azure Synapse Analytics Spark Pool               | `synsp`               | `Microsoft.Synapse/workspaces/bigDataPools`                            |
| Azure Synapse Analytics workspaces               | `synw`                | `Microsoft.Synapse/workspaces`                                         |
| Data Lake Store account                          | `dls`                 | `Microsoft.DataLakeStore/accounts`                                     |
| Event Hubs namespace                             | `evhns`               | `Microsoft.EventHub/namespaces`                                        |
| Event hub                                        | `evh`                 | `Microsoft.EventHub/namespaces/eventHubs`                              |
| Event Grid domain                                | `evgd`                | `Microsoft.EventGrid/domains`                                          |
| Event Grid namespace                             | `evgns`               | `Microsoft.EventGrid/namespaces`                                       |
| Event Grid subscriptions                         | `evgs`                | `Microsoft.EventGrid/eventSubscriptions`                               |
| Event Grid topic                                 | `evgt`                | `Microsoft.EventGrid/domains/topics`                                   |
| Event Grid system topic                          | `egst`                | `Microsoft.EventGrid/systemTopics`                                     |
| Fabric Capacity                                  | `fc`                  | `Microsoft.Fabric/capacities`                                          |
| HDInsight - Hadoop cluster                       | `hadoop`              | `Microsoft.HDInsight/clusters`                                         |
| HDInsight - HBase cluster                        | `hbase`               | `Microsoft.HDInsight/clusters`                                         |
| HDInsight - Kafka cluster                        | `kafka`               | `Microsoft.HDInsight/clusters`                                         |
| HDInsight - Spark cluster                        | `spark`               | `Microsoft.HDInsight/clusters`                                         |
| HDInsight - Storm cluster                        | `storm`               | `Microsoft.HDInsight/clusters`                                         |
| HDInsight - ML Services cluster                  | `mls`                 | `Microsoft.HDInsight/clusters`                                         |
| IoT hub                                          | `iot`                 | `Microsoft.Devices/IotHubs`                                            |
| Provisioning services                            | `provs`               | `Microsoft.Devices/provisioningServices`                               |
| Provisioning services certificate                | `pcert`               | `Microsoft.Devices/provisioningServices/certificates`                  |
| Power BI Embedded                                | `pbi`                 | `Microsoft.PowerBIDedicated/capacities`                                |
| Time Series Insights environment                 | `tsi`                 | `Microsoft.TimeSeriesInsights/environments`                            |
| App Service environment                          | `ase`                 | `Microsoft.Web/hostingEnvironments`                                    |
| App Service plan                                 | `asp`                 | `Microsoft.Web/serverFarms`                                            |
| Azure Load Testing instance                      | `lt`                  | `Microsoft.LoadTestService/loadTests`                                  |
| Availability set                                 | `avail`               | `Microsoft.Compute/availabilitySets`                                   |
| Azure Arc enabled server                         | `arcs`                | `Microsoft.HybridCompute/machines`                                     |
| Azure Arc enabled Kubernetes cluster             | `arck`                | `Microsoft.Kubernetes/connectedClusters`                               |
| Azure Arc private link scope                     | `pls`                 | `Microsoft.HybridCompute/privateLinkScopes`                            |
| Azure Arc gateway                                | `arcgw`               | `Microsoft.HybridCompute/gateways`                                     |
| Batch accounts                                   | `ba`                  | `Microsoft.Batch/batchAccounts`                                        |
| Cloud service                                    | `cld`                 | `Microsoft.Compute/cloudServices`                                      |
| Communication Services                           | `acs`                 | `Microsoft.Communication/communicationServices`                        |
| Disk encryption set                              | `des`                 | `Microsoft.Compute/diskEncryptionSets`                                 |
| Function app                                     | `func`                | `Microsoft.Web/sites`                                                  |
| Gallery                                          | `gal`                 | `Microsoft.Compute/galleries`                                          |
| Hosting environment                              | `host`                | `Microsoft.Web/hostingEnvironments`                                    |
| Image template                                   | `it`                  | `Microsoft.VirtualMachineImages/imageTemplates`                        |
| Managed disk (OS)                                | `osdisk`              | `Microsoft.Compute/disks`                                              |
| Managed disk (data)                              | `disk`                | `Microsoft.Compute/disks`                                              |
| Notification Hubs                                | `ntf`                 | `Microsoft.NotificationHubs/namespaces/notificationHubs`               |
| Notification Hubs namespace                      | `ntfns`               | `Microsoft.NotificationHubs/namespaces`                                |
| Proximity placement group                        | `ppg`                 | `Microsoft.Compute/proximityPlacementGroups`                           |
| Restore point collection                         | `rpc`                 | `Microsoft.Compute/restorePointCollections`                            |
| Snapshot                                         | `snap`                | `Microsoft.Compute/snapshots`                                          |
| Static web app                                   | `stapp`               | `Microsoft.Web/staticSites`                                            |
| Virtual machine                                  | `vm`                  | `Microsoft.Compute/virtualMachines`                                    |
| Virtual machine scale set                        | `vmss`                | `Microsoft.Compute/virtualMachineScaleSets`                            |
| Virtual machine maintenance configuration        | `mc`                  | `Microsoft.Maintenance/maintenanceConfigurations`                      |
| VM storage account                               | `stvm`                | `Microsoft.Storage/storageAccounts`                                    |
| Web app                                          | `app`                 | `Microsoft.Web/sites`                                                  |
| AKS cluster                                      | `aks`                 | `Microsoft.ContainerService/managedClusters`                           |
| AKS system node pool                             | `npsystem`            | `Microsoft.ContainerService/managedClusters/agentPools (mode: System)` |
| AKS user node pool                               | `np`                  | `Microsoft.ContainerService/managedClusters/agentPools (mode: User)`   |
| Container apps                                   | `ca`                  | `Microsoft.App/containerApps`                                          |
| Container apps environment                       | `cae`                 | `Microsoft.App/managedEnvironments`                                    |
| Container apps job                               | `caj`                 | `Microsoft.App/jobs`                                                   |
| Container registry                               | `cr`                  | `Microsoft.ContainerRegistry/registries`                               |
| Container instance                               | `ci`                  | `Microsoft.ContainerInstance/containerGroups`                          |
| Service Fabric cluster                           | `sf`                  | `Microsoft.ServiceFabric/clusters`                                     |
| Service Fabric managed cluster                   | `sfmc`                | `Microsoft.ServiceFabric/managedClusters`                              |
| Azure Cosmos DB database                         | `cosmos`              | `Microsoft.DocumentDB/databaseAccounts/sqlDatabases`                   |
| Azure Cosmos DB for Apache Cassandra account     | `coscas`              | `Microsoft.DocumentDB/databaseAccounts`                                |
| Azure Cosmos DB for MongoDB account              | `cosmon`              | `Microsoft.DocumentDB/databaseAccounts`                                |
| Azure Cosmos DB for NoSQL account                | `cosno`               | `Microsoft.DocumentDb/databaseAccounts`                                |
| Azure Cosmos DB for Table account                | `costab`              | `Microsoft.DocumentDb/databaseAccounts`                                |
| Azure Cosmos DB for Apache Gremlin account       | `cosgrm`              | `Microsoft.DocumentDb/databaseAccounts`                                |
| Azure Cosmos DB PostgreSQL cluster               | `cospos`              | `Microsoft.DBforPostgreSQL/serverGroupsv2`                             |
| Azure Cache for Redis instance                   | `redis`               | `Microsoft.Cache/Redis`                                                |
| Azure Managed Redis                              | `amr`                 | `Microsoft.Cache/RedisEnterprise`                                      |
| Azure SQL Database server                        | `sql`                 | `Microsoft.Sql/servers`                                                |
| Azure SQL database                               | `sqldb`               | `Microsoft.Sql/servers/databases`                                      |
| Azure SQL Elastic Job agent                      | `sqlja`               | `Microsoft.Sql/servers/jobAgents`                                      |
| Azure SQL Elastic Pool                           | `sqlep`               | `Microsoft.Sql/servers/elasticpool`                                    |
| MySQL database                                   | `mysql`               | `Microsoft.DBforMySQL/servers`                                         |
| PostgreSQL database                              | `psql`                | `Microsoft.DBforPostgreSQL/servers`                                    |
| SQL Managed Instance                             | `sqlmi`               | `Microsoft.Sql/managedInstances`                                       |
| App Configuration store                          | `appcs`               | `Microsoft.AppConfiguration/configurationStores`                       |
| Maps account                                     | `map`                 | `Microsoft.Maps/accounts`                                              |
| SignalR                                          | `sigr`                | `Microsoft.SignalRService/SignalR`                                     |
| WebPubSub                                        | `wps`                 | `Microsoft.SignalRService/webPubSub`                                   |
| Azure Managed Grafana                            | `amg`                 | `Microsoft.Dashboard/grafana`                                          |
| Managed DevOps Pools                             | `mdp`                 | `Microsoft.DevOpsInfrastructure/pools`                                 |
| API management service instance                  | `apim`                | `Microsoft.ApiManagement/service`                                      |
| Integration account                              | `ia`                  | `Microsoft.Logic/integrationAccounts`                                  |
| Logic app                                        | `logic`               | `Microsoft.Logic/workflows`                                            |
| Service Bus namespace                            | `sbns`                | `Microsoft.ServiceBus/namespaces`                                      |
| Service Bus queue                                | `sbq`                 | `Microsoft.ServiceBus/namespaces/queues`                               |
| Service Bus topic                                | `sbt`                 | `Microsoft.ServiceBus/namespaces/topics`                               |
| Service Bus topic subscription                   | `sbts`                | `Microsoft.ServiceBus/namespaces/topics/subscriptions`                 |
| Automation account                               | `aa`                  | `Microsoft.Automation/automationAccounts`                              |
| Azure Policy definition                          | *\<descriptive\>*     | `Microsoft.Authorization/policyDefinitions`                            |
| Application Insights                             | `appi`                | `Microsoft.Insights/components`                                        |
| Azure Monitor action group                       | `ag`                  | `Microsoft.Insights/actionGroups`                                      |
| Azure Monitor data collection rule               | `dcr`                 | `Microsoft.Insights/dataCollectionRules`                               |
| Azure Monitor alert processing rule              | `apr`                 | `Microsoft.AlertsManagement/actionRules`                               |
| Data collection endpoint                         | `dce`                 | `Microsoft.Insights/dataCollectionEndpoints`                           |
| Diagnostic settings                              | `ds`                  | `Microsoft.Insights/diagnosticSettings`                                |
| Deployment scripts                               | `script`              | `Microsoft.Resources/deploymentScripts`                                |
| Log Analytics workspace                          | `log`                 | `Microsoft.OperationalInsights/workspaces`                             |
| Log Analytics query packs                        | `pack`                | `Microsoft.OperationalInsights/querypacks`                             |
| Management group                                 | `mg`                  | `Microsoft.Management/managementGroups`                                |
| Microsoft Purview instance                       | `pview`               | `Microsoft.Purview/accounts`                                           |
| Resource group                                   | rg                    | Microsoft.Resources/resourceGroups                                     |
| Template specs name                              | `ts`                  | `Microsoft.Resources/templateSpecs`                                    |
| Azure Migrate project                            | `migr`                | `Microsoft.Migrate/assessmentProjects`                                 |
| Database Migration Service instance              | `dms`                 | `Microsoft.DataMigration/services`                                     |
| Recovery Services vault                          | `rsv`                 | `Microsoft.RecoveryServices/vaults`                                    |
| Application gateway                              | `agw`                 | `Microsoft.Network/applicationGateways`                                |
| Application security group (ASG)                 | `asg`                 | `Microsoft.Network/applicationSecurityGroups`                          |
| CDN profile                                      | `cdnp`                | `Microsoft.Cdn/profiles`                                               |
| CDN endpoint                                     | `cdne`                | `Microsoft.Cdn/profiles/endpoints`                                     |
| Connections                                      | `con`                 | `Microsoft.Network/connections`                                        |
| DNS                                              | *\<DNS domain name\>* | `Microsoft.Network/dnsZones`                                           |
| DNS forwarding ruleset                           | `dnsfrs`              | `Microsoft.Network/dnsForwardingRulesets`                              |
| DNS private resolver                             | `dnspr`               | `Microsoft.Network/dnsResolvers`                                       |
| DNS private resolver inbound endpoint            | `in`                  | `Microsoft.Network/dnsResolvers/inboundEndpoints`                      |
| DNS private resolver outbound endpoint           | `out`                 | `Microsoft.Network/dnsResolvers/outboundEndpoints`                     |
| DNS zone                                         | *\<DNS domain name\>* | `Microsoft.Network/privateDnsZones`                                    |
| Firewall                                         | `afw`                 | `Microsoft.Network/azureFirewalls`                                     |
| Firewall policy                                  | `afwp`                | `Microsoft.Network/firewallPolicies`                                   |
| ExpressRoute circuit                             | `erc`                 | `Microsoft.Network/expressRouteCircuits`                               |
| ExpressRoute direct                              | `erd`                 | `Microsoft.Network/expressRoutePorts`                                  |
| ExpressRoute gateway                             | `ergw`                | `Microsoft.Network/virtualNetworkGateways`                             |
| Front Door (Standard/Premium) profile            | `afd`                 | `Microsoft.Cdn/profiles`                                               |
| Front Door (Standard/Premium) endpoint           | `fde`                 | `Microsoft.Cdn/profiles/afdEndpoints`                                  |
| Front Door firewall policy                       | `fdfp`                | `Microsoft.Network/frontdoorWebApplicationFirewallPolicies`            |
| Front Door (classic)                             | `afd`                 | `Microsoft.Network/frontDoors`                                         |
| IP group                                         | `ipg`                 | `Microsoft.Network/ipGroups`                                           |
| Load balancer (internal)                         | `lbi`                 | `Microsoft.Network/loadBalancers`                                      |
| Load balancer (external)                         | `lbe`                 | `Microsoft.Network/loadBalancers`                                      |
| Load balancer rule                               | `rule`                | `Microsoft.Network/loadBalancers/inboundNatRules`                      |
| Local network gateway                            | `lgw`                 | `Microsoft.Network/localNetworkGateways`                               |
| NAT gateway                                      | `ng`                  | `Microsoft.Network/natGateways`                                        |
| Network interface (NIC)                          | `nic`                 | `Microsoft.Network/networkInterfaces`                                  |
| Network security perimeter                       | `nsp`                 | `Microsoft.Network/networkSecurityPerimeters`                          |
| Network security group (NSG)                     | `nsg`                 | `Microsoft.Network/networkSecurityGroups`                              |
| Network security group (NSG) security rules      | `nsgsr`               | `Microsoft.Network/networkSecurityGroups/securityRules`                |
| Network Watcher                                  | `nw`                  | `Microsoft.Network/networkWatchers`                                    |
| Private Link                                     | `pl`                  | `Microsoft.Network/privateLinkServices`                                |
| Private endpoint                                 | `pep`                 | `Microsoft.Network/privateEndpoints`                                   |
| Public IP address                                | `pip`                 | `Microsoft.Network/publicIPAddresses`                                  |
| Public IP address prefix                         | `ippre`               | `Microsoft.Network/publicIPPrefixes`                                   |
| Route filter                                     | `rf`                  | `Microsoft.Network/routeFilters`                                       |
| Route server                                     | `rtserv`              | `Microsoft.Network/virtualHubs`                                        |
| Route table                                      | `rt`                  | `Microsoft.Network/routeTables`                                        |
| Service endpoint policy                          | `se`                  | `Microsoft.Network/serviceEndPointPolicies`                            |
| Traffic Manager profile                          | `traf`                | `Microsoft.Network/trafficManagerProfiles`                             |
| User defined route (UDR)                         | `udr`                 | `Microsoft.Network/routeTables/routes`                                 |
| Virtual network                                  | `vnet`                | `Microsoft.Network/virtualNetworks`                                    |
| Virtual network gateway                          | `vgw`                 | `Microsoft.Network/virtualNetworkGateways`                             |
| Virtual network manager                          | `vnm`                 | `Microsoft.Network/networkManagers`                                    |
| Virtual network peering                          | `peer`                | `Microsoft.Network/virtualNetworks/virtualNetworkPeerings`             |
| Virtual network subnet                           | `snet`                | `Microsoft.Network/virtualNetworks/subnets`                            |
| Virtual WAN                                      | `vwan`                | `Microsoft.Network/virtualWans`                                        |
| Virtual WAN Hub                                  | `vhub`                | `Microsoft.Network/virtualHubs`                                        |
| Azure Bastion                                    | `bas`                 | `Microsoft.Network/bastionHosts`                                       |
| Key vault                                        | `kv`                  | `Microsoft.KeyVault/vaults`                                            |
| Key Vault Managed HSM                            | `kvmhsm`              | `Microsoft.KeyVault/managedHSMs`                                       |
| Managed identity                                 | `id`                  | `Microsoft.ManagedIdentity/userAssignedIdentities`                     |
| SSH key                                          | `sshkey`              | `Microsoft.Compute/sshPublicKeys`                                      |
| VPN Gateway                                      | `vpng`                | `Microsoft.Network/vpnGateways`                                        |
| VPN connection                                   | `vcn`                 | `Microsoft.Network/vpnGateways/vpnConnections`                         |
| VPN site                                         | `vst`                 | `Microsoft.Network/vpnGateways/vpnSites`                               |
| Web Application Firewall (WAF) policy            | `waf`                 | `Microsoft.Network/firewallPolicies`                                   |
| Web Application Firewall (WAF) policy rule group | `wafrg`               | `Microsoft.Network/firewallPolicies/ruleGroups`                        |
| Backup Vault name                                | `bvault`              | `Microsoft.DataProtection/backupVaults`                                |
| Backup Vault policy                              | `bkpol`               | `Microsoft.DataProtection/backupVaults/backupPolicies`                 |
| File share                                       | `share`               | `Microsoft.Storage/storageAccounts/fileServices/shares`                |
| Storage account                                  | `st`                  | `Microsoft.Storage/storageAccounts`                                    |
| Storage Sync Service name                        | `sss`                 | `Microsoft.StorageSync/storageSyncServices`                            |
| Virtual desktop host pool                        | `vdpool`              | `Microsoft.DesktopVirtualization/hostPools`                            |
| Virtual desktop application group                | `vdag`                | `Microsoft.DesktopVirtualization/applicationGroups`                    |
| Virtual desktop workspace                        | `vdws`                | `Microsoft.DesktopVirtualization/workspaces`                           |
| Virtual desktop scaling plan                     | `vdscaling`           | `Microsoft.DesktopVirtualization/scalingPlans`                         |
