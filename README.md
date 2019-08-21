# Project Title : Migrate RESTful web services from Struts to Spring

##### **Primary Mentor  :** Daniela Butano
##### **Backup Mentor   :** Julie Sullivan
##### **Student         :** Prabodh Kotasthane
##### [**Project wiki here.**](https://wiki.openmrs.org/display/projects/OAuth+module+enhancements+and+SMART+apps+support)

##### Source Code and Downloads 
+ *Source Code for OpenMRS OAuth2 Module :* [https://github.com/openmrs/openmrs-module-oauth2/tree/gsoc-18](https://github.com/openmrs/openmrs-module-oauth2/tree/gsoc-18)
+ *Source Code for SMART OWA :* [https://github.com/PKatGITHUB/openmrs-owa-smartowa](https://github.com/PKatGITHUB/openmrs-owa-smartowa)
+ *Download OpenMRS OAuth2 Module 2.0 .omod file :* [https://github.com/PKatGITHUB/GSoC-2018-Final-Evaluations/blob/master/oauth2-2.0.omod](https://github.com/PKatGITHUB/GSoC-2018-Final-Evaluations/blob/master/oauth2-2.0.omod)
+ *Download SMART OWA .zip bundle :* [https://github.com/PKatGITHUB/GSoC-2018-Final-Evaluations/blob/master/smartowa.zip](https://github.com/PKatGITHUB/GSoC-2018-Final-Evaluations/blob/master/smartowa.zip)

#### Major Objectives 
* **Registration of SMART clients/application RESTfully**
* **Integration of SMART's EHR Launch Flow**
* **Functionality of Scopes and Launch Context**

#### Extra Credit 
* **Open Web Application supporting SMART**

#### Project Overview 
The main objective of this project was to enhance the OpenMRS OAuth2 Module by extending the support for SMART's EHR launch flow. Also making sure that the module works fine with the OpenMRS reference  application. Adding support for various scopes and launch context was another major task. Finally as a cherry on top, an OWA was made in order to make the EHR launch sequence more user friendly and for easy registration of SMART clients using manifest file. 

##### Registration of SMART clients/application RESTfully
+ In order to be able to run SMART apps from the EHR, i.e. OpenMRS, user is first needed to register the respective SMART application/client. A SMART client is no different than a normal OAuth client except that it must have a Launch Url which is the SMART app launch url to which the browser would redirect when the user attempts to run SMART apps. This objective involved adding the required new tables for the SMART application, also adding the respective DAOs and Services. The functionality to register and modify a SMART application  was added by modifying the existing REST controllers to manage OAuth Clients.

##### Integration of SMART's EHR Launch Flow
+ The EHR launch flow of SMART apps is properly integrated within the module. Now a user may see the list of registered SMART application and is able to run them from within OpenMRS. Whenever the user hits "Run", a random launch value is generated and saved in the database, and passed to the SMART application. The application, at the time of requesting authorization, sends back the launch value which is verified to ensure that the SMART app ran in same session. This objective also involved changing the metadata controller so as it gives the metadata response in proper conformance statement format as the SMART apps require.

##### Functionality of Scopes and Launch Context
+ The support for patient and user specific scopes was added. Also say, if some application is launched requests patient specific scopes, then the token response must involve the patient id of current patient in context. This was done by adding a custom token enhancer which modifies the token response and adds the relevant launch context requested by the SMART application. Right now Patient and User specific scopes are supported but this functionality could be extended further to other FHIR resources.

##### Open Web Application supporting SMART
+ After successfully integrating the EHR launch flow and adding the support of OAuth2 Module with the OpenMRS reference application, now it was needed to make an OWA for extending the support of SMART functionality towards the OpenMRS reference application by displaying the OWA on the user dashboard. SMART OWA also supports registration of SMART applications using manifest file upload. This OWA is generated with the help of OpenMRS OWA generator and developed using HTML, CSS and jQuery.

##### Other Objectives
+ One objective of the project was to convert the existing XML-based configuration to java annotation-based configuration. But after a lot of research and possibilities about which one suits better to the module, me and my mentor settled on keeping the XML-based configuration as it is. Reason for this is that the OAuth2 module has multiple http security configuration which uses many common authentication managers. XML-based configuration makes this task easy to represent and understand as compared to the java counterpart. 

+ Talking  about the testing, API layer of the module is well tested. The OMOD layer though remains untested, which I will be completing soon. Also the module is currently based upon Spring Security OAuth2 version 1.x and we thought of migrating it to version 2.x but due to some technical incompatibility we were required to postpone this. I would be looking forward to these two things in near future. 

This was really an awesome project to work upon. This project included changes from the database layer, service layer to the UI layer. Also many new technologies were involved which was challenging and fun part too.

#### Contributions 
##### JIRA Issues I have worked on and respective Pull Requests 
+ **[OA-8](https://issues.openmrs.org/browse/OA-8)** : [https://github.com/openmrs/openmrs-module-oauth2/pull/6](https://github.com/openmrs/openmrs-module-oauth2/pull/6)
+ **[OA-9](https://issues.openmrs.org/browse/OA-9)** : [https://github.com/openmrs/openmrs-module-oauth2/pull/7](https://github.com/openmrs/openmrs-module-oauth2/pull/7)
+ **[OA-10](https://issues.openmrs.org/browse/OA-10)** : [https://github.com/openmrs/openmrs-module-oauth2/pull/8](https://github.com/openmrs/openmrs-module-oauth2/pull/8)
+ **[OA-11](https://issues.openmrs.org/browse/OA-11)** and **[OA-12](https://issues.openmrs.org/browse/OA-12)** : [https://github.com/openmrs/openmrs-module-oauth2/pull/11](https://github.com/openmrs/openmrs-module-oauth2/pull/11)
+ **[OA-13](https://issues.openmrs.org/browse/OA-13)** : [https://github.com/openmrs/openmrs-module-oauth2/pull/12](https://github.com/openmrs/openmrs-module-oauth2/pull/12)
+ **[OA-14](https://issues.openmrs.org/browse/OA-14)** : [https://github.com/openmrs/openmrs-module-oauth2/pull/13](https://github.com/openmrs/openmrs-module-oauth2/pull/13)
+ **[OA-15](https://issues.openmrs.org/browse/OA-15)** : [https://github.com/openmrs/openmrs-module-oauth2/pull/14](https://github.com/openmrs/openmrs-module-oauth2/pull/14) and [https://github.com/openmrs/openmrs-module-oauth2/pull/15](https://github.com/openmrs/openmrs-module-oauth2/pull/15)
+ **[OA-17](https://issues.openmrs.org/browse/OA-17)** : [https://github.com/openmrs/openmrs-module-oauth2/pull/16](https://github.com/openmrs/openmrs-module-oauth2/pull/16)
+ **[OA-18](https://issues.openmrs.org/browse/OA-18)** : [https://github.com/openmrs/openmrs-module-oauth2/pull/17](https://github.com/openmrs/openmrs-module-oauth2/pull/17)

#### Resources and Demo Presentations

##### [Community Project Talk thread here.](https://talk.openmrs.org/t/gsoc-2018-oauth-module-enhancements-and-smart-apps-support-project/18012)
##### [OAuth2 Module documentation here.](https://wiki.openmrs.org/display/projects/OpenMRS+-+OAuth2+Module)
##### [Weekly Blog Posts here.](https://prabodhgsoc2018.wordpress.com/)

##### My mid-term presentation video 
<a href="https://www.youtube.com/watch?v=DqZ5ufwvCZs" target="_blank"><img src="http://img.youtube.com/vi/DqZ5ufwvCZs/0.jpg" 
alt="GSoC-2018 Mid Term Presentation" width="240" height="180" border="10" /></a>

##### Demo of SMART OWA 
<a href="https://www.youtube.com/watch?v=v8zonYOZMjM" target="_blank"><img src="http://img.youtube.com/vi/v8zonYOZMjM/0.jpg" 
alt="Demo of SMART OWA" width="240" height="180" border="10" /></a>
#### Thoughts on GSoC
>This past summer was the most awesome experience for me. Google Summer of Code with OpenMRS was the most challenging and fun filled coding experience I have ever had. OpenMRS community has been a beautiful community. Everyone here always have a "ready to help!" attitude which makes working very comfortable here. My mentors did helped me a lot whenever I was stuck. Everyday through the summer I had something new, something challenging to do which would push me to do my best and to explore and learn new things. GSoC gave me the exposure to work with such big code base and dynamic tech stack which was really a great experience. Overall, GSoC with OpenMRS made me more confident and helped me in developing technical, communication and managerial skills. Kudos to whole OpenMRS community and GSoC!
