# MATSHOME
MATSHOME is an app that serves as a landing page for all the MATS apps that are deployed to a specific namespace.

This chart requires the pre-allocation of a Persistent Volume Claim with minimum 10GB of storage space.
 
1. MATSMONGO
1. MATSHOME and
1. A set of MATSAPPs 

are all deployed into the same namespace. 

This Persistent Volume Claim will be shared among all the above.

