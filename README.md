# Project Title: Migrate RESTful web services from Struts to Spring

##### **Primary Mentor:** Daniela Butano
##### **Backup Mentor:** Julie Sullivan
##### **Student:** Prabodh Kotasthane
##### [**Project idea here.**](http://intermine.org/gsoc/project-ideas/2019/#migrate-restful-web-services-from-struts-to-spring)

##### Source Code and Downloads 
+ *Source Code for InterMine Web-services Spring Boot Module :* [InterMine Web Services](https://github.com/PKatGITHUB/intermine/tree/ws-spring/intermine/webservices) 
+ *Source Code for Bio Web-services :* [Bio Web Services](https://github.com/PKatGITHUB/intermine/tree/ws-spring/bio/webservices)
+ *Swagger Specifications for InterMine and Bio Web-services :* [Swagger Specifications](https://github.com/PKatGITHUB/intermine-ws-spring-swagger)

#### Major Objectives 
* **Migrate the web-services from Struts (Http servlet-service architecture) to Spring**
* **Well documented APIs using OpenAPI Specifications**
* **Functional and unit testing**

#### Extra Credit 
* **Add the APIs to SmartAPI project**

#### Project Overview 
InterMine integrates biological data sources, making it easy to query and analyse data. Presently InterMine uses Struts framework which is outdated. InterMine provides RESTful web-services which facilitates to execute custom or templated queries, search keywords, manage lists, discover metadata, perform enrichment statistics and manage user profiles. The main objective of this project was to migrate the web-services from Struts (Http service-service architecture) to Spring framework and document the APIs with Swagger in compliance with OpenAPI Specifications. OpenAPI specifications are easy to write and Swagger Codegen, which supports Spring, makes the job of developer easy by generating the code stubs which can be modified to render the services. Also Swagger UI provides an interactive documentation which also provides the test calls facility to quickly test-run APIs in your browser only. InterMine currently contains the web application and the web-services bundled under a single module “webapp”. InterMine team is now able to split the webapp module into three modules namely webapp, webservices and webcore. The migration of the webapp was not the part of this project.

##### Migrate the web-services from Struts (Http servlet-service architecture) to Spring
* Previously the webapp module contained both, the InterMine web application and the web-services. The pre-requirement for this project was to split the webapp into three modules namely webapp, webservices and webcore. This pre-requirement was successfully fulfilled by InterMine team and we had independent webservices module which specifically provide the InterMine web-services.
The Implementation plan to migrate the web-services is as follows:
  * The mappings of all the web-services to their respective Servlets were present in the Web.xml file of the webservices module. These mappings also defined and described the metadata about the web-service. I used this data to write Swagger/OpenAPI Specifications.
  * I used Swagger Codegen to generate code stubs. Various API interfaces, controllers, model classes and integrated test classes were generated.
  * I migrated the previous struts based webservices module to a Spring Boot module. Then integrated the code stubs generated above with this project ensuring that there are no errors.
  * Next I migrated the business logic for the API. This was, according to me, the trickiest part of the migration flow. The service classes were then changed to return the model objects which eliminited the need of many classes such as Output and Writer classes.
  * Finally we can deploy the web services and test them live on the swagger-ui. The above steps were followed for all the webservices to migrate them.

##### Well documented APIs using OpenAPI Specifications
+ The documentation of all the APIs written using the OpenAPI specifications lies within the code, linked to the API interfaces. Swagger helps us in doing this. User can easily have a look at the web service documentation through the Swagger UI. Also, the  OpenAP spacifications for both, [InterMine](https://github.com/PKatGITHUB/intermine-ws-spring-swagger/blob/master/InterMine_OpenAPI_Specifications.json) and [Bio webservices](https://github.com/PKatGITHUB/intermine-ws-spring-swagger/blob/master/Bio_OpenAPI_Specifications.json), is present in respective files.  

##### Functional and unit testing
+ Functional testing can be done with the help of swagger-ui. All the web services are tested and running fine. However, unit testing of web services is still pending due to lack of time as I felt there were a bit too much of web services. This would probably be done soon.

##### Add the APIs to SmartAPI project
+ This was a bonus deliverable, which was supposed to be done if some extra time is left. Unfortunately, due to lack of time, some discussions are still pending regarding this. Hopefully, I will be able to complete this task soon. 

This was really an awesome project to work upon. This project included development of large API layer consisting of a lot of different types of functional endpoints, which challenged my coding and time management skills. Also, I learnt many new technologies, like Swagger and Spring Boot, which was challenging and fun part too.

#### Contributions 
##### All the [commits](https://github.com/PKatGITHUB/intermine/commits/ws-spring): 
+ **[Added webservices-spring module.](https://github.com/PKatGITHUB/intermine/commit/259227030f7a5dda9996ef840b584cf2e6d6ea03)**
+ **[Added test model service.](https://github.com/PKatGITHUB/intermine/commit/d46649ea382f8fee560320000752cce6e04a7a78)**
+ **[Updated build.gradle and Removed struts-config.xml and web.xml .](https://github.com/PKatGITHUB/intermine/commit/c5c7483e298809ccb4a8e7cd6b7bd19a53a40447)**
+ **[Shifted to webservice Project.](https://github.com/PKatGITHUB/intermine/commit/97f49e30610d60d5ea2f5ed3b85f7bc43903ef93)**
+ **[Migrated /model endpoint.](https://github.com/PKatGITHUB/intermine/commit/308a25a41686548aec7df0b844d70edd34175a93)**
+ **[Migrated /version service. Removed webservices-spring project. Removed agentIsRobot() and checkEnabled(). Removed HttpServletResponse dependency.](https://github.com/PKatGITHUB/intermine/commit/82ec2a39d79969f78732b36af44ef0f8442b7182)**
+ **[Migrated /summaryfields service.](https://github.com/PKatGITHUB/intermine/commit/4aa0b2ceff4b465ca27637d6942bf4b7052a18d5)**
+ **[Migrated /classkeys and /branding services.](https://github.com/PKatGITHUB/intermine/commit/11973a6c17e93f4f1902334cede5de64ceaf5034)**
+ **[Migrated /schema service.](https://github.com/PKatGITHUB/intermine/commit/88733240dd400130bdc000d1b1c6b9b729af8e8b)**
+ **[Migrated /facet-list, /session and /web-properties services.](https://github.com/PKatGITHUB/intermine/commit/ae28ef191fc35f5465cec5833a92dd3d22d1ef33)**
+ **[Migrated /templates/system and /semantic-markup/datacatalog services.](https://github.com/PKatGITHUB/intermine/commit/86e2ad43d3d0e788fc000a0a38a172b314339a39)**
+ **[Migrated /facets and /users service.](https://github.com/PKatGITHUB/intermine/commit/c584457af1fc4dd7578ea555929e66f6d6e111fd)**
+ **[Setting up correct response headers and loading the web.properties properly.](https://github.com/PKatGITHUB/intermine/commit/3e4bd26dc21614e1236420d9a413d1316b8e1537)**
+ **[Migrated /semantic-markup/dataset, /semantic-markup/bioentity, /permanent-url, /sequence, /query/code, /search and /data/{type}. Changes related to setting up correct headers.](https://github.com/PKatGITHUB/intermine/commit/6df1b24a40dfa22a971751b6f1fb2c83e8d564b0)**
+ **[Issue of 406 Error resolved.](https://github.com/PKatGITHUB/intermine/commit/753b105ecb4b9f558b88ed3a101ac5b2ec9ffa37)**
+ **[Code review changes. Removed unwanted code.](https://github.com/PKatGITHUB/intermine/commit/e55503c438b6d35dd878259fdf14bc40b037d77b)**
+ **[Refactored models. Added JSONModel and InterMineController. Moved setFooter to InterMineController.](https://github.com/PKatGITHUB/intermine/commit/f4062c7d52c373389b390e023462676bf8141379)**
+ **[Removed setFooter() and sendError() dependecy from WebServiceSpring class.](https://github.com/PKatGITHUB/intermine/commit/17ea084ccf3141993c70e1222db2c3b3be6c3c75)**
+ **[Moved setHeaders to InterMineController and injected format into to the services.](https://github.com/PKatGITHUB/intermine/commit/aee604840b5f60e2f01296bd74840fdcb7db3d2b)**
+ **[Migrated /user/whoami service.](https://github.com/PKatGITHUB/intermine/commit/3bdf80307fbcccad79f6694d30fccfe97f9e3cc7)**
+ **[Migrated /user/token endpoint.](https://github.com/PKatGITHUB/intermine/commit/fc0fd284d3bdb6f442264aaabb9114ccb331393c)**
+ **[Added initController() method.](https://github.com/PKatGITHUB/intermine/commit/65be574d42399155bc722be7ff47aa83ac03af14)**
+ **[Solved swagger authorization issue. Migrated /templates endpoint.](https://github.com/PKatGITHUB/intermine/commit/06917467be8124d7e74147993c559c3d52bf9750)**
+ **[Migrated /template/upload service.](https://github.com/PKatGITHUB/intermine/commit/591aaa361cb5326a0c04d0b9de270aa3dc9eba43)**
+ **[Migrated /user/deregistration/service.](https://github.com/PKatGITHUB/intermine/commit/aeae7b2d658e77dbef23ffdae891fa7d03fa8455)**
+ **[Migrated /user service.](https://github.com/PKatGITHUB/intermine/commit/7398567751caabc1eba970db9a55ec4581639a4c)**
+ **[Migrated /user/preferences service.](https://github.com/PKatGITHUB/intermine/commit/c9570c1e577fcbba77d8dd301fcdd793b6725cf7)**
+ **[Migrated /user/tokens, /user/tokens/{uid}, /templates/{name} and /template/tags services.](https://github.com/PKatGITHUB/intermine/commit/2c251a5114dc294a3c0f50f4a3711b5c923d82b5)**
+ **[Migrated /lists, /lists/append, /lists/rename and /list/tags endpoints.](https://github.com/PKatGITHUB/intermine/commit/efda1df5c4a394f6c7f68ea0cd2546a572e1d783)**
+ **[Migrated /lists/union, /lists/subtract, /lists/intersect and /lists/difference endpoints.](https://github.com/PKatGITHUB/intermine/commit/f501ad7c7b7068f39b0a5cf4dd2218732847c245)**
+ **[Migrated /widgets, /queries, /query/results, /listswithobjects and /lists/jaccard-index endpoints.](https://github.com/PKatGITHUB/intermine/commit/a872cf68dbf4dcbe531ce7698cf701cc26426389)**
+ **[Migrated /lists/shares and /lists/invitations endpoints.](https://github.com/PKatGITHUB/intermine/commit/e7ec8d097c5b7e71832a51549a6eed7d3cbe0bd0)**
+ **[Migrated /user/queries/{name}, /user/queries, /query/upload, /ids/* and /path/values endpoints.](https://github.com/PKatGITHUB/intermine/commit/d3ef64f5ba87447f7eb8c44577df9ddbdb1014e5)**
+ **[Migrated /query/tolist, /query/append/tolist, /template/results, /template/tolist and /template/append/tolist endpoints.](https://github.com/PKatGITHUB/intermine/commit/475fca02471c4eab1a127e01c98a6f57774d2d7a)**
+ **[Added tags for better grouping of web services.](https://github.com/PKatGITHUB/intermine/commit/7263d937ac4d55f98f5ae12e3785bd27e782a832)**
+ **[Migrated /list/chart, /list/table and /list/enrichment endpoints.](https://github.com/PKatGITHUB/intermine/commit/cbd4061083dd1f50619929d974ec2d6a475e3e3a)**
+ **[Changes related to some output format issues.](https://github.com/PKatGITHUB/intermine/commit/ba8ba1d76cc5e957e6022e3188fa331210e2a48b)**
+ **[Support for bio webservices. Bio webservices swagger added.](https://github.com/PKatGITHUB/intermine/commit/2217a274e9998e9bea4c90ad94cb1061b914dd94)**
+ **[Migrated all bio webservices.](https://github.com/PKatGITHUB/intermine/commit/7d4bea98b866ba3330e10c922ff7a9654b10b86d)**
+ **[Migrated JBrowse endpoints.](https://github.com/PKatGITHUB/intermine/commit/fa5bf72da9739757f434af9a693b5ed8a9601c89)**

#### Resources and Demo Presentations

##### [Community presentation for GSoC 2019.](https://intermineorg.wordpress.com/2019/08/15/call-recording-available-gsoc-2019-final-presentations/)
##### [My presentation slides.](https://docs.google.com/presentation/d/16fAWfx1IlK9_orVGKg0bcgT576ecY13BWWf8TnKiV0Q/edit?usp=sharing)
##### [Initial blog post on GSoC 2019.](https://prabodhk.wordpress.com/2019/04/18/gsoc-2019-new-year-new-organisation-new-enthusiasm/)

#### Thoughts on GSoC
>This past summer was again a great experience for me following the last edition of GSoC. Google Summer of Code with InterMine was an amaing coding and time management experience for me. InterMine community is awesome. People here are always excited and available to help. My mentors did help me promptly whenever needed. This edition of GSoC tested my time management and coding skills as the project was a bit lengthy one. I had new challenges every week which were needed to be resolved quickly. GSoC 2019 agian gave me the exposure to work with a big code base and various different technologies which was really a great experience. Overall, GSoC with InterMine made me more confident and helped me in developing technical, communication and managerial skills. Kudos to whole InterMine community and GSoC!
