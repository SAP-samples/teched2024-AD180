[![REUSE status](https://api.reuse.software/badge/github.com/SAP-samples/teched2024-AD180)](https://api.reuse.software/info/github.com/SAP-samples/teched2024-AD180)

# AD180 - Build SAP Fiori Apps with ABAP Cloud powered by Joule's ABAP developer capabilities

## Description

This repository contains the material for the SAP TechEd 2024 session called **AD180 - Build SAP Fiori Apps with ABAP Cloud powered by Joule's ABAP developer capabilities**.

>> **DISCLAIMER**:   
>> Please note that the GenAi capabilities used in this hands-on workshop are part of a beta release.   
>> This workshop and SAP's strategy and possible future developments are subject to change and may be changed by SAP at any time for any reason without notice. 

- [Requirements for attending this workshop](#requirements-for-attending-this-workshop)
- [Overview](#overview)
- [Presentation & Replay](#recording)
- [Exercises](#exercises)
- [How to obtain support](#how-to-obtain-support) 
- [Further Information](#further-information)

## Overview
[^Top of page](#)

ABAP Cloud is the development model for building clean core compliant apps, services, and extensions on SAP S/4HANA Cloud, SAP S/4HANA, and SAP BTP ABAP Environment. ABAP Cloud covers different development scenarios such as transactional, analytical, intgeration, and enterprise search scenarios. The ABAP RESTful Application Programming Model (RAP) ist at the heart of ABAP Cloud for building transactional SAP Fiori apps, OData-based Web API, local APIs, and business events.

This jump-start session introduces attendees to the Joule's ABAP developer capabilities that support rapid development of both transactional and read-only SAP Fiori elements-based apps with ABAP Cloud. Attendees will also learn how to display data in hierarchical treeview in SAP Fiori apps and how to use ABAP Cloud to define and raise business events that can be consumed locally or remotely via SAP Event Mesh for loosely coupled integration scenarios. 

## Requirements for attending this workshop
[^Top of page](#)

> The prerequisites for following the exercises in this repository are the installation of the latest version of the ABAP Development Tools for Eclipse (ADT)
on your laptop or PC and the access to a suitable ABAP system (i.e. SAP BTP ABAP Environment) connected to the [SAP AI Core](https://discovery-center.cloud.sap/serviceCatalog/sap-ai-core). In addition, the appropriate flavor of the [ABAP Flight Reference Scenario](https://github.com/SAP-samples/abap-platform-refscen-flight) (package `/DMO/FLIGHT`) must be imported into the system. 

Before completing the exercises in this repository, you need to:

1. [Install the latest Eclipse platform and the latest ABAP Development Tools (ADT) plugin](https://developers.sap.com/tutorials/abap-install-adt.html)
2. [Create an user on the SAP BTP ABAP Environment Trial](https://developers.sap.com/tutorials/abap-environment-trial-onboarding.html)
   > ℹ️ **Note**: The _SAP BTP ABAP Environment_ trial will be connected to the SAP AI Core from 8 to 11 October for SAP TechEd Virtual 2024.
3. [Create an ABAP Cloud Project](https://developers.sap.com/tutorials/abap-environment-create-abap-cloud-project.html)
4. Adapt the Web Browser settings in your ADT installation:   
    i) Choose _Window_ > _Preferences_ in the menu bar.   
    ii) Navigate to _General_ > _Web Browser_.  
    iii) Activate the radio button _Use external web browser_.   
    iv) Select one of the listed external web browsers that are available, e.g. _Default system web browser_.    
        ❗Make sure that _Internet Explorer_ is not selected.   

<!--   
## Overview
[^Top of page](#)

 🔗[Access the presentation](url)
-->

## Presentation & Replay

* Watch the live jump-start session on 📅 Tuesday, Oct 8 | 🕐 7:30 PM - 7:55 PM CEST (10:30 AM – 10:55 AM PDT)    
  [AD180 | Build SAP Fiori Apps with ABAP Cloud powered by Joule's ABAP developer capabilities](https://www.sap.com/events/teched/virtual/flow/sap/te24/catalog/page/catalog/session/1722394882075001dE44)    
  
* Access the presentation: 📄[AD180@SAPTechEd2024.pdf (extended version)](/exercises/images/AD180@SAPTechEd2024.pdf)

## Exercises
[^Top of page](#)

### 🛠Exercise Block A: Building Transactional, Draft-enabled SAP Fiori Apps with Business Events

> In this exercise block, you will learn how to build a **transactional**, draft-enabled SAP Fiori app from scratch using RAP powered by Joule's ABAP developer capabilities to manage _agency_ data. You will then learn how to define and raise business events for loosely coupled integration scenarios. Finally, you will learn how to implement an event handler for the local consumption of the RAP business events directly on the application server.

<details>
   <summary>Resulting SAP Fiori app 01: Manage Agencies > Click to expand!</summary>
     <img src="exercises/images/fioriapp01.png" alt="create package" width="100%">
</details>  

| Exercise Block A | -- |
| ------------- |  -- |
| [Getting Started](exercises/ex0/README.md) | -- |
| [Exercise 1: Generate a transactional OData UI Service E2E with Joule's ABAP Developer capabilities](exercises/ex01/README.md) | -- |
| [Exercise 2: Enhance the RAP BO behavior with a business event and consume it locally](exercises/ex02/README.md) | -- |
| [Exercise 3: Play around with the AI-based ADT Wizard](exercises/ex03/README.md) | -- |


### 🛠Exercise Block B: Displaying hierachical data in SAP Fiori UI using read-only treeview

> In this exercise block, you will learn how to build a **read-only** SAP Fiori app using ABAP Cloud assisted by the Joule's ABAP developer capabilities to display _employee_ data. You will then learn how to define and display hierarchical data in a read-only treeview in an SAP Fiori app.
> 
> ℹ️ **Note**: This is a standalone exercise block that can be completed independently of the previous exercise block (A). In case you are starting with this exercise block, then please start with [Getting Started](exercises/ex0/README.md). 

<details>
  <summary>Resulting SAP Fiori app 02: Display Employee > Click to expand!</summary>  
    <img src="exercises/images/fioriapp02.png" alt="create package" width="100%">
</details>  


| Exercise Block B | -- |
| ------------- |  -- |
| [Exercise 4: Generate a read-only OData UI service with Joule's ABAP Developer capabilities](exercises/ex04/README.md) | -- |
| [Exercise 5: Implement the read-only treeview for hierachical data display](exercises/ex05/README.md) | -- |


### 🛠 Optional Exercise: Create and deploy a SAP Fiori elements app with SAP Build Code

> To create, deploy, and run the actual SAP Fiori elements-based _Manage Agency_ or _Manage Employee_ app using SAP Build COde (especially the _SAP Business Application Studio_), follow the instructions provided in the tutorial below.    
> The _SAP Fiori elements App Preview_ integrated in ADT is only used to preview of the resulting app as the name indicates. 

<!-- > ℹ️ **Note**: This exercise can be completed immediately after Exercise Block A and Exercise Block B, which are independent exercises blocks. -->

[Exercise 6: Create and deploy an SAP Fiori app to the SAP BTP ABAP Environment with SAP Business Application Studio | SAP Tutorials](https://developers.sap.com/tutorials/abap-environment-deploy-fiori-elements-ui.html)

## Known Issues
[^Top of page](#)

No known Issue.

## Contributing
[^Top of page](#)

Please read the [CONTRIBUTING.md](./CONTRIBUTING.md) to understand the contribution guidelines.

## Code of Conduct
[^Top of page](#)

Please read the [SAP Open Source Code of Conduct](https://github.com/SAP-samples/.github/blob/main/CODE_OF_CONDUCT.md).

## How to obtain support
[^Top of page](#)

Support for the content in this repository is available during the actual time of the online session for which this content has been designed. Otherwise, you may request support via the [Issues](../../issues) tab.

## Further Information
[^Top of page](#)

 - [ABAP RESTful Application Programming Model (RAP)](https://community.sap.com/topics/abap/rap) | SAP Community page   
 - [Modernization with RAP](https://blogs.sap.com/2021/10/18/modernization-with-rap/) | SAP Blogs
 - [ABAP Cloud Roadmap Information](https://help.sap.com/docs/abap-cross-product/roadmap-info/ui-services) | SAP Help Portal
 - [Explore the interactive SAP BTP ABAP Environment road map](https://roadmaps.sap.com/board?range=CURRENT-LAST&PRODUCT=6EAE8B28C5D91EDA9FF40F3CC2DBE0E6&PRODUCT=73555000100800001164) | SAP Road Map Explorer
 - [RAP100 Tutorials Mission on SAP Developers Center](https://developers.sap.com/mission.sap-fiori-abap-rap100.html) | SAP Tutorials
 - [Create an SAP Fiori elements app with SAP Business Application Studio and deploy it to the SAP BTP ABAP Environment](https://developers.sap.com/tutorials/abap-environment-deploy-fiori-elements-ui.html) | SAP Tutorials
 - 
## License
Copyright (c) 2024 SAP SE or an SAP affiliate company. All rights reserved. This project is licensed under the Apache Software License, version 2.0 except as noted otherwise in the [LICENSE](LICENSES/Apache-2.0.txt) file.
