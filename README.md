
# JSON - Lab

## Introduction

In this lab, you'll practice navigating JSON data structures.

## Objectives
You will be able to:
* Use the JSON module to load and parse JSON documents

## JSON

### Open the dataset from json


```python
#Your code here
import json
f = open('nyc_2001_campaign_finance.json')
data = json.load(f)
```

### What is the root data type of the json file?


```python
### Your code here
type(data)
```




    dict



### Navigate to the 'data' key of your loaded json object. What data type is this?


```python
#Your code here
type(data['data'])
```




    list



### Preview the first entry from the value returned by the 'data' key above.


```python
#Your code here
data['data'][0]
```




    [1,
     'E3E9CC9F-7443-43F6-94AF-B5A0F802DBA1',
     1,
     1315925633,
     '392904',
     1315925633,
     '392904',
     '{\n  "invalidCells" : {\n    "1519001" : "TOTALPAY",\n    "1518998" : "PRIMARYPAY",\n    "1519000" : "RUNOFFPAY",\n    "1518999" : "GENERALPAY",\n    "1518994" : "OFFICECD",\n    "1518996" : "OFFICEDIST",\n    "1518991" : "ELECTION"\n  }\n}',
     None,
     'CANDID',
     'CANDNAME',
     None,
     'OFFICEBORO',
     None,
     'CANCLASS',
     None,
     None,
     None,
     None]



### Preview the Entry under meta -> view -> columns (the keys of three successively nested dictionaries)


```python
data['meta']['view']['columns']
```




    [{'id': -1,
      'name': 'sid',
      'dataTypeName': 'meta_data',
      'fieldName': ':sid',
      'position': 0,
      'renderTypeName': 'meta_data',
      'format': {},
      'flags': ['hidden']},
     {'id': -1,
      'name': 'id',
      'dataTypeName': 'meta_data',
      'fieldName': ':id',
      'position': 0,
      'renderTypeName': 'meta_data',
      'format': {},
      'flags': ['hidden']},
     {'id': -1,
      'name': 'position',
      'dataTypeName': 'meta_data',
      'fieldName': ':position',
      'position': 0,
      'renderTypeName': 'meta_data',
      'format': {},
      'flags': ['hidden']},
     {'id': -1,
      'name': 'created_at',
      'dataTypeName': 'meta_data',
      'fieldName': ':created_at',
      'position': 0,
      'renderTypeName': 'meta_data',
      'format': {},
      'flags': ['hidden']},
     {'id': -1,
      'name': 'created_meta',
      'dataTypeName': 'meta_data',
      'fieldName': ':created_meta',
      'position': 0,
      'renderTypeName': 'meta_data',
      'format': {},
      'flags': ['hidden']},
     {'id': -1,
      'name': 'updated_at',
      'dataTypeName': 'meta_data',
      'fieldName': ':updated_at',
      'position': 0,
      'renderTypeName': 'meta_data',
      'format': {},
      'flags': ['hidden']},
     {'id': -1,
      'name': 'updated_meta',
      'dataTypeName': 'meta_data',
      'fieldName': ':updated_meta',
      'position': 0,
      'renderTypeName': 'meta_data',
      'format': {},
      'flags': ['hidden']},
     {'id': -1,
      'name': 'meta',
      'dataTypeName': 'meta_data',
      'fieldName': ':meta',
      'position': 0,
      'renderTypeName': 'meta_data',
      'format': {},
      'flags': ['hidden']},
     {'id': 75768833,
      'name': 'ELECTION',
      'dataTypeName': 'number',
      'fieldName': 'election',
      'position': 2,
      'renderTypeName': 'number',
      'tableColumnId': 1518991,
      'width': 196,
      'cachedContents': {'non_null': 284,
       'average': '2001',
       'largest': '2001',
       'null': 1,
       'top': [{'item': '2001', 'count': 20}],
       'smallest': '2001',
       'sum': '568284'},
      'format': {'precisionStyle': 'standard',
       'noCommas': 'true',
       'align': 'right'}},
     {'id': 75768834,
      'name': 'CANDID',
      'dataTypeName': 'text',
      'fieldName': 'candid',
      'position': 3,
      'renderTypeName': 'text',
      'tableColumnId': 1518992,
      'width': 172,
      'cachedContents': {'non_null': 285,
       'largest': 'YA',
       'null': 0,
       'top': [{'item': '490', 'count': 20},
        {'item': '577', 'count': 19},
        {'item': 'GF', 'count': 18},
        {'item': '265', 'count': 17},
        {'item': '549', 'count': 16},
        {'item': '260', 'count': 15},
        {'item': 'DH', 'count': 14},
        {'item': '168', 'count': 13},
        {'item': '561', 'count': 12},
        {'item': '317', 'count': 11},
        {'item': '240', 'count': 10},
        {'item': 'B1', 'count': 9},
        {'item': '337', 'count': 8},
        {'item': '202', 'count': 7},
        {'item': 'DP', 'count': 6},
        {'item': '554', 'count': 5},
        {'item': '529', 'count': 4},
        {'item': '521', 'count': 3},
        {'item': 'CY', 'count': 2},
        {'item': '327', 'count': 1}],
       'smallest': '148'},
      'format': {}},
     {'id': 75768835,
      'name': 'CANDNAME',
      'dataTypeName': 'text',
      'fieldName': 'candname',
      'position': 4,
      'renderTypeName': 'text',
      'tableColumnId': 1518993,
      'width': 196,
      'cachedContents': {'non_null': 285,
       'largest': 'Zett, Lori M',
       'null': 0,
       'top': [{'item': 'Taitt, Samuel A', 'count': 20},
        {'item': 'Taliaferro, Phyllis', 'count': 19},
        {'item': 'Taveras, Germania', 'count': 18},
        {'item': 'Thakral, Jairam D', 'count': 17},
        {'item': 'Thomas, Carl W', 'count': 16},
        {'item': 'Thompson, Jr., William C', 'count': 15},
        {'item': 'Tiraco, Joseph E', 'count': 14},
        {'item': 'Toney, Vaughan', 'count': 13},
        {'item': 'Toppin, Roger N', 'count': 12},
        {'item': 'Torres, Mario A', 'count': 11},
        {'item': 'Vallone, Jr., Peter F', 'count': 10},
        {'item': 'Vallone, Peter F', 'count': 9},
        {'item': 'Van Bramer, James G', 'count': 8},
        {'item': 'Vann, Albert', 'count': 7},
        {'item': 'Vargas, Ruben Dario', 'count': 6},
        {'item': 'Vassos, Sandra', 'count': 5},
        {'item': 'Vernet, Jean D', 'count': 4},
        {'item': 'Viest, Nicholas D', 'count': 3},
        {'item': 'Villaverde, Sergio', 'count': 2},
        {'item': 'Vogel, Mark H', 'count': 1}],
       'smallest': 'Aboulafia, Sandy'},
      'format': {}},
     {'id': 75768836,
      'name': 'OFFICECD',
      'dataTypeName': 'number',
      'fieldName': 'officecd',
      'position': 5,
      'renderTypeName': 'number',
      'tableColumnId': 1518994,
      'width': 196,
      'cachedContents': {'non_null': 284,
       'average': '4.700704225352113',
       'largest': '5',
       'null': 1,
       'top': [{'item': '5', 'count': 20},
        {'item': '1', 'count': 19},
        {'item': '3', 'count': 18},
        {'item': '4', 'count': 17},
        {'item': '2', 'count': 16}],
       'smallest': '1',
       'sum': '1335'},
      'format': {}},
     {'id': 75768837,
      'name': 'OFFICEBORO',
      'dataTypeName': 'text',
      'fieldName': 'officeboro',
      'position': 6,
      'renderTypeName': 'text',
      'tableColumnId': 1518995,
      'width': 220,
      'cachedContents': {'non_null': 21,
       'largest': 'X',
       'null': 264,
       'top': [{'item': 'OFFICEBORO', 'count': 20},
        {'item': 'X', 'count': 19},
        {'item': 'M', 'count': 18},
        {'item': 'K', 'count': 17},
        {'item': 'Q', 'count': 16},
        {'item': 'S', 'count': 15}],
       'smallest': 'K'},
      'format': {}},
     {'id': 75768838,
      'name': 'OFFICEDIST',
      'dataTypeName': 'number',
      'fieldName': 'officedist',
      'position': 7,
      'renderTypeName': 'number',
      'tableColumnId': 1518996,
      'width': 220,
      'cachedContents': {'non_null': 245,
       'average': '26.33061224489796',
       'largest': '51',
       'null': 40,
       'top': [{'item': '7', 'count': 20},
        {'item': '32', 'count': 19},
        {'item': '37', 'count': 18},
        {'item': '28', 'count': 17},
        {'item': '19', 'count': 16},
        {'item': '39', 'count': 15},
        {'item': '35', 'count': 14},
        {'item': '42', 'count': 13},
        {'item': '31', 'count': 12},
        {'item': '6', 'count': 11},
        {'item': '47', 'count': 10},
        {'item': '20', 'count': 9},
        {'item': '1', 'count': 8},
        {'item': '27', 'count': 7},
        {'item': '26', 'count': 6},
        {'item': '10', 'count': 5},
        {'item': '34', 'count': 4},
        {'item': '45', 'count': 3},
        {'item': '40', 'count': 2},
        {'item': '12', 'count': 1}],
       'smallest': '1',
       'sum': '6451'},
      'format': {}},
     {'id': 75768839,
      'name': 'CANCLASS',
      'dataTypeName': 'text',
      'fieldName': 'canclass',
      'position': 8,
      'renderTypeName': 'text',
      'tableColumnId': 1518997,
      'width': 196,
      'cachedContents': {'non_null': 285,
       'largest': 'P',
       'null': 0,
       'top': [{'item': 'CANCLASS', 'count': 20}, {'item': 'P', 'count': 19}],
       'smallest': 'CANCLASS'},
      'format': {}},
     {'id': 75768840,
      'name': 'PRIMARYPAY',
      'dataTypeName': 'number',
      'fieldName': 'primarypay',
      'position': 9,
      'renderTypeName': 'number',
      'tableColumnId': 1518998,
      'width': 220,
      'cachedContents': {'non_null': 284,
       'average': '112243.9612676056',
       'largest': '2846148.00',
       'null': 1,
       'top': [{'item': '75350.00', 'count': 20},
        {'item': '0', 'count': 19},
        {'item': '91333.00', 'count': 18},
        {'item': '69780.00', 'count': 17},
        {'item': '22172.00', 'count': 16},
        {'item': '65356.00', 'count': 15},
        {'item': '11423.00', 'count': 14},
        {'item': '60152.00', 'count': 13},
        {'item': '75040.00', 'count': 12},
        {'item': '62436.00', 'count': 11},
        {'item': '42075.00', 'count': 10},
        {'item': '74920.00', 'count': 9},
        {'item': '38088.00', 'count': 8},
        {'item': '74850.00', 'count': 7},
        {'item': '89502.00', 'count': 6},
        {'item': '74350.00', 'count': 5},
        {'item': '58348.00', 'count': 4},
        {'item': '55100.00', 'count': 3},
        {'item': '508893.00', 'count': 2},
        {'item': '74750.00', 'count': 1}],
       'smallest': '0',
       'sum': '31877285.00'},
      'format': {}},
     {'id': 75768841,
      'name': 'GENERALPAY',
      'dataTypeName': 'number',
      'fieldName': 'generalpay',
      'position': 10,
      'renderTypeName': 'number',
      'tableColumnId': 1518999,
      'width': 220,
      'cachedContents': {'non_null': 284,
       'average': '28753.57394366197',
       'largest': '976545.00',
       'null': 1,
       'top': [{'item': '0', 'count': 20},
        {'item': '75350.00', 'count': 19},
        {'item': '201131.00', 'count': 18},
        {'item': '39760.00', 'count': 17},
        {'item': '57796.00', 'count': 16},
        {'item': '75200.00', 'count': 15},
        {'item': '68234.00', 'count': 14},
        {'item': '5732.00', 'count': 13},
        {'item': '58488.00', 'count': 12},
        {'item': '62184.00', 'count': 11},
        {'item': '44748.00', 'count': 10},
        {'item': '21946.00', 'count': 9},
        {'item': '70500.00', 'count': 8}],
       'smallest': '0',
       'sum': '8166015.00'},
      'format': {}},
     {'id': 75768842,
      'name': 'RUNOFFPAY',
      'dataTypeName': 'number',
      'fieldName': 'runoffpay',
      'position': 11,
      'renderTypeName': 'number',
      'tableColumnId': 1519000,
      'width': 208,
      'cachedContents': {'non_null': 284,
       'average': '7776.778169014085',
       'largest': '711537.00',
       'null': 1,
       'top': [{'item': '0', 'count': 20},
        {'item': '267331.00', 'count': 19},
        {'item': '574387.00', 'count': 18},
        {'item': '303270.00', 'count': 17},
        {'item': '711537.00', 'count': 16},
        {'item': '114407.00', 'count': 15},
        {'item': '237673.00', 'count': 14}],
       'smallest': '0',
       'sum': '2208605.00'},
      'format': {}},
     {'id': 75768843,
      'name': 'TOTALPAY',
      'dataTypeName': 'number',
      'fieldName': 'totalpay',
      'position': 12,
      'renderTypeName': 'number',
      'tableColumnId': 1519001,
      'width': 196,
      'cachedContents': {'non_null': 284,
       'average': '148774.3133802817',
       'largest': '4534230.00',
       'null': 1,
       'top': [{'item': '0', 'count': 20},
        {'item': '75350.00', 'count': 19},
        {'item': '150700.00', 'count': 18},
        {'item': '2458534.00', 'count': 17},
        {'item': '133146.00', 'count': 16},
        {'item': '75200.00', 'count': 15},
        {'item': '68234.00', 'count': 14},
        {'item': '70664.00', 'count': 13},
        {'item': '58488.00', 'count': 12},
        {'item': '50112.00', 'count': 11},
        {'item': '62184.00', 'count': 10},
        {'item': '44748.00', 'count': 9},
        {'item': '21946.00', 'count': 8},
        {'item': '41656.00', 'count': 7},
        {'item': '61260.00', 'count': 6},
        {'item': '145850.00', 'count': 5},
        {'item': '35808.00', 'count': 4},
        {'item': '12172.00', 'count': 3}],
       'smallest': '0',
       'sum': '42251905.00'},
      'format': {}}]



### Create a DataFrame from your json data
The previous two questions previewed one entry from the data object within the json file, as well as the column details associated with that data from the meta entry within the json file. Both should have 19 entries. Create a pandas DataFrame of the data. Be sure to use the information from the meta entry to add appropriate column names to your DataFrame.


```python
#Your code here
import pandas as pd
df = pd.DataFrame(data['data'])
cols = [i['name'] for i in data['meta']['view']['columns']]
df.columns = cols
df.head()
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>sid</th>
      <th>id</th>
      <th>position</th>
      <th>created_at</th>
      <th>created_meta</th>
      <th>updated_at</th>
      <th>updated_meta</th>
      <th>meta</th>
      <th>ELECTION</th>
      <th>CANDID</th>
      <th>CANDNAME</th>
      <th>OFFICECD</th>
      <th>OFFICEBORO</th>
      <th>OFFICEDIST</th>
      <th>CANCLASS</th>
      <th>PRIMARYPAY</th>
      <th>GENERALPAY</th>
      <th>RUNOFFPAY</th>
      <th>TOTALPAY</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>1</td>
      <td>E3E9CC9F-7443-43F6-94AF-B5A0F802DBA1</td>
      <td>1</td>
      <td>1315925633</td>
      <td>392904</td>
      <td>1315925633</td>
      <td>392904</td>
      <td>{\n  "invalidCells" : {\n    "1519001" : "TOTA...</td>
      <td>None</td>
      <td>CANDID</td>
      <td>CANDNAME</td>
      <td>None</td>
      <td>OFFICEBORO</td>
      <td>None</td>
      <td>CANCLASS</td>
      <td>None</td>
      <td>None</td>
      <td>None</td>
      <td>None</td>
    </tr>
    <tr>
      <th>1</th>
      <td>2</td>
      <td>9D257416-581A-4C42-85CC-B6EAD9DED97F</td>
      <td>2</td>
      <td>1315925633</td>
      <td>392904</td>
      <td>1315925633</td>
      <td>392904</td>
      <td>{\n}</td>
      <td>2001</td>
      <td>B4</td>
      <td>Aboulafia, Sandy</td>
      <td>5</td>
      <td>None</td>
      <td>44</td>
      <td>P</td>
      <td>45410.00</td>
      <td>0</td>
      <td>0</td>
      <td>45410.00</td>
    </tr>
    <tr>
      <th>2</th>
      <td>3</td>
      <td>B80D7891-93CF-49E8-86E8-182B618E68F2</td>
      <td>3</td>
      <td>1315925633</td>
      <td>392904</td>
      <td>1315925633</td>
      <td>392904</td>
      <td>{\n}</td>
      <td>2001</td>
      <td>445</td>
      <td>Adams, Jackie R</td>
      <td>5</td>
      <td>None</td>
      <td>7</td>
      <td>P</td>
      <td>11073.00</td>
      <td>0</td>
      <td>0</td>
      <td>11073.00</td>
    </tr>
    <tr>
      <th>3</th>
      <td>4</td>
      <td>BB012003-78F5-406D-8A87-7FF8A425EE3F</td>
      <td>4</td>
      <td>1315925633</td>
      <td>392904</td>
      <td>1315925633</td>
      <td>392904</td>
      <td>{\n}</td>
      <td>2001</td>
      <td>HF</td>
      <td>Addabbo, Joseph P</td>
      <td>5</td>
      <td>None</td>
      <td>32</td>
      <td>P</td>
      <td>75350.00</td>
      <td>73970.00</td>
      <td>0</td>
      <td>149320.00</td>
    </tr>
    <tr>
      <th>4</th>
      <td>5</td>
      <td>945825F9-2F5D-47C2-A16B-75B93E61E1AD</td>
      <td>5</td>
      <td>1315925633</td>
      <td>392904</td>
      <td>1315925633</td>
      <td>392904</td>
      <td>{\n}</td>
      <td>2001</td>
      <td>IR</td>
      <td>Alamo-Estrada, Agustin</td>
      <td>5</td>
      <td>None</td>
      <td>14</td>
      <td>P</td>
      <td>25000.00</td>
      <td>2400.00</td>
      <td>0</td>
      <td>27400.00</td>
    </tr>
  </tbody>
</table>
</div>



### What's wrong with the first row of the DataFrame?


```python
df.meta.iloc[0]
```




    '{\n  "invalidCells" : {\n    "1519001" : "TOTALPAY",\n    "1518998" : "PRIMARYPAY",\n    "1519000" : "RUNOFFPAY",\n    "1518999" : "GENERALPAY",\n    "1518994" : "OFFICECD",\n    "1518996" : "OFFICEDIST",\n    "1518991" : "ELECTION"\n  }\n}'



## Summary

Congratulations! You've started exploring some more JSON data structures used for the web and got to practice data munging and exploring!
