# AD180 - Build SAP Fiori Apps with ABAP Cloud powered by Joule's ABAP Developer capabilities

## Description

This repository contains the material for the SAP TechEd 2024 session called **AD180 - Build SAP Fiori Apps with ABAP Cloud powered by Joule's ABAP Developer capabilities**.

## Overview
[^Top of page](#)

This session introduces attendees to the Joule's ABAP Developer capabilities that support the fast development of transactional, draft-enabled SAP Fiori elements apps as well as read-only SAP Fiori elements apps with ABAP Cloud. Attendees will also learn how to use the _ABAP RESTful Application Programming Model_ (RAP) to define and raise business events that can be consumed locally or remotely via SAP Event Mesh for loosely coupled integration scenarios. A simple event handler class will also be implemented for the local consumption of business events.

ABAP Cloud is the development model for building clean core compliant apps, services, and extensions on SAP S/4HANA Cloud, SAP S/4HANA, and SAP BTP ABAP Environment. ABAP Cloud covers different development scenarios such as transactional, analytical, intgeration, and enterprise search scenarios. The ABAP RESTful Application Programming Model (RAP) ist at the heart of ABAP Cloud for building transactional SAP Fiori apps, OData-based Web API, local APIs, and business events.

## Requirements
[^Top of page](#)

The requirements to follow the exercises in this repository are the installation of the latest version of the ABAP Development Tools for Eclipse (ADT) installation 
on your laptop or PC and the access to a suitable ABAP system with a connection to the GenAI Hub, i.e. SAP BTP ABAP Environment with the connection to the [SAP AI Core](https://discovery-center.cloud.sap/serviceCatalog/sap-ai-core). The appropriate flavor of the [ABAP Flight Reference Scenario](https://github.com/SAP-samples/abap-platform-refscen-flight) (package `/DMO/FLIGHT`) must be imported into the relevant system. 

The requirements to follow the exercises in this repository are:
1. [Install the latest Eclipse platform and the latest ABAP Development Tools (ADT) plugin](https://developers.sap.com/tutorials/abap-install-adt.html)
2. Access to an SAP BTP ABAP Environment system that is connected to SAP AI Core
   > ℹ️ **Info for SAP TechEd Virtual 2024**:   
   > During the virtual event, the exercises can be completed on the _SAP BTP ABAP Environment Trial_ that will be connected to the SAP AI Core.
   > → [Create an user on the SAP BTP ABAP Environment Trial](https://developers.sap.com/tutorials/abap-environment-trial-onboarding.html)      

4. [Create an ABAP Cloud Project](https://developers.sap.com/tutorials/abap-environment-create-abap-cloud-project.html)
5. [Adapt the Web Browser settings in your ADT installation](https://github.com/SAP-samples/abap-platform-rap-workshops/blob/main/requirements_rap_workshops.md#4-adapt-the-web-browser-settings-in-your-adt-installation)   

## Exercises
[^Top of page](#)

### 🛠Exercise Group A: Building Transactional, Draft-enabled SAP Fiori Apps with Business Events

Learn to build a transactional, draft-enabled SAP Fiori app with the ABAP RESTful Application Programming Model (RAP) powered by Joule's ABAP Developer capabilities, define and raise business events for loosely coupled scenarios.

| Exercise Group A | -- |
| ------------- |  -- |
| [Getting Started](exercises/ex0/README.md) | -- |
| [Exercise 1: Generate a transactional OData UI Service E2E with Joule's ABAP Developer capabilities](exercises/ex01/README.md) | -- |
| [Exercise 2: Enhance the RAP BO behavior with a business event](exercises/ex02/README.md) | -- |
| [Exercise 3: Play around with the AI-based ADT Wizard](exercises/ex03/README.md) | -- |


### 🛠Exercise Group B: Displaying hierachical data in SAP Fiori UI using read-only treeview

Learn to build a read-only SAP Fiori app with ABAP Cloud assisted by Joule's ABAP Developer capabilities and display hierachical data in a read-only treeview.

> ℹ️ **Note**: This is a standalone exercise that can be carried out independently of the previous exercise group (A).   
> In case you start with this block then please begin with [Getting Started](exercises/ex0/README.md). 

| Exercise Group B | -- |
| ------------- |  -- |
| [Exercise 4: Generate a read-only OData UI service with Joule's ABAP Developer capabilities](exercises/ex04/README.md) | -- |
| [Exercise 5: Implement the read-only treeview for hierachical data display](exercises/ex05/README.md) | -- |


### 🛠Exercise Group C: Create and deploy a SAP Fiori elements app with SAP BAS (_optional_)

Create a productive SAP Fiori elements List Report app with the SAP Business Application Studio (SAP BAS) on top of an OData service built with the ABAP RESTful Application Programming Model (RAP) and deploy it into the SAP BTP ABAP Environment system. 

> ℹ️ **Note**: This exercise can be completed immediately after Exercise Group A and Exercise Group B.

| Exercise Group C | -- |
| ------------- |  -- |
| [Exercise 6: Create an SAP Fiori elements app with SAP Business Application Studio and deploy it to the SAP BTP ABAP Environment](https://developers.sap.com/tutorials/abap-environment-deploy-fiori-elements-ui.html) (_Tutorial in the SAP Developer Center_)| -- |


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

## License
Copyright (c) 2024 SAP SE or an SAP affiliate company. All rights reserved. This project is licensed under the Apache Software License, version 2.0 except as noted otherwise in the [LICENSE](LICENSES/Apache-2.0.txt) file.
