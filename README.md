kill-long-running-impala-queries
====================

This project provides an example of using Cloudera Manager's Python API Client to list and/or kill Impala queries that have been running longer than a user-defined time duration

Info on the CM API is [here](http://cloudera.github.io/cm_api/)

####Requirements
- Cloudera Manager 5.2 or higher (I tested with CM 5.4.8)  
- CDH 5.2 or higher (I tested with CDH 5.4.8)
- The version of the CM API that matches your CM version
- A CM login with "Cluster Administrator" role is required to kill Impala queries

####Install the Cloudera Manager API 
Download the version of the CM API that matches the version of Cloudera Manager you are using. Consult the chart [here](http://cloudera.github.io/cm_api/docs/releases/) to see what version of the the API you will need to install

####Usage: 
    ./killLongRunningImpalaQueries.py  queryRunningSeconds [KILL]

Set <code>queryRunningSeconds</code> to the threshold considered "too long" for an Impala query to run, so that queries that have been running longer than that will be identifed as queries to be killed

The second argument "KILL" is optional
Without this argument, no queries will actually be killed, instead a list of queries that are identified as running too long will just be printed to the console
If the argument "KILL" is provided a cancel command will be issues for each selcted query 

CM versions <= 5.4 require Full Administrator role to cancel Impala queries 

Set the CM URL, Cluster Name, login and password in the settings below

This script assumes there is only a single Impala service per cluster
