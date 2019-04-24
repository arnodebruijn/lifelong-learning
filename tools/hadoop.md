Apache Hadoop Ecosystem
=======================
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



