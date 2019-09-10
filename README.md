JOINS
-----------

**Expression**: /s/joins

**Description** : This  will be used for joining multiple tables and get records..

**Input Type(JSON/Json Array/Form-Data)** : json object - raw data

**Rest Method**: POST

> A sample is shown here

**Trigger Expression** : [https://dbapp.500apps.com/v2/s/joins](https://dbapp.500apps.com/v2/s/joins)

**Method** : ”POST”

json object - raw data

{{raw-data}}
{{image}}

**************************************************

FILTERS
-------

1.Supported Data Types

* String

* Number

* Date

* Boolean

2.Supported Operators

* EQUALS - User has to pass EQ in the attribute

* NOT EQUALS - User has to pass NE

* LIKE - User has to pass LIKE

* NOT LIKE - User has to pass NOTLIKE

* IN - User has to pass IN

* NOT IN - User has to pass NOTIN

* IS NULL - User has to pass NULL

* IS NOT NULL - User has to pass NOTNULL

* BETWEEN - User has to pass BW

* NOT BETWEEN - User has to pass NBW

* STARTS WITH - User has to pass STARTSWITH

* NOT STARTS WITH - User has to pass NOTSTARTSWITH

* Ends with - User has to pass ENDS

* Not Ends with - User has to passNOTENDS

* To check empty data - EMPTY

* To check non empty data - NOTEMPTY

* '>' - User has to pass GT

* '<' - User has to pass LT

* '>=' - User has to pass GTE

* '<=' - User has to pass LTE

**Expression**: /s/filters

**Description** : This will be used to specify various filter criteria and retrieve the data from several tables.

**Input Type(JSON/Json Array/Form-Data)** : json object - raw data

**Rest Method**: POST

> A sample is shown here

**Trigger Expression** : [https://dbapp.500apps.com/v2/s/filters](https://dbapp.500apps.com/v2/s/filters)

**Method** : ”POST”

json object - raw data

{{raw-data}}
{{image}}

***************************

SEARCH
-------

**Expression**: /s/multi

**Description** : Let you do the search for multiple entities once at time, this  will useful.

**Input Type(JSON/Json Array/Form-Data)** : json object - raw data

**Rest Method**: POST

> A sample is shown here

**Trigger Expression** : [https://dbapp.500apps.com/v2/s/multi](https://dbapp.500apps.com/v2/s/multi)

**Method** : ”POST”

json object - raw data

{{raw-data}}
{{image}}

*******************************************

DESC
------

**Expression**: /m/desc/{table_name}

**Description** : Describe is used to describe the metadata of table. This will describe the structure of a table.

**Input Type(JSON/Json Array/Form-Data)** : path

**Rest Method**: GET

> A sample is shown here

**Trigger Expression** : [https://dbapp.500apps.com/v2/m/desc/ticket](https://dbapp.500apps.com/v2/m/desc/ticket)

**Method** : ”GET”

{{raw-data}}
{{image}}

**********************************************

IMPORT
------

**Expression**: /m/import

**Description** : This  is used for import data from csv file.

**Input Type(JSON/Json Array/Form-Data)** : params,form data

**Rest Method**: POST

> A sample is shown here

**Trigger Expression** : [https://dbapp.500apps.com/v2/m/import](https://dbapp.500apps.com/v2/m/import)

**Method** : ”POST”

params

form data

{{raw-data}}
{{image}}

*****************************************************

EXPORT
------

**Expression**: /m/export

**Description** : This  is used for export data to csv file.

**Input Type(JSON/Json Array/Form-Data)** : params,json object - raw data

**Rest Method**: POST

> A sample is shown here

**Trigger Expression** : [https://dbapp.500apps.com/v2/m/export](https://dbapp.500apps.com/v2/m/export)

**Method** : ”POST”

params

json object - raw data

{{raw-data}}
{{image}}

****************************************************

CUSTOM QUERIES
------

**Expression**: /cq/{entity_id}

**Description** : In this scenario we get the results based on customQueryId which we pass dynamically in rest call.

**Input Type(JSON/Json Array/Form-Data)** : params

**Rest Method**: GET

> A sample is shown here

**Trigger Expression** : [https://dbapp.500apps.com/v2/cq/11](https://dbapp.500apps.com/v2/cq/11)

**Method** : ”GET”

params

{{raw-data}}
{{image}}

**************************************************

CUSTOM QUERIES INSERT
----------------------

**Expression**: /cq/{entity_id}

**Description** :  In this scenario we get the results based on customQueryId which we pass dynamically in rest call.

**Input Type(JSON/Json Array/Form-Data)** : json object - raw data

**Rest Method**: POST

> A sample is shown here

**Trigger Expression** : [https://dbapp.500apps.com/v2/cq/7](https://dbapp.500apps.com/v2/cq/7)

**Method** : ”POST”

params

json object - raw data

{{raw-data}}
{{image}}

**************************************************

CUSTOM QUERIES UPDATE
----------------------

**Expression**: /cq/{entity_id}

**Description** :  In this scenario we get the results based on customQueryId which we pass dynamically in rest call.

**Input Type(JSON/Json Array/Form-Data)** : json object - raw data

**Rest Method**: PUT

> A sample is shown here

**Trigger Expression** : [https://dbapp.500apps.com/v2/cq/8](https://dbapp.500apps.com/v2/cq/8)

**Method** : ”PUT”

json object - raw data

{{raw-data}}
{{image}}

************************************************************

REPORTS
--------

* Bar Chart

**Expression**: /r/bar

**Description** :  This is used for reports barchart.

**Input Type(JSON/Json Array/Form-Data)** : json object - raw data

**Rest Method**: POST

> A sample is shown here

**Trigger Expression** : [https://dbapp.500apps.com/v2/r/bar](https://dbapp.500apps.com/v2/r/bar)

**Method** : ”POST”

json object - raw data

{{raw-data}}
{{image}}

* Line Chart

**Expression**: /r/line

**Description** :  This is used for reports linechart.

**Input Type(JSON/Json Array/Form-Data)** : json object - raw data

**Rest Method**: POST

> A sample is shown here

**Trigger Expression** : [https://dbapp.500apps.com/v2/r/bar](https://dbapp.500apps.com/v2/r/bar)

**Method** : ”POST”

json object - raw data

{{raw-data}}
{{image}}

* Funnel Chart

**Expression**: /r/fc

**Description** :  This is used for reports funnelchart.

**Input Type(JSON/Json Array/Form-Data)** : json object - raw data

**Rest Method**: POST

> A sample is shown here

**Trigger Expression** : [https://dbapp.500apps.com/v2/r/bar](https://dbapp.500apps.com/v2/r/bar)

**Method** : ”POST”

json object - raw data

{{raw-data}}
{{image}}

* Pie Chart

**Expression**: /r/pie

**Description** :  This is used for reports piechart.

**Input Type(JSON/Json Array/Form-Data)** : json object - raw data

**Rest Method**: POST

> A sample is shown here

**Trigger Expression** : [https://dbapp.500apps.com/v2/r/bar](https://dbapp.500apps.com/v2/r/bar)

**Method** : ”POST”

json object - raw data

{{raw-data}}
{{image}}
