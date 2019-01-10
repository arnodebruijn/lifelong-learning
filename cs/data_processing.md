Data Processing
===============


Hadoop
======
The Apache Hadoop software library is a framework that allows for the distributed processing of large data sets across clusters of computers using simple programming models. It is designed to scale up from single servers to thousands of machines, each offering local computation and storage.

Storage
------
HDFS (Hadoop Distributed File System)
Hadoop splits files into large blocks and distributes them accross nodes in a cluster.

Processing
----------
MapReduce
Nodes manipulate the data they have access to (data locality) and as such process the data in parallel


Apache Spark
============
Open source cluster computing framework. Provides an interface for programming entire clusters with implicit data parallelism and fault tolerance. Requires a cluster manager and a distributed file system.

Cluster managers:
* Native Spark cluster
* Hadoop YARN
* Apache Mesos

Distributed file systems:
* Hadoop Distributed File System
* MapR File System
* Cassandra - a scalable multi-master database with no single point of failure
* Openstack Swift
* Amazon S3
* Kudu



Concepts
========

ETL (Extract Transform Load)
---
Database usage process. Commonly the three phases are executed in parallel.

Extraction:     data is extracted from various sources
Transformation: data is transformed for storing in the proper format or structure for the purposes of querying and analysis.
Loading:        data is loaded into the final target database


MapReduce
---------
Programming model for processing and generating big data sets with a parallel distributed algotithm on a cluster.
Map:    performs filtering and sorting
Reduce: performs a summary operation


OLAP (Online Analytical Processing)
-----------------------------------
Analyze multidimensional data interactively from multiple perspectives. Consist of thtree basic analytical operations:
* Consolidation (roll-up)     involves the aggregation of data that can be accumulated and computed in one or more dimensions
* drill-down                  navigate through the details
* slicing and dicing          take out a specific set of data and view the slices from different viewpoints (also called dimensions)

OLAP deals with Historical Data or Archival Data. OLAP is characterized by relatively low volume of transactions.
Queries are often very complex and involve aggregations. For OLAP systems a response time is an effectiveness measure.
OLAP applications are widely used by Data Mining techniques. In OLAP database there is aggregated, historical data, stored in multi-dimensional schemas (usually star schema). Sometimes a query needs to access large amount of data in management records for example what is the companies profit of last year.


OLTP (On-line Transaction Processing)
-------------------------------------
OLTP is characterized by a large number of short on-line transactions (INSERT, UPDATE, DELETE).
The main emphasis for OLTP systems is put on very fast query processing, maintaining data integrity in multi-access environments and an effectiveness measured by number of transactions per second.
In OLTP database there is detailed and current data, and schema used to store transactional databases is the entity model (usually 3NF). It involves queries accessing individual record like Update your Email in Company database.


Dimensional Modeling
--------------------
A set of methods, techniques and concepts for use in data warehouse design.

Concepts
  * facts       measures, typically numeric values that can be aggregated
  * dimensions  context, groups of hierarchies and descriptors that define the facts.

Kimball dimensional design process
1. Select the business process
2. Declare the grain
3. Identify the dimensions
4. Identify the facts


Data warehouse
--------------
Central repositories of integrated data from one or more disparate sources. They store current and historical data in one single place that are used for creating analytical reports for workers. Designed to access large groups of related records usually implemented read-only.

Data marts
----------
A subset of the data warehouse usually oriented to a specific business line or team. Access pattern specific to data warehouse environments, used to retrieve client-facing data.

Data staging area
-----------------
An intermediate storage area used for data processing during the ETL process. The data staging area sits between the data sources and the data targets (data warehouses, data marts or other data repositories)
Functions:
  * consolidation of data from multiple sources
  * aligning data: standardizing reference data across multiple source systems and validation of relationships between sources.
  * minimizing contention: copying data from the source systems to the staging area in one shot is often more efficitent than retrieving individual record on a one-of basis.
  * independant scheduling
  * change detection
  * cleansing data


Glossary
========
* Block/physical record     a sequence of bytes usually containing some whole number of records.
* Contention                multiple processes or instances competing for access to the same index or data block at the same time.

