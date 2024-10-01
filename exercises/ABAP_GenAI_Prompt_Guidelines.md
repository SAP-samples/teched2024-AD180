# Prompt Guidelines and Examples for ABAP GenAI

To achieve good results with your prompts, please consider the following recommendations. 

**Table of Content**
- [Accuracy](#accuracy) 
- [Context](#context) 
- [Terminology](#terminology)
- [Model-related Recommendations](#model-related-recommendations)
- [Prompt Examples](#prompt-examples) 

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

### Example 1: Generate a read-only OData V4 UI service with a single business entity to display customers 

```PROMPT
Generate a read-only application for managing customers.
The customer entity requires the fields customer_id, customer_name, address, phone_number, and email_address.
Use charater like daa types for the fields.
Create the object names with prefix '###'.
````

### Example 2: Generate a draft-enabled OData V4 UI service with a single business object entity to manage customer

```PROMPT
Generate an application for managing customers.
The customer entity requires the fields customer_id, customer_name, address, phone_number, and email_address.
Use charater like daa types for the fields.
Create the object names with prefix '###'.

````

### Example 3: Generate a draft-enabled OData V4 UI service with multiple entities connected via compositional associations

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

## License

Copyright (c) 2024 SAP SE or an SAP affiliate company. All rights reserved. This project is licensed under the Apache Software License, version 2.0 except as noted otherwise in the [LICENSE](LICENSES/Apache-2.0.txt) file.
