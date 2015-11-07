kill-long-running-impala-queries
====================

This project provides an example of using Cloudera Manager's Python API Client to create a Flume Service and Flume Agents, to set and update Flume Agent config files, and to restart Flume Agent processes. Along the way it also shows the use of Cloudera Manager's user roles

More information:  [Flume](http://archive.cloudera.com/cdh5/cdh/5/flume-ng/FlumeUserGuide.html),  [Cloudera Manager](http://www.cloudera.com/content/cloudera/en/products-and-services/cloudera-enterprise/cloudera-manager.html), [CM API Client](http://cloudera.github.io/cm_api/)




####Requirements
- Cloudera Manager 5.2 or higher (I tested with CM 5.4.7)  
- CDH 5.2 or higher (I tested with CDH 5.4.7)
- A configured HDFS Service.
- Python (I tested on CentOS 6.6 which includes Python 2.6.6)
- Python setuptools (see below)
- The correct version of the CM API (see below)
- A CM login with at least "Cluster Administrator" role to create a Flume Service
- A CM login with at least "Cluster Administrator" role to add Agents to a Flume Service 
- A CM login with at least "Configurator" role to deploy an Agent's config file
- A CM login with at least "Operator" role to start or restart Agent(s)


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
