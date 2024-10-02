[Home - AD180](/README.md#exercises)

<!-- Exercise 0: Getting Started -->
# Getting Started

## Introduction

1. The screenshots in this document have been taken using group ID **`000`** and system **`AI1`**. We **do not recommend** using group ID **`000`**. 

2. Please note that ADT dialogs and views, as well as Fiori UIs, may change in future releases.

3. You can find a solution for this workshop in the development package **`ZRAP120_SOL`**, or you can import it from [here](https://github.com/SAP-samples/abap-platform-rap120/) into your system.  

4. You've already received user credentials (_read Login Details below_) from the SAP Team  **or** created an account on the SAP BTP ABAP environment Trial.

    > ⚠ Regarding SAP-led events:        
    > Participants of SAP-led events (e.g. **ABAP Developer Day** or **SAP CodeJam**) will receive logon details - i.e. system information and user credentials - to a dedicated ABAP system from the SAP team via e-mail prior to the event or during the respective event.  
    > Please inform the workshop instructor if you haven't received your login details.

**Now, let's get started!**

<!--
Table of Content:
- [Group ID](#group-id)
- [Create an _ABAP Cloud Project_ in ADT](#create-an-abap-cloud-project-in-adt)
- [Helpful Information](#helpful-information)
  - Find/Replace
  - Modern ABAP Syntax
  - Useful ADT Shortcuts
- [First exercise](#first-exercise)
-->

## Suffix / Group ID 
[^Top of page](#)

> Define a suffix (sometimes called _Group ID_) that you will need throughout this workshop.
> 
> ⚠️ Skip this step if you've already been assigned a group ID by the SAP team.  

  You will use the suffix to replace all occurrences of the placeholder **`###`** in the various exercises to uniquely identify your repository artefacts and separate them from those of other users completing the same workshop on this system.
 
  Your suffix must be a **maximum of 3 characters (numbers and/or letters)** - e.g. `123`, `XY1`, or `ABC`. **Do not use** `000` or `XXX` as these are reserved suffixes.
     

## Create an ABAP Cloud Project in ADT

> In this step, you will create an **ABAP Cloud Project** in your ADT installation to establish a connection to the relevant *SAP BTP ABAP Environment* system.
> 
> ⚠️ Skip this step if you've already created an _ABAP Cloud Project_.

<details>
  <summary>🔵Click to expand!</summary>
   
1. Open the **ABAP** perspective if you have not already done so.

    ![Open ABAP Perspective](images/abap_perspective.png)

2. Now create the **ABAP Cloud Project** as shown on the screenshots provided below.       

    ![Create ABAP Project Cloud 1/2](images/abap_cloud_project01.png)

    ![Create ABAP Project Cloud 2/2](images/abap_cloud_project02.png)

</details>


## Helpful Information
[^Top of page](#)

> This section contains some helpful information for the exercises: _Find/Replace_ functionality, modern ABAP syntax, and useful ADT shortcuts.

<details>
  <summary>🔵Click to expand!</summary>
 
### Find/Replace

In the course of these exercises you will frequently see the task to "_replace the placeholder **`###`** with chosen or assigned suffix". 

For this it's recommended to make use of the **Find/Replace** feature of the Eclipse Editor. It can be opened either via the menu (**_Edit -> Find/Replace..._**) or via **Ctrl+F**.
  
 ![find and replace](images/find01.png)
   
Choosing **Replace All** allows you to replace all ocurrences of **`###`** with your group ID.

  
### Modern ABAP Syntax

The modern, declarative, and expression-oriented ABAP language syntax will be used in the different exercises. It allows developers to write more simple and concise source code using new language features like inline declarations, constructor expressions.

> **Find more information in the ABAP Keyword Documentation**: [ABAP - Programming Language](https://help.sap.com/doc/abapdocu_cp_index_htm/CLOUD/en-US/index.htm?file=abenabap_reference.htm) 

  
### Useful ADT Shortcuts

Here are some useful ADT keyboard shortcuts for the ABAP development in Eclipse.

![ADT Shortcuts](images/adt_shortcuts.png)

More useful ADT shortcuts can be found here: [Link](https://blogs.sap.com/2013/11/21/useful-keyboard-shortcuts-for-abap-in-eclipse/).

> **Info**: You can display the full list of available shortcuts in the **Show Key Assit** in ADT by pressing **Ctrl+Shift+L**.
 
</details>


## First exercise
[^Top of page](#)

You can begin with the first exercise of one of the execise groups A and B:
- **Exercise Block A: Building Draft-enabled, Transactional SAP Fiori Apps with Business Events**      
  ► **[Exercise 1: Generate a transactional OData UI Service E2E with GenAI and RAP](../ex01/README.md)**. 
  
- **Exercise Block B: Displaying Hierachical Data in SAP Fiori UI using read-only Treeview**  
  ► **[Exercise 4: Generate a read-only OData UI Service with GenAI](../ex04/README.md)**. 

## License

Copyright (c) 2024 SAP SE or an SAP affiliate company. All rights reserved. This project is licensed under the Apache Software License, version 2.0 except as noted otherwise in the [LICENSE](LICENSES/Apache-2.0.txt) file.
