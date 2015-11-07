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

At the time of this writing, the current version of CM is 5.4.7 and I will install version 10 of the CM API

I've listed below the steps I used on CentOS 6.6 to install the current version (v10) of the Pythin CM API Client for use with CM 5.4.x  (docs are [here](http://cloudera.github.io/cm_api/docs/python-client/)) 

Steps to install the Python CM API Client:

1) Use a browser to go to [https://github.com/cloudera/cm_api](https://github.com/cloudera/cm_api)

2) Use the dropdown to pick the branch you need. For example, I will use the branch for CM5.4:

![](images/github.jpg)

3) Once the right branch is selected, right-click on the "Download ZIP" button and select "Copy Link Address":

![](images/github-2.jpg)

In my case for the CM5.4 API (which is the current version at the time of this writing) the link is: 

	https://github.com/cloudera/cm_api/archive/cm5-5.4.zip

If you need an older version, for example, the CM5.2 version, the download link would be:

	https://github.com/cloudera/cm_api/archive/cm5-5.2.zip
