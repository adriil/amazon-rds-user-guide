# Multi\-AZ DB clusters<a name="Concepts.RDS_Fea_Regions_DB-eng.Feature.MultiAZDBClusters"></a>

A Multi\-AZ DB cluster deployment in Amazon RDS provides a high availability deployment mode of Amazon RDS with two readable standby DB instances\. A Multi\-AZ DB cluster has a writer DB instance and two reader DB instances in three separate Availability Zones in the same Region\. Multi\-AZ DB clusters provide high availability, increased capacity for read workloads, and lower write latency when compared to Multi\-AZ DB instance deployments\. For more information, see [Multi\-AZ DB cluster deployments](multi-az-db-clusters-concepts.md)\. 

Multi\-AZ DB clusters aren't available with the following engines:
+ RDS for MariaDB
+ RDS for Oracle
+ RDS for SQL Server

**Topics**
+ [Multi\-AZ DB clusters with RDS for MySQL](#Concepts.RDS_Fea_Regions_DB-eng.Feature.MultiAZDBClusters.my)
+ [Multi\-AZ DB clusters with RDS for PostgreSQL](#Concepts.RDS_Fea_Regions_DB-eng.Feature.MultiAZDBClusters.pg)

## Multi\-AZ DB clusters with RDS for MySQL<a name="Concepts.RDS_Fea_Regions_DB-eng.Feature.MultiAZDBClusters.my"></a>

Following are the supported engines and Region availability for Multi\-AZ DB clusters with RDS for MySQL\.


| Region | RDS for MySQL 8\.0 | 
| --- | --- | 
| US East \(Ohio\) | Version 8\.0\.28 and higher | 
| US East \(N\. Virginia\) | Version 8\.0\.28 and higher | 
| US West \(N\. California\) | – | 
| US West \(Oregon\) | Version 8\.0\.28 and higher | 
| Africa \(Cape Town\) | – | 
| Asia Pacific \(Hong Kong\) | – | 
| Asia Pacific \(Jakarta\) | – | 
| Asia Pacific \(Mumbai\) | – | 
| Asia Pacific \(Osaka\) | – | 
| Asia Pacific \(Seoul\) | – | 
| Asia Pacific \(Singapore\) | Version 8\.0\.28 and higher | 
| Asia Pacific \(Sydney\) | Version 8\.0\.28 and higher | 
| Asia Pacific \(Tokyo\) | Version 8\.0\.28 and higher | 
| Canada \(Central\) | – | 
| China \(Beijing\) | – | 
| China \(Ningxia\) | – | 
| Europe \(Frankfurt\) | Version 8\.0\.28 and higher | 
| Europe \(Ireland\) | Version 8\.0\.28 and higher | 
| Europe \(London\) | – | 
| Europe \(Milan\) | – | 
| Europe \(Paris\) | – | 
| Europe \(Stockholm\) | Version 8\.0\.28 and higher | 
| Middle East \(Bahrain\) | – | 
| Middle East \(UAE\) | – | 
| South America \(São Paulo\) | – | 
| AWS GovCloud \(US\-East\) | – | 
| AWS GovCloud \(US\-West\) | – | 

## Multi\-AZ DB clusters with RDS for PostgreSQL<a name="Concepts.RDS_Fea_Regions_DB-eng.Feature.MultiAZDBClusters.pg"></a>

Following are the supported engine version and Region availability for Multi\-AZ DB clusters with RDS for PostgreSQL\.


| Region | RDS for PostgreSQL 13 | 
| --- | --- | 
| US East \(Ohio\) | Version 13\.4 and version 13\.7 | 
| US East \(N\. Virginia\) | Version 13\.4 and version 13\.7 | 
| US West \(N\. California\) | – | 
| US West \(Oregon\) | Version 13\.4 and version 13\.7 | 
| Africa \(Cape Town\) | – | 
| Asia Pacific \(Hong Kong\) | – | 
| Asia Pacific \(Jakarta\) | – | 
| Asia Pacific \(Mumbai\) | – | 
| Asia Pacific \(Osaka\) | – | 
| Asia Pacific \(Seoul\) | – | 
| Asia Pacific \(Singapore\) | Version 13\.4 and version 13\.7 | 
| Asia Pacific \(Sydney\) | Version 13\.4 and version 13\.7 | 
| Asia Pacific \(Tokyo\) | Version 13\.4 and version 13\.7 | 
| Canada \(Central\) | – | 
| China \(Beijing\) | – | 
| China \(Ningxia\) | – | 
| Europe \(Frankfurt\) | Version 13\.4 and version 13\.7 | 
| Europe \(Ireland\) | Version 13\.4 and version 13\.7 | 
| Europe \(London\) | – | 
| Europe \(Milan\) | – | 
| Europe \(Paris\) | – | 
| Europe \(Stockholm\) | Version 13\.4 and version 13\.7 | 
| Middle East \(Bahrain\) | – | 
| Middle East \(UAE\) | – | 
| South America \(São Paulo\) | – | 
| AWS GovCloud \(US\-East\) | – | 
| AWS GovCloud \(US\-West\) | – | 