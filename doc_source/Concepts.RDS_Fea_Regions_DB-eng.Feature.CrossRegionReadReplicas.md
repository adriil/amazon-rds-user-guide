# Cross\-Region read replicas<a name="Concepts.RDS_Fea_Regions_DB-eng.Feature.CrossRegionReadReplicas"></a>

By using cross\-Region read replicas in Amazon RDS, you can create a MariaDB, MySQL, Oracle, or PostgreSQL read replica in a different Region from the source DB instance\. For more information, see [Creating a read replica in a different AWS Region](USER_ReadRepl.md#USER_ReadRepl.XRgn)\.

Cross\-Region read replicas aren't available with the following engines:
+ RDS for SQL Server

**Topics**
+ [Cross\-Region read replicas with RDS for MariaDB](#Concepts.RDS_Fea_Regions_DB-eng.Feature.CrossRegionReadReplicas.mdb)
+ [Cross\-Region read replicas with RDS for MySQL](#Concepts.RDS_Fea_Regions_DB-eng.Feature.CrossRegionReadReplicas.my)
+ [Cross\-Region read replicas with RDS for PostgreSQL](#Concepts.RDS_Fea_Regions_DB-eng.Feature.CrossRegionReadReplicas.pg)
+ [Cross\-Region read replicas with RDS for Oracle](#Concepts.RDS_Fea_Regions_DB-eng.Feature.CrossRegionReadReplicas.ora)

## Cross\-Region read replicas with RDS for MariaDB<a name="Concepts.RDS_Fea_Regions_DB-eng.Feature.CrossRegionReadReplicas.mdb"></a>

Cross\-Region read replicas with RDS for MariaDB are available in all Regions for the following versions:
+ RDS for MariaDB 10\.6 \(All versions\)
+ RDS for MariaDB 10\.5 \(All versions\)
+ RDS for MariaDB 10\.4 \(All versions\)
+ RDS for MariaDB 10\.3 \(All versions\)

## Cross\-Region read replicas with RDS for MySQL<a name="Concepts.RDS_Fea_Regions_DB-eng.Feature.CrossRegionReadReplicas.my"></a>

Cross\-Region read replicas with RDS for MySQL are available in all Regions for the following versions:
+ RDS for MySQL 8\.0 \(All versions\)
+ RDS for MySQL 5\.7 \(All versions\)
+ RDS for MySQL 5\.6 \(All versions\)

## Cross\-Region read replicas with RDS for PostgreSQL<a name="Concepts.RDS_Fea_Regions_DB-eng.Feature.CrossRegionReadReplicas.pg"></a>

Cross\-Region read replicas with RDS for PostgreSQL are available in all Regions for the following versions:
+ RDS for PostgreSQL 14 \(All versions\)
+ RDS for PostgreSQL 13 \(All versions\)
+ RDS for PostgreSQL 12 \(All versions\)
+ RDS for PostgreSQL 11 \(All versions\)
+ RDS for PostgreSQL 10 \(All versions\)

## Cross\-Region read replicas with RDS for Oracle<a name="Concepts.RDS_Fea_Regions_DB-eng.Feature.CrossRegionReadReplicas.ora"></a>

Cross\-Region read replicas for RDS for Oracle are available in all Regions with the following version limitations:
+ For RDS for Oracle 21c, cross\-Region read replicas aren't available\.
+ For RDS for Oracle 19c, cross\-Region read replicas are available for instances of Oracle Database 19c that aren't container database \(CBD\) instances\.
+ For RDS for Oracle 12c, cross\-Region read replicas are available for Oracle Enterprise Edition \(EE\) of Oracle Database 12c Release 1 \(12\.1\) using 12\.1\.0\.2\.v10 and higher 12c releases\.
+ You can replicate between the AWS GovCloud \(US\-East\) and AWS GovCloud \(US\-West\) Regions, but not into or out of AWS GovCloud \(US\)\.

For more information on additional requirements for cross\-Region read replicas with RDS for Oracle, see [Considerations for RDS for Oracle replicas](oracle-read-replicas.limitations.md)\. 