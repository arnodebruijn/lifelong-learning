Data Processing
===============


Database types
--------------
- Relational:     store data with pre-defined schema and relationships between them.
- Key-value:      optimized to quickly store and retrieve large volumes of key-value pairs.
- Graph:          store highly connected graph datasets and query and navigate relationships.
- Time series:    efficiently collect, synthesize and derive insights from enormous amounts of data that change over time.
- Ledger:         public decentralized trusted authority
- Document:       store semi structured data as documents

Database examples
-----------------
- MySQL                 ORDBMS
- PostgresSQL           ORDBMS
- Redis                 Distributed, in-memory key-value database
- Amazon DynamoDB       NoSQL, document-oriented key-value database
- MongoDB               NoSQL, document-oriented database
- Apache Cassandra      NoSQL, distributed, wide column store
- Apache CouchDB        NoSQL, document-oriented database
- Apache HBase          Non-relational distributed database
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
* ACID                      Atomicity, Consistency, Isolation, Durability. A sequence of database operations that satisfy the ACID properties can be perceived as a single logical operation on the data (a transaction).
