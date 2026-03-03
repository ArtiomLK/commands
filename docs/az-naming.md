# Azure Resource Naming Conventions

> **⚠️ Disclaimer:** The API endpoint examples in this document are for illustration purposes only and may be inaccurate or outdated. Always verify against the [official Azure documentation](https://learn.microsoft.com/en-us/azure).
>
Recommended abbreviations for Azure resources based on the [Cloud Adoption Framework](https://learn.microsoft.com/en-us/azure/cloud-adoption-framework/ready/azure-best-practices/resource-abbreviations). Character length constraints are sourced from [Naming rules and restrictions for Azure resources](https://learn.microsoft.com/en-us/azure/azure-resource-manager/management/resource-name-rules).

All endpoints require `https://` — it is omitted from examples below for brevity.

---

## AI + Machine Learning

| Resource                              | Abbreviation | Char Length | API Endpoint Example                     |
| ------------------------------------- | ------------ | ----------- | ---------------------------------------- |
| AI Search                             | `srch`       | 2-60        | `srch-app1.search.windows.net`           |
| Foundry Tools (multi-service account) | `ais`        | 2-64        | `ais-app1.cognitiveservices.azure.com`   |
| Foundry account                       | `aif`        | 2-64        | `aif-app1.cognitiveservices.azure.com`   |
| Foundry account project               | `proj`       | 2-64        |                                          |
| Foundry hub                           | `hub`        | 3-33        |                                          |
| Foundry hub project                   | `proj`       | 3-33        |                                          |
| Azure AI Video Indexer                | `avi`        | 3-24        |                                          |
| Azure Machine Learning workspace      | `mlw`        | 3-33        | `mlw-app1.api.azureml.ms`                |
| Azure OpenAI Service                  | `oai`        | 2-64        | `oai-app1.openai.azure.com`              |
| Bot service                           | `bot`        | 2-64        |                                          |
| Computer vision                       | `cv`         | 2-64        | `cv-app1.cognitiveservices.azure.com`    |
| Content moderator                     | `cm`         | 2-64        | `cm-app1.cognitiveservices.azure.com`    |
| Content safety                        | `cs`         | 2-64        | `cs-app1.cognitiveservices.azure.com`    |
| Custom vision (prediction)            | `cstv`       | 2-64        | `cstv-app1.cognitiveservices.azure.com`  |
| Custom vision (training)              | `cstvt`      | 2-64        | `cstvt-app1.cognitiveservices.azure.com` |
| Document intelligence                 | `di`         | 2-64        | `di-app1.cognitiveservices.azure.com`    |
| Face API                              | `face`       | 2-64        | `face-app1.cognitiveservices.azure.com`  |
| Health Insights                       | `hi`         | 2-64        | `hi-app1.cognitiveservices.azure.com`    |
| Immersive reader                      | `ir`         | 2-64        | `ir-app1.cognitiveservices.azure.com`    |
| Language service                      | `lang`       | 2-64        | `lang-app1.cognitiveservices.azure.com`  |
| Speech service                        | `spch`       | 2-64        | `spch-app1.cognitiveservices.azure.com`  |
| Translator                            | `trsl`       | 2-64        | `trsl-app1.cognitiveservices.azure.com`  |

## Analytics and IoT

| Resource                                   | Abbreviation | Char Length | API Endpoint Example                           |
| ------------------------------------------ | ------------ | ----------- | ---------------------------------------------- |
| Azure Analysis Services server             | `as`         | 3-63        | `asazure://eastus.asazure.windows.net/as-app1` |
| Azure Databricks Access Connector          | `dbac`       | 3-64        |                                                |
| Azure Databricks workspace                 | `dbw`        | 3-64        | `adb-dbw-app1.azuredatabricks.net`             |
| Azure Data Explorer cluster                | `dec`        | 4-22        | `dec-app1.eastus.kusto.windows.net`            |
| Azure Data Explorer cluster database       | `dedb`       | 1-260       |                                                |
| Azure Data Factory                         | `adf`        | 3-63        | `adf-app1.adf.azure.com`                       |
| Azure Digital Twin instance                | `dt`         | 3-48        | `dt-app1.api.eus.digitaltwins.azure.net`       |
| Azure Stream Analytics                     | `asa`        | 3-63        |                                                |
| Azure Synapse Analytics private link hub   | `synplh`     | 1-45        |                                                |
| Azure Synapse Analytics SQL Dedicated Pool | `syndp`      | 1-60        |                                                |
| Azure Synapse Analytics Spark Pool         | `synsp`      | 1-15        |                                                |
| Azure Synapse Analytics workspaces         | `synw`       | 1-50        | `synw-app1.dev.azuresynapse.net`               |
| Data Lake Store account                    | `dls`        | 3-24        | `dls-app1.azuredatalakestore.net`              |
| Event Hubs namespace                       | `evhns`      | 6-50        | `evhns-app1.servicebus.windows.net`            |
| Event hub                                  | `evh`        | 1-256       |                                                |
| Event Grid domain                          | `evgd`       | 3-50        |                                                |
| Event Grid namespace                       | `evgns`      | 3-50        |                                                |
| Event Grid subscriptions                   | `evgs`       | 3-64        |                                                |
| Event Grid topic                           | `evgt`       | 3-50        |                                                |
| Event Grid system topic                    | `egst`       | 3-128       |                                                |
| Fabric Capacity                            | `fc`         | 3-63        |                                                |
| HDInsight - Hadoop cluster                 | `hadoop`     | 3-59        | `hadoop-app1.azurehdinsight.net`               |
| HDInsight - HBase cluster                  | `hbase`      | 3-59        | `hbase-app1.azurehdinsight.net`                |
| HDInsight - Kafka cluster                  | `kafka`      | 3-59        | `kafka-app1.azurehdinsight.net`                |
| HDInsight - Spark cluster                  | `spark`      | 3-59        | `spark-app1.azurehdinsight.net`                |
| HDInsight - Storm cluster                  | `storm`      | 3-59        | `storm-app1.azurehdinsight.net`                |
| HDInsight - ML Services cluster            | `mls`        | 3-59        | `mls-app1.azurehdinsight.net`                  |
| IoT hub                                    | `iot`        | 3-50        | `iot-app1.azure-devices.net`                   |
| Provisioning services                      | `provs`      | 3-64        | `provs-app1.azure-devices-provisioning.net`    |
| Provisioning services certificate          | `pcert`      | 1-64        |                                                |
| Power BI Embedded                          | `pbi`        | 3-63        |                                                |
| Time Series Insights environment           | `tsi`        | 1-90        | `tsi-app1.env.timeseries.azure.com`            |

## Compute and Web

| Resource                                  | Abbreviation | Char Length              | API Endpoint Example                |
| ----------------------------------------- | ------------ | ------------------------ | ----------------------------------- |
| App Service environment                   | `ase`        | 1-40                     |                                     |
| App Service plan                          | `asp`        | 1-60                     |                                     |
| Azure Load Testing instance               | `lt`         | 1-64                     |                                     |
| Availability set                          | `avail`      | 1-80                     |                                     |
| Azure Arc enabled server                  | `arcs`       | 1-54                     |                                     |
| Azure Arc enabled Kubernetes cluster      | `arck`       | 1-63                     |                                     |
| Azure Arc private link scope              | `pls`        | 3-90                     |                                     |
| Azure Arc gateway                         | `arcgw`      | 1-80                     |                                     |
| Batch accounts                            | `ba`         | 3-24                     | `ba-app1.eastus.batch.azure.com`    |
| Cloud service                             | `cld`        | 1-15                     | `cld-app1.cloudapp.net`             |
| Communication Services                    | `acs`        | 1-63                     |                                     |
| Disk encryption set                       | `des`        | 1-80                     |                                     |
| Function app                              | `func`       | 2-60                     | `func-app1.azurewebsites.net`       |
| Gallery                                   | `gal`        | 1-80                     |                                     |
| Hosting environment                       | `host`       | 1-40                     |                                     |
| Image template                            | `it`         | 1-80                     |                                     |
| Managed disk (OS)                         | `osdisk`     | 1-80                     |                                     |
| Managed disk (data)                       | `disk`       | 1-80                     |                                     |
| Notification Hubs                         | `ntf`        | 1-260                    |                                     |
| Notification Hubs namespace               | `ntfns`      | 6-50                     | `ntfns-app1.servicebus.windows.net` |
| Proximity placement group                 | `ppg`        | 1-80                     |                                     |
| Restore point collection                  | `rpc`        | 1-80                     |                                     |
| Snapshot                                  | `snap`       | 1-80                     |                                     |
| Static web app                            | `stapp`      | 1-40                     | `stapp-app1.azurestaticapps.net`    |
| Virtual machine                           | `vm`         | 1-15 (Win), 1-64 (Linux) |                                     |
| Virtual machine scale set                 | `vmss`       | 1-15 (Win), 1-64 (Linux) |                                     |
| Virtual machine maintenance configuration | `mc`         | 1-260                    |                                     |
| VM storage account                        | `stvm`       | 3-24                     | `stvmapp1.blob.core.windows.net`    |
| Web app                                   | `app`        | 2-60                     | `app-app1.azurewebsites.net`        |

## Containers

| Resource                       | Abbreviation | Char Length | API Endpoint Example                     |
| ------------------------------ | ------------ | ----------- | ---------------------------------------- |
| AKS cluster                    | `aks`        | 1-63        |                                          |
| AKS system node pool           | `npsystem`   | 1-12        |                                          |
| AKS user node pool             | `np`         | 1-12        |                                          |
| Container apps                 | `ca`         | 2-32        | `ca-app1.{region}.azurecontainerapps.io` |
| Container apps environment     | `cae`        | 1-60        |                                          |
| Container apps job             | `caj`        | 2-32        |                                          |
| Container registry             | `cr`         | 5-50        | `crapp1.azurecr.io`                      |
| Container instance             | `ci`         | 1-63        |                                          |
| Service Fabric cluster         | `sf`         | 4-23        | `sf-app1.eastus.cloudapp.azure.com`      |
| Service Fabric managed cluster | `sfmc`       | 3-63        | `sfmc-app1.eastus.cloudapp.azure.com`    |

## Databases

| Resource                                     | Abbreviation | Char Length | API Endpoint Example                       |
| -------------------------------------------- | ------------ | ----------- | ------------------------------------------ |
| Azure Cosmos DB database                     | `cosmos`     | 3-44        |                                            |
| Azure Cosmos DB for Apache Cassandra account | `coscas`     | 3-44        | `coscas-app1.cassandra.cosmos.azure.com`   |
| Azure Cosmos DB for MongoDB account          | `cosmon`     | 3-44        | `cosmon-app1.mongo.cosmos.azure.com`       |
| Azure Cosmos DB for NoSQL account            | `cosno`      | 3-44        | `cosno-app1.documents.azure.com:443/`      |
| Azure Cosmos DB for Table account            | `costab`     | 3-44        | `costab-app1.table.cosmos.azure.com`       |
| Azure Cosmos DB for Apache Gremlin account   | `cosgrm`     | 3-44        | `cosgrm-app1.gremlin.cosmos.azure.com`     |
| Azure Cosmos DB PostgreSQL cluster           | `cospos`     | 3-63        | `c-cospos-app1.postgres.cosmos.azure.com`  |
| Azure Cache for Redis instance               | `redis`      | 1-63        | `redis-app1.redis.cache.windows.net:6380`  |
| Azure Managed Redis                          | `amr`        | 1-63        | `amr-app1.redisenterprise.cache.azure.net` |
| Azure SQL Database server                    | `sql`        | 1-63        | `sql-app1.database.windows.net`            |
| Azure SQL database                           | `sqldb`      | 1-128       |                                            |
| Azure SQL Elastic Job agent                  | `sqlja`      | 1-128       |                                            |
| Azure SQL Elastic Pool                       | `sqlep`      | 1-128       |                                            |
| MySQL database                               | `mysql`      | 3-63        | `mysql-app1.mysql.database.azure.com`      |
| PostgreSQL database                          | `psql`       | 3-63        | `psql-app1.postgres.database.azure.com`    |
| SQL Managed Instance                         | `sqlmi`      | 1-63        | `sqlmi-app1.database.windows.net`          |

## Developer Tools

| Resource                | Abbreviation | Char Length | API Endpoint Example            |
| ----------------------- | ------------ | ----------- | ------------------------------- |
| App Configuration store | `appcs`      | 5-50        | `appcs-app1.azconfig.io`        |
| Maps account            | `map`        | 1-98        |                                 |
| SignalR                 | `sigr`       | 3-63        | `sigr-app1.service.signalr.net` |
| WebPubSub               | `wps`        | 3-63        | `wps-app1.webpubsub.azure.com`  |

## DevOps

| Resource              | Abbreviation | Char Length | API Endpoint Example         |
| --------------------- | ------------ | ----------- | ---------------------------- |
| Azure Managed Grafana | `amg`        | 2-23        | `amg-app1.grafana.azure.com` |
| Managed DevOps Pools  | `mdp`        | 1-64        |                              |

## Integration

| Resource                        | Abbreviation | Char Length | API Endpoint Example               |
| ------------------------------- | ------------ | ----------- | ---------------------------------- |
| API management service instance | `apim`       | 1-50        | `apim-app1.azure-api.net`          |
| Integration account             | `ia`         | 1-80        |                                    |
| Logic app                       | `logic`      | 1-43        |                                    |
| Service Bus namespace           | `sbns`       | 6-50        | `sbns-app1.servicebus.windows.net` |
| Service Bus queue               | `sbq`        | 1-260       |                                    |
| Service Bus topic               | `sbt`        | 1-260       |                                    |
| Service Bus topic subscription  | `sbts`       | 1-50        |                                    |

## Management and Governance

| Resource                            | Abbreviation      | Char Length | API Endpoint Example           |
| ----------------------------------- | ----------------- | ----------- | ------------------------------ |
| Automation account                  | `aa`              | 6-50        |                                |
| Azure Policy definition             | *\<descriptive\>* | 1-64        |                                |
| Application Insights                | `appi`            | 1-260       |                                |
| Azure Monitor action group          | `ag`              | 1-260       |                                |
| Azure Monitor data collection rule  | `dcr`             | 1-64        |                                |
| Azure Monitor alert processing rule | `apr`             | 1-260       |                                |
| Data collection endpoint            | `dce`             | 3-44        |                                |
| Diagnostic settings                 | `ds`              | 1-260       |                                |
| Deployment scripts                  | `script`          | 1-64        |                                |
| Log Analytics workspace             | `log`             | 4-63        |                                |
| Log Analytics query packs           | `pack`            | 1-260       |                                |
| Management group                    | `mg`              | 1-90        |                                |
| Microsoft Purview instance          | `pview`           | 3-63        | `pview-app1.purview.azure.com` |
| Resource group                      | rg                | 1-90        | rg-app1                        |
| Template specs name                 | `ts`              | 1-90        |                                |

## Migration

| Resource                            | Abbreviation | Char Length | API Endpoint Example |
| ----------------------------------- | ------------ | ----------- | -------------------- |
| Azure Migrate project               | `migr`       | 2-62        |                      |
| Database Migration Service instance | `dms`        | 2-62        |                      |
| Recovery Services vault             | `rsv`        | 2-50        |                      |

## Networking

| Resource                                    | Abbreviation          | Char Length | API Endpoint Example                |
| ------------------------------------------- | --------------------- | ----------- | ----------------------------------- |
| Application gateway                         | `agw`                 | 1-80        |                                     |
| Application security group (ASG)            | `asg`                 | 1-80        |                                     |
| CDN profile                                 | `cdnp`                | 1-260       |                                     |
| CDN endpoint                                | `cdne`                | 1-50        | `cdne-app1.azureedge.net`           |
| Connections                                 | `con`                 | 1-80        |                                     |
| DNS                                         | *\<DNS domain name\>* | 1-63        | `contoso.com`                       |
| DNS forwarding ruleset                      | `dnsfrs`              | 1-80        |                                     |
| DNS private resolver                        | `dnspr`               | 1-80        |                                     |
| DNS private resolver inbound endpoint       | `in`                  | 1-80        |                                     |
| DNS private resolver outbound endpoint      | `out`                 | 1-80        |                                     |
| DNS zone                                    | *\<DNS domain name\>* | 1-63        | `privatelink.blob.core.windows.net` |
| Firewall                                    | `afw`                 | 1-80        |                                     |
| Firewall policy                             | `afwp`                | 1-80        |                                     |
| ExpressRoute circuit                        | `erc`                 | 1-80        |                                     |
| ExpressRoute direct                         | `erd`                 | 1-80        |                                     |
| ExpressRoute gateway                        | `ergw`                | 1-80        |                                     |
| Front Door (Standard/Premium) profile       | `afd`                 | 1-260       |                                     |
| Front Door (Standard/Premium) endpoint      | `fde`                 | 1-50        | `fde-app1.azurefd.net`              |
| Front Door firewall policy                  | `fdfp`                | 1-128       |                                     |
| Front Door (classic)                        | `afd`                 | 5-64        | `afd-app1.azurefd.net`              |
| IP group                                    | `ipg`                 | 1-80        |                                     |
| Load balancer (internal)                    | `lbi`                 | 1-80        |                                     |
| Load balancer (external)                    | `lbe`                 | 1-80        |                                     |
| Load balancer rule                          | `rule`                | 1-80        |                                     |
| Local network gateway                       | `lgw`                 | 1-80        |                                     |
| NAT gateway                                 | `ng`                  | 1-80        |                                     |
| Network interface (NIC)                     | `nic`                 | 1-80        |                                     |
| Network security perimeter                  | `nsp`                 | 1-80        |                                     |
| Network security group (NSG)                | `nsg`                 | 1-80        |                                     |
| Network security group (NSG) security rules | `nsgsr`               | 1-80        |                                     |
| Network Watcher                             | `nw`                  | 1-80        |                                     |
| Private Link                                | `pl`                  | 2-64        |                                     |
| Private endpoint                            | `pe`                  | 2-64        |                                     |
| Public IP address                           | `pip`                 | 1-80        |                                     |
| Public IP address prefix                    | `ippre`               | 1-80        |                                     |
| Route filter                                | `rf`                  | 1-80        |                                     |
| Route server                                | `rtserv`              | 1-80        |                                     |
| Route table                                 | `rt`                  | 1-80        |                                     |
| Service endpoint policy                     | `se`                  | 1-80        |                                     |
| Traffic Manager profile                     | `traf`                | 1-63        | `traf-app1.trafficmanager.net`      |
| User defined route (UDR)                    | `udr`                 | 1-80        |                                     |
| Virtual network                             | `vnet`                | 2-64        |                                     |
| Virtual network gateway                     | `vgw`                 | 1-80        |                                     |
| Virtual network manager                     | `vnm`                 | 1-80        |                                     |
| Virtual network peering                     | `peer`                | 1-80        |                                     |
| Virtual network subnet                      | `snet`                | 1-80        |                                     |
| Virtual WAN                                 | `vwan`                | 1-80        |                                     |
| Virtual WAN Hub                             | `vhub`                | 1-80        |                                     |

## Security

| Resource                                         | Abbreviation | Char Length | API Endpoint Example               |
| ------------------------------------------------ | ------------ | ----------- | ---------------------------------- |
| Azure Bastion                                    | `bas`        | 1-80        |                                    |
| Key vault                                        | `kv`         | 3-24        | `kv-app1.vault.azure.net`          |
| Key Vault Managed HSM                            | `kvmhsm`     | 3-24        | `kvmhsm-app1.managedhsm.azure.net` |
| Managed identity                                 | `id`         | 3-128       |                                    |
| SSH key                                          | `sshkey`     | 1-80        |                                    |
| VPN Gateway                                      | `vpng`       | 1-80        |                                    |
| VPN connection                                   | `vcn`        | 1-80        |                                    |
| VPN site                                         | `vst`        | 1-80        |                                    |
| Web Application Firewall (WAF) policy            | `waf`        | 1-80        |                                    |
| Web Application Firewall (WAF) policy rule group | `wafrg`      | 1-80        |                                    |

## Storage

| Resource                  | Abbreviation | Char Length | API Endpoint Example           |
| ------------------------- | ------------ | ----------- | ------------------------------ |
| Backup Vault name         | `bvault`     | 2-50        |                                |
| Backup Vault policy       | `bkpol`      | 1-75        |                                |
| File share                | `share`      | 3-63        |                                |
| Storage account           | `st`         | 3-24        | `stapp1.blob.core.windows.net` |
| Storage Sync Service name | `sss`        | 1-260       |                                |

## Virtual Desktop Infrastructure

| Resource                          | Abbreviation | Char Length | API Endpoint Example |
| --------------------------------- | ------------ | ----------- | -------------------- |
| Virtual desktop host pool         | `vdpool`     | 3-64        |                      |
| Virtual desktop application group | `vdag`       | 3-64        |                      |
| Virtual desktop workspace         | `vdws`       | 3-64        |                      |
| Virtual desktop scaling plan      | `vdscaling`  | 3-64        |                      |

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
