[Home - AD180](/README.md#exercises)

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

   2. Clear the promt example, insert the prompt provided below for this exercise, and click **Next >**.
     
      Do not forget to replace **`###`** with your choosen suffix.
 
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
 
   5. The generator shows a preview of all artifacts that will be generated. 
 
      > ℹ️ Note: The names of the artifacts, database fields, and other elements in your preview may differ from those shown on the screenshots below or used later in this exercise, as they are generated by GenAI and there is no guarantee from the GenAI side.  
      > The ability to customize the suggestions will be provided with future releases.
      >
      > ℹ️ Note: If you have forgotten to replace **`###`**  with your choosen suffix you will get the error message: _Object name can only contain characters from syntactical character set_  
 
      <img src="images/p8.png" alt="generate UI service" width="70%">
      
   5. Click **Next >**, select a transport request, and click **Finish** to start the generation of all artifacts. 
 
      The generation of all artifacts may take a few moments.
  
      <!-- <img src="images/p9.png" alt="generate UI service" width="70%"> -->
  
   6. Go to the _**Project Explorer**_ view and check all artifacts that have been generated in your package. You may need to press **F5** to refresh your package.
  
      Then go to your service binding ![service binding](../images/adt_srvb.png)**`ZUI_AGENCY###_O4`** which is opened in the editor and click **Publish** to publish its local service endpoint to view service URL, entity sets, and associations.  
 
      <img src="images/p10.png" alt="generate UI service" width="100%"> 

 
      **ℹ️ List of the generated objects**: 
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

> Typically, you will need to adjust the generated repository object to fit your use case. 
> For example, you can adjust the data type of the database table fields, adjust the consumption view to enrich the projected data model, and adjust the metadata extension to change the Fiori app layout.  
> 
> In the present exercise, you will eventually have to adjust the data type of the **agency ID**  in the database tables for active and draft data. 
> The data type of this field should be a numical text with length 6, i.e. **`abap.numc(6)`**. 
> 
> ⚠️ PS: The names of the generated repository objects and fields in your exercise package may differ from those used in the description, code snippets, and screenshots below.


### Exercise 1.3.1: Adjust the Generated Database Tables 

> In this exercise, you will eventually have to adjust the data type of the **agency ID**  in the database tables for active and draft data. 
> The data type of this field should be a numical text with length 6, i.e. **`abap.numc(6)`**. 

 <details>
  <summary>🔵 Click to expand!</summary>

   1. Go to your package in the **Project Explorer**, open the database tabl ![table](../images/adt_tabl.png)**`ZAGENCY###`** for storing the active _agency_ data and replace the data type of the field **`agency_id`** with **`abap.numc(6)`** if necessary. Then save ![save icon](../images/adt_save.png) and activate ![activate icon](../images/adt_activate.png) the changes.     
 
      Do the same for the database table ![table](../images/adt_tabl.png)**`ZAGENCY###_D`** for storing the draft _agency_ data, and replace the data type of the field **`agency_id`** with **`abap.numc(6)`** if necessary. Then save ![save icon](../images/adt_save.png) and activate ![activate icon](../images/adt_activate.png) the changes. 
 
      ```ABAP
       abap.numc(6); 
      ```       
      
      <img src="images/p13.png" alt="Adjust generated UI service" width="70%">

 </details>
 
 
### Exercise 1.3.2: Adjust the Consumption view    

> You can also go ahead and adjust the projected data model by defining value helps in the ![ddls](../images/adt_ddls.png)CDS projection view (`ZC*`) to ease the data maintenance in the app.

 <details>
  <summary>🔵 Click to expand!</summary>
 
   1. Go to your package in the **Project Explorer** and open the the projection view ![ddls](../images/adt_ddls.png)**`ZC_AGENCY###`**
 
   2. specify the field element **`AgencyId`** as semantic key for the application by add the **view annotation** below.  
 
      ```ABAP_CDS
       @ObjectModel.semanticKey: ['AgencyId']
      ```         
 
   3. Also specify the projection view as searchable by adding the following view annotation as shown on the screenshot below:
 
      ```
      @Search.searchable: true
      ```

   4. Enable the fuzzy search, i.e. a full-text search with the error tolerance (fuzziness threshold) `0.8`, for the element **`AgencyName`**by specifying the following annotation block directly before the element:
 
      ```
      @Search: {
        defaultSearchElement: true,
        fuzzinessThreshold:  0.8
      }
      ```
 
   5. Now, add the **element annotation** block below just before **`AgencyId`* in the _select_ list to define a value help for the _agency ID_. The `additionalBinding` annotation will help automatically filling the related fields `AgencyName`, `Street`, `PostalCode`, and `City` at the same time.
 
      ```ABAP_CDS
       @Consumption.valueHelpDefinition: [{
             entity : {name: '/DMO/I_Agency_StdVH', element: 'AgencyID'  },
             additionalBinding: [ { localElement: 'AgencyName',  element: 'Name',         usage: #RESULT },
                                  { localElement: 'Street',      element: 'Street',       usage: #RESULT },
                                  { localElement: 'PostalCode',  element: 'PostalCode',   usage: #RESULT },
                                  { localElement: 'City',        element: 'City',         usage: #RESULT } ],
             useForValidation: true }] 
      ```        
      
      <br/>
      <img src="images/p13b.png" alt="Adjust generated UI service" width="70%">
 
   4. Save ![save icon](../images/adt_save.png) and activate ![activate icon](../images/adt_activate.png) the changes. 
 
 </details> 
 
 
### Exercise 1.3.3: Adjust the UI Semantics   
 
> In this exercise, you will adjust the application layout by adjusting the UI semantics in the ![ddlx](../images/adt_ddlx.png)CDS metadata extension. 

 <details>
  <summary>🔵 Click to expand!</summary>
 
   1. Go to your package in the **Project Explorer** and open the generated CDS metadata extension ![ddlx](../images/adt_ddlx.png)**`ZC_AGENCY###`**. 
 
   2. Adjust the **`@headerInfo`** annotation by specifying **`AgencyId`** as title value and **`AgencyName`** as description. 
 
      For that, simply replace the line _`@UI.headerInfo.title.value: 'Uuid'`_ with 
 
      ```
      @UI.headerInfo.title.value: 'AgencyId'
      ```
      
      Replace the line _`@UI.headerInfo.description.value: 'Uuid'`_ with 
 
      ```
      @UI.headerInfo.description.value: 'AgencyName'
      ```
      
      Insert the code snippet below to specify _Agency_ as type name and _Agencies_ as its plural in the header info: 
 
      ```
      @UI.headerInfo.typeName: 'Agency'
      @UI.headerInfo.typeNamePlural: 'Agencies'
      ``` 
 
      <img src="images/p13c.png" alt="Adjust generated UI service" width="50%"> 
 
   3. Adjust the filter bar by removing some fields by deleting or commenting out (`//`) the element annotation block **`@UI.selectionField`** as shown in the screenshot below. 

      For example, remove **`AgencyName`**, **`Street`**, **`PostalCode`**, **`CountryCode`**, **`PhoneNumber`**, **`EmailAddress`**, and **`WebAddress`** - from the filter bar. 
 
      <img src="images/p13d.png" alt="Adjust generated UI service" width="30%">
 
   4. Adjust the list table on the entry page by removing some of the table columns by deleting or commenting out (`//`) the element annotation block **`@UI.lineItem`** as shown in the screenshot. 
 
      For example, remove following table columns - e.g. **`Street`**, **`PostalCode`**, **`CountryCode`**, **`PhoneNumber`**, **`EmailAddress`**, and **`WebAddress`**.   
 
      <img src="images/p13e.png" alt="Adjust generated UI service" width="30%">
 
   5. Remove the adminstrative fields and their related annotations from the metadata extension: **`LocalCreatedBy`**, **`LocalCreatedAt`**, **`LocalLastChangedBy`**, **`LocalLastChangedAt`**, and **`LastChangedAt`**.
 
      <img src="images/p13f.png" alt="Adjust generated UI service" width="50%">  
 
   6. Save ![save icon](../images/adt_save.png) and activate ![activate icon](../images/adt_activate.png) the changes. 
 
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
              DATA: agencies  TYPE TABLE OF zagency###.
         
         *     DELETE FROM zagency###_e.
         *     "EXIT.
         
              "delete existing data
              DELETE FROM zagency###.
              DELETE FROM zagency###_d.
         
              "insert demo agency data
              agencies = VALUE #(
                 ( uuid = 'C68D1DF0F7B5ED251900D4AECE7F7813' agency_id = '070001' agency_name = 'Sunshine Travel' street = '134 West Street' postal_code = '54323' city = 'Rochester' country_code = 'US' phone_number = '+1 901-632-5620'
                 email_address = 'info@sunshine-travel.sap' web_address = 'http://www.sunshine-travel.sap' local_created_by = '' local_created_at = '0.0000000 ' local_last_changed_by = '' local_last_changed_at = '0.0000000 ' last_changed_at = '0.0000000 '  )
                 (  uuid = 'C78D1DF0F7B5ED251900D4AECE7F7813' agency_id = '070002' agency_name = 'Fly High' street = 'Berliner Allee 11' postal_code = '40880' city = 'Duesseldorf' country_code = 'DE' phone_number = '+49 2102 69555'
                 email_address = 'info@flyhigh.sap' web_address = 'http://www.flyhigh.sap' local_created_by = '' local_created_at = '0.0000000 ' local_last_changed_by = '' local_last_changed_at = '0.0000000 ' last_changed_at = '0.0000000 '  )
                 (  uuid = 'C88D1DF0F7B5ED251900D4AECE7F7813' agency_id = '070003' agency_name = 'Happy Hopping' street = 'Calvinstr. 36' postal_code = '13467' city = 'Berlin' country_code = 'DE' phone_number = '+49 30-8853-0'
                 email_address = 'info@haphop.sap' web_address = 'http://www.haphop.sap' local_created_by = '' local_created_at = '0.0000000 ' local_last_changed_by = '' local_last_changed_at = '0.0000000 ' last_changed_at = '0.0000000 '  )
                 (  uuid = 'C98D1DF0F7B5ED251900D4AECE7F7813' agency_id = '070004' agency_name = 'Pink Panther' street = 'Auf der Schanz 54' postal_code = '65936' city = 'Frankfurt' country_code = 'DE' phone_number = '+49 69-467653-0'
                 email_address = 'info@pinkpanther.sap' web_address = 'http://www.pinkpanther.sap' local_created_by = '' local_created_at = '0.0000000 ' local_last_changed_by = '' local_last_changed_at = '0.0000000 ' last_changed_at = '0.0000000 '  )
                 (  uuid = 'CA8D1DF0F7B5ED251900D4AECE7F7813' agency_id = '070005' agency_name = 'Your Choice' street = 'Gustav-Jung-Str. 425' postal_code = '90455' city = 'Nuernberg' country_code = 'DE' phone_number = '+49 9256-4548-0'
                 email_address = 'info@yc.sap' web_address = 'http://www.yc.sap' local_created_by = '' local_created_at = '0.0000000 ' local_last_changed_by = '' local_last_changed_at = '0.0000000 ' last_changed_at = '0.0000000 '  )
                  ).
         
         *    insert the new table entries
              INSERT zagency### FROM TABLE @agencies.
         
              COMMIT WORK.
              out->write( |[RAP120 / AD180] Demo agency data successfully generated. | ).
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
