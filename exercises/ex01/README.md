[Home - RAP120](/README.md#exercises)

# Exercise 1: Generate transactional OData UI Service E2E with GenAI and RAP

## Introduction

In this exercise, you will create a transactional UI service along with the underlying RAP business object to manage agencies using the GenAI-based ABAP repository object generator (_Beta_) provided in the ABAP Development Tools for Eclipse (ADT). 

You will create an ABAP package, generate all development artefacts using the GenAI-based ADT wizard and a predefined promt with a natural description of the application, and then create am ABAP class to populate demo agency data in the generated database table. The generation will create the required database table, the CDS data model, RAP BO behavior definition, service definition, and service binding. At the end, you will publish and preview your _**Manage Agencies**_ application using the _Fiori Elements App Preview_ function provided in ADT. 

### Exercises

- [1.1 - Create an ABAP Package](#exercise-11-create-an-abap-package)
- [1.2 - Generate OData UI Service using GenAI](#exercise-12-generate-odata-ui-service-using-genai)
- [1.3 - Adjust the Generated UI Service](#exercise-13-adjust-the-generated-ui-service)
- [1.4 - Populate Demo Data](#exercise-14-populate-demo-data)
- [1.5 - Preview the _Agency_ App](#exercise-15-preview-the-agency-app)
- [Summary & Next Exercise](#summary--next-exercise)  


> **Reminder:**   
> Don't forget to replace all occurences of the placeholder **`###`** with your suffix or Group ID in the exercise steps below.   
> You can use the ADT function **Replace All** (**Ctrl+F**) for the purpose.   
> If you haven't been assigned a Group ID, select a combination of three (3) numbers and/or letters, such as e.g. **`000`** or **`AI1`**.  

## Exercise 1.1: Create an ABAP Package
[^Top of page](#)

> Create your exercise package![package](../images/adt_package.png).   
> This ABAP package will contain all the artefacts you will be creating in the different exercises of this hands-on session.

 <details>
  <summary>🔵 Click to expand!</summary>

   1. In ADT, go to the **Project Explorer**, right-click on your ABAP Cloud Project, select **New** > **ABAP Package** from the context menu.
 
      Maintain the required information provided below. Replace all occurrences of the placeholder **`###`** with your chosen or assigned suffix, which should be a combination of three (3) numbers and/or letters, e.g. **`476`** or **`AP3`**.
 
      > ℹ️ The suffix **`000`** is used for the screenshots in this exercise. Use a different suffix.            
 
      - Name: **`ZRAP120_Agency_###`**
      - Description: _**`Manage Agencies App`**_
      - Select the box ✅**Add to favorites package**
      - Superpackage: **`ZLOCAL`**  
 
      Then click **Next >**. 
 
      <table>
      <tr>
          <td><img src="images/p1.png" alt="create package" width="100%"></td>
          <td><img src="images/p2.png" alt="create package" width="100%"></td>
      </tr>
      </table> 
   
   3. Leave the **ABAP Package** screen unchanged and click **Next >**. 
 
      Select or create a transport request, enter a request description if necessary (e.g., _**RAP120 - Manage Agencies App ###**_), and then click **Finish** to complete the package creation.
      
      <table>
      <tr>
          <td><img src="images/p3a.png" alt="create package" width="100%"></td>
          <td><img src="images/p3b.png" alt="create package" width="100%"></td>
          <td><img src="images/p3c.png" alt="create package" width="100%"></td>       
      </tr>
      </table> 

</details>

## Exercise 1.2: Generate OData UI Service using GenAI
[^Top of page](#)

> Generate an OData UI service using the AI-based RAP BO generator (Beta) provided in ADT.

 <details>
  <summary>🔵 Click to expand!</summary>

   1. Right-click on your ![project](../images/adt_project.png)ABAP Cloud project and select **Generate ABAP Repository Objects** from the context menu.
      
      Select the entry **OData UI Service Supported by AI (Beta)** in the wizard and click **Next >**.
      
      Maintain your package name ![package](../images/adt_package.png)**`ZRAP120_Agency_###`** and click **Next >**.                  
 
      <img src="images/p456.png" alt="create package" width="100%">
      
<!--
      <table>
      <tr>
          <td><img src="images/p4.png" alt="generate UI service" width="100%"></td>
          <td><img src="images/p5.png" alt="generate UI service" width="100%"></td>
          <td><img src="images/p6.png" alt="generate UI service" width="100%"></td>
      </tr>
      </table>
-->      

   2. Clear the promt example, insert the prompt provided below for this exercise, and click **Next >**. Do not forget to replace **`###`** with your choosen suffix.
 
      > **Info**: In Exercise 3, you'will have the possibility to play around with the GenAI-based generator and write your own prompt.
      
      ```PROMPT
      Generate an application for managing agencies. 
      The agency entity requires the fields agency_id, agency_name, street, postal_code, city, 
      country_code, phone_number, email_address, and /dmo/web_address.
      Use a numerical data type with length 6 for the field agency_id. 
      country_code is a country key with length 3.
      Use character like data types for the other fields with length 80 for field agency_name, 
      length 60 for field street, length 10 for field postal_code, length 40 for field city, 
      length 30 for field phone_number, length 256 for field email_address, and length 256 for field web_address.
      Create the object names with the suffix '###'.
      ```

      <img src="images/p7.png" alt="generate UI service" width="70%">
 
   3. The generator shows a preview of all artifacts that will be generated. 
 
      > ℹ️ Note: The names of the artifacts, database fields, and other elements in your preview may differ from those shown on the screenshots below or used later in this exercise, as they are generated by GenAI and there is no guarantee from the GenAI side.  
      > The ability to customize the suggestions will be provided with future releases.
 
      <img src="images/p8.png" alt="generate UI service" width="70%">
      
   4. Click **Next >**, select a transport request, and click **Finish** to start the generation of all artifacts. 
 
      The generation of all artifacts may take a few moments.
  
      <!-- <img src="images/p9.png" alt="generate UI service" width="70%"> -->
  
   5. Go to the _**Project Explorer**_ view and check all artifacts that have been generated in your package. You may need to press **F5** to refresh your package.
  
      Then go to your service binding ![service binding](../images/adt_srvb.png)**`ZUI_AGENCY###_O4`** which is opened in the editor and click **Publish** to publish its local service endpoint to view service URL, entity sets, and associations.  
 
      <img src="images/p10.png" alt="generate UI service" width="100%"> 
 
      > **ℹ️ List of the generated objects**:
 
      <details>
        <summary>Click to expand!</summary>

        > **Note**: The names of the artifacts generated in your exercise package may differ from those listed in the table below,
        > because they are generated by GenAI and there is no guarantee from the GenAI side.

        | **Object Category**       | **Repository Object Type**  | **Artefact Names**                                                         |
        |---------------------------|-----------------------------|----------------------------------------------------------------------------|
        | **Business Services**     |                             |                                                                            |
        |                           | **Service Definitions**     | **`ZUI_AGENCY###_O4`**                                                     |
        |                           | **Service Bindings**        | **`ZUI_AGENCY###_O4`**                                                     |
        | **Core Data Services**    |                             |                                                                            |
        |                           | **Behavior Definitions**    | **`ZR_AGENCY###`** - Base BO behavior definition                           |
        |                           |                             | **`ZC_AGENCY###`** - BO behavior projection                                |     
        |                           | **Data Definitions**        | **`ZR_AGENCY###`** - Base BO composition model                             |
        |                           |                             | **`ZC_AGENCY###`** - Projected BO composition model                        |        
        |                           | **Metadata Definitions**    | **`ZC_AGENCY###`** - Metadata extension for the projection view            |
        | **Dictionary**            |                             |                                                                            |
        |                           | **Database Tables**         | **`ZAGENCY###`** - Database table for storing active data                  |
        |                           |                             | **`ZAGENCY###_D`** - Database table for storing draft data                 |
        | **Source Code Library**   |                             |                                                                            |
        |                           | **Classes**                 | **`ZBP_C_AGENCY###`** - Behavior implementation class for the projected BO |
        |                           |                             | **`ZBP_R_AGENCY###`** - Behavior implementation class for the base BO      |

      </details>
       
      The exposed entity **Agency** now appears in the **Entity Set** area. You can directly launch the **Fiori Elements App Preview** in ADT to start the app in the browser or you can proceed to the next exercise to populate the demo data in the application by filling the database table with the _Agency_ demo data.
 
       The preview of the _Manage Agencies_ app is now displayed in the browser without any data.
  
      > ⛔ **Attention** ⛔   
      > **DO NOT** yet create any _**agency**_ records in the app yet, as you'll be adjusting the generated database table definitions in the next step. 
     
      <table>
      <tr>
          <td><img src="images/p11.png" alt="publish UI service" width="100%"></td>
          <td><img src="images/p12.png" alt="publish UI service" width="100%"></td>   
      </tr>
      </table> 

</details>


## Exercise 1.3: Adjust the Generated UI Service
[^Top of page](#)

> Typically, you will need to adjust the generated artifacts to fit your use case. 
> 
> In the present exercise, you will eventually have to adjust the data type of the **agency ID**  in the database tables for active and draft data. 
> The data type of this field should be a numical text with length 6, i.e. **`abap.numc(6)`**. 
> 
> ⚠️ PS: The names of the database tables and fields generated in your exercise package may differ from those used in the description, code snippets, and screenshots below.

 <details>
  <summary>🔵 Click to expand!</summary>

   1. Go to your package in the **Project Explorer**, open the database tabl ![table](../images/adt_table.png)**`ZAGENCY###`** for storing the active _agency_ data and replace the data type of the field **`agency_id`** with **`abap.numc(6)`** if necessary. Then save ![save icon](../images/adt_save.png) and activate ![activate icon](../images/adt_activate.png) the changes.     
 
      Do the same for the database table ![table](../images/adt_tabl.png)**`ZAGENCY###_D`** for storing the draft _agency_ data, and replace the data type of the field **`agency_id`** with **`abap.numc(6)`** if necessary. Then save ![save icon](../images/adt_save.png) and activate ![activate icon](../images/adt_activate.png) the changes. 
 
      ```ABAP
       abap.numc(6); 
      ```       
      
      <img src="images/p13.png" alt="Adjust generated UI service" width="100%">
  
   2. You can also go ahead and, for example, adjust the projected data model by defining value helps in the ![ddls](../images/adt_ddls.png)CDS projection view (`ZC*`), and adjust the UI semantics in the ![ddlx](../images/adt_ddlx.png)CDS metadata extension.
 
      For example, open the the projection view ![ddls](../images/adt_ddls.png)**`ZC_AGENCY###`** and specify the field element **`AgencyId`** as semantic key for the application and also define a value help for the **`AgencyId`**.
     
      Add the view annotation below to specify the field element **`AgencyId`** as semantic key for the application.  
 
      ```ABAP_CDS
       @ObjectModel.semanticKey: ['AgencyId']
      ```         
 
      Now, add the element annotation block below to define an associated text and a value help for the field **`AgencyId`**.
 
      ```ABAP_CDS
       @ObjectModel.text.element: ['AgencyName']
       @Consumption.valueHelpDefinition: [{
             entity : {name: '/DMO/I_Agency_StdVH', element: 'AgencyID'  },
             additionalBinding: [ { localElement: 'AgencyName',  element: 'Name',         usage: #RESULT },
                                  { localElement: 'Street',      element: 'Street',       usage: #RESULT },
                                  { localElement: 'PostalCode',  element: 'PostalCode',   usage: #RESULT },
                                  { localElement: 'City',        element: 'City',         usage: #RESULT } ],
             useForValidation: true }] 
      ```        
 
      <img src="images/p13b.png" alt="Adjust generated UI service" width="100%">
 
   3. Save ![save icon](../images/adt_save.png) and activate ![activate icon](../images/adt_activate.png) the changes. 
 
</details>


## Exercise 1.4: Populate Demo Data
[^Top of page](#)
 
> Create an ABAP class![class](../images/adt_class.png) to generate demo _employee_ data.
> 
> ℹ️ PS: This step is optional, as it will only fill your app with demo data. You can skip to **Exercise 1.4** if you prefer.

 <details>
  <summary>🔵 Click to expand!</summary>

   1. Right-click your ABAP package **`ZRAP120_AGENCY_###`** and select **New** > **ABAP Class** from the context menu.

      Maintain the required information (`###` is your group ID) and click **Next >**.
      - Name: **`ZGENERATE_AGENCY_DATA_###`**
      - Description: _**`Generate demo agency data`**_       
      
      Select a transport request and click **Finish** to create the class.
 
      <table>
      <tr>
          <td><img src="images/data1.png" alt="Generate demo data" width="100%"></td>
          <td><img src="images/data2.png" alt="Generate demo data" width="100%"></td>
          <td><img src="images/data3.png" alt="Generate demo data" width="100%"></td>       
      </tr>
      </table> 
   
   4. Replace the default class template with the source code provided below and replace all occurences of the placeholder **`###`** with your suffix using the **Replace All** function (**Ctrl+F**).
 
      <details>
      <summary>🟠📄 Click to expand the source code!</summary>

         ```ABAP 
          CLASS zgenerate_agency_data_### DEFINITION
            PUBLIC
            FINAL
            CREATE PUBLIC .

            PUBLIC SECTION.
            INTERFACES if_oo_adt_classrun.

            PROTECTED SECTION.
            PRIVATE SECTION.
          ENDCLASS.

          CLASS zgenerate_agency_data_### IMPLEMENTATION.
           METHOD if_oo_adt_classrun~main.
              "delete any existing active and draft data, if available
              DELETE FROM zagency###.
              DELETE FROM zagency###_d.
              "EXIT.                     "PS: uncomment this line if you only want to delete data from databases.
       
              "insert agency data
              INSERT ZAGENCY###  FROM (
                  SELECT
                    FROM /dmo/agency AS agency
                    FIELDS
                      uuid(  ) as uuid,
                      agency~agency_id      AS agency_id,
                      agency~name           AS agency_name,
                      agency~street         AS street,
                      agency~postal_code    AS postal_code,
                      agency~city           AS city,
                      agency~country_code   AS country_code,
                      agency~phone_number   AS phone_number ,
                      agency~email_address  AS email_address,
                      agency~web_address    AS web_address
                      ORDER BY agency_id UP TO 50 ROWS 
                ).
              COMMIT WORK.
              out->write( |[RAP120] Demo agency data successfully generated. | ).
            ENDMETHOD.       
          ENDCLASS.
         ```   
      </details>   

      <img src="images/data4.png" alt="Generate demo data" width="70%">
  
   3. Save ![save icon](../images/adt_save.png) and activate ![activate icon](../images/adt_activate.png) the class.
 
   4. Execute the class as console application. 

      For that, select your ABAP class ![class](../images/adt_class.png)**`ZGENERATE_AGENCY_DATA_###`**, select the run button > **Run As** > **ABAP Application (Console) F9** or press **F9**. 
 
      A successful message now appears displayed in the _ABAP Console_. 
 
      <table>
      <tr>
          <td><img src="images/data5.png" alt="Generate demo data" width="100%"></td>
          <td><img src="images/data6.png" alt="Generate demo data" width="100%"></td>
      </tr>
      </table>  
 
   5. You can open your generated database table ![table](../images/adt_tabl.png) **`ZAGENCY###`** for storing the active _Agency_ data and press **F8** to start the data preview and display the filled database entries. 
 
      > ℹ️ PS: Always remember that the name of the artifacts and properties generated by GenAI may differ from the one in the screenshot.
   
</details>


## Exercise 1.5: Preview the _Agency_ App
[^Top of page](#)

>  Preview the _Managing Agencies_ app in the browser.

 <details>
  <summary>🔵 Click to expand!</summary>

   1. Open your service binding ![service binding](../images/adt_srvb.png)**`ZUI_AGENCY###_O4`**, select the entity set **Agency**, and click **Preview** to start the Fiori Elements App Preview and open the app in the browser.
 
      <img src="images/p12b.png" alt="preview UI service mit demo data" width="70%">
     
   3. Play around with the application to familiarize yourself. Generic CRUD operations are available out of the box since a managed RAP BO has been generated.
 
</details>


## Summary & Next Exercise
[^Top of page](#)

Now that you've... 
- created an ABAP package,
- generated an OData-based UI service and the underlying RAP BO using the GenAI-based wizard (Beta) in ADT,
- published a local service endpoint, 
- started the _Fiori elements App Preview_ in ADT and make yourself familiar with it,

you can continue with the next exercise - **[Exercise 2: Enhance the RAP BO Behavior with a Business Event](../ex02/README.md)**.

## License

Copyright (c) 2024 SAP SE or an SAP affiliate company. All rights reserved. This project is licensed under the Apache Software License, version 2.0 except as noted otherwise in the [LICENSE](LICENSES/Apache-2.0.txt) file.