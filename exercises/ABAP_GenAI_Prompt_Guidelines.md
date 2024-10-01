# Prompt Guidelines and Examples for ABAP GenAI

To achieve good results with your prompts, please consider the following recommendations. 

**Table of Content**
- [Accuracy](#accuracy) 
- [Context](#context) 
- [Terminology](#terminology)
- [Model-related Recommendations](#model-related-recommendations)
- [Prompt Examples](#prompt-examples) 🚧🚧

## Accuracy 

The quality of a response received from a Large Language Model heavily depends on the level of detail 

comprised in your prompt. The more accurate your prompt, the greater the probability that the response 

received from the AI matches your expectations. Therefore, it is recommended to describe every requirement 

for the RAP Fiori service to be generated accurately. 


## Context 

As mentioned above, the prompt you enter in the wizard is combined with a system prompt before it is sent 

to the AI for evaluation. The prompt provided by the system already contains the required context information 

of your request. Adding general information about the ABAP RESTFul Application Programming Model (RAP), 

the general structure of RAP business objects or the purpose of their artifacts is not required. 

Within the given scope, however, you should describe your requirement accurately, see section above. 


## Terminology 

Avoid ambiguity in your prompts by using the correct terminology when describing the read-only or transactional 
(RAP-based) Fiori service to be generated. For this purpose, choose your terms in accordance with the related technology, e.g. composition association in RAP to describe the composition hierarchy of a RAP business object.


## Model-related Recommendations 

Specify the entities to be included in your data model as accurately as possible. Describe their purpose, the 

desired naming convention and their cardinality, where required. 

**By default**, the wizard generates draft-enabled OData V4 Fiori UI services. In case your requirements differ 

from these defaults, specify them accordingly. 


# Prompt Examples 

Feel free to play around with different types of prompts. If you want to get an impression of how meaningful prompts 

with good results can look like, please refer to the following examples. 

Replace `###` with your own desired prefix or suffix. 

---

### Example 1: Generate a read-only OData V4 UI service with a single business entity 🚧


**Display Employee entities**

```PROMPT
Generate a read-only application for displaying employees. 
The employee entity requires the fields employee_id, first_name, last_name, salary, and manager. 
Use a numerical data type with length 6 for the fields employee_id and manager.
Use built-in character string data type CHAR with length 40 for the fields first_name and last_name. 
Salary is a decimals with length 21. The field salary is a currency field. 
Create the object names with the suffix '###'.
````

**Display Customer entities**

```PROMPT
Generate a read-only application for managing customers.
The customer entity requires the fields customer_id, customer_name, address, phone_number, and email_address.
Use charater like daa types for the fields.
Create the object names with prefix '###'.
````

----

### Example 2: Generate a read-only OData V4 UI service with a multiple business entities 🚧


**Display Agency and Employee entities.**

```PROMPT
Generate a read-only application for managing agencies and employees. 
🚧 to be enhanced soon 🚧
The employee entity requires the fields employee_id, first_name, last_name, salary, and manager_id.
Use numerical text data type with length 8 like data types for the fields employee_id and manager_id. 
Use character like data types for the other fields.
The field salary is a currency field. 

Create the object names with the suffix '###'.
````

----

### Example 3: Generate a draft-enabled OData V4 UI service with a single business object entity to manage customer

**Manage Travel entity.**

```PROMPT
Generate an application for managing customers.
The customer entity requires the fields customer_id, customer_name, address, phone_number, and email_address.
Use charater like daa types for the fields.
Create the object names with prefix '###'.

````

----

### Example 4: Generate a draft-enabled OData V4 UI service with multiple entities connected via compositional associations

**Manage Travel, Booking, and Booking Supplement entities.**

```PROMPT
Generate an application for managing travel data.
The app should include the entities travel, booking, and supplement.
The entities should be connected via compositional associatiions with the cardinalities [0..*] respectively.

The travel entity requires the fields travel_id, begin_date, end_date, travel_price, and currency.
Use charater like data types for the fields travel_id, begin_date, end_date, travel_price, and currency.
Use currency dta types for fields travel_price and currency.

The booking entity requires the fields booking_id, booking_date, flight_date, flight_price, and currency.
Use charater like data types for the fields booking_id, booking_date, flight_date, and flight_price.
Use currency data types for fields booking_price and currency.

The booking supplement entity requires the fields supplement_id, price, and currency.
Use charater like data types for the field supplement_id.
Use currency data types for fields price and currency.

Create the object names with prefix '###'.
````

----

### Example 5: Generate a read-only OData V4 UI service with multiple entities 
🚧
```PROMPT
 🚧 coming soon 🚧
 Generate an application for managing agencies. 
 
 The agency entity requires the fields agency_id, agency_name, street, postal_code, city, 
 country_code, phone_number, email_address, and /dmo/web_address.
 
 Use a numerical data type with length 6 for the field agency_id. 
 country_code is a country key with length 3.
 
 Use character like data types for the other fields with length 80 for field agency_name, 
 length 60 for field street, length 10 for field postal_code, length 40 for field city, 
 length 30 for field phone_number, length 256 for field email_address, and length 256 for field web_address.
 
 Create the object names with the suffix '###'.
 🚧
```

## License

Copyright (c) 2024 SAP SE or an SAP affiliate company. All rights reserved. This project is licensed under the Apache Software License, version 2.0 except as noted otherwise in the [LICENSE](LICENSES/Apache-2.0.txt) file.
