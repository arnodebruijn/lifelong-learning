Pentaho
=======

Web-based Components
--------------------
* Analyzer              helps you visualize data to make informed business decisions.
* Interactive Reports   desing interface to create operational reports
* Dashboard Desinger    create visual dashboards


Design tools
------------
* PDI (Pentaho Data Integration)    provides access to an ETL engine
* Report Designer                   generate reports
* Aggregation Designer              interface to create aggregate tables to improve the performance of OLAP cubes

Other tools
-----------
* Pan             Commandline tool for executing transformations
* Kitchen         Commandline tool for executing jobs (? can also export repository objects into XML format)

Spoon (PDI client)
-----
Spoon is the graphical transformation and job designer associated with the Pentaho Data Integration suite — also known as the Kettle project.
* transformations - describe the data flows for ETL
* jobs - coordinate ETL activities such as:
  - defining the flow and dependencies for what order transformations should be run
  - preparing for execution by checking conditions
  - performing bulk load database operations
  - file management
  - sending success or fail notifications

Pentaho user console (webbrowser)
---------------------------------
A web-based design environment where you can analyze data, create interactive reports, dashboard reports, and build integrated dashboards. Also offers a wide variety of system administration features for configuring the Pentaho Server.

Artifacts
---------
.kjb    (kettle) job files
.ktr    (kettle) transformation files
.cda    parameter description files


Likes
=====
* Easy and fast way to connect different data sources
* Open source


Dislikes
========
* Buggy interface
  - repository connection lost after suspend without visible warning or error 
  - repository login flakey
* Tutorial full of errors
* Definitely doesn't make debugging easier
* Community support
* Documentation
? We still use external systems like cron jobs


Uncertain
=========
* What happens if some feature is not supported
* limitations of the comunity edition


Installation
============
sudo add-apt-repository ppa:webupd8team/java
sudo apt update
sudo apt-get install oracle-java8-installer
sudo apt-get install oracle-java8-set-default
sudo apt-get install libwebkitgtk-1.0-0
