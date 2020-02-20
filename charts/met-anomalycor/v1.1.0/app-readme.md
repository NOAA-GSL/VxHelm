# met-anomalycor
met-anomalycor is an app that that performs data visualization for meteorological forecast verification data. 

This chart requires the pre-allocation of a Persistent Volume Claim with minimum 10GB of storage space that will contain the specific database credentials and settings for the specific app.
This Persistent Volume Claim should exist in a specific namespace that is dedicated to 
1. a collection of these apps
1. a mongo database
1. a MATSHOME app which is an app home/landing page.

The Persistent Volume Claim will provide persistence for all of the above.

The deployment of MATSHOME and MATSMONGO is a prerequisite for the deployment of any MATSAPPS.

Only one of each type of app should be deployed into a single namespace.

The chart is intended to be deployed into a specific namespace in a [Rancher](https://rancher.com/) environment.

