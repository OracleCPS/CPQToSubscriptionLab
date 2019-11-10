
# LAB 2: CPQ CLOUD TO SUBSCRIPTION MANAGEMENT CLOUD INTEGRATION TEST

![Homepage](Images/image1.png)


## BACKGROUND

This document outlines a step-by-step guide on how to import Oracle Integration Cloud (OIC) artifacts from Oracle Cloud Marketplace into an OIC environment, and create web service connections between CPQ Cloud and Subscription Mangement Cloud. This lab will focus on how to create subscriptions and terminate subscriptions in CPQ, and have those changes reflected in Subscripton Managment Cloud.

The business scenario is to allow sales teams to capture subscription orders and perform subscription management activities throughout the lifecycle of these customer relationships. The integration, enabled by Oracle’s next generation Oracle Integration Cloud middleware, comes with a Subscription Management package that includes installable artifacts for both CPQ Cloud and OIC.

<p>&nbsp;</p>

## COMPONENTS COVERED

* How to download integration artifacts from Oracle Cloud Marketplace
* How to import integration artifacts into OIC
* How to update web service connections
* How to activate integrations
* How to create subscriptions through CPQ Cloud
* How to terminate subscriptions through CPQ Cloud

<p>&nbsp;</p>

## APPLICATIONS USED

* Oracle Integration Cloud (OIC)
* CPQ Cloud
* Subscription Management Cloud (OSS)
<p>&nbsp;</p>

## 1.1 IMPORT INTEGRATION ARTIFACTS FROM ORACLE CLOUD MARKETPLACE

#### 1.1.1: Click <a href="https://cloudmarketplace.oracle.com/marketplace/en_US/adf.task-flow?adf.tfDoc=%2FWEB-INF%2Ftaskflow%2Fadhtf.xml&adf.tfId=adhtf&application_id=53214800&tabName=O" target="blank"> HERE</a> to got to Oracle Cloud Marketplace.

You should get redirected to a prebuilt Oracle CPQ Cloud to Oracle Subscription Cloud app.

<p>&nbsp;</p>

#### 1.1.2: Click on Get App
![Homepage](Images/image2.png)

<p>&nbsp;</p>

#### 1.1.3: Review and accept the Oracle Standard Terms and Restrictons, and click Next
![Homepage](Images/image3.png)

<p>&nbsp;</p>

#### 1.1.4: Scroll to the Details section of the page, click on the "End to End Flow" Integration .jar file from the CPQ- OSS Integration Artifacts table </b>
The OIC Integration for End-to-End Flow contains the integrations for the create subscription, modify subscription, renew subscription, and terminate subscription workflows. This lab will focus on create and terminate.

![Homepage](Images/image4.png)

#### 1.1.5: Save your downloaded .jar file in a directory on your local machine </b>

<p>&nbsp;</p>
<p>&nbsp;</p>


## 1.2: IMPORT INTEGRATION ARTIFACT INTO OIC 

#### 1.2.1: Go to Oracle Integration Cloud home page:
OIC URL: <em>https://oictraining3-oicpm.integration.ocp.oraclecloud.com/ic/home/</em>
<p>&nbsp;</p>

![Homepage](Images/image5.png)
<p>&nbsp;</p>

#### 1.2.2: Log in using the same credentials you used for Lab 1 <br/>

<strong>OIC User Name</strong>: OICTraining3ic[User Number] <br/>
Your OIC Password will be provided by your lab facilitator.
<p>&nbsp;</p>

#### 1.2.3: After logging in, select Integrations from the left side menu of the OIC home page <br/>
![Homepage](Images/image5.1.png)
<p>&nbsp;</p>

#### 1.2.4: Click on Integrations again from the left hand side menu, and click on Import from the top right.
![Homepage](Images/image6.png)
<p>&nbsp;</p>

#### 1.2.5: Click on Browse from the Import Integration dialogue box and select the END2ENDINTEGRATION_19A .jar file. Click on Import. <br/>
![Homepage](Images/image7.png)
<p>&nbsp;</p>

#### 1.2.6: Your integration is now imported successfully. <br/>
![Homepage](Images/image8.png)



<p>&nbsp;</p>
<p>&nbsp;</p>

## 1.3: CONFIGURE CPQ CLOUD AND SUBSCRIPTION MANAGEMENT CLOUD CONNECTIONS IN OIC 

### 1.3.1: CONFIGURE CPQ CLOUD CONNECTION

#### 1.3.2: Click on Connections from the left side menu under Designer
![Homepage](Images/image8.png)
<p>&nbsp;</p>

#### 1.3.3: Search for the CPQ connection in the search box. In this case, "CPQ-055"
![Homepage](Images/image9.png)
<p>&nbsp;</p>

#### 1.3.4: Select the CPQ-055 connector. When the connection is displayed, click on the hamburger menu and select Edit
![Homepage](Images/image10.png)
<p>&nbsp;</p>

#### 1.3.5: Click on Configure Connectivity
![Homepage](Images/image11.png)
<p>&nbsp;</p>

#### 1.3.6: Make sure SOAP WSDL URL is selected under Connection Type. For Connection URL, copy and paste the WSDL URL below. 
<p>&nbsp;</p>

Connection URL: https://cpq-20263.bigmachines.com/v2_0/receiver/commerce/oraclecpqo?WSDL

![Homepage](Images/image12.png)
<p>&nbsp;</p>

#### 1.3.7: Click on Save from the top right
<p>&nbsp;</p>

#### 1.3.8: Click on Configure Security
![Homepage](Images/image13.png)
<p>&nbsp;</p>

#### 1.3.9: Provide credentials to access your CPQ application, and click OK
![Homepage](Images/image14.png)
<p>&nbsp;</p>

#### 1.3.10: Click on Save from the right top corner, and click Save again from the Save Changes dialogue box. Close the "saved successfully" notification box
![Homepage](Images/image15.png)
<p>&nbsp;</p>

#### 1.3.11: Click on Test from the top right
![Homepage](Images/image16.png)
<p>&nbsp;</p>

#### 1.3.12: Make sure the connection tests successfully and reflects 100%. Close the green notification box.
![Homepage](Images/image17.png)
<p>&nbsp;</p>

#### 1.3.13: Click Save from the top right. click Save again from the Save Changes dialogue box, 
![Homepage](Images/image17.1.png)
<p>&nbsp;</p>

#### 1.3.14: Click Close from the top right
![Homepage](Images/image18.png)
<p>&nbsp;</p>

#### 1.3.15: Your CPQ connection is now active
![Homepage](Images/image19.png)

<p>&nbsp;</p>
<p>&nbsp;</p>

## 1.4: CONFIGURE REST CONNECTION for SUBSCRIPTION MANAGEMENT CLOUD

In this lab, we're going to use a REST adapter to connect to Subscripton Management Cloud.

#### 1.4.1: Search the REST connection in the search box. In this case, "OSS_REST_CONN"
![Homepage](Images/image20.png)
<p>&nbsp;</p>

#### 1.4.2: Select the OSS_REST_CONN connector. When the connection is displayed, click on the hamburger menu and select Edit
![Homepage](Images/image21.png)
<p>&nbsp;</p>

#### 1.4.3: Click on Configure Connectivity 
![Homepage](Images/image22.png)
<p>&nbsp;</p>

#### 1.4.4: Make sure REST API Base URL is selected under Connection Type. Provide your REST URL for Connection URL, and click OK. REST URL will be provided by lab facilitator. 
![Homepage](Images/image23.png)
<p>&nbsp;</p>

#### 1.4.5: Click on Save from the top right

#### 1.4.6: Click on Configure Security
![Homepage](Images/image24.png)
<p>&nbsp;</p>

#### 1.4.7: Provide credentials to access your Subscription Management Cloud application, and click OK
![Homepage](Images/image25.png)
<p>&nbsp;</p>

#### 1.4.8: Click on Save from the right top corner, and click Save again from the Save Changes dialogue box. Close the "saved successfully" notification box

#### 1.4.9: Click on Test from the top right

#### 1.4.10: Make sure the connection tests successfully and reflects 100%. Close the green notification box
![Homepage](Images/image26.png)

#### 1.4.11: Click Save from the top right. click Save again from the Save Changes dialogue box

#### 1.4.12: Click Close from the top right
![Homepage](Images/image27.png)
<p>&nbsp;</p>

#### 1.4.13: Your REST connection is now active
![Homepage](Images/image28.png)

<p>&nbsp;</p>
<p>&nbsp;</p>


## 1.5: ACTIVATE INTEGRATION

#### 1.5.1: Select Integrations from the left side menu
![Homepage](Images/image29.png)
<p>&nbsp;</p>

#### 1.5.2: Find the End2EndIntegration-19A. Hover over the integration and click on the power switch
![Homepage](Images/image30.png)
<p>&nbsp;</p>

#### 1.5.3: From the Activation Integration dialogue box, select Enable Tracing and Include Payload
![Homepage](Images/image30.png)
<p>&nbsp;</p>

#### 1.5.4: Click on Activate
![Homepage](Images/image31.png)


## 1.6: CLONE INTEGRATION

#### 1.6.1: Hover over the activated integration, and select the hamburger menu. Select Clone from the action items list
![Homepage](Images/image32.png)
<p>&nbsp;</p>

#### 1.6.2: Rename the integration as follows: "User [insert user number] End2Endintegration". Click Clone.
![Homepage](Images/image33.png)
<p>&nbsp;</p>

#### 1.6.3: Hover over your cloned integration and click on the power switch
![Homepage](Images/image34.png)
<p>&nbsp;</p>

#### 1.6.4: From the Activation Integration dialogue box, select Enable Tracing and Include Payload. Click on Activate
![Homepage](Images/image35.png)


<p>&nbsp;</p>
<p>&nbsp;</p>

## 1.7: CREATE A SUBSCRIPTION IN SUBSCRIPTION MANGEMENT CLOUD

#### 1.7.1: Go to Subscription Management Cloud home page:
OSS URL: <em>https://adc3-zids-login.oracledemos.com</em>
<p>&nbsp;</p>

![Homepage](Images/image36.png)
<p>&nbsp;</p>

#### 1.7.2: Log in using the same credentials you used for Lab 1 <br/>

Your OSS login credientals will be provided by your lab facilitator.
<p>&nbsp;</p>

#### 1.7.3: Click on the home icon <br/>
![Homepage](Images/image37.png)
<p>&nbsp;</p>

#### 1.7.4: Under Sales Cloud, select Opportunities <br/>
![Homepage](Images/image38.png)
<p>&nbsp;</p>

#### 1.7.5: Click on Create Opportunity from the top right <br/>
![Homepage](Images/image39.png)
<p>&nbsp;</p>

#### 1.7.6: Insert Opportunity Name. "FIT 5000 Purchase User [user name]". <br/>
Account: New Start Gyms <br/>
Primary Contact: Lisa Lauber <br/>
<p>&nbsp;</p>

Click Save and Close <br/>

![Homepage](Images/image40.png)

#### 1.7.7: Select the opportunity you created from the Opportunities list <br/>
![Homepage](Images/image41.png)
<p>&nbsp;</p>

#### 1.7.8: Select Quotes and Order from the Left hand side menu <br/>
![Homepage](Images/image42.png)
<p>&nbsp;</p>

#### 1.7.9: Click on Create Quote from the top right <br/>
<p>&nbsp;</p>

![Homepage](Images/image43.png)

<p>&nbsp;</p>

This will now redirect you to the embedded CPQ application.

<p>&nbsp;</p>

#### 1.7.10: Under Line Item Details, click on Add <br/>
![Homepage](Images/image44.png)
<p>&nbsp;</p>

#### 1.7.11: Select Supremo Fitness, and choose VR Cardio from the products list <br/>
![Homepage](Images/image44.1.png)
<p>&nbsp;</p>

#### 1.7.12: Click on product FIT5000 <br/>
![Homepage](Images/image45.png)
<p>&nbsp;</p>

#### 1.7.13: Under the Subscription Services drop down, select cCoach-12month. Select Yearly from the Monitoring drop down, and click Update from the top right <br/>
![Homepage](Images/image46.png)
<p>&nbsp;</p>

#### 1.7.14: Click Add to Transaction <br/>
![Homepage](Images/image47.png)
<p>&nbsp;</p>

#### 1.7.15: Your product is now added to the quote. Click Save <br/>
![Homepage](Images/image48.png)
<p>&nbsp;</p>

#### 1.7.16: Click Submit <br/>
![Homepage](Images/image49.png)
<p>&nbsp;</p>

#### 1.7.17: Click Submit Order <br/>

Make sure to note down the Transaction Number!

![Homepage](Images/image50.png)
<p>&nbsp;</p>

#### 1.7.18: Click Return to Sales Cloud <br/>
![Homepage](Images/image50.1.png)
<p>&nbsp;</p>

#### 1.7.18: Click Save and Close <br/>
![Homepage](Images/image68.png)

<p>&nbsp;</p>
<p>&nbsp;</p>

## 1.8: CHECK CREATE SUBSCRIPTION INTEGRATION WORK FLOW

#### 1.8.1: Go to the OIC Home Page. Select Monitoring from the left side menu <br/>
![Homepage](Images/image51.png)
<p>&nbsp;</p>

#### 1.8.2: Click Integrations <br/>
![Homepage](Images/image52.png)
<p>&nbsp;</p>

#### 1.8.3: Click Tracking <br/>
![Homepage](Images/image53.png)
<p>&nbsp;</p>


#### 1.8.4: Find you integration, and click on the Id number <br/>
![Homepage](Images/image54.png)
<p>&nbsp;</p>

#### 1.8.5: Understand and explain the Create Subscription integration flow <br/>
![Homepage](Images/image55.png)
<p>&nbsp;</p>
<p>&nbsp;</p>

## 1.9: CHECK CREATED SUBSCRIPTION IN SUBSCRIPTION CLOUD
<p>&nbsp;</p>

#### 1.9.1: Return to Subscription Cloud Home Page <br/>
![Homepage](Images/image55.1.png)
<p>&nbsp;</p>

#### 1.9.2: Click on the hamburger menu from the top left <br/>
![Homepage](Images/image69.png)
<p>&nbsp;</p>

#### 1.9.3: Click Subscription Management from the list <br/>
![Homepage](Images/image70.png)
<p>&nbsp;</p>

#### 1.9.4: Enter your quote Transaction Number to find your subscription, and search <br/>
![Homepage](Images/image71.png)
<p>&nbsp;</p>

#### 1.9.5: You now see your product, and your subscription listed in Subscription <br/>
![Homepage](Images/image72.png)
<p>&nbsp;</p>
<p>&nbsp;</p>

## 1.20: TERMINATE SUBSCRIPTON

#### 1.20.1: In Subscription Managment Cloud, click on the hamburger menu on the top left <br/>
![Homepage](Images/image73.png)
<p>&nbsp;</p>

#### 1.20.2: Under Sales Cloud, select Opportunities <br/> 
![Homepage](Images/image74.png)
<p>&nbsp;</p>

#### 1.20.3: Search and select the opportunity you created in the Find field<br/> 
![Homepage](Images/image75.png)
<p>&nbsp;</p>

#### 1.20.4: Click Quotes and Order from the left side menu<br/>
![Homepage](Images/image76.png)
<p>&nbsp;</p>

#### 1.20.5: Click on Create Quote <br/>
![Homepage](Images/image77.png)
<p>&nbsp;</p>

#### 1.20.6: Change the year in Start Contract Date and End Contract Date to reflect the screen shot below, and click Save <br/>
![Homepage](Images/image78.png)
<p>&nbsp;</p>

#### 1.20.7: Click Customer Assets <br/>
![Homepage](Images/image79.png)
<p>&nbsp;</p>

#### 1.20.8: Double on the Date Added arrow to find the product you recently subscribed to <br/>
![Homepage](Images/image80.png)
<p>&nbsp;</p>

#### 1.20.9: Select your product <br/>
![Homepage](Images/image81.png)
<p>&nbsp;</p>

#### 1.20.10: Click Terminate <br/>
![Homepage](Images/image82.png)
<p>&nbsp;</p>

#### 1.20.11: Click Terminate <br/>
Under Line Item Details, if you scroll all the way to the right, you'll notice that the Action Code for the subscription now reflects Terminate.
![Homepage](Images/image83.png)
<p>&nbsp;</p>

#### 1.20.12: Click Submit <br/>
![Homepage](Images/image84.png)
<p>&nbsp;</p>

#### 1.20.13: Click Submit Order <br/>
![Homepage](Images/image85.png)
<p>&nbsp;</p>

#### 1.20.14: Click Return to Sales Order <br/>
![Homepage](Images/image86.png)
<p>&nbsp;</p>

#### 1.20.15: Click Save and Close <br/>
![Homepage](Images/image87.png)
<p>&nbsp;</p>
<p>&nbsp;</p>

## 1.21: CHECK TERMINATED SUBSCRIPTON IN SUBSCRIPTION MANGEMENT CLOUD

#### 1.21.1: Click on the hamburger menu from the top left <br/>
![Homepage](Images/image89.png)
<p>&nbsp;</p>

#### 1.21.2: Select Subscription Management from the list <br/>
![Homepage](Images/image70.png)
<p>&nbsp;</p>

#### 1.21.3: Enter your orginal Transaction Number to find your subscription, and search <br/>
![Homepage](Images/image90.png)
<p>&nbsp;</p>

#### 1.21.4: You now see your your subscription is closed <br/>
![Homepage](Images/image91.png)
<p>&nbsp;</p>


## 1.22: CHECK TERMINATE SUBSCRIPTION INTEGRATION WORK FLOW

#### 1.8.1: Go to the OIC Home Page. Select Monitoring from the left side menu <br/>
![Homepage](Images/image51.png)
<p>&nbsp;</p>

#### 1.8.2: Click Integrations <br/>
![Homepage](Images/image52.png)
<p>&nbsp;</p>

#### 1.8.3: Click Tracking <br/>
![Homepage](Images/image53.png)
<p>&nbsp;</p>


#### 1.8.4: Find you integration, and click on the Id number <br/>
![Homepage](Images/image54.png)
<p>&nbsp;</p>

#### 1.8.5: Understand and explain the terminate subscription integration flow <br/>
![Homepage](Images/image93.png)
<p>&nbsp;</p>
<p>&nbsp;</p>

You have now completed this lab.