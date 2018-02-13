# Microservices Example

This repository is an example of how to get Microservices and Single Page application going using AngularJS, Spring Boot, Spring Cloud, Spring OAuth 2 and Netflix OSS frameworks.

**Application Components**

The application consists of 7 different services:

spring-cloud-eureka-server - Eureka server<br/>
auth-pase-server - Oauth2 authorization server<br/>
zuul.gateway.app - API gateway that proxies all the micro-services<br/>
com.main.ux - Single page application main UX service<br/>
com.allowedvalue.ux -  UX service<br/>
com.allowedvalue.service -  service<br/>
com.allowedvalue.db -  DB service<br/>

<br/>
**Technology Stack**
  <br/>
  
![TS](https://github.csc.com/storage/user/23/files/640da842-5def-11e6-94dc-1630650308e2)
  
  <br/>
  <br/>
  **Target Architecture**
  <br/>
  
  ![TA](https://github.csc.com/storage/user/23/files/2bf9d8f6-5de8-11e6-9c92-4adbb3e85adf)
  
   **Application Components**
  
  ![AP](https://github.csc.com/storage/user/23/files/b853cb8a-5de9-11e6-8fcd-c0a319646d9c)

<br/>
<br/>
**Using the application**<br/><br/>
*Running on local m/c*

Note: <br/>
In order to run the application on local machine, we need to start all services (details below). All services runs on different ports. Here, EUREKA server needs to be started first  becuase all other services are EUREKA client(Except ZUUL,Auth server and main UX). For login authorization "auth-pase-server" service must be up and running. For API GATEWAY, "zuul.gateway.app" should be up and running. Rest of the services can be started in any order post the above services mentioned.      

Pre-requisites:<br/>

1. Authentication server and DB service uses mongoDB as database. Pre-requisite is to have mongoDB up and running on local with 27017 port.
2. For dummy access credentials, please hit below URL, it will create one user with username "aaa" and password "aaa". 
   http://localhost:8095/save

Setup Steps - 

1.	Import project("pANextGen") into your work space and check all nested project
2.	Run  “spring-cloud-eureka-server” project  “com.server.main.App.java” as “RunAs - > java application” , it will start your Eureka server
3.	Run  “auth-server-ex” project  “auth.pase.server.ex.App.java” as “RunAs - > java application” , it will start your your auth server
4.	Run “zuul.gateway.app” project  “zuul.gateway.app.App.java” as “RunAs - > java application” , it will start your ZUUL gateway
5.	Rest bundles can be start in any sequesce.
6.	If you want multiple client then make change port in “application.yaml” or "application.properties" and execute step 5.

Testing Steps - 

Please follow the below steps once all services are up and running - 

1. Access the applciation using - http://localhost:8090/
2. It will redirect you to login page 
3. Enter credentials (user-aaa,pwd-aaa)
4. It will redirect you on home page with 2 menus, "Allowed Value" and "Plan"
5. Click on "Allowed Value"
6. It will show data of allowed value from Mongo DB.
 

