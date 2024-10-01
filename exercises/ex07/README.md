[Home - RAP120](/README.md#exercises)

# ⚠️ THIS PAGE WILL BE DELETED SOON ⚠️- Exercise 7: Adjust the Generated Consumption View & Display the Tree-view

🚧🚧🚧🚧

## Introduction

> In the previous exercise, you've defining the hierarchy interpretation, i.e how the hierarchical data is interpreted with a parent-child hierarchy. (see [Exercise 6](../ex06/README.md)). 
> 
> In the present exercise, you will enhance the consumption view, i.e. the projection view, by adding a self-association to the parent node of that same CDS view and  connect it with the hierarchical interpretation of the data from the hierarchy entity.
> 
> see https://help.sap.com/docs/abap-cloud/abap-rap/creating-consumption-view?version=s4hana_cloud 


### Exercise Steps:
- [Exercise 7.1 - Adjust the Generated Consumption View](#exercise-71-adjust-the-generated-consumption-view)
- [Exercise 7.2 - Display the Tree-view](#exercise-72-display-the-tree-view) 
- [Summary & Next Exercise](#summary--next-exercise)  


## Exercise 7.1: Add the self-association to the Consumption View
[^Top of page](#)
   
 > You also need to define and expose a self-association in the projection view on the the consumption level for the hierachy you will later define in the next exercise.  
 > 🚧
 > In this view, you need to add a self-association to the parent node of that same CDS view **`ZC_???`**. 
 > 
 > This adds the hierarchical logic to the exisiting data, indicating that an employee ID can also serve as the manager ID for another employee. Since one manager can have several employees, the cardinality is defined as many to one.
 > https://help.sap.com/docs/abap-cloud/abap-rap/creating-consumption-view?version=s4hana_cloud

 <details>
  <summary>🔵 Click to expand!</summary>

   1. Go to your package in the **Project Explorer**, ...
 
      ```ABAP
       blablabla
      ```       
 
      <img src="images/p13xxx.png" alt="Adjust consumption View" width="100%">

   3. Save ![save icon](../images/adt_save.png) and activate ![activate icon](../images/adt_activate.png) both database tables.
          
</details>


 ### Display the Tree-view
 
 <details>
  <summary>🔵 Click to expand!</summary>

   1. Go to your package in the **Project Explorer**, open the database table **`ZAGENCY###`** for storing the active agency data, and replace the data type of the fields **`employee_id`** and **`manager_id`** with **`abap.numc(8)`** if necessary.
 
      ```ABAP
       blablabla
      ```       
 
      <img src="images/p13xxx.png" alt="Display the Tree-view" width="100%">

   3. Save ![save icon](../images/adt_save.png) and activate ![activate icon](../images/adt_activate.png) both database tables.
          
</details>

## Summary & Next Exercise
[^Top of page](#)

Now that you've... 
- enhanced the consumption view with the self-association and the connection to the hierarchy interpretation, and
- preview hierachical data using the tree-view in the enhanced _Employee_ app in the browser,

you are done with this exercise group (B). Congratulations! 🎉

In this hands-on exercise group, you have hopefully have some more insights into new ABAP Cloud capabilities such as the GenAI generation of OData-based UI services and tree-views! Note that SAP planed to support editable tree-view. Learn more in the [ABAP Cloud Roadmap Information](https://help.sap.com/docs/abap-cross-product/roadmap-info/ui-services).

You can now return to ► **[Home - RAP120](/README.md#exercises)**.


## License

Copyright (c) 2024 SAP SE or an SAP affiliate company. All rights reserved. This project is licensed under the Apache Software License, version 2.0 except as noted otherwise in the [LICENSE](LICENSES/Apache-2.0.txt) file.

