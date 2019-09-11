

 Generic DB App will be useful for programmers who work with database operations.
 
 In the application properties, we hve to set the following key-values;
 
 **1. id_type** - you have to give tenant_id/domain_id based on the column name which is present in your schema tables.
 
 ![Image](images/keyvalueaction.png "icon")
 ![Image](images/id_type.png "icon")
 
 **2. tablename** - here you have to mention the table names for which the actions(insert,update,delete....) to be performed. The table names which you give in the trigger path must match the tablenames which we give here then only the result is retrived.
 
 ![Image](images/tablename.png "icon")
 
 **3. activity.{{parent_table}}** - the child tablenames whose data must be stored separated in activity tables when you perform any action(insert,update,delete) are mentioned here .
 
 ![Image](images/activity.png "icon")
 
 **4. version_tables** - the tablenames for which their versions are need to be stored are named here. For each entity there will be separate entity_version table.
 
 ![Image](images/version.png "icon")
 
 **5. custom.query.{{id}}** - the complex query which couldnot be achieved through the existing dbapp operations need to be added here. We get the results based on customQueryId which we pass dynamically in rest call.(id must be unique)
 
 ![Image](images/customprops.png "icon")
 
 **6. Limit** - when you don't give the limit in the form data while retrieving data, by deafult the limit is set to 100 to limit the retrived records

JOINS
-----------

**Expression**: /s/joins

**Description** : This  will be used for joining multiple tables and get records.

**Input Type(JSON/Json Array/Form-Data)** : json object - raw data

**Rest Method**: POST

- A sample collection is shown below

**Trigger Expression** : https://dbapp.500apps.com/v2/s/joins

**Method** : ”POST”

**json object - raw data**

{"data":{

"fields": "t.id,count(tn.is_reply) as count",

"tables":[{"ticket_note":"tn"},{"ticket":"t"}],

"join":[{"join_type":"left join", "table1":"tn","join_column1":"ticket_id","table2":"t","join_column2":"id"}],

"group_by":"t.id"}}

![Image](images/joins.png "icon")

**************************************************

FILTERS
-------

**Description** : This will be used to specify various filter criteria and retrieve the data from several tables.

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

**Input Type(JSON/Json Array/Form-Data)** : json object - raw data

**Rest Method**: POST

- A sample collection is shown below

**Trigger Expression** : https://dbapp.500apps.com/v2/s/filters

**Method** : ”POST”

**json object - raw data**

{"data":{

"fields":"distinct c.id,c.first_name,c.last_name,c.tag,c.custom_value",

"tables":[{"contact_tag":"ct"},{"contact_details":"c"}],

"join":[{"join_type":"join","table1":"ct","join_column1":"contact_id","table2":"c","join_column2":"id"}],

"filters":[{"filter_condition":"","table_name":"ct","field_name":"tag_id","operator":"IN","value1":"'2','5'","value2":""}],

"jsonsearch":[{"filter_condition":"and","table_name":"c","field_name":"tag","operator":"SEARCH_VALUE","value1":"agile","value2":""}],

"order_by":"c.id",

"order_by_type":"desc",

"limit":"10",

"offset":"0"}}

![Image](images/filters.png "icon")

***************************

SEARCH
-------

**Expression**: /s/multi

**Description** : Let you do the search for multiple entities once at time, this  will useful.

**Input Type(JSON/Json Array/Form-Data)** : json object - raw data

**Rest Method**: POST

- A sample collection is shown below

**Trigger Expression** : https://dbapp.500apps.com/v2/s/multi

**Method** : ”POST”

**json object - raw data**

{"fields":["json_object('name',subject,'email',requester_email)",

"json_object('name',concat(ifnull(first_name,''),' ',ifnull(last_name,'')))"],

"tablename":["ticket","contact"],

"where":[{"search_by":"subject,requester_email"},{"search_by":"first_name,last_name,email"}],

"search":"somi"}

![Image](images/search.png "icon")

*******************************************

IMPORT
------

**Expression**: /m/import

**Description** : This  is used for import data from csv file.

**Input Type(JSON/Json Array/Form-Data)** : params,form data

**Rest Method**: POST

- A sample is shown below

**Trigger Expression** : https://dbapp.500apps.com/v2/m/import

**Method** : ”POST”

**params**

file_name:contact_import (5).csv

bucket_name:temptrash

table_name:staging

**form data**

fields : first_name,last_name

![Image](images/import.png "icon")

****************************************************

CUSTOM QUERIES
------

**Expression**: /cq/{entity_id}

**Description** : In this scenario we get the results based on customQueryId which we pass dynamically in rest call.

**Input Type(JSON/Json Array/Form-Data)** : params

**Rest Method**: GET

- A sample collection is shown below

**Trigger Expression** : https://dbapp.500apps.com/v2/cq/11

**Method** : ”GET”

**params**

boolean_value=true

![Image](images/custom.png "icon")

**************************************************

CUSTOM QUERIES INSERT
----------------------

**Expression**: /cq/{entity_id}

**Description** :  In this scenario we get the results based on customQueryId which we pass dynamically in rest call.

**Input Type(JSON/Json Array/Form-Data)** : json object - raw data

**Rest Method**: POST

- A sample collection is shown below

**Trigger Expression** : https://dbapp.500apps.com/v2/cq/6

**Method** : ”POST”

**json object - raw data**

{

"fields":"'raju'"

}

![Image](images/custominsert.png "icon")

**************************************************

CUSTOM QUERIES UPDATE
----------------------

**Expression**: /cq/{entity_id}

**Description** :  In this scenario we get the results based on customQueryId which we pass dynamically in rest call.

**Input Type(JSON/Json Array/Form-Data)** : json object - raw data

**Rest Method**: PUT

- A sample collection is shown below

**Trigger Expression** : https://dbapp.500apps.com/v2/cq/7

**Method** : ”PUT”

**json object - raw data**

{

"update_name":"test",

 "id":"4"  
 
}

![Image](images/customupdate.png "icon")

************************************************************

REPORTS
--------

**Bar Chart**

**Expression**: /r/bar

**Description** :  This is used for reports barchart.

**Input Type(JSON/Json Array/Form-Data)** : json object - raw data

**Rest Method**: POST

- A sample collection is shown below

**Trigger Expression** : https://dbapp.500apps.com/v2/r/bar

**Method** : ”POST”

**json object - raw data**

{"data":{ 

"x_axis": "date_format((t.created_time),'%Y-%m')",

"function":"count",

"y_axis":"t.id",

"tables":[{"ticket":"t"}],

"where":"month(t.created_time)=month(current_date)-1",

"order_by":"t.created_time",

"order_by_type":"desc"}}

![Image](images/bar.png "icon")

**Line Chart**

**Expression**: /r/line

**Description** :  This is used for reports linechart.

**Input Type(JSON/Json Array/Form-Data)** : json object - raw data

**Rest Method**: POST

- A sample collection is shown below

**Trigger Expression** : https://dbapp.500apps.com/v2/r/line

**Method** : ”POST”

**json object - raw data**

{"data":{ 

"x_axis": "date_format((t.created_time),'%Y-%m')",

"function":"count",

"y_axis":"t.id",

"tables":[{"ticket":"t"}],

"where":"month(t.created_time)=month(current_date)-1",

"order_by":"t.created_time",

"order_by_type":"desc"}}

![Image](images/line.png "icon")

**Funnel Chart**

**Expression**: /r/fc

**Description** :  This is used for reports funnelchart.

**Input Type(JSON/Json Array/Form-Data)** : json object - raw data

**Rest Method**: POST

- A sample collection is shown below

**Trigger Expression** : https://dbapp.500apps.com/v2/r/fc

**Method** : ”POST”

**json object - raw data**

{"data":{ 

"x_axis": "t.id",

"function":"count",

"y_axis":"t.id",

"tables":[{"ticket":"t"},{"`contact`":"c"}],

"join":[{"join_type":"join","table1":"t","join_column1":"contact_id","table2":"c","join_column2":"id"}],

"group_by":"t.contact_id"}}

![Image](images/funnel.png "icon")

**Pie Chart**

**Expression**: /r/pie

**Description** :  This is used for reports piechart.

**Input Type(JSON/Json Array/Form-Data)** : json object - raw data

**Rest Method**: POST

- A sample collection is shown below

**Trigger Expression** : https://dbapp.500apps.com/v2/r/pie

**Method** : ”POST”

**json object - raw data**

{"data": {

"Aggregate": "count",

"pie": "tc.name",

"percentage_by": "t.id",

"name": "high,medium,low",

"tables": {"ticket_category": "tc","ticket": "t"},

"tables": [{"ticket_category": "tc"},{"ticket": "t"}],

"join": [{"join_type": "join","table1": "tc","join_column1": "id","table2": "t","join_column2": "priority"}]

}}

![Image](images/pie.png "icon")
