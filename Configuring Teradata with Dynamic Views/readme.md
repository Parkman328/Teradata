![logo](./media/image1.png)

# **_Configuring Teradata 17.00 with Dynamic Views_**

## **Partner Engineering**

<br>  
<br>
<br>
<br>

John Park  
Principal Solution Architect  
john.park@qlik.com  
![TDLogo](./media/image2.png)  

**Version: 1.0**  
**Initial Release Date: 7-May-20**
**Revisions**      | **Notes**   | **Date**  | **Version**
------------------ | ----------- | --------- | -----------
Initial Draft      | 12-May-2020 | John Park | 1.0       |


# Table of Contents

--------------------

[**Summary**](#summary)  

[**Part 1 - Checklist - PreConfiguration**](#part-1)

[**Part 2 - Creating Source Connection**](#part-2)

[**Part 3 - Creating Target Connections**](#part-3)

[**Part 4 - Testing and Additional Information**](#part-4)

## **Summary**

This document was created to supplement Qlik Sense Documentation and Teradata 17.00 Release Documentation from Following Pages

- <https://docs.teradata.com/>
- <https://help.qlik.com/en-US/sense>

Teradata is MPP Database that is supported by Qlik Replicate, Qlik Sense and QlikView 

For This testing and guide we are using Qlik Sense April 2020 and (TTU) Teradata Tools and Utilities 17.00

## **Part 1**

### Checklist - PreConfiguration

First, we need to set up have a Teradata Database Instance stood up and able to be reached.
For this documentation we tested against installed versions of Teradata 17, 16.2 and 16.1.

On your Windows or Linux box makes sure you have installed TTU and following components
  
- ODBC Driver for Teradata

***Figure A.1.0.***  
TTUList Screen Capture  
![TTUList](./media/image3.jpeg) 

**Install Qlik Sense and make sure ODBC Connection can be created** 

## **Part 2**

### Creating Source Connection

Now we need to create an Create Qlik Source Connection for Teradata with appropriate settings.

**Configure Teradata as a source in Data Connection Manager for Qlik Sense.**

## **Part 3**

### Creating App with Dynamic Views Connection

Now we need to create an Create Qlik Sense App with Teradata Connection for Teradata with appropriate settings.

**Configure Teradata as a source in Connection Manager for Attunity.**

Click "Manage Endpoint Connections" and following window should popup.

***Figure A.3.0.***  
Confirm Target Connection  
![Confirm Target Connections](./media/image12.jpeg)  

Select "Target" as role and "Teradata" as Type.

Enter Credentials for *Teradata Server*, *Username*, *Password*

**Do not Click "Browse" on *"Default Database"* now (We will Do that after Internal Parameters are set).**

Click  on **“Advanced”** on Top Menu Bar and it should bring Internal Parameter Window

Add Internal Driver for Teradata as Override. If you type keyword "driver" in the prompt is should allow you to click on the variable and add a value.  

***Figure A.3.1.***  
Add Internal Parameters  
![Add Internal Parameters](./media/image13.jpeg)  

***Following Setting were used for testing.***  

- Parameter: provider  
- Value: Teradata Database ODBC Driver 17.00

View setting summary to make sure **"provider"** variable is used to override drivers setting for Target End Point.  


***Figure A.3.2.***  
View Setting Summary  
![View Setting Summary](./media/image14.jpeg)  

Qlik Replicate uses TPT Operator with Attribute which can be tweaked based on environment requirements.

***Figure A.3.3.***  
View TPT Settings  
![View Settings](./media/image15.jpeg)  

***Press **"Browse"** button select Default database for Replicate and **"Test Connection"** button and Verify Connectivity.***

***Figure A.3.3.***  
Finalize Target Endpoint Settings  
![Target Endpoint](./media/image11.jpeg)  
## **Part 4**

### Testing and Additional Information

If you fail in any of these steps please use the ODBC Manager built in with your os and test connections to your Teradata Server.

For Specific Qlik Replicate functions please follow replicate guidelines to setup and test CDC Tasks.

Additional information can be found in help documentation in [**Summary**](#summary).

For Testing Method Please contact your Qlik or Teradata Representatives for support from Professional services teams.

Othen Information can be found in [Qlik Community Technology Partners](https://community.qlik.com/t5/Technology-Partners-Ecosystem/ct-p/qlik-ecosystem "Qlik Technology Partner Eco System") in Technology Partner Sections where users can post questions and get them answered