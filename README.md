## Introduction

Mosaicme is a [Microservice](http://en.wikipedia.org/wiki/Microservices "Microservices") application that retrieves images from selected Twitter feeds, stores them on an [object store](http://en.wikipedia.org/wiki/Object_storage "Object Store"), and then it process them to build a mosaic based on a selected set of pictures. 

Mosaicme's goal is to provide developers with an example of how to build a distributed microservice application using Linux containers. It focuses on current best practices, showcases the use of Object stores,  the use of multiple [APIs](http://en.wikipedia.org/wiki/Application_programming_interface "APIs") ([REST](http://en.wikipedia.org/wiki/Representational_state_transfer "REST"), [S3](http://en.wikipedia.org/wiki/Amazon_S3 "AWS S3"), [SWIFT](http://en.wikipedia.org/wiki/OpenStack#Swift "OpenStack Swift"), [HDFS](http://en.wikipedia.org/wiki/Apache_Hadoop#HDFS "Haddop Distributed File System"), and [Twilio](https://www.twilio.com/ "Twilio.com")), and automated deployment models.


[Architecture Diagram goes here]



## Use Cases


The following section provides an overview of the Use Cases for Mosaicme. There are two main actors for this application  only one actor for this application, the end-user:

 
Use Case	                          | Description
------------------------------------- | -----------|
Retrieve images from Twitter accounts | Mosaicme retrieves images from the selected list of Twitter accounts and stores them in the Object store.
Process a mosaic from selected pictures | It will build a mosaic from a picture using the stored pictures. The resulting mosaic is then stored in the Object store.
Mosaic "My" picture					  | Mosaicme creates a mosaic based on the picture provided by the user.
Post Mosaic to Twitter Account		  | Mosaicme will post a mosaic to a selected Twitter account(s) on a regular interval. This can be configured via the Configuration Section.
Display list Pictures				  | Shows the list of pictures currently stored in the system.
Display list Mosaics				  | Shows the list of mosaics currently stored in the system.
SMS "My" Mosaic						  | Using Twilio Services, the System will SMS you the selected Mosaic. This can be done via the Web Interface or by the user send it an SMS with the picture ID.
Configure Mosaicme 					  | Enables administrator to configure the system via a web interface.
Mosaicme statistics                   | Generates a list of statistics based on usage, storage, and images. meta data.			



## Architecture 

Mosaicme is composed of multiple tiers. The following design shows the high level application architecture: 

[Architecture Model image]

The following has an overview of each one of the components

Component Name              |	Component Description
--------------------------- | ---------------------|
Web Interface               | Web Interface to for displaying pictures, mosaics, statistics and system configuration. 
Orchestration API service   | API service that orchestrates interactions with all services in the application. 
Mosaic processing service   | Mosaic processing service. Takes the mosaic generation request from the Orchestration API and generates the mosaic data and meta data.
Statistics Service			| Haddop Cluster that takes the data in the Object Store and processes the statistics. Stores the data back to the Object store using HDFS.
Queuing Service				| Service to host the queues required by the system.
Caching Service             | Data caching service to speed the application.
Configuration Service       | Service to maintain configuration, synchronization and naming registry.
Log Routing Service		    | Service to route all services logs to the Object Store.
Twitter retrieval service   | Service that retrieves pictures and their meta data from the selected twitter accounts and adds them Object store.


### Component 1 

Introduction 

**[Image of Component 1]**

Description



### Component 2 

Introduction 

**[Image of Component 2]**

Description
   

### Component 3 

Introduction 

**[Image of Component 3]**

Description
   



## References

[1] Reference 1
 
[2] Reference 2 

[3] Reference 3

