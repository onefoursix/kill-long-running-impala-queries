kill-long-running-impala-queries
====================

This project provides an example of using Cloudera Manager's Python API Client to list and/or kill Impala queries that have been running longer than a user-defined time duration. It may be useful in shops if there are times when poorly formed queries run for too long, consuming too many cluster resources

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

The second argument <code>KILL</code> is optional.
Without this argument, a list of queries that are identified as running too long will be printed to the console, but no queries will be killed. 
If the argument <code>KILL</code> is provided, a cancel command will be issued for each query identified as running tool long. 
See [here](http://www.cloudera.com/content/www/en-us/documentation/enterprise/latest/topics/cm_dg_impala_queries.html) for info on cancelling Impala queries.

CM versions <= 5.4 require Full Administrator role to cancel Impala queries 

Set the CM URL, Cluster Name, login and password in the settings below

This script assumes there is only a single Impala service per cluster

Here is an example with an artificially low query running time (60 seconds) used just as a demonstration:

Listing queries that have run for more than 60 seconds:

$ ./killLongRunningImpalaQueries.py  30

<code>Connecting to Cloudera Manager at toronto.onefoursix.com:7180
Located Impala Service: impala
Looking for Impala queries running more than 30 seconds
-- long running queries -------------
queryState : CREATED
queryId: 4d420cb99e73ce11:a9e6c682a4543596
user: mark
startTime: 2015-11-07 23:25:17 
Query running time (seconds): 154
statement: select * from ratings
-------------------------------------
queryState : CREATED
queryId: 624f2fbd95631f24:de221acfa5af4395
user: mark
startTime: 2015-11-07 23:26:41 
Query running time (seconds): 70
statement: select * from ratings
-------------------------------------
done<code>



Killing queries that have run for more than 60 seconds:







