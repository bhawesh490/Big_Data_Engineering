```python
!pip install pymongo

```

    Requirement already satisfied: pymongo in c:\users\bhawe\appdata\local\packages\pythonsoftwarefoundation.python.3.7_qbz5n2kfra8p0\localcache\local-packages\python37\site-packages (4.3.3)
    Requirement already satisfied: dnspython<3.0.0,>=1.16.0 in c:\users\bhawe\appdata\local\packages\pythonsoftwarefoundation.python.3.7_qbz5n2kfra8p0\localcache\local-packages\python37\site-packages (from pymongo) (2.3.0)
    

    
    [notice] A new release of pip is available: 23.0.1 -> 23.1.1
    [notice] To update, run: C:\Users\bhawe\AppData\Local\Microsoft\WindowsApps\PythonSoftwareFoundation.Python.3.7_qbz5n2kfra8p0\python.exe -m pip install --upgrade pip
    


```python
import pymongo
```


```python
client=pymongo.MongoClient("mongodb://localhost:27017/")
```


```python
print (client)
```

    MongoClient(host=['localhost:27017'], document_class=dict, tz_aware=False, connect=True)
    


```python
# let's create a database
```


```python
DEFAULT_CONNECTION_URL="mongodb://localhost:27017/"
```


```python
DB_NAME="BigData"
```


```python
client=pymongo.MongoClient(DEFAULT_CONNECTION_URL)
print (client)
```

    MongoClient(host=['localhost:27017'], document_class=dict, tz_aware=False, connect=True)
    


```python
database=client[DB_NAME]
```


```python
COLLECTION_NAME='movies'
```


```python
collection=database[COLLECTION_NAME]
```


```python
list_of_movies=[{
  "_id": "10006546",
  "listing_url": "https://www.airbnb.com/rooms/10006546",
  "name": "Ribeira Charming Duplex",
  "summary": "Fantastic duplex apartment with three bedrooms, located in the historic area of Porto, Ribeira (Cube)...",
  "interaction": "Cot - 10 € / night Dog - € 7,5 / night",
  "house_rules": "Make the house your home...",
  "property_type": "House",
  "room_type": "Entire home/apt",
  "bed_type": "Real Bed",
  "minimum_nights": "2",
  "maximum_nights": "30",
  "cancellation_policy": "moderate",
  "last_scraped": {
    "$date": {
      "$numberLong": "1550293200000"
    }
  },
  "calendar_last_scraped": {
    "$date": {
      "$numberLong": "1550293200000"
    }
  },
  "first_review": {
    "$date": {
      "$numberLong": "1451797200000"
    }
  },
  "last_review": {
    "$date": {
      "$numberLong": "1547960400000"
    }
  },
  "accommodates": {
    "$numberInt": "8"
  },
  "bedrooms": {
    "$numberInt": "3"
  },
  "beds": {
    "$numberInt": "5"
  },
  "number_of_reviews": {
    "$numberInt": "51"
  },
  "bathrooms": {
    "$numberDecimal": "1.0"
  },
  "amenities": [
    "TV",
    "Cable TV",
    "Wifi",
    "Kitchen",
    "Paid parking off premises",
    "Smoking allowed",
    "Pets allowed",
    "Buzzer/wireless intercom",
    "Heating",
    "Family/kid friendly",
    "Washer",
    "First aid kit",
    "Fire extinguisher",
    "Essentials",
    "Hangers",
    "Hair dryer",
    "Iron",
    "Pack ’n Play/travel crib",
    "Room-darkening shades",
    "Hot water",
    "Bed linens",
    "Extra pillows and blankets",
    "Microwave",
    "Coffee maker",
    "Refrigerator",
    "Dishwasher",
    "Dishes and silverware",
    "Cooking basics",
    "Oven",
    "Stove",
    "Cleaning before checkout",
    "Waterfront"
  ],
  "price": {
    "$numberDecimal": "80.00"
  },
  "security_deposit": {
    "$numberDecimal": "200.00"
  },
  "cleaning_fee": {
    "$numberDecimal": "35.00"
  },
  "extra_people": {
    "$numberDecimal": "15.00"
  },
  "guests_included": {
    "$numberDecimal": "6"
  },
  "images": {
    "thumbnail_url": "",
    "medium_url": "",
    "picture_url": "https://a0.muscache.com/im/pictures/e83e702f-ef49-40fb-8fa0-6512d7e26e9b.jpg?aki_policy=large",
    "xl_picture_url": ""
  },
  "host": {
    "host_id": "51399391",
    "host_url": "https://www.airbnb.com/users/show/51399391",
    "host_name": "Ana&Gonçalo",
    "host_location": "Porto, Porto District, Portugal",
    "host_about": "Gostamos de passear, de viajar, de conhecer pessoas e locais novos, gostamos de desporto e animais! Vivemos na cidade mais linda do mundo!!!",
    "host_response_time": "within an hour",
    "host_thumbnail_url": "https://a0.muscache.com/im/pictures/fab79f25-2e10-4f0f-9711-663cb69dc7d8.jpg?aki_policy=profile_small",
    "host_picture_url": "https://a0.muscache.com/im/pictures/fab79f25-2e10-4f0f-9711-663cb69dc7d8.jpg?aki_policy=profile_x_medium",
    "host_neighbourhood": "",
    "host_response_rate": {
      "$numberInt": "100"
    },
    "host_is_superhost": False,
    "host_has_profile_pic": True,
    "host_identity_verified": True,
    "host_listings_count": {
      "$numberInt": "3"
    },
    "host_total_listings_count": {
      "$numberInt": "3"
    },
    "host_verifications": [
      "email",
      "phone",
      "reviews",
      "jumio",
      "offline_government_id",
      "government_id"
    ]
  },
  "address": {
    "street": "Porto, Porto, Portugal",
    "suburb": "",
    "government_area": "Cedofeita, Ildefonso, Sé, Miragaia, Nicolau, Vitória",
    "market": "Porto",
    "country": "Portugal",
    "country_code": "PT",
    "location": {
      "type": "Point",
      "coordinates": [
        {
          "$numberDouble": "-8.61308"
        },
        {
          "$numberDouble": "41.1413"
        }
      ],
      "is_location_exact": False
    }
  },
  "availability": {
    "availability_30": {
      "$numberInt": "28"
    },
    "availability_60": {
      "$numberInt": "47"
    },
    "availability_90": {
      "$numberInt": "74"
    },
    "availability_365": {
      "$numberInt": "239"
    }
  },
  "review_scores": {
    "review_scores_accuracy": {
      "$numberInt": "9"
    },
    "review_scores_cleanliness": {
      "$numberInt": "9"
    },
    "review_scores_checkin": {
      "$numberInt": "10"
    },
    "review_scores_communication": {
      "$numberInt": "10"
    },
    "review_scores_location": {
      "$numberInt": "10"
    },
    "review_scores_value": {
      "$numberInt": "9"
    },
    "review_scores_rating": {
      "$numberInt": "89"
    }
  },
  "reviews": [
    {
      "_id": "362865132",
      "date": {
        "$date": {
          "$numberLong": "1545886800000"
        }
      },
      "listing_id": "10006546",
      "reviewer_id": "208880077",
      "reviewer_name": "Thomas",
      "comments": "Very helpful hosts. Cooked traditional..."
    },
    {
      "_id": "364728730",
      "date": {
        "$date": {
          "$numberLong": "1546232400000"
        }
      },
      "listing_id": "10006546",
      "reviewer_id": "91827533",
      "reviewer_name": "Mr",
      "comments": "Ana & Goncalo were great on communication..."
    },
    {
      "_id": "403055315",
      "date": {
        "$date": {
          "$numberLong": "1547960400000"
        }
      },
      "listing_id": "10006546",
      "reviewer_id": "15138940",
      "reviewer_name": "Milo",
      "comments": "The house was extremely well located..."
    }
  ]
}]
```


```python
rec=collection.insert_many(list_of_movies)

```


```python
database.list_collection_names()

```




    ['movies']




```python
db_name_2='Learning'
```


```python
database=client[db_name_2]
```


```python
#function to check if database exists or not
def checkdatabase(db_name,client):
    db_list=client.list_database_names()
    if db_name in db_list:
        print (f"{db_name} exists as a database")
    else:
        print (f"{db_name} does not exists as a database")

checkdatabase(db_name='Learning',client=client)   

    
```

    Learning does not exists as a database
    


```python
checkdatabase('BigData',client)
```

    BigData exists as a database
    


```python
#create a Collection inside Learning Database
collection_name='test_table'
collection=database[collection_name]
```


```python
print (collection)
```

    Collection(Database(MongoClient(host=['localhost:27017'], document_class=dict, tz_aware=False, connect=True), 'Learning'), 'test_table')
    


```python
#Inserting documents inside this test_table using pandas 
import pandas as pd
```


```python
gre_data=pd.read_csv('https://raw.githubusercontent.com/vigneshk/Admission-Dataset/master/Admission.csv')
```


```python
gre_data.head(10)
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
      <th>Serial No.</th>
      <th>GRE Score</th>
      <th>TOEFL Score</th>
      <th>University Rating</th>
      <th>SOP</th>
      <th>LOR</th>
      <th>CGPA</th>
      <th>Research</th>
      <th>Chance of Admit</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>1</td>
      <td>337</td>
      <td>118</td>
      <td>4</td>
      <td>4.5</td>
      <td>4.5</td>
      <td>9.65</td>
      <td>1</td>
      <td>0.92</td>
    </tr>
    <tr>
      <th>1</th>
      <td>2</td>
      <td>324</td>
      <td>107</td>
      <td>4</td>
      <td>4.0</td>
      <td>4.5</td>
      <td>8.87</td>
      <td>1</td>
      <td>0.76</td>
    </tr>
    <tr>
      <th>2</th>
      <td>3</td>
      <td>316</td>
      <td>104</td>
      <td>3</td>
      <td>3.0</td>
      <td>3.5</td>
      <td>8.00</td>
      <td>1</td>
      <td>0.72</td>
    </tr>
    <tr>
      <th>3</th>
      <td>4</td>
      <td>322</td>
      <td>110</td>
      <td>3</td>
      <td>3.5</td>
      <td>2.5</td>
      <td>8.67</td>
      <td>1</td>
      <td>0.80</td>
    </tr>
    <tr>
      <th>4</th>
      <td>5</td>
      <td>314</td>
      <td>103</td>
      <td>2</td>
      <td>2.0</td>
      <td>3.0</td>
      <td>8.21</td>
      <td>0</td>
      <td>0.65</td>
    </tr>
    <tr>
      <th>5</th>
      <td>6</td>
      <td>330</td>
      <td>115</td>
      <td>5</td>
      <td>4.5</td>
      <td>3.0</td>
      <td>9.34</td>
      <td>1</td>
      <td>0.90</td>
    </tr>
    <tr>
      <th>6</th>
      <td>7</td>
      <td>321</td>
      <td>109</td>
      <td>3</td>
      <td>3.0</td>
      <td>4.0</td>
      <td>8.20</td>
      <td>1</td>
      <td>0.75</td>
    </tr>
    <tr>
      <th>7</th>
      <td>8</td>
      <td>308</td>
      <td>101</td>
      <td>2</td>
      <td>3.0</td>
      <td>4.0</td>
      <td>7.90</td>
      <td>0</td>
      <td>0.68</td>
    </tr>
    <tr>
      <th>8</th>
      <td>9</td>
      <td>302</td>
      <td>102</td>
      <td>1</td>
      <td>2.0</td>
      <td>1.5</td>
      <td>8.00</td>
      <td>0</td>
      <td>0.50</td>
    </tr>
    <tr>
      <th>9</th>
      <td>10</td>
      <td>323</td>
      <td>108</td>
      <td>3</td>
      <td>3.5</td>
      <td>3.0</td>
      <td>8.60</td>
      <td>0</td>
      <td>0.45</td>
    </tr>
  </tbody>
</table>
</div>




```python
json_format=gre_data.to_dict('records')
```


```python
json_format

```




    [{'Serial No.': 1,
      'GRE Score': 337,
      'TOEFL Score': 118,
      'University Rating': 4,
      'SOP': 4.5,
      'LOR ': 4.5,
      'CGPA': 9.65,
      'Research': 1,
      'Chance of Admit ': 0.92},
     {'Serial No.': 2,
      'GRE Score': 324,
      'TOEFL Score': 107,
      'University Rating': 4,
      'SOP': 4.0,
      'LOR ': 4.5,
      'CGPA': 8.87,
      'Research': 1,
      'Chance of Admit ': 0.76},
     {'Serial No.': 3,
      'GRE Score': 316,
      'TOEFL Score': 104,
      'University Rating': 3,
      'SOP': 3.0,
      'LOR ': 3.5,
      'CGPA': 8.0,
      'Research': 1,
      'Chance of Admit ': 0.72},
     {'Serial No.': 4,
      'GRE Score': 322,
      'TOEFL Score': 110,
      'University Rating': 3,
      'SOP': 3.5,
      'LOR ': 2.5,
      'CGPA': 8.67,
      'Research': 1,
      'Chance of Admit ': 0.8},
     {'Serial No.': 5,
      'GRE Score': 314,
      'TOEFL Score': 103,
      'University Rating': 2,
      'SOP': 2.0,
      'LOR ': 3.0,
      'CGPA': 8.21,
      'Research': 0,
      'Chance of Admit ': 0.65},
     {'Serial No.': 6,
      'GRE Score': 330,
      'TOEFL Score': 115,
      'University Rating': 5,
      'SOP': 4.5,
      'LOR ': 3.0,
      'CGPA': 9.34,
      'Research': 1,
      'Chance of Admit ': 0.9},
     {'Serial No.': 7,
      'GRE Score': 321,
      'TOEFL Score': 109,
      'University Rating': 3,
      'SOP': 3.0,
      'LOR ': 4.0,
      'CGPA': 8.2,
      'Research': 1,
      'Chance of Admit ': 0.75},
     {'Serial No.': 8,
      'GRE Score': 308,
      'TOEFL Score': 101,
      'University Rating': 2,
      'SOP': 3.0,
      'LOR ': 4.0,
      'CGPA': 7.9,
      'Research': 0,
      'Chance of Admit ': 0.68},
     {'Serial No.': 9,
      'GRE Score': 302,
      'TOEFL Score': 102,
      'University Rating': 1,
      'SOP': 2.0,
      'LOR ': 1.5,
      'CGPA': 8.0,
      'Research': 0,
      'Chance of Admit ': 0.5},
     {'Serial No.': 10,
      'GRE Score': 323,
      'TOEFL Score': 108,
      'University Rating': 3,
      'SOP': 3.5,
      'LOR ': 3.0,
      'CGPA': 8.6,
      'Research': 0,
      'Chance of Admit ': 0.45},
     {'Serial No.': 11,
      'GRE Score': 325,
      'TOEFL Score': 106,
      'University Rating': 3,
      'SOP': 3.5,
      'LOR ': 4.0,
      'CGPA': 8.4,
      'Research': 1,
      'Chance of Admit ': 0.52},
     {'Serial No.': 12,
      'GRE Score': 327,
      'TOEFL Score': 111,
      'University Rating': 4,
      'SOP': 4.0,
      'LOR ': 4.5,
      'CGPA': 9.0,
      'Research': 1,
      'Chance of Admit ': 0.84},
     {'Serial No.': 13,
      'GRE Score': 328,
      'TOEFL Score': 112,
      'University Rating': 4,
      'SOP': 4.0,
      'LOR ': 4.5,
      'CGPA': 9.1,
      'Research': 1,
      'Chance of Admit ': 0.78},
     {'Serial No.': 14,
      'GRE Score': 307,
      'TOEFL Score': 109,
      'University Rating': 3,
      'SOP': 4.0,
      'LOR ': 3.0,
      'CGPA': 8.0,
      'Research': 1,
      'Chance of Admit ': 0.62},
     {'Serial No.': 15,
      'GRE Score': 311,
      'TOEFL Score': 104,
      'University Rating': 3,
      'SOP': 3.5,
      'LOR ': 2.0,
      'CGPA': 8.2,
      'Research': 1,
      'Chance of Admit ': 0.61},
     {'Serial No.': 16,
      'GRE Score': 314,
      'TOEFL Score': 105,
      'University Rating': 3,
      'SOP': 3.5,
      'LOR ': 2.5,
      'CGPA': 8.3,
      'Research': 0,
      'Chance of Admit ': 0.54},
     {'Serial No.': 17,
      'GRE Score': 317,
      'TOEFL Score': 107,
      'University Rating': 3,
      'SOP': 4.0,
      'LOR ': 3.0,
      'CGPA': 8.7,
      'Research': 0,
      'Chance of Admit ': 0.66},
     {'Serial No.': 18,
      'GRE Score': 319,
      'TOEFL Score': 106,
      'University Rating': 3,
      'SOP': 4.0,
      'LOR ': 3.0,
      'CGPA': 8.0,
      'Research': 1,
      'Chance of Admit ': 0.65},
     {'Serial No.': 19,
      'GRE Score': 318,
      'TOEFL Score': 110,
      'University Rating': 3,
      'SOP': 4.0,
      'LOR ': 3.0,
      'CGPA': 8.8,
      'Research': 0,
      'Chance of Admit ': 0.63},
     {'Serial No.': 20,
      'GRE Score': 303,
      'TOEFL Score': 102,
      'University Rating': 3,
      'SOP': 3.5,
      'LOR ': 3.0,
      'CGPA': 8.5,
      'Research': 0,
      'Chance of Admit ': 0.62},
     {'Serial No.': 21,
      'GRE Score': 312,
      'TOEFL Score': 107,
      'University Rating': 3,
      'SOP': 3.0,
      'LOR ': 2.0,
      'CGPA': 7.9,
      'Research': 1,
      'Chance of Admit ': 0.64},
     {'Serial No.': 22,
      'GRE Score': 325,
      'TOEFL Score': 114,
      'University Rating': 4,
      'SOP': 3.0,
      'LOR ': 2.0,
      'CGPA': 8.4,
      'Research': 0,
      'Chance of Admit ': 0.7},
     {'Serial No.': 23,
      'GRE Score': 328,
      'TOEFL Score': 116,
      'University Rating': 5,
      'SOP': 5.0,
      'LOR ': 5.0,
      'CGPA': 9.5,
      'Research': 1,
      'Chance of Admit ': 0.94},
     {'Serial No.': 24,
      'GRE Score': 334,
      'TOEFL Score': 119,
      'University Rating': 5,
      'SOP': 5.0,
      'LOR ': 4.5,
      'CGPA': 9.7,
      'Research': 1,
      'Chance of Admit ': 0.95},
     {'Serial No.': 25,
      'GRE Score': 336,
      'TOEFL Score': 119,
      'University Rating': 5,
      'SOP': 4.0,
      'LOR ': 3.5,
      'CGPA': 9.8,
      'Research': 1,
      'Chance of Admit ': 0.97},
     {'Serial No.': 26,
      'GRE Score': 340,
      'TOEFL Score': 120,
      'University Rating': 5,
      'SOP': 4.5,
      'LOR ': 4.5,
      'CGPA': 9.6,
      'Research': 1,
      'Chance of Admit ': 0.94},
     {'Serial No.': 27,
      'GRE Score': 322,
      'TOEFL Score': 109,
      'University Rating': 5,
      'SOP': 4.5,
      'LOR ': 3.5,
      'CGPA': 8.8,
      'Research': 0,
      'Chance of Admit ': 0.76},
     {'Serial No.': 28,
      'GRE Score': 298,
      'TOEFL Score': 98,
      'University Rating': 2,
      'SOP': 1.5,
      'LOR ': 2.5,
      'CGPA': 7.5,
      'Research': 1,
      'Chance of Admit ': 0.44},
     {'Serial No.': 29,
      'GRE Score': 295,
      'TOEFL Score': 93,
      'University Rating': 1,
      'SOP': 2.0,
      'LOR ': 2.0,
      'CGPA': 7.2,
      'Research': 0,
      'Chance of Admit ': 0.46},
     {'Serial No.': 30,
      'GRE Score': 310,
      'TOEFL Score': 99,
      'University Rating': 2,
      'SOP': 1.5,
      'LOR ': 2.0,
      'CGPA': 7.3,
      'Research': 0,
      'Chance of Admit ': 0.54},
     {'Serial No.': 31,
      'GRE Score': 300,
      'TOEFL Score': 97,
      'University Rating': 2,
      'SOP': 3.0,
      'LOR ': 3.0,
      'CGPA': 8.1,
      'Research': 1,
      'Chance of Admit ': 0.65},
     {'Serial No.': 32,
      'GRE Score': 327,
      'TOEFL Score': 103,
      'University Rating': 3,
      'SOP': 4.0,
      'LOR ': 4.0,
      'CGPA': 8.3,
      'Research': 1,
      'Chance of Admit ': 0.74},
     {'Serial No.': 33,
      'GRE Score': 338,
      'TOEFL Score': 118,
      'University Rating': 4,
      'SOP': 3.0,
      'LOR ': 4.5,
      'CGPA': 9.4,
      'Research': 1,
      'Chance of Admit ': 0.91},
     {'Serial No.': 34,
      'GRE Score': 340,
      'TOEFL Score': 114,
      'University Rating': 5,
      'SOP': 4.0,
      'LOR ': 4.0,
      'CGPA': 9.6,
      'Research': 1,
      'Chance of Admit ': 0.9},
     {'Serial No.': 35,
      'GRE Score': 331,
      'TOEFL Score': 112,
      'University Rating': 5,
      'SOP': 4.0,
      'LOR ': 5.0,
      'CGPA': 9.8,
      'Research': 1,
      'Chance of Admit ': 0.94},
     {'Serial No.': 36,
      'GRE Score': 320,
      'TOEFL Score': 110,
      'University Rating': 5,
      'SOP': 5.0,
      'LOR ': 5.0,
      'CGPA': 9.2,
      'Research': 1,
      'Chance of Admit ': 0.88},
     {'Serial No.': 37,
      'GRE Score': 299,
      'TOEFL Score': 106,
      'University Rating': 2,
      'SOP': 4.0,
      'LOR ': 4.0,
      'CGPA': 8.4,
      'Research': 0,
      'Chance of Admit ': 0.64},
     {'Serial No.': 38,
      'GRE Score': 300,
      'TOEFL Score': 105,
      'University Rating': 1,
      'SOP': 1.0,
      'LOR ': 2.0,
      'CGPA': 7.8,
      'Research': 0,
      'Chance of Admit ': 0.58},
     {'Serial No.': 39,
      'GRE Score': 304,
      'TOEFL Score': 105,
      'University Rating': 1,
      'SOP': 3.0,
      'LOR ': 1.5,
      'CGPA': 7.5,
      'Research': 0,
      'Chance of Admit ': 0.52},
     {'Serial No.': 40,
      'GRE Score': 307,
      'TOEFL Score': 108,
      'University Rating': 2,
      'SOP': 4.0,
      'LOR ': 3.5,
      'CGPA': 7.7,
      'Research': 0,
      'Chance of Admit ': 0.48},
     {'Serial No.': 41,
      'GRE Score': 308,
      'TOEFL Score': 110,
      'University Rating': 3,
      'SOP': 3.5,
      'LOR ': 3.0,
      'CGPA': 8.0,
      'Research': 1,
      'Chance of Admit ': 0.46},
     {'Serial No.': 42,
      'GRE Score': 316,
      'TOEFL Score': 105,
      'University Rating': 2,
      'SOP': 2.5,
      'LOR ': 2.5,
      'CGPA': 8.2,
      'Research': 1,
      'Chance of Admit ': 0.49},
     {'Serial No.': 43,
      'GRE Score': 313,
      'TOEFL Score': 107,
      'University Rating': 2,
      'SOP': 2.5,
      'LOR ': 2.0,
      'CGPA': 8.5,
      'Research': 1,
      'Chance of Admit ': 0.53},
     {'Serial No.': 44,
      'GRE Score': 332,
      'TOEFL Score': 117,
      'University Rating': 4,
      'SOP': 4.5,
      'LOR ': 4.0,
      'CGPA': 9.1,
      'Research': 0,
      'Chance of Admit ': 0.87},
     {'Serial No.': 45,
      'GRE Score': 326,
      'TOEFL Score': 113,
      'University Rating': 5,
      'SOP': 4.5,
      'LOR ': 4.0,
      'CGPA': 9.4,
      'Research': 1,
      'Chance of Admit ': 0.91},
     {'Serial No.': 46,
      'GRE Score': 322,
      'TOEFL Score': 110,
      'University Rating': 5,
      'SOP': 5.0,
      'LOR ': 4.0,
      'CGPA': 9.1,
      'Research': 1,
      'Chance of Admit ': 0.88},
     {'Serial No.': 47,
      'GRE Score': 329,
      'TOEFL Score': 114,
      'University Rating': 5,
      'SOP': 4.0,
      'LOR ': 5.0,
      'CGPA': 9.3,
      'Research': 1,
      'Chance of Admit ': 0.86},
     {'Serial No.': 48,
      'GRE Score': 339,
      'TOEFL Score': 119,
      'University Rating': 5,
      'SOP': 4.5,
      'LOR ': 4.0,
      'CGPA': 9.7,
      'Research': 0,
      'Chance of Admit ': 0.89},
     {'Serial No.': 49,
      'GRE Score': 321,
      'TOEFL Score': 110,
      'University Rating': 3,
      'SOP': 3.5,
      'LOR ': 5.0,
      'CGPA': 8.85,
      'Research': 1,
      'Chance of Admit ': 0.82},
     {'Serial No.': 50,
      'GRE Score': 327,
      'TOEFL Score': 111,
      'University Rating': 4,
      'SOP': 3.0,
      'LOR ': 4.0,
      'CGPA': 8.4,
      'Research': 1,
      'Chance of Admit ': 0.78},
     {'Serial No.': 51,
      'GRE Score': 313,
      'TOEFL Score': 98,
      'University Rating': 3,
      'SOP': 2.5,
      'LOR ': 4.5,
      'CGPA': 8.3,
      'Research': 1,
      'Chance of Admit ': 0.76},
     {'Serial No.': 52,
      'GRE Score': 312,
      'TOEFL Score': 100,
      'University Rating': 2,
      'SOP': 1.5,
      'LOR ': 3.5,
      'CGPA': 7.9,
      'Research': 1,
      'Chance of Admit ': 0.56},
     {'Serial No.': 53,
      'GRE Score': 334,
      'TOEFL Score': 116,
      'University Rating': 4,
      'SOP': 4.0,
      'LOR ': 3.0,
      'CGPA': 8.0,
      'Research': 1,
      'Chance of Admit ': 0.78},
     {'Serial No.': 54,
      'GRE Score': 324,
      'TOEFL Score': 112,
      'University Rating': 4,
      'SOP': 4.0,
      'LOR ': 2.5,
      'CGPA': 8.1,
      'Research': 1,
      'Chance of Admit ': 0.72},
     {'Serial No.': 55,
      'GRE Score': 322,
      'TOEFL Score': 110,
      'University Rating': 3,
      'SOP': 3.0,
      'LOR ': 3.5,
      'CGPA': 8.0,
      'Research': 0,
      'Chance of Admit ': 0.7},
     {'Serial No.': 56,
      'GRE Score': 320,
      'TOEFL Score': 103,
      'University Rating': 3,
      'SOP': 3.0,
      'LOR ': 3.0,
      'CGPA': 7.7,
      'Research': 0,
      'Chance of Admit ': 0.64},
     {'Serial No.': 57,
      'GRE Score': 316,
      'TOEFL Score': 102,
      'University Rating': 3,
      'SOP': 2.0,
      'LOR ': 3.0,
      'CGPA': 7.4,
      'Research': 0,
      'Chance of Admit ': 0.64},
     {'Serial No.': 58,
      'GRE Score': 298,
      'TOEFL Score': 99,
      'University Rating': 2,
      'SOP': 4.0,
      'LOR ': 2.0,
      'CGPA': 7.6,
      'Research': 0,
      'Chance of Admit ': 0.46},
     {'Serial No.': 59,
      'GRE Score': 300,
      'TOEFL Score': 99,
      'University Rating': 1,
      'SOP': 3.0,
      'LOR ': 2.0,
      'CGPA': 6.8,
      'Research': 1,
      'Chance of Admit ': 0.36},
     {'Serial No.': 60,
      'GRE Score': 311,
      'TOEFL Score': 104,
      'University Rating': 2,
      'SOP': 2.0,
      'LOR ': 2.0,
      'CGPA': 8.3,
      'Research': 0,
      'Chance of Admit ': 0.42},
     {'Serial No.': 61,
      'GRE Score': 309,
      'TOEFL Score': 100,
      'University Rating': 2,
      'SOP': 3.0,
      'LOR ': 3.0,
      'CGPA': 8.1,
      'Research': 0,
      'Chance of Admit ': 0.48},
     {'Serial No.': 62,
      'GRE Score': 307,
      'TOEFL Score': 101,
      'University Rating': 3,
      'SOP': 4.0,
      'LOR ': 3.0,
      'CGPA': 8.2,
      'Research': 0,
      'Chance of Admit ': 0.47},
     {'Serial No.': 63,
      'GRE Score': 304,
      'TOEFL Score': 105,
      'University Rating': 2,
      'SOP': 3.0,
      'LOR ': 3.0,
      'CGPA': 8.2,
      'Research': 1,
      'Chance of Admit ': 0.54},
     {'Serial No.': 64,
      'GRE Score': 315,
      'TOEFL Score': 107,
      'University Rating': 2,
      'SOP': 4.0,
      'LOR ': 3.0,
      'CGPA': 8.5,
      'Research': 1,
      'Chance of Admit ': 0.56},
     {'Serial No.': 65,
      'GRE Score': 325,
      'TOEFL Score': 111,
      'University Rating': 3,
      'SOP': 3.0,
      'LOR ': 3.5,
      'CGPA': 8.7,
      'Research': 0,
      'Chance of Admit ': 0.52},
     {'Serial No.': 66,
      'GRE Score': 325,
      'TOEFL Score': 112,
      'University Rating': 4,
      'SOP': 3.5,
      'LOR ': 3.5,
      'CGPA': 8.92,
      'Research': 0,
      'Chance of Admit ': 0.55},
     {'Serial No.': 67,
      'GRE Score': 327,
      'TOEFL Score': 114,
      'University Rating': 3,
      'SOP': 3.0,
      'LOR ': 3.0,
      'CGPA': 9.02,
      'Research': 0,
      'Chance of Admit ': 0.61},
     {'Serial No.': 68,
      'GRE Score': 316,
      'TOEFL Score': 107,
      'University Rating': 2,
      'SOP': 3.5,
      'LOR ': 3.5,
      'CGPA': 8.64,
      'Research': 1,
      'Chance of Admit ': 0.57},
     {'Serial No.': 69,
      'GRE Score': 318,
      'TOEFL Score': 109,
      'University Rating': 3,
      'SOP': 3.5,
      'LOR ': 4.0,
      'CGPA': 9.22,
      'Research': 1,
      'Chance of Admit ': 0.68},
     {'Serial No.': 70,
      'GRE Score': 328,
      'TOEFL Score': 115,
      'University Rating': 4,
      'SOP': 4.5,
      'LOR ': 4.0,
      'CGPA': 9.16,
      'Research': 1,
      'Chance of Admit ': 0.78},
     {'Serial No.': 71,
      'GRE Score': 332,
      'TOEFL Score': 118,
      'University Rating': 5,
      'SOP': 5.0,
      'LOR ': 5.0,
      'CGPA': 9.64,
      'Research': 1,
      'Chance of Admit ': 0.94},
     {'Serial No.': 72,
      'GRE Score': 336,
      'TOEFL Score': 112,
      'University Rating': 5,
      'SOP': 5.0,
      'LOR ': 5.0,
      'CGPA': 9.76,
      'Research': 1,
      'Chance of Admit ': 0.96},
     {'Serial No.': 73,
      'GRE Score': 321,
      'TOEFL Score': 111,
      'University Rating': 5,
      'SOP': 5.0,
      'LOR ': 5.0,
      'CGPA': 9.45,
      'Research': 1,
      'Chance of Admit ': 0.93},
     {'Serial No.': 74,
      'GRE Score': 314,
      'TOEFL Score': 108,
      'University Rating': 4,
      'SOP': 4.5,
      'LOR ': 4.0,
      'CGPA': 9.04,
      'Research': 1,
      'Chance of Admit ': 0.84},
     {'Serial No.': 75,
      'GRE Score': 314,
      'TOEFL Score': 106,
      'University Rating': 3,
      'SOP': 3.0,
      'LOR ': 5.0,
      'CGPA': 8.9,
      'Research': 0,
      'Chance of Admit ': 0.74},
     {'Serial No.': 76,
      'GRE Score': 329,
      'TOEFL Score': 114,
      'University Rating': 2,
      'SOP': 2.0,
      'LOR ': 4.0,
      'CGPA': 8.56,
      'Research': 1,
      'Chance of Admit ': 0.72},
     {'Serial No.': 77,
      'GRE Score': 327,
      'TOEFL Score': 112,
      'University Rating': 3,
      'SOP': 3.0,
      'LOR ': 3.0,
      'CGPA': 8.72,
      'Research': 1,
      'Chance of Admit ': 0.74},
     {'Serial No.': 78,
      'GRE Score': 301,
      'TOEFL Score': 99,
      'University Rating': 2,
      'SOP': 3.0,
      'LOR ': 2.0,
      'CGPA': 8.22,
      'Research': 0,
      'Chance of Admit ': 0.64},
     {'Serial No.': 79,
      'GRE Score': 296,
      'TOEFL Score': 95,
      'University Rating': 2,
      'SOP': 3.0,
      'LOR ': 2.0,
      'CGPA': 7.54,
      'Research': 1,
      'Chance of Admit ': 0.44},
     {'Serial No.': 80,
      'GRE Score': 294,
      'TOEFL Score': 93,
      'University Rating': 1,
      'SOP': 1.5,
      'LOR ': 2.0,
      'CGPA': 7.36,
      'Research': 0,
      'Chance of Admit ': 0.46},
     {'Serial No.': 81,
      'GRE Score': 312,
      'TOEFL Score': 105,
      'University Rating': 3,
      'SOP': 2.0,
      'LOR ': 3.0,
      'CGPA': 8.02,
      'Research': 1,
      'Chance of Admit ': 0.5},
     {'Serial No.': 82,
      'GRE Score': 340,
      'TOEFL Score': 120,
      'University Rating': 4,
      'SOP': 5.0,
      'LOR ': 5.0,
      'CGPA': 9.5,
      'Research': 1,
      'Chance of Admit ': 0.96},
     {'Serial No.': 83,
      'GRE Score': 320,
      'TOEFL Score': 110,
      'University Rating': 5,
      'SOP': 5.0,
      'LOR ': 4.5,
      'CGPA': 9.22,
      'Research': 1,
      'Chance of Admit ': 0.92},
     {'Serial No.': 84,
      'GRE Score': 322,
      'TOEFL Score': 115,
      'University Rating': 5,
      'SOP': 4.0,
      'LOR ': 4.5,
      'CGPA': 9.36,
      'Research': 1,
      'Chance of Admit ': 0.92},
     {'Serial No.': 85,
      'GRE Score': 340,
      'TOEFL Score': 115,
      'University Rating': 5,
      'SOP': 4.5,
      'LOR ': 4.5,
      'CGPA': 9.45,
      'Research': 1,
      'Chance of Admit ': 0.94},
     {'Serial No.': 86,
      'GRE Score': 319,
      'TOEFL Score': 103,
      'University Rating': 4,
      'SOP': 4.5,
      'LOR ': 3.5,
      'CGPA': 8.66,
      'Research': 0,
      'Chance of Admit ': 0.76},
     {'Serial No.': 87,
      'GRE Score': 315,
      'TOEFL Score': 106,
      'University Rating': 3,
      'SOP': 4.5,
      'LOR ': 3.5,
      'CGPA': 8.42,
      'Research': 0,
      'Chance of Admit ': 0.72},
     {'Serial No.': 88,
      'GRE Score': 317,
      'TOEFL Score': 107,
      'University Rating': 2,
      'SOP': 3.5,
      'LOR ': 3.0,
      'CGPA': 8.28,
      'Research': 0,
      'Chance of Admit ': 0.66},
     {'Serial No.': 89,
      'GRE Score': 314,
      'TOEFL Score': 108,
      'University Rating': 3,
      'SOP': 4.5,
      'LOR ': 3.5,
      'CGPA': 8.14,
      'Research': 0,
      'Chance of Admit ': 0.64},
     {'Serial No.': 90,
      'GRE Score': 316,
      'TOEFL Score': 109,
      'University Rating': 4,
      'SOP': 4.5,
      'LOR ': 3.5,
      'CGPA': 8.76,
      'Research': 1,
      'Chance of Admit ': 0.74},
     {'Serial No.': 91,
      'GRE Score': 318,
      'TOEFL Score': 106,
      'University Rating': 2,
      'SOP': 4.0,
      'LOR ': 4.0,
      'CGPA': 7.92,
      'Research': 1,
      'Chance of Admit ': 0.64},
     {'Serial No.': 92,
      'GRE Score': 299,
      'TOEFL Score': 97,
      'University Rating': 3,
      'SOP': 5.0,
      'LOR ': 3.5,
      'CGPA': 7.66,
      'Research': 0,
      'Chance of Admit ': 0.38},
     {'Serial No.': 93,
      'GRE Score': 298,
      'TOEFL Score': 98,
      'University Rating': 2,
      'SOP': 4.0,
      'LOR ': 3.0,
      'CGPA': 8.03,
      'Research': 0,
      'Chance of Admit ': 0.34},
     {'Serial No.': 94,
      'GRE Score': 301,
      'TOEFL Score': 97,
      'University Rating': 2,
      'SOP': 3.0,
      'LOR ': 3.0,
      'CGPA': 7.88,
      'Research': 1,
      'Chance of Admit ': 0.44},
     {'Serial No.': 95,
      'GRE Score': 303,
      'TOEFL Score': 99,
      'University Rating': 3,
      'SOP': 2.0,
      'LOR ': 2.5,
      'CGPA': 7.66,
      'Research': 0,
      'Chance of Admit ': 0.36},
     {'Serial No.': 96,
      'GRE Score': 304,
      'TOEFL Score': 100,
      'University Rating': 4,
      'SOP': 1.5,
      'LOR ': 2.5,
      'CGPA': 7.84,
      'Research': 0,
      'Chance of Admit ': 0.42},
     {'Serial No.': 97,
      'GRE Score': 306,
      'TOEFL Score': 100,
      'University Rating': 2,
      'SOP': 3.0,
      'LOR ': 3.0,
      'CGPA': 8.0,
      'Research': 0,
      'Chance of Admit ': 0.48},
     {'Serial No.': 98,
      'GRE Score': 331,
      'TOEFL Score': 120,
      'University Rating': 3,
      'SOP': 4.0,
      'LOR ': 4.0,
      'CGPA': 8.96,
      'Research': 1,
      'Chance of Admit ': 0.86},
     {'Serial No.': 99,
      'GRE Score': 332,
      'TOEFL Score': 119,
      'University Rating': 4,
      'SOP': 5.0,
      'LOR ': 4.5,
      'CGPA': 9.24,
      'Research': 1,
      'Chance of Admit ': 0.9},
     {'Serial No.': 100,
      'GRE Score': 323,
      'TOEFL Score': 113,
      'University Rating': 3,
      'SOP': 4.0,
      'LOR ': 4.0,
      'CGPA': 8.88,
      'Research': 1,
      'Chance of Admit ': 0.79},
     {'Serial No.': 101,
      'GRE Score': 322,
      'TOEFL Score': 107,
      'University Rating': 3,
      'SOP': 3.5,
      'LOR ': 3.5,
      'CGPA': 8.46,
      'Research': 1,
      'Chance of Admit ': 0.71},
     {'Serial No.': 102,
      'GRE Score': 312,
      'TOEFL Score': 105,
      'University Rating': 2,
      'SOP': 2.5,
      'LOR ': 3.0,
      'CGPA': 8.12,
      'Research': 0,
      'Chance of Admit ': 0.64},
     {'Serial No.': 103,
      'GRE Score': 314,
      'TOEFL Score': 106,
      'University Rating': 2,
      'SOP': 4.0,
      'LOR ': 3.5,
      'CGPA': 8.25,
      'Research': 0,
      'Chance of Admit ': 0.62},
     {'Serial No.': 104,
      'GRE Score': 317,
      'TOEFL Score': 104,
      'University Rating': 2,
      'SOP': 4.5,
      'LOR ': 4.0,
      'CGPA': 8.47,
      'Research': 0,
      'Chance of Admit ': 0.57},
     {'Serial No.': 105,
      'GRE Score': 326,
      'TOEFL Score': 112,
      'University Rating': 3,
      'SOP': 3.5,
      'LOR ': 3.0,
      'CGPA': 9.05,
      'Research': 1,
      'Chance of Admit ': 0.74},
     {'Serial No.': 106,
      'GRE Score': 316,
      'TOEFL Score': 110,
      'University Rating': 3,
      'SOP': 4.0,
      'LOR ': 4.5,
      'CGPA': 8.78,
      'Research': 1,
      'Chance of Admit ': 0.69},
     {'Serial No.': 107,
      'GRE Score': 329,
      'TOEFL Score': 111,
      'University Rating': 4,
      'SOP': 4.5,
      'LOR ': 4.5,
      'CGPA': 9.18,
      'Research': 1,
      'Chance of Admit ': 0.87},
     {'Serial No.': 108,
      'GRE Score': 338,
      'TOEFL Score': 117,
      'University Rating': 4,
      'SOP': 3.5,
      'LOR ': 4.5,
      'CGPA': 9.46,
      'Research': 1,
      'Chance of Admit ': 0.91},
     {'Serial No.': 109,
      'GRE Score': 331,
      'TOEFL Score': 116,
      'University Rating': 5,
      'SOP': 5.0,
      'LOR ': 5.0,
      'CGPA': 9.38,
      'Research': 1,
      'Chance of Admit ': 0.93},
     {'Serial No.': 110,
      'GRE Score': 304,
      'TOEFL Score': 103,
      'University Rating': 5,
      'SOP': 5.0,
      'LOR ': 4.0,
      'CGPA': 8.64,
      'Research': 0,
      'Chance of Admit ': 0.68},
     {'Serial No.': 111,
      'GRE Score': 305,
      'TOEFL Score': 108,
      'University Rating': 5,
      'SOP': 3.0,
      'LOR ': 3.0,
      'CGPA': 8.48,
      'Research': 0,
      'Chance of Admit ': 0.61},
     {'Serial No.': 112,
      'GRE Score': 321,
      'TOEFL Score': 109,
      'University Rating': 4,
      'SOP': 4.0,
      'LOR ': 4.0,
      'CGPA': 8.68,
      'Research': 1,
      'Chance of Admit ': 0.69},
     {'Serial No.': 113,
      'GRE Score': 301,
      'TOEFL Score': 107,
      'University Rating': 3,
      'SOP': 3.5,
      'LOR ': 3.5,
      'CGPA': 8.34,
      'Research': 1,
      'Chance of Admit ': 0.62},
     {'Serial No.': 114,
      'GRE Score': 320,
      'TOEFL Score': 110,
      'University Rating': 2,
      'SOP': 4.0,
      'LOR ': 3.5,
      'CGPA': 8.56,
      'Research': 0,
      'Chance of Admit ': 0.72},
     {'Serial No.': 115,
      'GRE Score': 311,
      'TOEFL Score': 105,
      'University Rating': 3,
      'SOP': 3.5,
      'LOR ': 3.0,
      'CGPA': 8.45,
      'Research': 1,
      'Chance of Admit ': 0.59},
     {'Serial No.': 116,
      'GRE Score': 310,
      'TOEFL Score': 106,
      'University Rating': 4,
      'SOP': 4.5,
      'LOR ': 4.5,
      'CGPA': 9.04,
      'Research': 1,
      'Chance of Admit ': 0.66},
     {'Serial No.': 117,
      'GRE Score': 299,
      'TOEFL Score': 102,
      'University Rating': 3,
      'SOP': 4.0,
      'LOR ': 3.5,
      'CGPA': 8.62,
      'Research': 0,
      'Chance of Admit ': 0.56},
     {'Serial No.': 118,
      'GRE Score': 290,
      'TOEFL Score': 104,
      'University Rating': 4,
      'SOP': 2.0,
      'LOR ': 2.5,
      'CGPA': 7.46,
      'Research': 0,
      'Chance of Admit ': 0.45},
     {'Serial No.': 119,
      'GRE Score': 296,
      'TOEFL Score': 99,
      'University Rating': 2,
      'SOP': 3.0,
      'LOR ': 3.5,
      'CGPA': 7.28,
      'Research': 0,
      'Chance of Admit ': 0.47},
     {'Serial No.': 120,
      'GRE Score': 327,
      'TOEFL Score': 104,
      'University Rating': 5,
      'SOP': 3.0,
      'LOR ': 3.5,
      'CGPA': 8.84,
      'Research': 1,
      'Chance of Admit ': 0.71},
     {'Serial No.': 121,
      'GRE Score': 335,
      'TOEFL Score': 117,
      'University Rating': 5,
      'SOP': 5.0,
      'LOR ': 5.0,
      'CGPA': 9.56,
      'Research': 1,
      'Chance of Admit ': 0.94},
     {'Serial No.': 122,
      'GRE Score': 334,
      'TOEFL Score': 119,
      'University Rating': 5,
      'SOP': 4.5,
      'LOR ': 4.5,
      'CGPA': 9.48,
      'Research': 1,
      'Chance of Admit ': 0.94},
     {'Serial No.': 123,
      'GRE Score': 310,
      'TOEFL Score': 106,
      'University Rating': 4,
      'SOP': 1.5,
      'LOR ': 2.5,
      'CGPA': 8.36,
      'Research': 0,
      'Chance of Admit ': 0.57},
     {'Serial No.': 124,
      'GRE Score': 308,
      'TOEFL Score': 108,
      'University Rating': 3,
      'SOP': 3.5,
      'LOR ': 3.5,
      'CGPA': 8.22,
      'Research': 0,
      'Chance of Admit ': 0.61},
     {'Serial No.': 125,
      'GRE Score': 301,
      'TOEFL Score': 106,
      'University Rating': 4,
      'SOP': 2.5,
      'LOR ': 3.0,
      'CGPA': 8.47,
      'Research': 0,
      'Chance of Admit ': 0.57},
     {'Serial No.': 126,
      'GRE Score': 300,
      'TOEFL Score': 100,
      'University Rating': 3,
      'SOP': 2.0,
      'LOR ': 3.0,
      'CGPA': 8.66,
      'Research': 1,
      'Chance of Admit ': 0.64},
     {'Serial No.': 127,
      'GRE Score': 323,
      'TOEFL Score': 113,
      'University Rating': 3,
      'SOP': 4.0,
      'LOR ': 3.0,
      'CGPA': 9.32,
      'Research': 1,
      'Chance of Admit ': 0.85},
     {'Serial No.': 128,
      'GRE Score': 319,
      'TOEFL Score': 112,
      'University Rating': 3,
      'SOP': 2.5,
      'LOR ': 2.0,
      'CGPA': 8.71,
      'Research': 1,
      'Chance of Admit ': 0.78},
     {'Serial No.': 129,
      'GRE Score': 326,
      'TOEFL Score': 112,
      'University Rating': 3,
      'SOP': 3.5,
      'LOR ': 3.0,
      'CGPA': 9.1,
      'Research': 1,
      'Chance of Admit ': 0.84},
     {'Serial No.': 130,
      'GRE Score': 333,
      'TOEFL Score': 118,
      'University Rating': 5,
      'SOP': 5.0,
      'LOR ': 5.0,
      'CGPA': 9.35,
      'Research': 1,
      'Chance of Admit ': 0.92},
     {'Serial No.': 131,
      'GRE Score': 339,
      'TOEFL Score': 114,
      'University Rating': 5,
      'SOP': 4.0,
      'LOR ': 4.5,
      'CGPA': 9.76,
      'Research': 1,
      'Chance of Admit ': 0.96},
     {'Serial No.': 132,
      'GRE Score': 303,
      'TOEFL Score': 105,
      'University Rating': 5,
      'SOP': 5.0,
      'LOR ': 4.5,
      'CGPA': 8.65,
      'Research': 0,
      'Chance of Admit ': 0.77},
     {'Serial No.': 133,
      'GRE Score': 309,
      'TOEFL Score': 105,
      'University Rating': 5,
      'SOP': 3.5,
      'LOR ': 3.5,
      'CGPA': 8.56,
      'Research': 0,
      'Chance of Admit ': 0.71},
     {'Serial No.': 134,
      'GRE Score': 323,
      'TOEFL Score': 112,
      'University Rating': 5,
      'SOP': 4.0,
      'LOR ': 4.5,
      'CGPA': 8.78,
      'Research': 0,
      'Chance of Admit ': 0.79},
     {'Serial No.': 135,
      'GRE Score': 333,
      'TOEFL Score': 113,
      'University Rating': 5,
      'SOP': 4.0,
      'LOR ': 4.0,
      'CGPA': 9.28,
      'Research': 1,
      'Chance of Admit ': 0.89},
     {'Serial No.': 136,
      'GRE Score': 314,
      'TOEFL Score': 109,
      'University Rating': 4,
      'SOP': 3.5,
      'LOR ': 4.0,
      'CGPA': 8.77,
      'Research': 1,
      'Chance of Admit ': 0.82},
     {'Serial No.': 137,
      'GRE Score': 312,
      'TOEFL Score': 103,
      'University Rating': 3,
      'SOP': 5.0,
      'LOR ': 4.0,
      'CGPA': 8.45,
      'Research': 0,
      'Chance of Admit ': 0.76},
     {'Serial No.': 138,
      'GRE Score': 316,
      'TOEFL Score': 100,
      'University Rating': 2,
      'SOP': 1.5,
      'LOR ': 3.0,
      'CGPA': 8.16,
      'Research': 1,
      'Chance of Admit ': 0.71},
     {'Serial No.': 139,
      'GRE Score': 326,
      'TOEFL Score': 116,
      'University Rating': 2,
      'SOP': 4.5,
      'LOR ': 3.0,
      'CGPA': 9.08,
      'Research': 1,
      'Chance of Admit ': 0.8},
     {'Serial No.': 140,
      'GRE Score': 318,
      'TOEFL Score': 109,
      'University Rating': 1,
      'SOP': 3.5,
      'LOR ': 3.5,
      'CGPA': 9.12,
      'Research': 0,
      'Chance of Admit ': 0.78},
     {'Serial No.': 141,
      'GRE Score': 329,
      'TOEFL Score': 110,
      'University Rating': 2,
      'SOP': 4.0,
      'LOR ': 3.0,
      'CGPA': 9.15,
      'Research': 1,
      'Chance of Admit ': 0.84},
     {'Serial No.': 142,
      'GRE Score': 332,
      'TOEFL Score': 118,
      'University Rating': 2,
      'SOP': 4.5,
      'LOR ': 3.5,
      'CGPA': 9.36,
      'Research': 1,
      'Chance of Admit ': 0.9},
     {'Serial No.': 143,
      'GRE Score': 331,
      'TOEFL Score': 115,
      'University Rating': 5,
      'SOP': 4.0,
      'LOR ': 3.5,
      'CGPA': 9.44,
      'Research': 1,
      'Chance of Admit ': 0.92},
     {'Serial No.': 144,
      'GRE Score': 340,
      'TOEFL Score': 120,
      'University Rating': 4,
      'SOP': 4.5,
      'LOR ': 4.0,
      'CGPA': 9.92,
      'Research': 1,
      'Chance of Admit ': 0.97},
     {'Serial No.': 145,
      'GRE Score': 325,
      'TOEFL Score': 112,
      'University Rating': 2,
      'SOP': 3.0,
      'LOR ': 3.5,
      'CGPA': 8.96,
      'Research': 1,
      'Chance of Admit ': 0.8},
     {'Serial No.': 146,
      'GRE Score': 320,
      'TOEFL Score': 113,
      'University Rating': 2,
      'SOP': 2.0,
      'LOR ': 2.5,
      'CGPA': 8.64,
      'Research': 1,
      'Chance of Admit ': 0.81},
     {'Serial No.': 147,
      'GRE Score': 315,
      'TOEFL Score': 105,
      'University Rating': 3,
      'SOP': 2.0,
      'LOR ': 2.5,
      'CGPA': 8.48,
      'Research': 0,
      'Chance of Admit ': 0.75},
     {'Serial No.': 148,
      'GRE Score': 326,
      'TOEFL Score': 114,
      'University Rating': 3,
      'SOP': 3.0,
      'LOR ': 3.0,
      'CGPA': 9.11,
      'Research': 1,
      'Chance of Admit ': 0.83},
     {'Serial No.': 149,
      'GRE Score': 339,
      'TOEFL Score': 116,
      'University Rating': 4,
      'SOP': 4.0,
      'LOR ': 3.5,
      'CGPA': 9.8,
      'Research': 1,
      'Chance of Admit ': 0.96},
     {'Serial No.': 150,
      'GRE Score': 311,
      'TOEFL Score': 106,
      'University Rating': 2,
      'SOP': 3.5,
      'LOR ': 3.0,
      'CGPA': 8.26,
      'Research': 1,
      'Chance of Admit ': 0.79},
     {'Serial No.': 151,
      'GRE Score': 334,
      'TOEFL Score': 114,
      'University Rating': 4,
      'SOP': 4.0,
      'LOR ': 4.0,
      'CGPA': 9.43,
      'Research': 1,
      'Chance of Admit ': 0.93},
     {'Serial No.': 152,
      'GRE Score': 332,
      'TOEFL Score': 116,
      'University Rating': 5,
      'SOP': 5.0,
      'LOR ': 5.0,
      'CGPA': 9.28,
      'Research': 1,
      'Chance of Admit ': 0.94},
     {'Serial No.': 153,
      'GRE Score': 321,
      'TOEFL Score': 112,
      'University Rating': 5,
      'SOP': 5.0,
      'LOR ': 5.0,
      'CGPA': 9.06,
      'Research': 1,
      'Chance of Admit ': 0.86},
     {'Serial No.': 154,
      'GRE Score': 324,
      'TOEFL Score': 105,
      'University Rating': 3,
      'SOP': 3.0,
      'LOR ': 4.0,
      'CGPA': 8.75,
      'Research': 0,
      'Chance of Admit ': 0.79},
     {'Serial No.': 155,
      'GRE Score': 326,
      'TOEFL Score': 108,
      'University Rating': 3,
      'SOP': 3.0,
      'LOR ': 3.5,
      'CGPA': 8.89,
      'Research': 0,
      'Chance of Admit ': 0.8},
     {'Serial No.': 156,
      'GRE Score': 312,
      'TOEFL Score': 109,
      'University Rating': 3,
      'SOP': 3.0,
      'LOR ': 3.0,
      'CGPA': 8.69,
      'Research': 0,
      'Chance of Admit ': 0.77},
     {'Serial No.': 157,
      'GRE Score': 315,
      'TOEFL Score': 105,
      'University Rating': 3,
      'SOP': 2.0,
      'LOR ': 2.5,
      'CGPA': 8.34,
      'Research': 0,
      'Chance of Admit ': 0.7},
     {'Serial No.': 158,
      'GRE Score': 309,
      'TOEFL Score': 104,
      'University Rating': 2,
      'SOP': 2.0,
      'LOR ': 2.5,
      'CGPA': 8.26,
      'Research': 0,
      'Chance of Admit ': 0.65},
     {'Serial No.': 159,
      'GRE Score': 306,
      'TOEFL Score': 106,
      'University Rating': 2,
      'SOP': 2.0,
      'LOR ': 2.5,
      'CGPA': 8.14,
      'Research': 0,
      'Chance of Admit ': 0.61},
     {'Serial No.': 160,
      'GRE Score': 297,
      'TOEFL Score': 100,
      'University Rating': 1,
      'SOP': 1.5,
      'LOR ': 2.0,
      'CGPA': 7.9,
      'Research': 0,
      'Chance of Admit ': 0.52},
     {'Serial No.': 161,
      'GRE Score': 315,
      'TOEFL Score': 103,
      'University Rating': 1,
      'SOP': 1.5,
      'LOR ': 2.0,
      'CGPA': 7.86,
      'Research': 0,
      'Chance of Admit ': 0.57},
     {'Serial No.': 162,
      'GRE Score': 298,
      'TOEFL Score': 99,
      'University Rating': 1,
      'SOP': 1.5,
      'LOR ': 3.0,
      'CGPA': 7.46,
      'Research': 0,
      'Chance of Admit ': 0.53},
     {'Serial No.': 163,
      'GRE Score': 318,
      'TOEFL Score': 109,
      'University Rating': 3,
      'SOP': 3.0,
      'LOR ': 3.0,
      'CGPA': 8.5,
      'Research': 0,
      'Chance of Admit ': 0.67},
     {'Serial No.': 164,
      'GRE Score': 317,
      'TOEFL Score': 105,
      'University Rating': 3,
      'SOP': 3.5,
      'LOR ': 3.0,
      'CGPA': 8.56,
      'Research': 0,
      'Chance of Admit ': 0.68},
     {'Serial No.': 165,
      'GRE Score': 329,
      'TOEFL Score': 111,
      'University Rating': 4,
      'SOP': 4.5,
      'LOR ': 4.0,
      'CGPA': 9.01,
      'Research': 1,
      'Chance of Admit ': 0.81},
     {'Serial No.': 166,
      'GRE Score': 322,
      'TOEFL Score': 110,
      'University Rating': 5,
      'SOP': 4.5,
      'LOR ': 4.0,
      'CGPA': 8.97,
      'Research': 0,
      'Chance of Admit ': 0.78},
     {'Serial No.': 167,
      'GRE Score': 302,
      'TOEFL Score': 102,
      'University Rating': 3,
      'SOP': 3.5,
      'LOR ': 5.0,
      'CGPA': 8.33,
      'Research': 0,
      'Chance of Admit ': 0.65},
     {'Serial No.': 168,
      'GRE Score': 313,
      'TOEFL Score': 102,
      'University Rating': 3,
      'SOP': 2.0,
      'LOR ': 3.0,
      'CGPA': 8.27,
      'Research': 0,
      'Chance of Admit ': 0.64},
     {'Serial No.': 169,
      'GRE Score': 293,
      'TOEFL Score': 97,
      'University Rating': 2,
      'SOP': 2.0,
      'LOR ': 4.0,
      'CGPA': 7.8,
      'Research': 1,
      'Chance of Admit ': 0.64},
     {'Serial No.': 170,
      'GRE Score': 311,
      'TOEFL Score': 99,
      'University Rating': 2,
      'SOP': 2.5,
      'LOR ': 3.0,
      'CGPA': 7.98,
      'Research': 0,
      'Chance of Admit ': 0.65},
     {'Serial No.': 171,
      'GRE Score': 312,
      'TOEFL Score': 101,
      'University Rating': 2,
      'SOP': 2.5,
      'LOR ': 3.5,
      'CGPA': 8.04,
      'Research': 1,
      'Chance of Admit ': 0.68},
     {'Serial No.': 172,
      'GRE Score': 334,
      'TOEFL Score': 117,
      'University Rating': 5,
      'SOP': 4.0,
      'LOR ': 4.5,
      'CGPA': 9.07,
      'Research': 1,
      'Chance of Admit ': 0.89},
     {'Serial No.': 173,
      'GRE Score': 322,
      'TOEFL Score': 110,
      'University Rating': 4,
      'SOP': 4.0,
      'LOR ': 5.0,
      'CGPA': 9.13,
      'Research': 1,
      'Chance of Admit ': 0.86},
     {'Serial No.': 174,
      'GRE Score': 323,
      'TOEFL Score': 113,
      'University Rating': 4,
      'SOP': 4.0,
      'LOR ': 4.5,
      'CGPA': 9.23,
      'Research': 1,
      'Chance of Admit ': 0.89},
     {'Serial No.': 175,
      'GRE Score': 321,
      'TOEFL Score': 111,
      'University Rating': 4,
      'SOP': 4.0,
      'LOR ': 4.0,
      'CGPA': 8.97,
      'Research': 1,
      'Chance of Admit ': 0.87},
     {'Serial No.': 176,
      'GRE Score': 320,
      'TOEFL Score': 111,
      'University Rating': 4,
      'SOP': 4.5,
      'LOR ': 3.5,
      'CGPA': 8.87,
      'Research': 1,
      'Chance of Admit ': 0.85},
     {'Serial No.': 177,
      'GRE Score': 329,
      'TOEFL Score': 119,
      'University Rating': 4,
      'SOP': 4.5,
      'LOR ': 4.5,
      'CGPA': 9.16,
      'Research': 1,
      'Chance of Admit ': 0.9},
     {'Serial No.': 178,
      'GRE Score': 319,
      'TOEFL Score': 110,
      'University Rating': 3,
      'SOP': 3.5,
      'LOR ': 3.5,
      'CGPA': 9.04,
      'Research': 0,
      'Chance of Admit ': 0.82},
     {'Serial No.': 179,
      'GRE Score': 309,
      'TOEFL Score': 108,
      'University Rating': 3,
      'SOP': 2.5,
      'LOR ': 3.0,
      'CGPA': 8.12,
      'Research': 0,
      'Chance of Admit ': 0.72},
     {'Serial No.': 180,
      'GRE Score': 307,
      'TOEFL Score': 102,
      'University Rating': 3,
      'SOP': 3.0,
      'LOR ': 3.0,
      'CGPA': 8.27,
      'Research': 0,
      'Chance of Admit ': 0.73},
     {'Serial No.': 181,
      'GRE Score': 300,
      'TOEFL Score': 104,
      'University Rating': 3,
      'SOP': 3.5,
      'LOR ': 3.0,
      'CGPA': 8.16,
      'Research': 0,
      'Chance of Admit ': 0.71},
     {'Serial No.': 182,
      'GRE Score': 305,
      'TOEFL Score': 107,
      'University Rating': 2,
      'SOP': 2.5,
      'LOR ': 2.5,
      'CGPA': 8.42,
      'Research': 0,
      'Chance of Admit ': 0.71},
     {'Serial No.': 183,
      'GRE Score': 299,
      'TOEFL Score': 100,
      'University Rating': 2,
      'SOP': 3.0,
      'LOR ': 3.5,
      'CGPA': 7.88,
      'Research': 0,
      'Chance of Admit ': 0.68},
     {'Serial No.': 184,
      'GRE Score': 314,
      'TOEFL Score': 110,
      'University Rating': 3,
      'SOP': 4.0,
      'LOR ': 4.0,
      'CGPA': 8.8,
      'Research': 0,
      'Chance of Admit ': 0.75},
     {'Serial No.': 185,
      'GRE Score': 316,
      'TOEFL Score': 106,
      'University Rating': 2,
      'SOP': 2.5,
      'LOR ': 4.0,
      'CGPA': 8.32,
      'Research': 0,
      'Chance of Admit ': 0.72},
     {'Serial No.': 186,
      'GRE Score': 327,
      'TOEFL Score': 113,
      'University Rating': 4,
      'SOP': 4.5,
      'LOR ': 4.5,
      'CGPA': 9.11,
      'Research': 1,
      'Chance of Admit ': 0.89},
     {'Serial No.': 187,
      'GRE Score': 317,
      'TOEFL Score': 107,
      'University Rating': 3,
      'SOP': 3.5,
      'LOR ': 3.0,
      'CGPA': 8.68,
      'Research': 1,
      'Chance of Admit ': 0.84},
     {'Serial No.': 188,
      'GRE Score': 335,
      'TOEFL Score': 118,
      'University Rating': 5,
      'SOP': 4.5,
      'LOR ': 3.5,
      'CGPA': 9.44,
      'Research': 1,
      'Chance of Admit ': 0.93},
     {'Serial No.': 189,
      'GRE Score': 331,
      'TOEFL Score': 115,
      'University Rating': 5,
      'SOP': 4.5,
      'LOR ': 3.5,
      'CGPA': 9.36,
      'Research': 1,
      'Chance of Admit ': 0.93},
     {'Serial No.': 190,
      'GRE Score': 324,
      'TOEFL Score': 112,
      'University Rating': 5,
      'SOP': 5.0,
      'LOR ': 5.0,
      'CGPA': 9.08,
      'Research': 1,
      'Chance of Admit ': 0.88},
     {'Serial No.': 191,
      'GRE Score': 324,
      'TOEFL Score': 111,
      'University Rating': 5,
      'SOP': 4.5,
      'LOR ': 4.0,
      'CGPA': 9.16,
      'Research': 1,
      'Chance of Admit ': 0.9},
     {'Serial No.': 192,
      'GRE Score': 323,
      'TOEFL Score': 110,
      'University Rating': 5,
      'SOP': 4.0,
      'LOR ': 5.0,
      'CGPA': 8.98,
      'Research': 1,
      'Chance of Admit ': 0.87},
     {'Serial No.': 193,
      'GRE Score': 322,
      'TOEFL Score': 114,
      'University Rating': 5,
      'SOP': 4.5,
      'LOR ': 4.0,
      'CGPA': 8.94,
      'Research': 1,
      'Chance of Admit ': 0.86},
     {'Serial No.': 194,
      'GRE Score': 336,
      'TOEFL Score': 118,
      'University Rating': 5,
      'SOP': 4.5,
      'LOR ': 5.0,
      'CGPA': 9.53,
      'Research': 1,
      'Chance of Admit ': 0.94},
     {'Serial No.': 195,
      'GRE Score': 316,
      'TOEFL Score': 109,
      'University Rating': 3,
      'SOP': 3.5,
      'LOR ': 3.0,
      'CGPA': 8.76,
      'Research': 0,
      'Chance of Admit ': 0.77},
     {'Serial No.': 196,
      'GRE Score': 307,
      'TOEFL Score': 107,
      'University Rating': 2,
      'SOP': 3.0,
      'LOR ': 3.5,
      'CGPA': 8.52,
      'Research': 1,
      'Chance of Admit ': 0.78},
     {'Serial No.': 197,
      'GRE Score': 306,
      'TOEFL Score': 105,
      'University Rating': 2,
      'SOP': 3.0,
      'LOR ': 2.5,
      'CGPA': 8.26,
      'Research': 0,
      'Chance of Admit ': 0.73},
     {'Serial No.': 198,
      'GRE Score': 310,
      'TOEFL Score': 106,
      'University Rating': 2,
      'SOP': 3.5,
      'LOR ': 2.5,
      'CGPA': 8.33,
      'Research': 0,
      'Chance of Admit ': 0.73},
     {'Serial No.': 199,
      'GRE Score': 311,
      'TOEFL Score': 104,
      'University Rating': 3,
      'SOP': 4.5,
      'LOR ': 4.5,
      'CGPA': 8.43,
      'Research': 0,
      'Chance of Admit ': 0.7},
     {'Serial No.': 200,
      'GRE Score': 313,
      'TOEFL Score': 107,
      'University Rating': 3,
      'SOP': 4.0,
      'LOR ': 4.5,
      'CGPA': 8.69,
      'Research': 0,
      'Chance of Admit ': 0.72},
     {'Serial No.': 201,
      'GRE Score': 317,
      'TOEFL Score': 103,
      'University Rating': 3,
      'SOP': 2.5,
      'LOR ': 3.0,
      'CGPA': 8.54,
      'Research': 1,
      'Chance of Admit ': 0.73},
     {'Serial No.': 202,
      'GRE Score': 315,
      'TOEFL Score': 110,
      'University Rating': 2,
      'SOP': 3.5,
      'LOR ': 3.0,
      'CGPA': 8.46,
      'Research': 1,
      'Chance of Admit ': 0.72},
     {'Serial No.': 203,
      'GRE Score': 340,
      'TOEFL Score': 120,
      'University Rating': 5,
      'SOP': 4.5,
      'LOR ': 4.5,
      'CGPA': 9.91,
      'Research': 1,
      'Chance of Admit ': 0.97},
     {'Serial No.': 204,
      'GRE Score': 334,
      'TOEFL Score': 120,
      'University Rating': 5,
      'SOP': 4.0,
      'LOR ': 5.0,
      'CGPA': 9.87,
      'Research': 1,
      'Chance of Admit ': 0.97},
     {'Serial No.': 205,
      'GRE Score': 298,
      'TOEFL Score': 105,
      'University Rating': 3,
      'SOP': 3.5,
      'LOR ': 4.0,
      'CGPA': 8.54,
      'Research': 0,
      'Chance of Admit ': 0.69},
     {'Serial No.': 206,
      'GRE Score': 295,
      'TOEFL Score': 99,
      'University Rating': 2,
      'SOP': 2.5,
      'LOR ': 3.0,
      'CGPA': 7.65,
      'Research': 0,
      'Chance of Admit ': 0.57},
     {'Serial No.': 207,
      'GRE Score': 315,
      'TOEFL Score': 99,
      'University Rating': 2,
      'SOP': 3.5,
      'LOR ': 3.0,
      'CGPA': 7.89,
      'Research': 0,
      'Chance of Admit ': 0.63},
     {'Serial No.': 208,
      'GRE Score': 310,
      'TOEFL Score': 102,
      'University Rating': 3,
      'SOP': 3.5,
      'LOR ': 4.0,
      'CGPA': 8.02,
      'Research': 1,
      'Chance of Admit ': 0.66},
     {'Serial No.': 209,
      'GRE Score': 305,
      'TOEFL Score': 106,
      'University Rating': 2,
      'SOP': 3.0,
      'LOR ': 3.0,
      'CGPA': 8.16,
      'Research': 0,
      'Chance of Admit ': 0.64},
     {'Serial No.': 210,
      'GRE Score': 301,
      'TOEFL Score': 104,
      'University Rating': 3,
      'SOP': 3.5,
      'LOR ': 4.0,
      'CGPA': 8.12,
      'Research': 1,
      'Chance of Admit ': 0.68},
     {'Serial No.': 211,
      'GRE Score': 325,
      'TOEFL Score': 108,
      'University Rating': 4,
      'SOP': 4.5,
      'LOR ': 4.0,
      'CGPA': 9.06,
      'Research': 1,
      'Chance of Admit ': 0.79},
     {'Serial No.': 212,
      'GRE Score': 328,
      'TOEFL Score': 110,
      'University Rating': 4,
      'SOP': 5.0,
      'LOR ': 4.0,
      'CGPA': 9.14,
      'Research': 1,
      'Chance of Admit ': 0.82},
     {'Serial No.': 213,
      'GRE Score': 338,
      'TOEFL Score': 120,
      'University Rating': 4,
      'SOP': 5.0,
      'LOR ': 5.0,
      'CGPA': 9.66,
      'Research': 1,
      'Chance of Admit ': 0.95},
     {'Serial No.': 214,
      'GRE Score': 333,
      'TOEFL Score': 119,
      'University Rating': 5,
      'SOP': 5.0,
      'LOR ': 4.5,
      'CGPA': 9.78,
      'Research': 1,
      'Chance of Admit ': 0.96},
     {'Serial No.': 215,
      'GRE Score': 331,
      'TOEFL Score': 117,
      'University Rating': 4,
      'SOP': 4.5,
      'LOR ': 5.0,
      'CGPA': 9.42,
      'Research': 1,
      'Chance of Admit ': 0.94},
     {'Serial No.': 216,
      'GRE Score': 330,
      'TOEFL Score': 116,
      'University Rating': 5,
      'SOP': 5.0,
      'LOR ': 4.5,
      'CGPA': 9.36,
      'Research': 1,
      'Chance of Admit ': 0.93},
     {'Serial No.': 217,
      'GRE Score': 322,
      'TOEFL Score': 112,
      'University Rating': 4,
      'SOP': 4.5,
      'LOR ': 4.5,
      'CGPA': 9.26,
      'Research': 1,
      'Chance of Admit ': 0.91},
     {'Serial No.': 218,
      'GRE Score': 321,
      'TOEFL Score': 109,
      'University Rating': 4,
      'SOP': 4.0,
      'LOR ': 4.0,
      'CGPA': 9.13,
      'Research': 1,
      'Chance of Admit ': 0.85},
     {'Serial No.': 219,
      'GRE Score': 324,
      'TOEFL Score': 110,
      'University Rating': 4,
      'SOP': 3.0,
      'LOR ': 3.5,
      'CGPA': 8.97,
      'Research': 1,
      'Chance of Admit ': 0.84},
     {'Serial No.': 220,
      'GRE Score': 312,
      'TOEFL Score': 104,
      'University Rating': 3,
      'SOP': 3.5,
      'LOR ': 3.5,
      'CGPA': 8.42,
      'Research': 0,
      'Chance of Admit ': 0.74},
     {'Serial No.': 221,
      'GRE Score': 313,
      'TOEFL Score': 103,
      'University Rating': 3,
      'SOP': 4.0,
      'LOR ': 4.0,
      'CGPA': 8.75,
      'Research': 0,
      'Chance of Admit ': 0.76},
     {'Serial No.': 222,
      'GRE Score': 316,
      'TOEFL Score': 110,
      'University Rating': 3,
      'SOP': 3.5,
      'LOR ': 4.0,
      'CGPA': 8.56,
      'Research': 0,
      'Chance of Admit ': 0.75},
     {'Serial No.': 223,
      'GRE Score': 324,
      'TOEFL Score': 113,
      'University Rating': 4,
      'SOP': 4.5,
      'LOR ': 4.0,
      'CGPA': 8.79,
      'Research': 0,
      'Chance of Admit ': 0.76},
     {'Serial No.': 224,
      'GRE Score': 308,
      'TOEFL Score': 109,
      'University Rating': 2,
      'SOP': 3.0,
      'LOR ': 4.0,
      'CGPA': 8.45,
      'Research': 0,
      'Chance of Admit ': 0.71},
     {'Serial No.': 225,
      'GRE Score': 305,
      'TOEFL Score': 105,
      'University Rating': 2,
      'SOP': 3.0,
      'LOR ': 2.0,
      'CGPA': 8.23,
      'Research': 0,
      'Chance of Admit ': 0.67},
     {'Serial No.': 226,
      'GRE Score': 296,
      'TOEFL Score': 99,
      'University Rating': 2,
      'SOP': 2.5,
      'LOR ': 2.5,
      'CGPA': 8.03,
      'Research': 0,
      'Chance of Admit ': 0.61},
     {'Serial No.': 227,
      'GRE Score': 306,
      'TOEFL Score': 110,
      'University Rating': 2,
      'SOP': 3.5,
      'LOR ': 4.0,
      'CGPA': 8.45,
      'Research': 0,
      'Chance of Admit ': 0.63},
     {'Serial No.': 228,
      'GRE Score': 312,
      'TOEFL Score': 110,
      'University Rating': 2,
      'SOP': 3.5,
      'LOR ': 3.0,
      'CGPA': 8.53,
      'Research': 0,
      'Chance of Admit ': 0.64},
     {'Serial No.': 229,
      'GRE Score': 318,
      'TOEFL Score': 112,
      'University Rating': 3,
      'SOP': 4.0,
      'LOR ': 3.5,
      'CGPA': 8.67,
      'Research': 0,
      'Chance of Admit ': 0.71},
     {'Serial No.': 230,
      'GRE Score': 324,
      'TOEFL Score': 111,
      'University Rating': 4,
      'SOP': 3.0,
      'LOR ': 3.0,
      'CGPA': 9.01,
      'Research': 1,
      'Chance of Admit ': 0.82},
     {'Serial No.': 231,
      'GRE Score': 313,
      'TOEFL Score': 104,
      'University Rating': 3,
      'SOP': 4.0,
      'LOR ': 4.5,
      'CGPA': 8.65,
      'Research': 0,
      'Chance of Admit ': 0.73},
     {'Serial No.': 232,
      'GRE Score': 319,
      'TOEFL Score': 106,
      'University Rating': 3,
      'SOP': 3.5,
      'LOR ': 2.5,
      'CGPA': 8.33,
      'Research': 1,
      'Chance of Admit ': 0.74},
     {'Serial No.': 233,
      'GRE Score': 312,
      'TOEFL Score': 107,
      'University Rating': 2,
      'SOP': 2.5,
      'LOR ': 3.5,
      'CGPA': 8.27,
      'Research': 0,
      'Chance of Admit ': 0.69},
     {'Serial No.': 234,
      'GRE Score': 304,
      'TOEFL Score': 100,
      'University Rating': 2,
      'SOP': 2.5,
      'LOR ': 3.5,
      'CGPA': 8.07,
      'Research': 0,
      'Chance of Admit ': 0.64},
     {'Serial No.': 235,
      'GRE Score': 330,
      'TOEFL Score': 113,
      'University Rating': 5,
      'SOP': 5.0,
      'LOR ': 4.0,
      'CGPA': 9.31,
      'Research': 1,
      'Chance of Admit ': 0.91},
     {'Serial No.': 236,
      'GRE Score': 326,
      'TOEFL Score': 111,
      'University Rating': 5,
      'SOP': 4.5,
      'LOR ': 4.0,
      'CGPA': 9.23,
      'Research': 1,
      'Chance of Admit ': 0.88},
     {'Serial No.': 237,
      'GRE Score': 325,
      'TOEFL Score': 112,
      'University Rating': 4,
      'SOP': 4.0,
      'LOR ': 4.5,
      'CGPA': 9.17,
      'Research': 1,
      'Chance of Admit ': 0.85},
     {'Serial No.': 238,
      'GRE Score': 329,
      'TOEFL Score': 114,
      'University Rating': 5,
      'SOP': 4.5,
      'LOR ': 5.0,
      'CGPA': 9.19,
      'Research': 1,
      'Chance of Admit ': 0.86},
     {'Serial No.': 239,
      'GRE Score': 310,
      'TOEFL Score': 104,
      'University Rating': 3,
      'SOP': 2.0,
      'LOR ': 3.5,
      'CGPA': 8.37,
      'Research': 0,
      'Chance of Admit ': 0.7},
     {'Serial No.': 240,
      'GRE Score': 299,
      'TOEFL Score': 100,
      'University Rating': 1,
      'SOP': 1.5,
      'LOR ': 2.0,
      'CGPA': 7.89,
      'Research': 0,
      'Chance of Admit ': 0.59},
     {'Serial No.': 241,
      'GRE Score': 296,
      'TOEFL Score': 101,
      'University Rating': 1,
      'SOP': 2.5,
      'LOR ': 3.0,
      'CGPA': 7.68,
      'Research': 0,
      'Chance of Admit ': 0.6},
     {'Serial No.': 242,
      'GRE Score': 317,
      'TOEFL Score': 103,
      'University Rating': 2,
      'SOP': 2.5,
      'LOR ': 2.0,
      'CGPA': 8.15,
      'Research': 0,
      'Chance of Admit ': 0.65},
     {'Serial No.': 243,
      'GRE Score': 324,
      'TOEFL Score': 115,
      'University Rating': 3,
      'SOP': 3.5,
      'LOR ': 3.0,
      'CGPA': 8.76,
      'Research': 1,
      'Chance of Admit ': 0.7},
     {'Serial No.': 244,
      'GRE Score': 325,
      'TOEFL Score': 114,
      'University Rating': 3,
      'SOP': 3.5,
      'LOR ': 3.0,
      'CGPA': 9.04,
      'Research': 1,
      'Chance of Admit ': 0.76},
     {'Serial No.': 245,
      'GRE Score': 314,
      'TOEFL Score': 107,
      'University Rating': 2,
      'SOP': 2.5,
      'LOR ': 4.0,
      'CGPA': 8.56,
      'Research': 0,
      'Chance of Admit ': 0.63},
     {'Serial No.': 246,
      'GRE Score': 328,
      'TOEFL Score': 110,
      'University Rating': 4,
      'SOP': 4.0,
      'LOR ': 2.5,
      'CGPA': 9.02,
      'Research': 1,
      'Chance of Admit ': 0.81},
     {'Serial No.': 247,
      'GRE Score': 316,
      'TOEFL Score': 105,
      'University Rating': 3,
      'SOP': 3.0,
      'LOR ': 3.5,
      'CGPA': 8.73,
      'Research': 0,
      'Chance of Admit ': 0.72},
     {'Serial No.': 248,
      'GRE Score': 311,
      'TOEFL Score': 104,
      'University Rating': 2,
      'SOP': 2.5,
      'LOR ': 3.5,
      'CGPA': 8.48,
      'Research': 0,
      'Chance of Admit ': 0.71},
     {'Serial No.': 249,
      'GRE Score': 324,
      'TOEFL Score': 110,
      'University Rating': 3,
      'SOP': 3.5,
      'LOR ': 4.0,
      'CGPA': 8.87,
      'Research': 1,
      'Chance of Admit ': 0.8},
     {'Serial No.': 250,
      'GRE Score': 321,
      'TOEFL Score': 111,
      'University Rating': 3,
      'SOP': 3.5,
      'LOR ': 4.0,
      'CGPA': 8.83,
      'Research': 1,
      'Chance of Admit ': 0.77},
     {'Serial No.': 251,
      'GRE Score': 320,
      'TOEFL Score': 104,
      'University Rating': 3,
      'SOP': 3.0,
      'LOR ': 2.5,
      'CGPA': 8.57,
      'Research': 1,
      'Chance of Admit ': 0.74},
     {'Serial No.': 252,
      'GRE Score': 316,
      'TOEFL Score': 99,
      'University Rating': 2,
      'SOP': 2.5,
      'LOR ': 3.0,
      'CGPA': 9.0,
      'Research': 0,
      'Chance of Admit ': 0.7},
     {'Serial No.': 253,
      'GRE Score': 318,
      'TOEFL Score': 100,
      'University Rating': 2,
      'SOP': 2.5,
      'LOR ': 3.5,
      'CGPA': 8.54,
      'Research': 1,
      'Chance of Admit ': 0.71},
     {'Serial No.': 254,
      'GRE Score': 335,
      'TOEFL Score': 115,
      'University Rating': 4,
      'SOP': 4.5,
      'LOR ': 4.5,
      'CGPA': 9.68,
      'Research': 1,
      'Chance of Admit ': 0.93},
     {'Serial No.': 255,
      'GRE Score': 321,
      'TOEFL Score': 114,
      'University Rating': 4,
      'SOP': 4.0,
      'LOR ': 5.0,
      'CGPA': 9.12,
      'Research': 0,
      'Chance of Admit ': 0.85},
     {'Serial No.': 256,
      'GRE Score': 307,
      'TOEFL Score': 110,
      'University Rating': 4,
      'SOP': 4.0,
      'LOR ': 4.5,
      'CGPA': 8.37,
      'Research': 0,
      'Chance of Admit ': 0.79},
     {'Serial No.': 257,
      'GRE Score': 309,
      'TOEFL Score': 99,
      'University Rating': 3,
      'SOP': 4.0,
      'LOR ': 4.0,
      'CGPA': 8.56,
      'Research': 0,
      'Chance of Admit ': 0.76},
     {'Serial No.': 258,
      'GRE Score': 324,
      'TOEFL Score': 100,
      'University Rating': 3,
      'SOP': 4.0,
      'LOR ': 5.0,
      'CGPA': 8.64,
      'Research': 1,
      'Chance of Admit ': 0.78},
     {'Serial No.': 259,
      'GRE Score': 326,
      'TOEFL Score': 102,
      'University Rating': 4,
      'SOP': 5.0,
      'LOR ': 5.0,
      'CGPA': 8.76,
      'Research': 1,
      'Chance of Admit ': 0.77},
     {'Serial No.': 260,
      'GRE Score': 331,
      'TOEFL Score': 119,
      'University Rating': 4,
      'SOP': 5.0,
      'LOR ': 4.5,
      'CGPA': 9.34,
      'Research': 1,
      'Chance of Admit ': 0.9},
     {'Serial No.': 261,
      'GRE Score': 327,
      'TOEFL Score': 108,
      'University Rating': 5,
      'SOP': 5.0,
      'LOR ': 3.5,
      'CGPA': 9.13,
      'Research': 1,
      'Chance of Admit ': 0.87},
     {'Serial No.': 262,
      'GRE Score': 312,
      'TOEFL Score': 104,
      'University Rating': 3,
      'SOP': 3.5,
      'LOR ': 4.0,
      'CGPA': 8.09,
      'Research': 0,
      'Chance of Admit ': 0.71},
     {'Serial No.': 263,
      'GRE Score': 308,
      'TOEFL Score': 103,
      'University Rating': 2,
      'SOP': 2.5,
      'LOR ': 4.0,
      'CGPA': 8.36,
      'Research': 1,
      'Chance of Admit ': 0.7},
     {'Serial No.': 264,
      'GRE Score': 324,
      'TOEFL Score': 111,
      'University Rating': 3,
      'SOP': 2.5,
      'LOR ': 1.5,
      'CGPA': 8.79,
      'Research': 1,
      'Chance of Admit ': 0.7},
     {'Serial No.': 265,
      'GRE Score': 325,
      'TOEFL Score': 110,
      'University Rating': 2,
      'SOP': 3.0,
      'LOR ': 2.5,
      'CGPA': 8.76,
      'Research': 1,
      'Chance of Admit ': 0.75},
     {'Serial No.': 266,
      'GRE Score': 313,
      'TOEFL Score': 102,
      'University Rating': 3,
      'SOP': 2.5,
      'LOR ': 2.5,
      'CGPA': 8.68,
      'Research': 0,
      'Chance of Admit ': 0.71},
     {'Serial No.': 267,
      'GRE Score': 312,
      'TOEFL Score': 105,
      'University Rating': 2,
      'SOP': 2.0,
      'LOR ': 2.5,
      'CGPA': 8.45,
      'Research': 0,
      'Chance of Admit ': 0.72},
     {'Serial No.': 268,
      'GRE Score': 314,
      'TOEFL Score': 107,
      'University Rating': 3,
      'SOP': 3.0,
      'LOR ': 3.5,
      'CGPA': 8.17,
      'Research': 1,
      'Chance of Admit ': 0.73},
     {'Serial No.': 269,
      'GRE Score': 327,
      'TOEFL Score': 113,
      'University Rating': 4,
      'SOP': 4.5,
      'LOR ': 5.0,
      'CGPA': 9.14,
      'Research': 0,
      'Chance of Admit ': 0.83},
     {'Serial No.': 270,
      'GRE Score': 308,
      'TOEFL Score': 108,
      'University Rating': 4,
      'SOP': 4.5,
      'LOR ': 5.0,
      'CGPA': 8.34,
      'Research': 0,
      'Chance of Admit ': 0.77},
     {'Serial No.': 271,
      'GRE Score': 306,
      'TOEFL Score': 105,
      'University Rating': 2,
      'SOP': 2.5,
      'LOR ': 3.0,
      'CGPA': 8.22,
      'Research': 1,
      'Chance of Admit ': 0.72},
     {'Serial No.': 272,
      'GRE Score': 299,
      'TOEFL Score': 96,
      'University Rating': 2,
      'SOP': 1.5,
      'LOR ': 2.0,
      'CGPA': 7.86,
      'Research': 0,
      'Chance of Admit ': 0.54},
     {'Serial No.': 273,
      'GRE Score': 294,
      'TOEFL Score': 95,
      'University Rating': 1,
      'SOP': 1.5,
      'LOR ': 1.5,
      'CGPA': 7.64,
      'Research': 0,
      'Chance of Admit ': 0.49},
     {'Serial No.': 274,
      'GRE Score': 312,
      'TOEFL Score': 99,
      'University Rating': 1,
      'SOP': 1.0,
      'LOR ': 1.5,
      'CGPA': 8.01,
      'Research': 1,
      'Chance of Admit ': 0.52},
     {'Serial No.': 275,
      'GRE Score': 315,
      'TOEFL Score': 100,
      'University Rating': 1,
      'SOP': 2.0,
      'LOR ': 2.5,
      'CGPA': 7.95,
      'Research': 0,
      'Chance of Admit ': 0.58},
     {'Serial No.': 276,
      'GRE Score': 322,
      'TOEFL Score': 110,
      'University Rating': 3,
      'SOP': 3.5,
      'LOR ': 3.0,
      'CGPA': 8.96,
      'Research': 1,
      'Chance of Admit ': 0.78},
     {'Serial No.': 277,
      'GRE Score': 329,
      'TOEFL Score': 113,
      'University Rating': 5,
      'SOP': 5.0,
      'LOR ': 4.5,
      'CGPA': 9.45,
      'Research': 1,
      'Chance of Admit ': 0.89},
     {'Serial No.': 278,
      'GRE Score': 320,
      'TOEFL Score': 101,
      'University Rating': 2,
      'SOP': 2.5,
      'LOR ': 3.0,
      'CGPA': 8.62,
      'Research': 0,
      'Chance of Admit ': 0.7},
     {'Serial No.': 279,
      'GRE Score': 308,
      'TOEFL Score': 103,
      'University Rating': 2,
      'SOP': 3.0,
      'LOR ': 3.5,
      'CGPA': 8.49,
      'Research': 0,
      'Chance of Admit ': 0.66},
     {'Serial No.': 280,
      'GRE Score': 304,
      'TOEFL Score': 102,
      'University Rating': 2,
      'SOP': 3.0,
      'LOR ': 4.0,
      'CGPA': 8.73,
      'Research': 0,
      'Chance of Admit ': 0.67},
     {'Serial No.': 281,
      'GRE Score': 311,
      'TOEFL Score': 102,
      'University Rating': 3,
      'SOP': 4.5,
      'LOR ': 4.0,
      'CGPA': 8.64,
      'Research': 1,
      'Chance of Admit ': 0.68},
     {'Serial No.': 282,
      'GRE Score': 317,
      'TOEFL Score': 110,
      'University Rating': 3,
      'SOP': 4.0,
      'LOR ': 4.5,
      'CGPA': 9.11,
      'Research': 1,
      'Chance of Admit ': 0.8},
     {'Serial No.': 283,
      'GRE Score': 312,
      'TOEFL Score': 106,
      'University Rating': 3,
      'SOP': 4.0,
      'LOR ': 3.5,
      'CGPA': 8.79,
      'Research': 1,
      'Chance of Admit ': 0.81},
     {'Serial No.': 284,
      'GRE Score': 321,
      'TOEFL Score': 111,
      'University Rating': 3,
      'SOP': 2.5,
      'LOR ': 3.0,
      'CGPA': 8.9,
      'Research': 1,
      'Chance of Admit ': 0.8},
     {'Serial No.': 285,
      'GRE Score': 340,
      'TOEFL Score': 112,
      'University Rating': 4,
      'SOP': 5.0,
      'LOR ': 4.5,
      'CGPA': 9.66,
      'Research': 1,
      'Chance of Admit ': 0.94},
     {'Serial No.': 286,
      'GRE Score': 331,
      'TOEFL Score': 116,
      'University Rating': 5,
      'SOP': 4.0,
      'LOR ': 4.0,
      'CGPA': 9.26,
      'Research': 1,
      'Chance of Admit ': 0.93},
     {'Serial No.': 287,
      'GRE Score': 336,
      'TOEFL Score': 118,
      'University Rating': 5,
      'SOP': 4.5,
      'LOR ': 4.0,
      'CGPA': 9.19,
      'Research': 1,
      'Chance of Admit ': 0.92},
     {'Serial No.': 288,
      'GRE Score': 324,
      'TOEFL Score': 114,
      'University Rating': 5,
      'SOP': 5.0,
      'LOR ': 4.5,
      'CGPA': 9.08,
      'Research': 1,
      'Chance of Admit ': 0.89},
     {'Serial No.': 289,
      'GRE Score': 314,
      'TOEFL Score': 104,
      'University Rating': 4,
      'SOP': 5.0,
      'LOR ': 5.0,
      'CGPA': 9.02,
      'Research': 0,
      'Chance of Admit ': 0.82},
     {'Serial No.': 290,
      'GRE Score': 313,
      'TOEFL Score': 109,
      'University Rating': 3,
      'SOP': 4.0,
      'LOR ': 3.5,
      'CGPA': 9.0,
      'Research': 0,
      'Chance of Admit ': 0.79},
     {'Serial No.': 291,
      'GRE Score': 307,
      'TOEFL Score': 105,
      'University Rating': 2,
      'SOP': 2.5,
      'LOR ': 3.0,
      'CGPA': 7.65,
      'Research': 0,
      'Chance of Admit ': 0.58},
     {'Serial No.': 292,
      'GRE Score': 300,
      'TOEFL Score': 102,
      'University Rating': 2,
      'SOP': 1.5,
      'LOR ': 2.0,
      'CGPA': 7.87,
      'Research': 0,
      'Chance of Admit ': 0.56},
     {'Serial No.': 293,
      'GRE Score': 302,
      'TOEFL Score': 99,
      'University Rating': 2,
      'SOP': 1.0,
      'LOR ': 2.0,
      'CGPA': 7.97,
      'Research': 0,
      'Chance of Admit ': 0.56},
     {'Serial No.': 294,
      'GRE Score': 312,
      'TOEFL Score': 98,
      'University Rating': 1,
      'SOP': 3.5,
      'LOR ': 3.0,
      'CGPA': 8.18,
      'Research': 1,
      'Chance of Admit ': 0.64},
     {'Serial No.': 295,
      'GRE Score': 316,
      'TOEFL Score': 101,
      'University Rating': 2,
      'SOP': 2.5,
      'LOR ': 2.0,
      'CGPA': 8.32,
      'Research': 1,
      'Chance of Admit ': 0.61},
     {'Serial No.': 296,
      'GRE Score': 317,
      'TOEFL Score': 100,
      'University Rating': 2,
      'SOP': 3.0,
      'LOR ': 2.5,
      'CGPA': 8.57,
      'Research': 0,
      'Chance of Admit ': 0.68},
     {'Serial No.': 297,
      'GRE Score': 310,
      'TOEFL Score': 107,
      'University Rating': 3,
      'SOP': 3.5,
      'LOR ': 3.5,
      'CGPA': 8.67,
      'Research': 0,
      'Chance of Admit ': 0.76},
     {'Serial No.': 298,
      'GRE Score': 320,
      'TOEFL Score': 120,
      'University Rating': 3,
      'SOP': 4.0,
      'LOR ': 4.5,
      'CGPA': 9.11,
      'Research': 0,
      'Chance of Admit ': 0.86},
     {'Serial No.': 299,
      'GRE Score': 330,
      'TOEFL Score': 114,
      'University Rating': 3,
      'SOP': 4.5,
      'LOR ': 4.5,
      'CGPA': 9.24,
      'Research': 1,
      'Chance of Admit ': 0.9},
     {'Serial No.': 300,
      'GRE Score': 305,
      'TOEFL Score': 112,
      'University Rating': 3,
      'SOP': 3.0,
      'LOR ': 3.5,
      'CGPA': 8.65,
      'Research': 0,
      'Chance of Admit ': 0.71},
     {'Serial No.': 301,
      'GRE Score': 309,
      'TOEFL Score': 106,
      'University Rating': 2,
      'SOP': 2.5,
      'LOR ': 2.5,
      'CGPA': 8.0,
      'Research': 0,
      'Chance of Admit ': 0.62},
     {'Serial No.': 302,
      'GRE Score': 319,
      'TOEFL Score': 108,
      'University Rating': 2,
      'SOP': 2.5,
      'LOR ': 3.0,
      'CGPA': 8.76,
      'Research': 0,
      'Chance of Admit ': 0.66},
     {'Serial No.': 303,
      'GRE Score': 322,
      'TOEFL Score': 105,
      'University Rating': 2,
      'SOP': 3.0,
      'LOR ': 3.0,
      'CGPA': 8.45,
      'Research': 1,
      'Chance of Admit ': 0.65},
     {'Serial No.': 304,
      'GRE Score': 323,
      'TOEFL Score': 107,
      'University Rating': 3,
      'SOP': 3.5,
      'LOR ': 3.5,
      'CGPA': 8.55,
      'Research': 1,
      'Chance of Admit ': 0.73},
     {'Serial No.': 305,
      'GRE Score': 313,
      'TOEFL Score': 106,
      'University Rating': 2,
      'SOP': 2.5,
      'LOR ': 2.0,
      'CGPA': 8.43,
      'Research': 0,
      'Chance of Admit ': 0.62},
     {'Serial No.': 306,
      'GRE Score': 321,
      'TOEFL Score': 109,
      'University Rating': 3,
      'SOP': 3.5,
      'LOR ': 3.5,
      'CGPA': 8.8,
      'Research': 1,
      'Chance of Admit ': 0.74},
     {'Serial No.': 307,
      'GRE Score': 323,
      'TOEFL Score': 110,
      'University Rating': 3,
      'SOP': 4.0,
      'LOR ': 3.5,
      'CGPA': 9.1,
      'Research': 1,
      'Chance of Admit ': 0.79},
     {'Serial No.': 308,
      'GRE Score': 325,
      'TOEFL Score': 112,
      'University Rating': 4,
      'SOP': 4.0,
      'LOR ': 4.0,
      'CGPA': 9.0,
      'Research': 1,
      'Chance of Admit ': 0.8},
     {'Serial No.': 309,
      'GRE Score': 312,
      'TOEFL Score': 108,
      'University Rating': 3,
      'SOP': 3.5,
      'LOR ': 3.0,
      'CGPA': 8.53,
      'Research': 0,
      'Chance of Admit ': 0.69},
     {'Serial No.': 310,
      'GRE Score': 308,
      'TOEFL Score': 110,
      'University Rating': 4,
      'SOP': 3.5,
      'LOR ': 3.0,
      'CGPA': 8.6,
      'Research': 0,
      'Chance of Admit ': 0.7},
     {'Serial No.': 311,
      'GRE Score': 320,
      'TOEFL Score': 104,
      'University Rating': 3,
      'SOP': 3.0,
      'LOR ': 3.5,
      'CGPA': 8.74,
      'Research': 1,
      'Chance of Admit ': 0.76},
     {'Serial No.': 312,
      'GRE Score': 328,
      'TOEFL Score': 108,
      'University Rating': 4,
      'SOP': 4.5,
      'LOR ': 4.0,
      'CGPA': 9.18,
      'Research': 1,
      'Chance of Admit ': 0.84},
     {'Serial No.': 313,
      'GRE Score': 311,
      'TOEFL Score': 107,
      'University Rating': 4,
      'SOP': 4.5,
      'LOR ': 4.5,
      'CGPA': 9.0,
      'Research': 1,
      'Chance of Admit ': 0.78},
     {'Serial No.': 314,
      'GRE Score': 301,
      'TOEFL Score': 100,
      'University Rating': 3,
      'SOP': 3.5,
      'LOR ': 3.0,
      'CGPA': 8.04,
      'Research': 0,
      'Chance of Admit ': 0.67},
     {'Serial No.': 315,
      'GRE Score': 305,
      'TOEFL Score': 105,
      'University Rating': 2,
      'SOP': 3.0,
      'LOR ': 4.0,
      'CGPA': 8.13,
      'Research': 0,
      'Chance of Admit ': 0.66},
     {'Serial No.': 316,
      'GRE Score': 308,
      'TOEFL Score': 104,
      'University Rating': 2,
      'SOP': 2.5,
      'LOR ': 3.0,
      'CGPA': 8.07,
      'Research': 0,
      'Chance of Admit ': 0.65},
     {'Serial No.': 317,
      'GRE Score': 298,
      'TOEFL Score': 101,
      'University Rating': 2,
      'SOP': 1.5,
      'LOR ': 2.0,
      'CGPA': 7.86,
      'Research': 0,
      'Chance of Admit ': 0.54},
     {'Serial No.': 318,
      'GRE Score': 300,
      'TOEFL Score': 99,
      'University Rating': 1,
      'SOP': 1.0,
      'LOR ': 2.5,
      'CGPA': 8.01,
      'Research': 0,
      'Chance of Admit ': 0.58},
     {'Serial No.': 319,
      'GRE Score': 324,
      'TOEFL Score': 111,
      'University Rating': 3,
      'SOP': 2.5,
      'LOR ': 2.0,
      'CGPA': 8.8,
      'Research': 1,
      'Chance of Admit ': 0.79},
     {'Serial No.': 320,
      'GRE Score': 327,
      'TOEFL Score': 113,
      'University Rating': 4,
      'SOP': 3.5,
      'LOR ': 3.0,
      'CGPA': 8.69,
      'Research': 1,
      'Chance of Admit ': 0.8},
     {'Serial No.': 321,
      'GRE Score': 317,
      'TOEFL Score': 106,
      'University Rating': 3,
      'SOP': 4.0,
      'LOR ': 3.5,
      'CGPA': 8.5,
      'Research': 1,
      'Chance of Admit ': 0.75},
     {'Serial No.': 322,
      'GRE Score': 323,
      'TOEFL Score': 104,
      'University Rating': 3,
      'SOP': 4.0,
      'LOR ': 4.0,
      'CGPA': 8.44,
      'Research': 1,
      'Chance of Admit ': 0.73},
     {'Serial No.': 323,
      'GRE Score': 314,
      'TOEFL Score': 107,
      'University Rating': 2,
      'SOP': 2.5,
      'LOR ': 4.0,
      'CGPA': 8.27,
      'Research': 0,
      'Chance of Admit ': 0.72},
     {'Serial No.': 324,
      'GRE Score': 305,
      'TOEFL Score': 102,
      'University Rating': 2,
      'SOP': 2.0,
      'LOR ': 2.5,
      'CGPA': 8.18,
      'Research': 0,
      'Chance of Admit ': 0.62},
     {'Serial No.': 325,
      'GRE Score': 315,
      'TOEFL Score': 104,
      'University Rating': 3,
      'SOP': 3.0,
      'LOR ': 2.5,
      'CGPA': 8.33,
      'Research': 0,
      'Chance of Admit ': 0.67},
     {'Serial No.': 326,
      'GRE Score': 326,
      'TOEFL Score': 116,
      'University Rating': 3,
      'SOP': 3.5,
      'LOR ': 4.0,
      'CGPA': 9.14,
      'Research': 1,
      'Chance of Admit ': 0.81},
     {'Serial No.': 327,
      'GRE Score': 299,
      'TOEFL Score': 100,
      'University Rating': 3,
      'SOP': 2.0,
      'LOR ': 2.0,
      'CGPA': 8.02,
      'Research': 0,
      'Chance of Admit ': 0.63},
     {'Serial No.': 328,
      'GRE Score': 295,
      'TOEFL Score': 101,
      'University Rating': 2,
      'SOP': 2.5,
      'LOR ': 2.0,
      'CGPA': 7.86,
      'Research': 0,
      'Chance of Admit ': 0.69},
     {'Serial No.': 329,
      'GRE Score': 324,
      'TOEFL Score': 112,
      'University Rating': 4,
      'SOP': 4.0,
      'LOR ': 3.5,
      'CGPA': 8.77,
      'Research': 1,
      'Chance of Admit ': 0.8},
     {'Serial No.': 330,
      'GRE Score': 297,
      'TOEFL Score': 96,
      'University Rating': 2,
      'SOP': 2.5,
      'LOR ': 1.5,
      'CGPA': 7.89,
      'Research': 0,
      'Chance of Admit ': 0.43},
     {'Serial No.': 331,
      'GRE Score': 327,
      'TOEFL Score': 113,
      'University Rating': 3,
      'SOP': 3.5,
      'LOR ': 3.0,
      'CGPA': 8.66,
      'Research': 1,
      'Chance of Admit ': 0.8},
     {'Serial No.': 332,
      'GRE Score': 311,
      'TOEFL Score': 105,
      'University Rating': 2,
      'SOP': 3.0,
      'LOR ': 2.0,
      'CGPA': 8.12,
      'Research': 1,
      'Chance of Admit ': 0.73},
     {'Serial No.': 333,
      'GRE Score': 308,
      'TOEFL Score': 106,
      'University Rating': 3,
      'SOP': 3.5,
      'LOR ': 2.5,
      'CGPA': 8.21,
      'Research': 1,
      'Chance of Admit ': 0.75},
     {'Serial No.': 334,
      'GRE Score': 319,
      'TOEFL Score': 108,
      'University Rating': 3,
      'SOP': 3.0,
      'LOR ': 3.5,
      'CGPA': 8.54,
      'Research': 1,
      'Chance of Admit ': 0.71},
     {'Serial No.': 335,
      'GRE Score': 312,
      'TOEFL Score': 107,
      'University Rating': 4,
      'SOP': 4.5,
      'LOR ': 4.0,
      'CGPA': 8.65,
      'Research': 1,
      'Chance of Admit ': 0.73},
     {'Serial No.': 336,
      'GRE Score': 325,
      'TOEFL Score': 111,
      'University Rating': 4,
      'SOP': 4.0,
      'LOR ': 4.5,
      'CGPA': 9.11,
      'Research': 1,
      'Chance of Admit ': 0.83},
     {'Serial No.': 337,
      'GRE Score': 319,
      'TOEFL Score': 110,
      'University Rating': 3,
      'SOP': 3.0,
      'LOR ': 2.5,
      'CGPA': 8.79,
      'Research': 0,
      'Chance of Admit ': 0.72},
     {'Serial No.': 338,
      'GRE Score': 332,
      'TOEFL Score': 118,
      'University Rating': 5,
      'SOP': 5.0,
      'LOR ': 5.0,
      'CGPA': 9.47,
      'Research': 1,
      'Chance of Admit ': 0.94},
     {'Serial No.': 339,
      'GRE Score': 323,
      'TOEFL Score': 108,
      'University Rating': 5,
      'SOP': 4.0,
      'LOR ': 4.0,
      'CGPA': 8.74,
      'Research': 1,
      'Chance of Admit ': 0.81},
     {'Serial No.': 340,
      'GRE Score': 324,
      'TOEFL Score': 107,
      'University Rating': 5,
      'SOP': 3.5,
      'LOR ': 4.0,
      'CGPA': 8.66,
      'Research': 1,
      'Chance of Admit ': 0.81},
     {'Serial No.': 341,
      'GRE Score': 312,
      'TOEFL Score': 107,
      'University Rating': 3,
      'SOP': 3.0,
      'LOR ': 3.0,
      'CGPA': 8.46,
      'Research': 1,
      'Chance of Admit ': 0.75},
     {'Serial No.': 342,
      'GRE Score': 326,
      'TOEFL Score': 110,
      'University Rating': 3,
      'SOP': 3.5,
      'LOR ': 3.5,
      'CGPA': 8.76,
      'Research': 1,
      'Chance of Admit ': 0.79},
     {'Serial No.': 343,
      'GRE Score': 308,
      'TOEFL Score': 106,
      'University Rating': 3,
      'SOP': 3.0,
      'LOR ': 3.0,
      'CGPA': 8.24,
      'Research': 0,
      'Chance of Admit ': 0.58},
     {'Serial No.': 344,
      'GRE Score': 305,
      'TOEFL Score': 103,
      'University Rating': 2,
      'SOP': 2.5,
      'LOR ': 3.5,
      'CGPA': 8.13,
      'Research': 0,
      'Chance of Admit ': 0.59},
     {'Serial No.': 345,
      'GRE Score': 295,
      'TOEFL Score': 96,
      'University Rating': 2,
      'SOP': 1.5,
      'LOR ': 2.0,
      'CGPA': 7.34,
      'Research': 0,
      'Chance of Admit ': 0.47},
     {'Serial No.': 346,
      'GRE Score': 316,
      'TOEFL Score': 98,
      'University Rating': 1,
      'SOP': 1.5,
      'LOR ': 2.0,
      'CGPA': 7.43,
      'Research': 0,
      'Chance of Admit ': 0.49},
     {'Serial No.': 347,
      'GRE Score': 304,
      'TOEFL Score': 97,
      'University Rating': 2,
      'SOP': 1.5,
      'LOR ': 2.0,
      'CGPA': 7.64,
      'Research': 0,
      'Chance of Admit ': 0.47},
     {'Serial No.': 348,
      'GRE Score': 299,
      'TOEFL Score': 94,
      'University Rating': 1,
      'SOP': 1.0,
      'LOR ': 1.0,
      'CGPA': 7.34,
      'Research': 0,
      'Chance of Admit ': 0.42},
     {'Serial No.': 349,
      'GRE Score': 302,
      'TOEFL Score': 99,
      'University Rating': 1,
      'SOP': 2.0,
      'LOR ': 2.0,
      'CGPA': 7.25,
      'Research': 0,
      'Chance of Admit ': 0.57},
     {'Serial No.': 350,
      'GRE Score': 313,
      'TOEFL Score': 101,
      'University Rating': 3,
      'SOP': 2.5,
      'LOR ': 3.0,
      'CGPA': 8.04,
      'Research': 0,
      'Chance of Admit ': 0.62},
     {'Serial No.': 351,
      'GRE Score': 318,
      'TOEFL Score': 107,
      'University Rating': 3,
      'SOP': 3.0,
      'LOR ': 3.5,
      'CGPA': 8.27,
      'Research': 1,
      'Chance of Admit ': 0.74},
     {'Serial No.': 352,
      'GRE Score': 325,
      'TOEFL Score': 110,
      'University Rating': 4,
      'SOP': 3.5,
      'LOR ': 4.0,
      'CGPA': 8.67,
      'Research': 1,
      'Chance of Admit ': 0.73},
     {'Serial No.': 353,
      'GRE Score': 303,
      'TOEFL Score': 100,
      'University Rating': 2,
      'SOP': 3.0,
      'LOR ': 3.5,
      'CGPA': 8.06,
      'Research': 1,
      'Chance of Admit ': 0.64},
     {'Serial No.': 354,
      'GRE Score': 300,
      'TOEFL Score': 102,
      'University Rating': 3,
      'SOP': 3.5,
      'LOR ': 2.5,
      'CGPA': 8.17,
      'Research': 0,
      'Chance of Admit ': 0.63},
     {'Serial No.': 355,
      'GRE Score': 297,
      'TOEFL Score': 98,
      'University Rating': 2,
      'SOP': 2.5,
      'LOR ': 3.0,
      'CGPA': 7.67,
      'Research': 0,
      'Chance of Admit ': 0.59},
     {'Serial No.': 356,
      'GRE Score': 317,
      'TOEFL Score': 106,
      'University Rating': 2,
      'SOP': 2.0,
      'LOR ': 3.5,
      'CGPA': 8.12,
      'Research': 0,
      'Chance of Admit ': 0.73},
     {'Serial No.': 357,
      'GRE Score': 327,
      'TOEFL Score': 109,
      'University Rating': 3,
      'SOP': 3.5,
      'LOR ': 4.0,
      'CGPA': 8.77,
      'Research': 1,
      'Chance of Admit ': 0.79},
     {'Serial No.': 358,
      'GRE Score': 301,
      'TOEFL Score': 104,
      'University Rating': 2,
      'SOP': 3.5,
      'LOR ': 3.5,
      'CGPA': 7.89,
      'Research': 1,
      'Chance of Admit ': 0.68},
     {'Serial No.': 359,
      'GRE Score': 314,
      'TOEFL Score': 105,
      'University Rating': 2,
      'SOP': 2.5,
      'LOR ': 2.0,
      'CGPA': 7.64,
      'Research': 0,
      'Chance of Admit ': 0.7},
     {'Serial No.': 360,
      'GRE Score': 321,
      'TOEFL Score': 107,
      'University Rating': 2,
      'SOP': 2.0,
      'LOR ': 1.5,
      'CGPA': 8.44,
      'Research': 0,
      'Chance of Admit ': 0.81},
     {'Serial No.': 361,
      'GRE Score': 322,
      'TOEFL Score': 110,
      'University Rating': 3,
      'SOP': 4.0,
      'LOR ': 5.0,
      'CGPA': 8.64,
      'Research': 1,
      'Chance of Admit ': 0.85},
     {'Serial No.': 362,
      'GRE Score': 334,
      'TOEFL Score': 116,
      'University Rating': 4,
      'SOP': 4.0,
      'LOR ': 3.5,
      'CGPA': 9.54,
      'Research': 1,
      'Chance of Admit ': 0.93},
     {'Serial No.': 363,
      'GRE Score': 338,
      'TOEFL Score': 115,
      'University Rating': 5,
      'SOP': 4.5,
      'LOR ': 5.0,
      'CGPA': 9.23,
      'Research': 1,
      'Chance of Admit ': 0.91},
     {'Serial No.': 364,
      'GRE Score': 306,
      'TOEFL Score': 103,
      'University Rating': 2,
      'SOP': 2.5,
      'LOR ': 3.0,
      'CGPA': 8.36,
      'Research': 0,
      'Chance of Admit ': 0.69},
     {'Serial No.': 365,
      'GRE Score': 313,
      'TOEFL Score': 102,
      'University Rating': 3,
      'SOP': 3.5,
      'LOR ': 4.0,
      'CGPA': 8.9,
      'Research': 1,
      'Chance of Admit ': 0.77},
     {'Serial No.': 366,
      'GRE Score': 330,
      'TOEFL Score': 114,
      'University Rating': 4,
      'SOP': 4.5,
      'LOR ': 3.0,
      'CGPA': 9.17,
      'Research': 1,
      'Chance of Admit ': 0.86},
     {'Serial No.': 367,
      'GRE Score': 320,
      'TOEFL Score': 104,
      'University Rating': 3,
      'SOP': 3.5,
      'LOR ': 4.5,
      'CGPA': 8.34,
      'Research': 1,
      'Chance of Admit ': 0.74},
     {'Serial No.': 368,
      'GRE Score': 311,
      'TOEFL Score': 98,
      'University Rating': 1,
      'SOP': 1.0,
      'LOR ': 2.5,
      'CGPA': 7.46,
      'Research': 0,
      'Chance of Admit ': 0.57},
     {'Serial No.': 369,
      'GRE Score': 298,
      'TOEFL Score': 92,
      'University Rating': 1,
      'SOP': 2.0,
      'LOR ': 2.0,
      'CGPA': 7.88,
      'Research': 0,
      'Chance of Admit ': 0.51},
     {'Serial No.': 370,
      'GRE Score': 301,
      'TOEFL Score': 98,
      'University Rating': 1,
      'SOP': 2.0,
      'LOR ': 3.0,
      'CGPA': 8.03,
      'Research': 1,
      'Chance of Admit ': 0.67},
     {'Serial No.': 371,
      'GRE Score': 310,
      'TOEFL Score': 103,
      'University Rating': 2,
      'SOP': 2.5,
      'LOR ': 2.5,
      'CGPA': 8.24,
      'Research': 0,
      'Chance of Admit ': 0.72},
     {'Serial No.': 372,
      'GRE Score': 324,
      'TOEFL Score': 110,
      'University Rating': 3,
      'SOP': 3.5,
      'LOR ': 3.0,
      'CGPA': 9.22,
      'Research': 1,
      'Chance of Admit ': 0.89},
     {'Serial No.': 373,
      'GRE Score': 336,
      'TOEFL Score': 119,
      'University Rating': 4,
      'SOP': 4.5,
      'LOR ': 4.0,
      'CGPA': 9.62,
      'Research': 1,
      'Chance of Admit ': 0.95},
     {'Serial No.': 374,
      'GRE Score': 321,
      'TOEFL Score': 109,
      'University Rating': 3,
      'SOP': 3.0,
      'LOR ': 3.0,
      'CGPA': 8.54,
      'Research': 1,
      'Chance of Admit ': 0.79},
     {'Serial No.': 375,
      'GRE Score': 315,
      'TOEFL Score': 105,
      'University Rating': 2,
      'SOP': 2.0,
      'LOR ': 2.5,
      'CGPA': 7.65,
      'Research': 0,
      'Chance of Admit ': 0.39},
     {'Serial No.': 376,
      'GRE Score': 304,
      'TOEFL Score': 101,
      'University Rating': 2,
      'SOP': 2.0,
      'LOR ': 2.5,
      'CGPA': 7.66,
      'Research': 0,
      'Chance of Admit ': 0.38},
     {'Serial No.': 377,
      'GRE Score': 297,
      'TOEFL Score': 96,
      'University Rating': 2,
      'SOP': 2.5,
      'LOR ': 2.0,
      'CGPA': 7.43,
      'Research': 0,
      'Chance of Admit ': 0.34},
     {'Serial No.': 378,
      'GRE Score': 290,
      'TOEFL Score': 100,
      'University Rating': 1,
      'SOP': 1.5,
      'LOR ': 2.0,
      'CGPA': 7.56,
      'Research': 0,
      'Chance of Admit ': 0.47},
     {'Serial No.': 379,
      'GRE Score': 303,
      'TOEFL Score': 98,
      'University Rating': 1,
      'SOP': 2.0,
      'LOR ': 2.5,
      'CGPA': 7.65,
      'Research': 0,
      'Chance of Admit ': 0.56},
     {'Serial No.': 380,
      'GRE Score': 311,
      'TOEFL Score': 99,
      'University Rating': 1,
      'SOP': 2.5,
      'LOR ': 3.0,
      'CGPA': 8.43,
      'Research': 1,
      'Chance of Admit ': 0.71},
     {'Serial No.': 381,
      'GRE Score': 322,
      'TOEFL Score': 104,
      'University Rating': 3,
      'SOP': 3.5,
      'LOR ': 4.0,
      'CGPA': 8.84,
      'Research': 1,
      'Chance of Admit ': 0.78},
     {'Serial No.': 382,
      'GRE Score': 319,
      'TOEFL Score': 105,
      'University Rating': 3,
      'SOP': 3.0,
      'LOR ': 3.5,
      'CGPA': 8.67,
      'Research': 1,
      'Chance of Admit ': 0.73},
     {'Serial No.': 383,
      'GRE Score': 324,
      'TOEFL Score': 110,
      'University Rating': 4,
      'SOP': 4.5,
      'LOR ': 4.0,
      'CGPA': 9.15,
      'Research': 1,
      'Chance of Admit ': 0.82},
     {'Serial No.': 384,
      'GRE Score': 300,
      'TOEFL Score': 100,
      'University Rating': 3,
      'SOP': 3.0,
      'LOR ': 3.5,
      'CGPA': 8.26,
      'Research': 0,
      'Chance of Admit ': 0.62},
     {'Serial No.': 385,
      'GRE Score': 340,
      'TOEFL Score': 113,
      'University Rating': 4,
      'SOP': 5.0,
      'LOR ': 5.0,
      'CGPA': 9.74,
      'Research': 1,
      'Chance of Admit ': 0.96},
     {'Serial No.': 386,
      'GRE Score': 335,
      'TOEFL Score': 117,
      'University Rating': 5,
      'SOP': 5.0,
      'LOR ': 5.0,
      'CGPA': 9.82,
      'Research': 1,
      'Chance of Admit ': 0.96},
     {'Serial No.': 387,
      'GRE Score': 302,
      'TOEFL Score': 101,
      'University Rating': 2,
      'SOP': 2.5,
      'LOR ': 3.5,
      'CGPA': 7.96,
      'Research': 0,
      'Chance of Admit ': 0.46},
     {'Serial No.': 388,
      'GRE Score': 307,
      'TOEFL Score': 105,
      'University Rating': 2,
      'SOP': 2.0,
      'LOR ': 3.5,
      'CGPA': 8.1,
      'Research': 0,
      'Chance of Admit ': 0.53},
     {'Serial No.': 389,
      'GRE Score': 296,
      'TOEFL Score': 97,
      'University Rating': 2,
      'SOP': 1.5,
      'LOR ': 2.0,
      'CGPA': 7.8,
      'Research': 0,
      'Chance of Admit ': 0.49},
     {'Serial No.': 390,
      'GRE Score': 320,
      'TOEFL Score': 108,
      'University Rating': 3,
      'SOP': 3.5,
      'LOR ': 4.0,
      'CGPA': 8.44,
      'Research': 1,
      'Chance of Admit ': 0.76},
     {'Serial No.': 391,
      'GRE Score': 314,
      'TOEFL Score': 102,
      'University Rating': 2,
      'SOP': 2.0,
      'LOR ': 2.5,
      'CGPA': 8.24,
      'Research': 0,
      'Chance of Admit ': 0.64},
     {'Serial No.': 392,
      'GRE Score': 318,
      'TOEFL Score': 106,
      'University Rating': 3,
      'SOP': 2.0,
      'LOR ': 3.0,
      'CGPA': 8.65,
      'Research': 0,
      'Chance of Admit ': 0.71},
     {'Serial No.': 393,
      'GRE Score': 326,
      'TOEFL Score': 112,
      'University Rating': 4,
      'SOP': 4.0,
      'LOR ': 3.5,
      'CGPA': 9.12,
      'Research': 1,
      'Chance of Admit ': 0.84},
     {'Serial No.': 394,
      'GRE Score': 317,
      'TOEFL Score': 104,
      'University Rating': 2,
      'SOP': 3.0,
      'LOR ': 3.0,
      'CGPA': 8.76,
      'Research': 0,
      'Chance of Admit ': 0.77},
     {'Serial No.': 395,
      'GRE Score': 329,
      'TOEFL Score': 111,
      'University Rating': 4,
      'SOP': 4.5,
      'LOR ': 4.0,
      'CGPA': 9.23,
      'Research': 1,
      'Chance of Admit ': 0.89},
     {'Serial No.': 396,
      'GRE Score': 324,
      'TOEFL Score': 110,
      'University Rating': 3,
      'SOP': 3.5,
      'LOR ': 3.5,
      'CGPA': 9.04,
      'Research': 1,
      'Chance of Admit ': 0.82},
     {'Serial No.': 397,
      'GRE Score': 325,
      'TOEFL Score': 107,
      'University Rating': 3,
      'SOP': 3.0,
      'LOR ': 3.5,
      'CGPA': 9.11,
      'Research': 1,
      'Chance of Admit ': 0.84},
     {'Serial No.': 398,
      'GRE Score': 330,
      'TOEFL Score': 116,
      'University Rating': 4,
      'SOP': 5.0,
      'LOR ': 4.5,
      'CGPA': 9.45,
      'Research': 1,
      'Chance of Admit ': 0.91},
     {'Serial No.': 399,
      'GRE Score': 312,
      'TOEFL Score': 103,
      'University Rating': 3,
      'SOP': 3.5,
      'LOR ': 4.0,
      'CGPA': 8.78,
      'Research': 0,
      'Chance of Admit ': 0.67},
     {'Serial No.': 400,
      'GRE Score': 333,
      'TOEFL Score': 117,
      'University Rating': 4,
      'SOP': 5.0,
      'LOR ': 4.0,
      'CGPA': 9.66,
      'Research': 1,
      'Chance of Admit ': 0.95}]




```python
collection.insert_many(json_format)
```




    <pymongo.results.InsertManyResult at 0x2287e95cdc8>




```python
find_first_record=collection.find_one()
```


```python
print(find_first_record)
```

    {'_id': ObjectId('6444ccd095bfe069933270d8'), 'Serial No.': 1, 'GRE Score': 337, 'TOEFL Score': 118, 'University Rating': 4, 'SOP': 4.5, 'LOR ': 4.5, 'CGPA': 9.65, 'Research': 1, 'Chance of Admit ': 0.92}
    


```python
print(find_first_record['Serial No.'])
```

    1
    


```python
print(find_first_record['University Rating'])
```

    4
    


```python
for i in collection.find():
    print (i)
```

    {'_id': ObjectId('6444ccd095bfe069933270d8'), 'Serial No.': 1, 'GRE Score': 337, 'TOEFL Score': 118, 'University Rating': 4, 'SOP': 4.5, 'LOR ': 4.5, 'CGPA': 9.65, 'Research': 1, 'Chance of Admit ': 0.92}
    {'_id': ObjectId('6444ccd095bfe069933270d9'), 'Serial No.': 2, 'GRE Score': 324, 'TOEFL Score': 107, 'University Rating': 4, 'SOP': 4.0, 'LOR ': 4.5, 'CGPA': 8.87, 'Research': 1, 'Chance of Admit ': 0.76}
    {'_id': ObjectId('6444ccd095bfe069933270da'), 'Serial No.': 3, 'GRE Score': 316, 'TOEFL Score': 104, 'University Rating': 3, 'SOP': 3.0, 'LOR ': 3.5, 'CGPA': 8.0, 'Research': 1, 'Chance of Admit ': 0.72}
    {'_id': ObjectId('6444ccd095bfe069933270db'), 'Serial No.': 4, 'GRE Score': 322, 'TOEFL Score': 110, 'University Rating': 3, 'SOP': 3.5, 'LOR ': 2.5, 'CGPA': 8.67, 'Research': 1, 'Chance of Admit ': 0.8}
    {'_id': ObjectId('6444ccd095bfe069933270dc'), 'Serial No.': 5, 'GRE Score': 314, 'TOEFL Score': 103, 'University Rating': 2, 'SOP': 2.0, 'LOR ': 3.0, 'CGPA': 8.21, 'Research': 0, 'Chance of Admit ': 0.65}
    {'_id': ObjectId('6444ccd095bfe069933270dd'), 'Serial No.': 6, 'GRE Score': 330, 'TOEFL Score': 115, 'University Rating': 5, 'SOP': 4.5, 'LOR ': 3.0, 'CGPA': 9.34, 'Research': 1, 'Chance of Admit ': 0.9}
    {'_id': ObjectId('6444ccd095bfe069933270de'), 'Serial No.': 7, 'GRE Score': 321, 'TOEFL Score': 109, 'University Rating': 3, 'SOP': 3.0, 'LOR ': 4.0, 'CGPA': 8.2, 'Research': 1, 'Chance of Admit ': 0.75}
    {'_id': ObjectId('6444ccd095bfe069933270df'), 'Serial No.': 8, 'GRE Score': 308, 'TOEFL Score': 101, 'University Rating': 2, 'SOP': 3.0, 'LOR ': 4.0, 'CGPA': 7.9, 'Research': 0, 'Chance of Admit ': 0.68}
    {'_id': ObjectId('6444ccd095bfe069933270e0'), 'Serial No.': 9, 'GRE Score': 302, 'TOEFL Score': 102, 'University Rating': 1, 'SOP': 2.0, 'LOR ': 1.5, 'CGPA': 8.0, 'Research': 0, 'Chance of Admit ': 0.5}
    {'_id': ObjectId('6444ccd095bfe069933270e1'), 'Serial No.': 10, 'GRE Score': 323, 'TOEFL Score': 108, 'University Rating': 3, 'SOP': 3.5, 'LOR ': 3.0, 'CGPA': 8.6, 'Research': 0, 'Chance of Admit ': 0.45}
    {'_id': ObjectId('6444ccd095bfe069933270e2'), 'Serial No.': 11, 'GRE Score': 325, 'TOEFL Score': 106, 'University Rating': 3, 'SOP': 3.5, 'LOR ': 4.0, 'CGPA': 8.4, 'Research': 1, 'Chance of Admit ': 0.52}
    {'_id': ObjectId('6444ccd095bfe069933270e3'), 'Serial No.': 12, 'GRE Score': 327, 'TOEFL Score': 111, 'University Rating': 4, 'SOP': 4.0, 'LOR ': 4.5, 'CGPA': 9.0, 'Research': 1, 'Chance of Admit ': 0.84}
    {'_id': ObjectId('6444ccd095bfe069933270e4'), 'Serial No.': 13, 'GRE Score': 328, 'TOEFL Score': 112, 'University Rating': 4, 'SOP': 4.0, 'LOR ': 4.5, 'CGPA': 9.1, 'Research': 1, 'Chance of Admit ': 0.78}
    {'_id': ObjectId('6444ccd095bfe069933270e5'), 'Serial No.': 14, 'GRE Score': 307, 'TOEFL Score': 109, 'University Rating': 3, 'SOP': 4.0, 'LOR ': 3.0, 'CGPA': 8.0, 'Research': 1, 'Chance of Admit ': 0.62}
    {'_id': ObjectId('6444ccd095bfe069933270e6'), 'Serial No.': 15, 'GRE Score': 311, 'TOEFL Score': 104, 'University Rating': 3, 'SOP': 3.5, 'LOR ': 2.0, 'CGPA': 8.2, 'Research': 1, 'Chance of Admit ': 0.61}
    {'_id': ObjectId('6444ccd095bfe069933270e7'), 'Serial No.': 16, 'GRE Score': 314, 'TOEFL Score': 105, 'University Rating': 3, 'SOP': 3.5, 'LOR ': 2.5, 'CGPA': 8.3, 'Research': 0, 'Chance of Admit ': 0.54}
    {'_id': ObjectId('6444ccd095bfe069933270e8'), 'Serial No.': 17, 'GRE Score': 317, 'TOEFL Score': 107, 'University Rating': 3, 'SOP': 4.0, 'LOR ': 3.0, 'CGPA': 8.7, 'Research': 0, 'Chance of Admit ': 0.66}
    {'_id': ObjectId('6444ccd095bfe069933270e9'), 'Serial No.': 18, 'GRE Score': 319, 'TOEFL Score': 106, 'University Rating': 3, 'SOP': 4.0, 'LOR ': 3.0, 'CGPA': 8.0, 'Research': 1, 'Chance of Admit ': 0.65}
    {'_id': ObjectId('6444ccd095bfe069933270ea'), 'Serial No.': 19, 'GRE Score': 318, 'TOEFL Score': 110, 'University Rating': 3, 'SOP': 4.0, 'LOR ': 3.0, 'CGPA': 8.8, 'Research': 0, 'Chance of Admit ': 0.63}
    {'_id': ObjectId('6444ccd095bfe069933270eb'), 'Serial No.': 20, 'GRE Score': 303, 'TOEFL Score': 102, 'University Rating': 3, 'SOP': 3.5, 'LOR ': 3.0, 'CGPA': 8.5, 'Research': 0, 'Chance of Admit ': 0.62}
    {'_id': ObjectId('6444ccd095bfe069933270ec'), 'Serial No.': 21, 'GRE Score': 312, 'TOEFL Score': 107, 'University Rating': 3, 'SOP': 3.0, 'LOR ': 2.0, 'CGPA': 7.9, 'Research': 1, 'Chance of Admit ': 0.64}
    {'_id': ObjectId('6444ccd095bfe069933270ed'), 'Serial No.': 22, 'GRE Score': 325, 'TOEFL Score': 114, 'University Rating': 4, 'SOP': 3.0, 'LOR ': 2.0, 'CGPA': 8.4, 'Research': 0, 'Chance of Admit ': 0.7}
    {'_id': ObjectId('6444ccd095bfe069933270ee'), 'Serial No.': 23, 'GRE Score': 328, 'TOEFL Score': 116, 'University Rating': 5, 'SOP': 5.0, 'LOR ': 5.0, 'CGPA': 9.5, 'Research': 1, 'Chance of Admit ': 0.94}
    {'_id': ObjectId('6444ccd095bfe069933270ef'), 'Serial No.': 24, 'GRE Score': 334, 'TOEFL Score': 119, 'University Rating': 5, 'SOP': 5.0, 'LOR ': 4.5, 'CGPA': 9.7, 'Research': 1, 'Chance of Admit ': 0.95}
    {'_id': ObjectId('6444ccd095bfe069933270f0'), 'Serial No.': 25, 'GRE Score': 336, 'TOEFL Score': 119, 'University Rating': 5, 'SOP': 4.0, 'LOR ': 3.5, 'CGPA': 9.8, 'Research': 1, 'Chance of Admit ': 0.97}
    {'_id': ObjectId('6444ccd095bfe069933270f1'), 'Serial No.': 26, 'GRE Score': 340, 'TOEFL Score': 120, 'University Rating': 5, 'SOP': 4.5, 'LOR ': 4.5, 'CGPA': 9.6, 'Research': 1, 'Chance of Admit ': 0.94}
    {'_id': ObjectId('6444ccd095bfe069933270f2'), 'Serial No.': 27, 'GRE Score': 322, 'TOEFL Score': 109, 'University Rating': 5, 'SOP': 4.5, 'LOR ': 3.5, 'CGPA': 8.8, 'Research': 0, 'Chance of Admit ': 0.76}
    {'_id': ObjectId('6444ccd095bfe069933270f3'), 'Serial No.': 28, 'GRE Score': 298, 'TOEFL Score': 98, 'University Rating': 2, 'SOP': 1.5, 'LOR ': 2.5, 'CGPA': 7.5, 'Research': 1, 'Chance of Admit ': 0.44}
    {'_id': ObjectId('6444ccd095bfe069933270f4'), 'Serial No.': 29, 'GRE Score': 295, 'TOEFL Score': 93, 'University Rating': 1, 'SOP': 2.0, 'LOR ': 2.0, 'CGPA': 7.2, 'Research': 0, 'Chance of Admit ': 0.46}
    {'_id': ObjectId('6444ccd095bfe069933270f5'), 'Serial No.': 30, 'GRE Score': 310, 'TOEFL Score': 99, 'University Rating': 2, 'SOP': 1.5, 'LOR ': 2.0, 'CGPA': 7.3, 'Research': 0, 'Chance of Admit ': 0.54}
    {'_id': ObjectId('6444ccd095bfe069933270f6'), 'Serial No.': 31, 'GRE Score': 300, 'TOEFL Score': 97, 'University Rating': 2, 'SOP': 3.0, 'LOR ': 3.0, 'CGPA': 8.1, 'Research': 1, 'Chance of Admit ': 0.65}
    {'_id': ObjectId('6444ccd095bfe069933270f7'), 'Serial No.': 32, 'GRE Score': 327, 'TOEFL Score': 103, 'University Rating': 3, 'SOP': 4.0, 'LOR ': 4.0, 'CGPA': 8.3, 'Research': 1, 'Chance of Admit ': 0.74}
    {'_id': ObjectId('6444ccd095bfe069933270f8'), 'Serial No.': 33, 'GRE Score': 338, 'TOEFL Score': 118, 'University Rating': 4, 'SOP': 3.0, 'LOR ': 4.5, 'CGPA': 9.4, 'Research': 1, 'Chance of Admit ': 0.91}
    {'_id': ObjectId('6444ccd095bfe069933270f9'), 'Serial No.': 34, 'GRE Score': 340, 'TOEFL Score': 114, 'University Rating': 5, 'SOP': 4.0, 'LOR ': 4.0, 'CGPA': 9.6, 'Research': 1, 'Chance of Admit ': 0.9}
    {'_id': ObjectId('6444ccd095bfe069933270fa'), 'Serial No.': 35, 'GRE Score': 331, 'TOEFL Score': 112, 'University Rating': 5, 'SOP': 4.0, 'LOR ': 5.0, 'CGPA': 9.8, 'Research': 1, 'Chance of Admit ': 0.94}
    {'_id': ObjectId('6444ccd095bfe069933270fb'), 'Serial No.': 36, 'GRE Score': 320, 'TOEFL Score': 110, 'University Rating': 5, 'SOP': 5.0, 'LOR ': 5.0, 'CGPA': 9.2, 'Research': 1, 'Chance of Admit ': 0.88}
    {'_id': ObjectId('6444ccd095bfe069933270fc'), 'Serial No.': 37, 'GRE Score': 299, 'TOEFL Score': 106, 'University Rating': 2, 'SOP': 4.0, 'LOR ': 4.0, 'CGPA': 8.4, 'Research': 0, 'Chance of Admit ': 0.64}
    {'_id': ObjectId('6444ccd095bfe069933270fd'), 'Serial No.': 38, 'GRE Score': 300, 'TOEFL Score': 105, 'University Rating': 1, 'SOP': 1.0, 'LOR ': 2.0, 'CGPA': 7.8, 'Research': 0, 'Chance of Admit ': 0.58}
    {'_id': ObjectId('6444ccd095bfe069933270fe'), 'Serial No.': 39, 'GRE Score': 304, 'TOEFL Score': 105, 'University Rating': 1, 'SOP': 3.0, 'LOR ': 1.5, 'CGPA': 7.5, 'Research': 0, 'Chance of Admit ': 0.52}
    {'_id': ObjectId('6444ccd095bfe069933270ff'), 'Serial No.': 40, 'GRE Score': 307, 'TOEFL Score': 108, 'University Rating': 2, 'SOP': 4.0, 'LOR ': 3.5, 'CGPA': 7.7, 'Research': 0, 'Chance of Admit ': 0.48}
    {'_id': ObjectId('6444ccd095bfe06993327100'), 'Serial No.': 41, 'GRE Score': 308, 'TOEFL Score': 110, 'University Rating': 3, 'SOP': 3.5, 'LOR ': 3.0, 'CGPA': 8.0, 'Research': 1, 'Chance of Admit ': 0.46}
    {'_id': ObjectId('6444ccd095bfe06993327101'), 'Serial No.': 42, 'GRE Score': 316, 'TOEFL Score': 105, 'University Rating': 2, 'SOP': 2.5, 'LOR ': 2.5, 'CGPA': 8.2, 'Research': 1, 'Chance of Admit ': 0.49}
    {'_id': ObjectId('6444ccd095bfe06993327102'), 'Serial No.': 43, 'GRE Score': 313, 'TOEFL Score': 107, 'University Rating': 2, 'SOP': 2.5, 'LOR ': 2.0, 'CGPA': 8.5, 'Research': 1, 'Chance of Admit ': 0.53}
    {'_id': ObjectId('6444ccd095bfe06993327103'), 'Serial No.': 44, 'GRE Score': 332, 'TOEFL Score': 117, 'University Rating': 4, 'SOP': 4.5, 'LOR ': 4.0, 'CGPA': 9.1, 'Research': 0, 'Chance of Admit ': 0.87}
    {'_id': ObjectId('6444ccd095bfe06993327104'), 'Serial No.': 45, 'GRE Score': 326, 'TOEFL Score': 113, 'University Rating': 5, 'SOP': 4.5, 'LOR ': 4.0, 'CGPA': 9.4, 'Research': 1, 'Chance of Admit ': 0.91}
    {'_id': ObjectId('6444ccd095bfe06993327105'), 'Serial No.': 46, 'GRE Score': 322, 'TOEFL Score': 110, 'University Rating': 5, 'SOP': 5.0, 'LOR ': 4.0, 'CGPA': 9.1, 'Research': 1, 'Chance of Admit ': 0.88}
    {'_id': ObjectId('6444ccd095bfe06993327106'), 'Serial No.': 47, 'GRE Score': 329, 'TOEFL Score': 114, 'University Rating': 5, 'SOP': 4.0, 'LOR ': 5.0, 'CGPA': 9.3, 'Research': 1, 'Chance of Admit ': 0.86}
    {'_id': ObjectId('6444ccd095bfe06993327107'), 'Serial No.': 48, 'GRE Score': 339, 'TOEFL Score': 119, 'University Rating': 5, 'SOP': 4.5, 'LOR ': 4.0, 'CGPA': 9.7, 'Research': 0, 'Chance of Admit ': 0.89}
    {'_id': ObjectId('6444ccd095bfe06993327108'), 'Serial No.': 49, 'GRE Score': 321, 'TOEFL Score': 110, 'University Rating': 3, 'SOP': 3.5, 'LOR ': 5.0, 'CGPA': 8.85, 'Research': 1, 'Chance of Admit ': 0.82}
    {'_id': ObjectId('6444ccd095bfe06993327109'), 'Serial No.': 50, 'GRE Score': 327, 'TOEFL Score': 111, 'University Rating': 4, 'SOP': 3.0, 'LOR ': 4.0, 'CGPA': 8.4, 'Research': 1, 'Chance of Admit ': 0.78}
    {'_id': ObjectId('6444ccd095bfe0699332710a'), 'Serial No.': 51, 'GRE Score': 313, 'TOEFL Score': 98, 'University Rating': 3, 'SOP': 2.5, 'LOR ': 4.5, 'CGPA': 8.3, 'Research': 1, 'Chance of Admit ': 0.76}
    {'_id': ObjectId('6444ccd095bfe0699332710b'), 'Serial No.': 52, 'GRE Score': 312, 'TOEFL Score': 100, 'University Rating': 2, 'SOP': 1.5, 'LOR ': 3.5, 'CGPA': 7.9, 'Research': 1, 'Chance of Admit ': 0.56}
    {'_id': ObjectId('6444ccd095bfe0699332710c'), 'Serial No.': 53, 'GRE Score': 334, 'TOEFL Score': 116, 'University Rating': 4, 'SOP': 4.0, 'LOR ': 3.0, 'CGPA': 8.0, 'Research': 1, 'Chance of Admit ': 0.78}
    {'_id': ObjectId('6444ccd095bfe0699332710d'), 'Serial No.': 54, 'GRE Score': 324, 'TOEFL Score': 112, 'University Rating': 4, 'SOP': 4.0, 'LOR ': 2.5, 'CGPA': 8.1, 'Research': 1, 'Chance of Admit ': 0.72}
    {'_id': ObjectId('6444ccd095bfe0699332710e'), 'Serial No.': 55, 'GRE Score': 322, 'TOEFL Score': 110, 'University Rating': 3, 'SOP': 3.0, 'LOR ': 3.5, 'CGPA': 8.0, 'Research': 0, 'Chance of Admit ': 0.7}
    {'_id': ObjectId('6444ccd095bfe0699332710f'), 'Serial No.': 56, 'GRE Score': 320, 'TOEFL Score': 103, 'University Rating': 3, 'SOP': 3.0, 'LOR ': 3.0, 'CGPA': 7.7, 'Research': 0, 'Chance of Admit ': 0.64}
    {'_id': ObjectId('6444ccd095bfe06993327110'), 'Serial No.': 57, 'GRE Score': 316, 'TOEFL Score': 102, 'University Rating': 3, 'SOP': 2.0, 'LOR ': 3.0, 'CGPA': 7.4, 'Research': 0, 'Chance of Admit ': 0.64}
    {'_id': ObjectId('6444ccd095bfe06993327111'), 'Serial No.': 58, 'GRE Score': 298, 'TOEFL Score': 99, 'University Rating': 2, 'SOP': 4.0, 'LOR ': 2.0, 'CGPA': 7.6, 'Research': 0, 'Chance of Admit ': 0.46}
    {'_id': ObjectId('6444ccd095bfe06993327112'), 'Serial No.': 59, 'GRE Score': 300, 'TOEFL Score': 99, 'University Rating': 1, 'SOP': 3.0, 'LOR ': 2.0, 'CGPA': 6.8, 'Research': 1, 'Chance of Admit ': 0.36}
    {'_id': ObjectId('6444ccd095bfe06993327113'), 'Serial No.': 60, 'GRE Score': 311, 'TOEFL Score': 104, 'University Rating': 2, 'SOP': 2.0, 'LOR ': 2.0, 'CGPA': 8.3, 'Research': 0, 'Chance of Admit ': 0.42}
    {'_id': ObjectId('6444ccd095bfe06993327114'), 'Serial No.': 61, 'GRE Score': 309, 'TOEFL Score': 100, 'University Rating': 2, 'SOP': 3.0, 'LOR ': 3.0, 'CGPA': 8.1, 'Research': 0, 'Chance of Admit ': 0.48}
    {'_id': ObjectId('6444ccd095bfe06993327115'), 'Serial No.': 62, 'GRE Score': 307, 'TOEFL Score': 101, 'University Rating': 3, 'SOP': 4.0, 'LOR ': 3.0, 'CGPA': 8.2, 'Research': 0, 'Chance of Admit ': 0.47}
    {'_id': ObjectId('6444ccd095bfe06993327116'), 'Serial No.': 63, 'GRE Score': 304, 'TOEFL Score': 105, 'University Rating': 2, 'SOP': 3.0, 'LOR ': 3.0, 'CGPA': 8.2, 'Research': 1, 'Chance of Admit ': 0.54}
    {'_id': ObjectId('6444ccd095bfe06993327117'), 'Serial No.': 64, 'GRE Score': 315, 'TOEFL Score': 107, 'University Rating': 2, 'SOP': 4.0, 'LOR ': 3.0, 'CGPA': 8.5, 'Research': 1, 'Chance of Admit ': 0.56}
    {'_id': ObjectId('6444ccd095bfe06993327118'), 'Serial No.': 65, 'GRE Score': 325, 'TOEFL Score': 111, 'University Rating': 3, 'SOP': 3.0, 'LOR ': 3.5, 'CGPA': 8.7, 'Research': 0, 'Chance of Admit ': 0.52}
    {'_id': ObjectId('6444ccd095bfe06993327119'), 'Serial No.': 66, 'GRE Score': 325, 'TOEFL Score': 112, 'University Rating': 4, 'SOP': 3.5, 'LOR ': 3.5, 'CGPA': 8.92, 'Research': 0, 'Chance of Admit ': 0.55}
    {'_id': ObjectId('6444ccd095bfe0699332711a'), 'Serial No.': 67, 'GRE Score': 327, 'TOEFL Score': 114, 'University Rating': 3, 'SOP': 3.0, 'LOR ': 3.0, 'CGPA': 9.02, 'Research': 0, 'Chance of Admit ': 0.61}
    {'_id': ObjectId('6444ccd095bfe0699332711b'), 'Serial No.': 68, 'GRE Score': 316, 'TOEFL Score': 107, 'University Rating': 2, 'SOP': 3.5, 'LOR ': 3.5, 'CGPA': 8.64, 'Research': 1, 'Chance of Admit ': 0.57}
    {'_id': ObjectId('6444ccd095bfe0699332711c'), 'Serial No.': 69, 'GRE Score': 318, 'TOEFL Score': 109, 'University Rating': 3, 'SOP': 3.5, 'LOR ': 4.0, 'CGPA': 9.22, 'Research': 1, 'Chance of Admit ': 0.68}
    {'_id': ObjectId('6444ccd095bfe0699332711d'), 'Serial No.': 70, 'GRE Score': 328, 'TOEFL Score': 115, 'University Rating': 4, 'SOP': 4.5, 'LOR ': 4.0, 'CGPA': 9.16, 'Research': 1, 'Chance of Admit ': 0.78}
    {'_id': ObjectId('6444ccd095bfe0699332711e'), 'Serial No.': 71, 'GRE Score': 332, 'TOEFL Score': 118, 'University Rating': 5, 'SOP': 5.0, 'LOR ': 5.0, 'CGPA': 9.64, 'Research': 1, 'Chance of Admit ': 0.94}
    {'_id': ObjectId('6444ccd095bfe0699332711f'), 'Serial No.': 72, 'GRE Score': 336, 'TOEFL Score': 112, 'University Rating': 5, 'SOP': 5.0, 'LOR ': 5.0, 'CGPA': 9.76, 'Research': 1, 'Chance of Admit ': 0.96}
    {'_id': ObjectId('6444ccd095bfe06993327120'), 'Serial No.': 73, 'GRE Score': 321, 'TOEFL Score': 111, 'University Rating': 5, 'SOP': 5.0, 'LOR ': 5.0, 'CGPA': 9.45, 'Research': 1, 'Chance of Admit ': 0.93}
    {'_id': ObjectId('6444ccd095bfe06993327121'), 'Serial No.': 74, 'GRE Score': 314, 'TOEFL Score': 108, 'University Rating': 4, 'SOP': 4.5, 'LOR ': 4.0, 'CGPA': 9.04, 'Research': 1, 'Chance of Admit ': 0.84}
    {'_id': ObjectId('6444ccd095bfe06993327122'), 'Serial No.': 75, 'GRE Score': 314, 'TOEFL Score': 106, 'University Rating': 3, 'SOP': 3.0, 'LOR ': 5.0, 'CGPA': 8.9, 'Research': 0, 'Chance of Admit ': 0.74}
    {'_id': ObjectId('6444ccd095bfe06993327123'), 'Serial No.': 76, 'GRE Score': 329, 'TOEFL Score': 114, 'University Rating': 2, 'SOP': 2.0, 'LOR ': 4.0, 'CGPA': 8.56, 'Research': 1, 'Chance of Admit ': 0.72}
    {'_id': ObjectId('6444ccd095bfe06993327124'), 'Serial No.': 77, 'GRE Score': 327, 'TOEFL Score': 112, 'University Rating': 3, 'SOP': 3.0, 'LOR ': 3.0, 'CGPA': 8.72, 'Research': 1, 'Chance of Admit ': 0.74}
    {'_id': ObjectId('6444ccd095bfe06993327125'), 'Serial No.': 78, 'GRE Score': 301, 'TOEFL Score': 99, 'University Rating': 2, 'SOP': 3.0, 'LOR ': 2.0, 'CGPA': 8.22, 'Research': 0, 'Chance of Admit ': 0.64}
    {'_id': ObjectId('6444ccd095bfe06993327126'), 'Serial No.': 79, 'GRE Score': 296, 'TOEFL Score': 95, 'University Rating': 2, 'SOP': 3.0, 'LOR ': 2.0, 'CGPA': 7.54, 'Research': 1, 'Chance of Admit ': 0.44}
    {'_id': ObjectId('6444ccd095bfe06993327127'), 'Serial No.': 80, 'GRE Score': 294, 'TOEFL Score': 93, 'University Rating': 1, 'SOP': 1.5, 'LOR ': 2.0, 'CGPA': 7.36, 'Research': 0, 'Chance of Admit ': 0.46}
    {'_id': ObjectId('6444ccd095bfe06993327128'), 'Serial No.': 81, 'GRE Score': 312, 'TOEFL Score': 105, 'University Rating': 3, 'SOP': 2.0, 'LOR ': 3.0, 'CGPA': 8.02, 'Research': 1, 'Chance of Admit ': 0.5}
    {'_id': ObjectId('6444ccd095bfe06993327129'), 'Serial No.': 82, 'GRE Score': 340, 'TOEFL Score': 120, 'University Rating': 4, 'SOP': 5.0, 'LOR ': 5.0, 'CGPA': 9.5, 'Research': 1, 'Chance of Admit ': 0.96}
    {'_id': ObjectId('6444ccd095bfe0699332712a'), 'Serial No.': 83, 'GRE Score': 320, 'TOEFL Score': 110, 'University Rating': 5, 'SOP': 5.0, 'LOR ': 4.5, 'CGPA': 9.22, 'Research': 1, 'Chance of Admit ': 0.92}
    {'_id': ObjectId('6444ccd095bfe0699332712b'), 'Serial No.': 84, 'GRE Score': 322, 'TOEFL Score': 115, 'University Rating': 5, 'SOP': 4.0, 'LOR ': 4.5, 'CGPA': 9.36, 'Research': 1, 'Chance of Admit ': 0.92}
    {'_id': ObjectId('6444ccd095bfe0699332712c'), 'Serial No.': 85, 'GRE Score': 340, 'TOEFL Score': 115, 'University Rating': 5, 'SOP': 4.5, 'LOR ': 4.5, 'CGPA': 9.45, 'Research': 1, 'Chance of Admit ': 0.94}
    {'_id': ObjectId('6444ccd095bfe0699332712d'), 'Serial No.': 86, 'GRE Score': 319, 'TOEFL Score': 103, 'University Rating': 4, 'SOP': 4.5, 'LOR ': 3.5, 'CGPA': 8.66, 'Research': 0, 'Chance of Admit ': 0.76}
    {'_id': ObjectId('6444ccd095bfe0699332712e'), 'Serial No.': 87, 'GRE Score': 315, 'TOEFL Score': 106, 'University Rating': 3, 'SOP': 4.5, 'LOR ': 3.5, 'CGPA': 8.42, 'Research': 0, 'Chance of Admit ': 0.72}
    {'_id': ObjectId('6444ccd095bfe0699332712f'), 'Serial No.': 88, 'GRE Score': 317, 'TOEFL Score': 107, 'University Rating': 2, 'SOP': 3.5, 'LOR ': 3.0, 'CGPA': 8.28, 'Research': 0, 'Chance of Admit ': 0.66}
    {'_id': ObjectId('6444ccd095bfe06993327130'), 'Serial No.': 89, 'GRE Score': 314, 'TOEFL Score': 108, 'University Rating': 3, 'SOP': 4.5, 'LOR ': 3.5, 'CGPA': 8.14, 'Research': 0, 'Chance of Admit ': 0.64}
    {'_id': ObjectId('6444ccd095bfe06993327131'), 'Serial No.': 90, 'GRE Score': 316, 'TOEFL Score': 109, 'University Rating': 4, 'SOP': 4.5, 'LOR ': 3.5, 'CGPA': 8.76, 'Research': 1, 'Chance of Admit ': 0.74}
    {'_id': ObjectId('6444ccd095bfe06993327132'), 'Serial No.': 91, 'GRE Score': 318, 'TOEFL Score': 106, 'University Rating': 2, 'SOP': 4.0, 'LOR ': 4.0, 'CGPA': 7.92, 'Research': 1, 'Chance of Admit ': 0.64}
    {'_id': ObjectId('6444ccd095bfe06993327133'), 'Serial No.': 92, 'GRE Score': 299, 'TOEFL Score': 97, 'University Rating': 3, 'SOP': 5.0, 'LOR ': 3.5, 'CGPA': 7.66, 'Research': 0, 'Chance of Admit ': 0.38}
    {'_id': ObjectId('6444ccd095bfe06993327134'), 'Serial No.': 93, 'GRE Score': 298, 'TOEFL Score': 98, 'University Rating': 2, 'SOP': 4.0, 'LOR ': 3.0, 'CGPA': 8.03, 'Research': 0, 'Chance of Admit ': 0.34}
    {'_id': ObjectId('6444ccd095bfe06993327135'), 'Serial No.': 94, 'GRE Score': 301, 'TOEFL Score': 97, 'University Rating': 2, 'SOP': 3.0, 'LOR ': 3.0, 'CGPA': 7.88, 'Research': 1, 'Chance of Admit ': 0.44}
    {'_id': ObjectId('6444ccd095bfe06993327136'), 'Serial No.': 95, 'GRE Score': 303, 'TOEFL Score': 99, 'University Rating': 3, 'SOP': 2.0, 'LOR ': 2.5, 'CGPA': 7.66, 'Research': 0, 'Chance of Admit ': 0.36}
    {'_id': ObjectId('6444ccd095bfe06993327137'), 'Serial No.': 96, 'GRE Score': 304, 'TOEFL Score': 100, 'University Rating': 4, 'SOP': 1.5, 'LOR ': 2.5, 'CGPA': 7.84, 'Research': 0, 'Chance of Admit ': 0.42}
    {'_id': ObjectId('6444ccd095bfe06993327138'), 'Serial No.': 97, 'GRE Score': 306, 'TOEFL Score': 100, 'University Rating': 2, 'SOP': 3.0, 'LOR ': 3.0, 'CGPA': 8.0, 'Research': 0, 'Chance of Admit ': 0.48}
    {'_id': ObjectId('6444ccd095bfe06993327139'), 'Serial No.': 98, 'GRE Score': 331, 'TOEFL Score': 120, 'University Rating': 3, 'SOP': 4.0, 'LOR ': 4.0, 'CGPA': 8.96, 'Research': 1, 'Chance of Admit ': 0.86}
    {'_id': ObjectId('6444ccd095bfe0699332713a'), 'Serial No.': 99, 'GRE Score': 332, 'TOEFL Score': 119, 'University Rating': 4, 'SOP': 5.0, 'LOR ': 4.5, 'CGPA': 9.24, 'Research': 1, 'Chance of Admit ': 0.9}
    {'_id': ObjectId('6444ccd095bfe0699332713b'), 'Serial No.': 100, 'GRE Score': 323, 'TOEFL Score': 113, 'University Rating': 3, 'SOP': 4.0, 'LOR ': 4.0, 'CGPA': 8.88, 'Research': 1, 'Chance of Admit ': 0.79}
    {'_id': ObjectId('6444ccd095bfe0699332713c'), 'Serial No.': 101, 'GRE Score': 322, 'TOEFL Score': 107, 'University Rating': 3, 'SOP': 3.5, 'LOR ': 3.5, 'CGPA': 8.46, 'Research': 1, 'Chance of Admit ': 0.71}
    {'_id': ObjectId('6444ccd095bfe0699332713d'), 'Serial No.': 102, 'GRE Score': 312, 'TOEFL Score': 105, 'University Rating': 2, 'SOP': 2.5, 'LOR ': 3.0, 'CGPA': 8.12, 'Research': 0, 'Chance of Admit ': 0.64}
    {'_id': ObjectId('6444ccd095bfe0699332713e'), 'Serial No.': 103, 'GRE Score': 314, 'TOEFL Score': 106, 'University Rating': 2, 'SOP': 4.0, 'LOR ': 3.5, 'CGPA': 8.25, 'Research': 0, 'Chance of Admit ': 0.62}
    {'_id': ObjectId('6444ccd095bfe0699332713f'), 'Serial No.': 104, 'GRE Score': 317, 'TOEFL Score': 104, 'University Rating': 2, 'SOP': 4.5, 'LOR ': 4.0, 'CGPA': 8.47, 'Research': 0, 'Chance of Admit ': 0.57}
    {'_id': ObjectId('6444ccd095bfe06993327140'), 'Serial No.': 105, 'GRE Score': 326, 'TOEFL Score': 112, 'University Rating': 3, 'SOP': 3.5, 'LOR ': 3.0, 'CGPA': 9.05, 'Research': 1, 'Chance of Admit ': 0.74}
    {'_id': ObjectId('6444ccd095bfe06993327141'), 'Serial No.': 106, 'GRE Score': 316, 'TOEFL Score': 110, 'University Rating': 3, 'SOP': 4.0, 'LOR ': 4.5, 'CGPA': 8.78, 'Research': 1, 'Chance of Admit ': 0.69}
    {'_id': ObjectId('6444ccd095bfe06993327142'), 'Serial No.': 107, 'GRE Score': 329, 'TOEFL Score': 111, 'University Rating': 4, 'SOP': 4.5, 'LOR ': 4.5, 'CGPA': 9.18, 'Research': 1, 'Chance of Admit ': 0.87}
    {'_id': ObjectId('6444ccd095bfe06993327143'), 'Serial No.': 108, 'GRE Score': 338, 'TOEFL Score': 117, 'University Rating': 4, 'SOP': 3.5, 'LOR ': 4.5, 'CGPA': 9.46, 'Research': 1, 'Chance of Admit ': 0.91}
    {'_id': ObjectId('6444ccd095bfe06993327144'), 'Serial No.': 109, 'GRE Score': 331, 'TOEFL Score': 116, 'University Rating': 5, 'SOP': 5.0, 'LOR ': 5.0, 'CGPA': 9.38, 'Research': 1, 'Chance of Admit ': 0.93}
    {'_id': ObjectId('6444ccd095bfe06993327145'), 'Serial No.': 110, 'GRE Score': 304, 'TOEFL Score': 103, 'University Rating': 5, 'SOP': 5.0, 'LOR ': 4.0, 'CGPA': 8.64, 'Research': 0, 'Chance of Admit ': 0.68}
    {'_id': ObjectId('6444ccd095bfe06993327146'), 'Serial No.': 111, 'GRE Score': 305, 'TOEFL Score': 108, 'University Rating': 5, 'SOP': 3.0, 'LOR ': 3.0, 'CGPA': 8.48, 'Research': 0, 'Chance of Admit ': 0.61}
    {'_id': ObjectId('6444ccd095bfe06993327147'), 'Serial No.': 112, 'GRE Score': 321, 'TOEFL Score': 109, 'University Rating': 4, 'SOP': 4.0, 'LOR ': 4.0, 'CGPA': 8.68, 'Research': 1, 'Chance of Admit ': 0.69}
    {'_id': ObjectId('6444ccd095bfe06993327148'), 'Serial No.': 113, 'GRE Score': 301, 'TOEFL Score': 107, 'University Rating': 3, 'SOP': 3.5, 'LOR ': 3.5, 'CGPA': 8.34, 'Research': 1, 'Chance of Admit ': 0.62}
    {'_id': ObjectId('6444ccd095bfe06993327149'), 'Serial No.': 114, 'GRE Score': 320, 'TOEFL Score': 110, 'University Rating': 2, 'SOP': 4.0, 'LOR ': 3.5, 'CGPA': 8.56, 'Research': 0, 'Chance of Admit ': 0.72}
    {'_id': ObjectId('6444ccd095bfe0699332714a'), 'Serial No.': 115, 'GRE Score': 311, 'TOEFL Score': 105, 'University Rating': 3, 'SOP': 3.5, 'LOR ': 3.0, 'CGPA': 8.45, 'Research': 1, 'Chance of Admit ': 0.59}
    {'_id': ObjectId('6444ccd095bfe0699332714b'), 'Serial No.': 116, 'GRE Score': 310, 'TOEFL Score': 106, 'University Rating': 4, 'SOP': 4.5, 'LOR ': 4.5, 'CGPA': 9.04, 'Research': 1, 'Chance of Admit ': 0.66}
    {'_id': ObjectId('6444ccd095bfe0699332714c'), 'Serial No.': 117, 'GRE Score': 299, 'TOEFL Score': 102, 'University Rating': 3, 'SOP': 4.0, 'LOR ': 3.5, 'CGPA': 8.62, 'Research': 0, 'Chance of Admit ': 0.56}
    {'_id': ObjectId('6444ccd095bfe0699332714d'), 'Serial No.': 118, 'GRE Score': 290, 'TOEFL Score': 104, 'University Rating': 4, 'SOP': 2.0, 'LOR ': 2.5, 'CGPA': 7.46, 'Research': 0, 'Chance of Admit ': 0.45}
    {'_id': ObjectId('6444ccd095bfe0699332714e'), 'Serial No.': 119, 'GRE Score': 296, 'TOEFL Score': 99, 'University Rating': 2, 'SOP': 3.0, 'LOR ': 3.5, 'CGPA': 7.28, 'Research': 0, 'Chance of Admit ': 0.47}
    {'_id': ObjectId('6444ccd095bfe0699332714f'), 'Serial No.': 120, 'GRE Score': 327, 'TOEFL Score': 104, 'University Rating': 5, 'SOP': 3.0, 'LOR ': 3.5, 'CGPA': 8.84, 'Research': 1, 'Chance of Admit ': 0.71}
    {'_id': ObjectId('6444ccd095bfe06993327150'), 'Serial No.': 121, 'GRE Score': 335, 'TOEFL Score': 117, 'University Rating': 5, 'SOP': 5.0, 'LOR ': 5.0, 'CGPA': 9.56, 'Research': 1, 'Chance of Admit ': 0.94}
    {'_id': ObjectId('6444ccd095bfe06993327151'), 'Serial No.': 122, 'GRE Score': 334, 'TOEFL Score': 119, 'University Rating': 5, 'SOP': 4.5, 'LOR ': 4.5, 'CGPA': 9.48, 'Research': 1, 'Chance of Admit ': 0.94}
    {'_id': ObjectId('6444ccd095bfe06993327152'), 'Serial No.': 123, 'GRE Score': 310, 'TOEFL Score': 106, 'University Rating': 4, 'SOP': 1.5, 'LOR ': 2.5, 'CGPA': 8.36, 'Research': 0, 'Chance of Admit ': 0.57}
    {'_id': ObjectId('6444ccd095bfe06993327153'), 'Serial No.': 124, 'GRE Score': 308, 'TOEFL Score': 108, 'University Rating': 3, 'SOP': 3.5, 'LOR ': 3.5, 'CGPA': 8.22, 'Research': 0, 'Chance of Admit ': 0.61}
    {'_id': ObjectId('6444ccd095bfe06993327154'), 'Serial No.': 125, 'GRE Score': 301, 'TOEFL Score': 106, 'University Rating': 4, 'SOP': 2.5, 'LOR ': 3.0, 'CGPA': 8.47, 'Research': 0, 'Chance of Admit ': 0.57}
    {'_id': ObjectId('6444ccd095bfe06993327155'), 'Serial No.': 126, 'GRE Score': 300, 'TOEFL Score': 100, 'University Rating': 3, 'SOP': 2.0, 'LOR ': 3.0, 'CGPA': 8.66, 'Research': 1, 'Chance of Admit ': 0.64}
    {'_id': ObjectId('6444ccd095bfe06993327156'), 'Serial No.': 127, 'GRE Score': 323, 'TOEFL Score': 113, 'University Rating': 3, 'SOP': 4.0, 'LOR ': 3.0, 'CGPA': 9.32, 'Research': 1, 'Chance of Admit ': 0.85}
    {'_id': ObjectId('6444ccd095bfe06993327157'), 'Serial No.': 128, 'GRE Score': 319, 'TOEFL Score': 112, 'University Rating': 3, 'SOP': 2.5, 'LOR ': 2.0, 'CGPA': 8.71, 'Research': 1, 'Chance of Admit ': 0.78}
    {'_id': ObjectId('6444ccd095bfe06993327158'), 'Serial No.': 129, 'GRE Score': 326, 'TOEFL Score': 112, 'University Rating': 3, 'SOP': 3.5, 'LOR ': 3.0, 'CGPA': 9.1, 'Research': 1, 'Chance of Admit ': 0.84}
    {'_id': ObjectId('6444ccd095bfe06993327159'), 'Serial No.': 130, 'GRE Score': 333, 'TOEFL Score': 118, 'University Rating': 5, 'SOP': 5.0, 'LOR ': 5.0, 'CGPA': 9.35, 'Research': 1, 'Chance of Admit ': 0.92}
    {'_id': ObjectId('6444ccd095bfe0699332715a'), 'Serial No.': 131, 'GRE Score': 339, 'TOEFL Score': 114, 'University Rating': 5, 'SOP': 4.0, 'LOR ': 4.5, 'CGPA': 9.76, 'Research': 1, 'Chance of Admit ': 0.96}
    {'_id': ObjectId('6444ccd095bfe0699332715b'), 'Serial No.': 132, 'GRE Score': 303, 'TOEFL Score': 105, 'University Rating': 5, 'SOP': 5.0, 'LOR ': 4.5, 'CGPA': 8.65, 'Research': 0, 'Chance of Admit ': 0.77}
    {'_id': ObjectId('6444ccd095bfe0699332715c'), 'Serial No.': 133, 'GRE Score': 309, 'TOEFL Score': 105, 'University Rating': 5, 'SOP': 3.5, 'LOR ': 3.5, 'CGPA': 8.56, 'Research': 0, 'Chance of Admit ': 0.71}
    {'_id': ObjectId('6444ccd095bfe0699332715d'), 'Serial No.': 134, 'GRE Score': 323, 'TOEFL Score': 112, 'University Rating': 5, 'SOP': 4.0, 'LOR ': 4.5, 'CGPA': 8.78, 'Research': 0, 'Chance of Admit ': 0.79}
    {'_id': ObjectId('6444ccd095bfe0699332715e'), 'Serial No.': 135, 'GRE Score': 333, 'TOEFL Score': 113, 'University Rating': 5, 'SOP': 4.0, 'LOR ': 4.0, 'CGPA': 9.28, 'Research': 1, 'Chance of Admit ': 0.89}
    {'_id': ObjectId('6444ccd095bfe0699332715f'), 'Serial No.': 136, 'GRE Score': 314, 'TOEFL Score': 109, 'University Rating': 4, 'SOP': 3.5, 'LOR ': 4.0, 'CGPA': 8.77, 'Research': 1, 'Chance of Admit ': 0.82}
    {'_id': ObjectId('6444ccd095bfe06993327160'), 'Serial No.': 137, 'GRE Score': 312, 'TOEFL Score': 103, 'University Rating': 3, 'SOP': 5.0, 'LOR ': 4.0, 'CGPA': 8.45, 'Research': 0, 'Chance of Admit ': 0.76}
    {'_id': ObjectId('6444ccd095bfe06993327161'), 'Serial No.': 138, 'GRE Score': 316, 'TOEFL Score': 100, 'University Rating': 2, 'SOP': 1.5, 'LOR ': 3.0, 'CGPA': 8.16, 'Research': 1, 'Chance of Admit ': 0.71}
    {'_id': ObjectId('6444ccd095bfe06993327162'), 'Serial No.': 139, 'GRE Score': 326, 'TOEFL Score': 116, 'University Rating': 2, 'SOP': 4.5, 'LOR ': 3.0, 'CGPA': 9.08, 'Research': 1, 'Chance of Admit ': 0.8}
    {'_id': ObjectId('6444ccd095bfe06993327163'), 'Serial No.': 140, 'GRE Score': 318, 'TOEFL Score': 109, 'University Rating': 1, 'SOP': 3.5, 'LOR ': 3.5, 'CGPA': 9.12, 'Research': 0, 'Chance of Admit ': 0.78}
    {'_id': ObjectId('6444ccd095bfe06993327164'), 'Serial No.': 141, 'GRE Score': 329, 'TOEFL Score': 110, 'University Rating': 2, 'SOP': 4.0, 'LOR ': 3.0, 'CGPA': 9.15, 'Research': 1, 'Chance of Admit ': 0.84}
    {'_id': ObjectId('6444ccd095bfe06993327165'), 'Serial No.': 142, 'GRE Score': 332, 'TOEFL Score': 118, 'University Rating': 2, 'SOP': 4.5, 'LOR ': 3.5, 'CGPA': 9.36, 'Research': 1, 'Chance of Admit ': 0.9}
    {'_id': ObjectId('6444ccd095bfe06993327166'), 'Serial No.': 143, 'GRE Score': 331, 'TOEFL Score': 115, 'University Rating': 5, 'SOP': 4.0, 'LOR ': 3.5, 'CGPA': 9.44, 'Research': 1, 'Chance of Admit ': 0.92}
    {'_id': ObjectId('6444ccd095bfe06993327167'), 'Serial No.': 144, 'GRE Score': 340, 'TOEFL Score': 120, 'University Rating': 4, 'SOP': 4.5, 'LOR ': 4.0, 'CGPA': 9.92, 'Research': 1, 'Chance of Admit ': 0.97}
    {'_id': ObjectId('6444ccd095bfe06993327168'), 'Serial No.': 145, 'GRE Score': 325, 'TOEFL Score': 112, 'University Rating': 2, 'SOP': 3.0, 'LOR ': 3.5, 'CGPA': 8.96, 'Research': 1, 'Chance of Admit ': 0.8}
    {'_id': ObjectId('6444ccd095bfe06993327169'), 'Serial No.': 146, 'GRE Score': 320, 'TOEFL Score': 113, 'University Rating': 2, 'SOP': 2.0, 'LOR ': 2.5, 'CGPA': 8.64, 'Research': 1, 'Chance of Admit ': 0.81}
    {'_id': ObjectId('6444ccd095bfe0699332716a'), 'Serial No.': 147, 'GRE Score': 315, 'TOEFL Score': 105, 'University Rating': 3, 'SOP': 2.0, 'LOR ': 2.5, 'CGPA': 8.48, 'Research': 0, 'Chance of Admit ': 0.75}
    {'_id': ObjectId('6444ccd095bfe0699332716b'), 'Serial No.': 148, 'GRE Score': 326, 'TOEFL Score': 114, 'University Rating': 3, 'SOP': 3.0, 'LOR ': 3.0, 'CGPA': 9.11, 'Research': 1, 'Chance of Admit ': 0.83}
    {'_id': ObjectId('6444ccd095bfe0699332716c'), 'Serial No.': 149, 'GRE Score': 339, 'TOEFL Score': 116, 'University Rating': 4, 'SOP': 4.0, 'LOR ': 3.5, 'CGPA': 9.8, 'Research': 1, 'Chance of Admit ': 0.96}
    {'_id': ObjectId('6444ccd095bfe0699332716d'), 'Serial No.': 150, 'GRE Score': 311, 'TOEFL Score': 106, 'University Rating': 2, 'SOP': 3.5, 'LOR ': 3.0, 'CGPA': 8.26, 'Research': 1, 'Chance of Admit ': 0.79}
    {'_id': ObjectId('6444ccd095bfe0699332716e'), 'Serial No.': 151, 'GRE Score': 334, 'TOEFL Score': 114, 'University Rating': 4, 'SOP': 4.0, 'LOR ': 4.0, 'CGPA': 9.43, 'Research': 1, 'Chance of Admit ': 0.93}
    {'_id': ObjectId('6444ccd095bfe0699332716f'), 'Serial No.': 152, 'GRE Score': 332, 'TOEFL Score': 116, 'University Rating': 5, 'SOP': 5.0, 'LOR ': 5.0, 'CGPA': 9.28, 'Research': 1, 'Chance of Admit ': 0.94}
    {'_id': ObjectId('6444ccd095bfe06993327170'), 'Serial No.': 153, 'GRE Score': 321, 'TOEFL Score': 112, 'University Rating': 5, 'SOP': 5.0, 'LOR ': 5.0, 'CGPA': 9.06, 'Research': 1, 'Chance of Admit ': 0.86}
    {'_id': ObjectId('6444ccd095bfe06993327171'), 'Serial No.': 154, 'GRE Score': 324, 'TOEFL Score': 105, 'University Rating': 3, 'SOP': 3.0, 'LOR ': 4.0, 'CGPA': 8.75, 'Research': 0, 'Chance of Admit ': 0.79}
    {'_id': ObjectId('6444ccd095bfe06993327172'), 'Serial No.': 155, 'GRE Score': 326, 'TOEFL Score': 108, 'University Rating': 3, 'SOP': 3.0, 'LOR ': 3.5, 'CGPA': 8.89, 'Research': 0, 'Chance of Admit ': 0.8}
    {'_id': ObjectId('6444ccd095bfe06993327173'), 'Serial No.': 156, 'GRE Score': 312, 'TOEFL Score': 109, 'University Rating': 3, 'SOP': 3.0, 'LOR ': 3.0, 'CGPA': 8.69, 'Research': 0, 'Chance of Admit ': 0.77}
    {'_id': ObjectId('6444ccd095bfe06993327174'), 'Serial No.': 157, 'GRE Score': 315, 'TOEFL Score': 105, 'University Rating': 3, 'SOP': 2.0, 'LOR ': 2.5, 'CGPA': 8.34, 'Research': 0, 'Chance of Admit ': 0.7}
    {'_id': ObjectId('6444ccd095bfe06993327175'), 'Serial No.': 158, 'GRE Score': 309, 'TOEFL Score': 104, 'University Rating': 2, 'SOP': 2.0, 'LOR ': 2.5, 'CGPA': 8.26, 'Research': 0, 'Chance of Admit ': 0.65}
    {'_id': ObjectId('6444ccd095bfe06993327176'), 'Serial No.': 159, 'GRE Score': 306, 'TOEFL Score': 106, 'University Rating': 2, 'SOP': 2.0, 'LOR ': 2.5, 'CGPA': 8.14, 'Research': 0, 'Chance of Admit ': 0.61}
    {'_id': ObjectId('6444ccd095bfe06993327177'), 'Serial No.': 160, 'GRE Score': 297, 'TOEFL Score': 100, 'University Rating': 1, 'SOP': 1.5, 'LOR ': 2.0, 'CGPA': 7.9, 'Research': 0, 'Chance of Admit ': 0.52}
    {'_id': ObjectId('6444ccd095bfe06993327178'), 'Serial No.': 161, 'GRE Score': 315, 'TOEFL Score': 103, 'University Rating': 1, 'SOP': 1.5, 'LOR ': 2.0, 'CGPA': 7.86, 'Research': 0, 'Chance of Admit ': 0.57}
    {'_id': ObjectId('6444ccd095bfe06993327179'), 'Serial No.': 162, 'GRE Score': 298, 'TOEFL Score': 99, 'University Rating': 1, 'SOP': 1.5, 'LOR ': 3.0, 'CGPA': 7.46, 'Research': 0, 'Chance of Admit ': 0.53}
    {'_id': ObjectId('6444ccd095bfe0699332717a'), 'Serial No.': 163, 'GRE Score': 318, 'TOEFL Score': 109, 'University Rating': 3, 'SOP': 3.0, 'LOR ': 3.0, 'CGPA': 8.5, 'Research': 0, 'Chance of Admit ': 0.67}
    {'_id': ObjectId('6444ccd095bfe0699332717b'), 'Serial No.': 164, 'GRE Score': 317, 'TOEFL Score': 105, 'University Rating': 3, 'SOP': 3.5, 'LOR ': 3.0, 'CGPA': 8.56, 'Research': 0, 'Chance of Admit ': 0.68}
    {'_id': ObjectId('6444ccd095bfe0699332717c'), 'Serial No.': 165, 'GRE Score': 329, 'TOEFL Score': 111, 'University Rating': 4, 'SOP': 4.5, 'LOR ': 4.0, 'CGPA': 9.01, 'Research': 1, 'Chance of Admit ': 0.81}
    {'_id': ObjectId('6444ccd095bfe0699332717d'), 'Serial No.': 166, 'GRE Score': 322, 'TOEFL Score': 110, 'University Rating': 5, 'SOP': 4.5, 'LOR ': 4.0, 'CGPA': 8.97, 'Research': 0, 'Chance of Admit ': 0.78}
    {'_id': ObjectId('6444ccd095bfe0699332717e'), 'Serial No.': 167, 'GRE Score': 302, 'TOEFL Score': 102, 'University Rating': 3, 'SOP': 3.5, 'LOR ': 5.0, 'CGPA': 8.33, 'Research': 0, 'Chance of Admit ': 0.65}
    {'_id': ObjectId('6444ccd095bfe0699332717f'), 'Serial No.': 168, 'GRE Score': 313, 'TOEFL Score': 102, 'University Rating': 3, 'SOP': 2.0, 'LOR ': 3.0, 'CGPA': 8.27, 'Research': 0, 'Chance of Admit ': 0.64}
    {'_id': ObjectId('6444ccd095bfe06993327180'), 'Serial No.': 169, 'GRE Score': 293, 'TOEFL Score': 97, 'University Rating': 2, 'SOP': 2.0, 'LOR ': 4.0, 'CGPA': 7.8, 'Research': 1, 'Chance of Admit ': 0.64}
    {'_id': ObjectId('6444ccd095bfe06993327181'), 'Serial No.': 170, 'GRE Score': 311, 'TOEFL Score': 99, 'University Rating': 2, 'SOP': 2.5, 'LOR ': 3.0, 'CGPA': 7.98, 'Research': 0, 'Chance of Admit ': 0.65}
    {'_id': ObjectId('6444ccd095bfe06993327182'), 'Serial No.': 171, 'GRE Score': 312, 'TOEFL Score': 101, 'University Rating': 2, 'SOP': 2.5, 'LOR ': 3.5, 'CGPA': 8.04, 'Research': 1, 'Chance of Admit ': 0.68}
    {'_id': ObjectId('6444ccd095bfe06993327183'), 'Serial No.': 172, 'GRE Score': 334, 'TOEFL Score': 117, 'University Rating': 5, 'SOP': 4.0, 'LOR ': 4.5, 'CGPA': 9.07, 'Research': 1, 'Chance of Admit ': 0.89}
    {'_id': ObjectId('6444ccd095bfe06993327184'), 'Serial No.': 173, 'GRE Score': 322, 'TOEFL Score': 110, 'University Rating': 4, 'SOP': 4.0, 'LOR ': 5.0, 'CGPA': 9.13, 'Research': 1, 'Chance of Admit ': 0.86}
    {'_id': ObjectId('6444ccd095bfe06993327185'), 'Serial No.': 174, 'GRE Score': 323, 'TOEFL Score': 113, 'University Rating': 4, 'SOP': 4.0, 'LOR ': 4.5, 'CGPA': 9.23, 'Research': 1, 'Chance of Admit ': 0.89}
    {'_id': ObjectId('6444ccd095bfe06993327186'), 'Serial No.': 175, 'GRE Score': 321, 'TOEFL Score': 111, 'University Rating': 4, 'SOP': 4.0, 'LOR ': 4.0, 'CGPA': 8.97, 'Research': 1, 'Chance of Admit ': 0.87}
    {'_id': ObjectId('6444ccd095bfe06993327187'), 'Serial No.': 176, 'GRE Score': 320, 'TOEFL Score': 111, 'University Rating': 4, 'SOP': 4.5, 'LOR ': 3.5, 'CGPA': 8.87, 'Research': 1, 'Chance of Admit ': 0.85}
    {'_id': ObjectId('6444ccd095bfe06993327188'), 'Serial No.': 177, 'GRE Score': 329, 'TOEFL Score': 119, 'University Rating': 4, 'SOP': 4.5, 'LOR ': 4.5, 'CGPA': 9.16, 'Research': 1, 'Chance of Admit ': 0.9}
    {'_id': ObjectId('6444ccd095bfe06993327189'), 'Serial No.': 178, 'GRE Score': 319, 'TOEFL Score': 110, 'University Rating': 3, 'SOP': 3.5, 'LOR ': 3.5, 'CGPA': 9.04, 'Research': 0, 'Chance of Admit ': 0.82}
    {'_id': ObjectId('6444ccd095bfe0699332718a'), 'Serial No.': 179, 'GRE Score': 309, 'TOEFL Score': 108, 'University Rating': 3, 'SOP': 2.5, 'LOR ': 3.0, 'CGPA': 8.12, 'Research': 0, 'Chance of Admit ': 0.72}
    {'_id': ObjectId('6444ccd095bfe0699332718b'), 'Serial No.': 180, 'GRE Score': 307, 'TOEFL Score': 102, 'University Rating': 3, 'SOP': 3.0, 'LOR ': 3.0, 'CGPA': 8.27, 'Research': 0, 'Chance of Admit ': 0.73}
    {'_id': ObjectId('6444ccd095bfe0699332718c'), 'Serial No.': 181, 'GRE Score': 300, 'TOEFL Score': 104, 'University Rating': 3, 'SOP': 3.5, 'LOR ': 3.0, 'CGPA': 8.16, 'Research': 0, 'Chance of Admit ': 0.71}
    {'_id': ObjectId('6444ccd095bfe0699332718d'), 'Serial No.': 182, 'GRE Score': 305, 'TOEFL Score': 107, 'University Rating': 2, 'SOP': 2.5, 'LOR ': 2.5, 'CGPA': 8.42, 'Research': 0, 'Chance of Admit ': 0.71}
    {'_id': ObjectId('6444ccd095bfe0699332718e'), 'Serial No.': 183, 'GRE Score': 299, 'TOEFL Score': 100, 'University Rating': 2, 'SOP': 3.0, 'LOR ': 3.5, 'CGPA': 7.88, 'Research': 0, 'Chance of Admit ': 0.68}
    {'_id': ObjectId('6444ccd095bfe0699332718f'), 'Serial No.': 184, 'GRE Score': 314, 'TOEFL Score': 110, 'University Rating': 3, 'SOP': 4.0, 'LOR ': 4.0, 'CGPA': 8.8, 'Research': 0, 'Chance of Admit ': 0.75}
    {'_id': ObjectId('6444ccd095bfe06993327190'), 'Serial No.': 185, 'GRE Score': 316, 'TOEFL Score': 106, 'University Rating': 2, 'SOP': 2.5, 'LOR ': 4.0, 'CGPA': 8.32, 'Research': 0, 'Chance of Admit ': 0.72}
    {'_id': ObjectId('6444ccd095bfe06993327191'), 'Serial No.': 186, 'GRE Score': 327, 'TOEFL Score': 113, 'University Rating': 4, 'SOP': 4.5, 'LOR ': 4.5, 'CGPA': 9.11, 'Research': 1, 'Chance of Admit ': 0.89}
    {'_id': ObjectId('6444ccd095bfe06993327192'), 'Serial No.': 187, 'GRE Score': 317, 'TOEFL Score': 107, 'University Rating': 3, 'SOP': 3.5, 'LOR ': 3.0, 'CGPA': 8.68, 'Research': 1, 'Chance of Admit ': 0.84}
    {'_id': ObjectId('6444ccd095bfe06993327193'), 'Serial No.': 188, 'GRE Score': 335, 'TOEFL Score': 118, 'University Rating': 5, 'SOP': 4.5, 'LOR ': 3.5, 'CGPA': 9.44, 'Research': 1, 'Chance of Admit ': 0.93}
    {'_id': ObjectId('6444ccd095bfe06993327194'), 'Serial No.': 189, 'GRE Score': 331, 'TOEFL Score': 115, 'University Rating': 5, 'SOP': 4.5, 'LOR ': 3.5, 'CGPA': 9.36, 'Research': 1, 'Chance of Admit ': 0.93}
    {'_id': ObjectId('6444ccd095bfe06993327195'), 'Serial No.': 190, 'GRE Score': 324, 'TOEFL Score': 112, 'University Rating': 5, 'SOP': 5.0, 'LOR ': 5.0, 'CGPA': 9.08, 'Research': 1, 'Chance of Admit ': 0.88}
    {'_id': ObjectId('6444ccd095bfe06993327196'), 'Serial No.': 191, 'GRE Score': 324, 'TOEFL Score': 111, 'University Rating': 5, 'SOP': 4.5, 'LOR ': 4.0, 'CGPA': 9.16, 'Research': 1, 'Chance of Admit ': 0.9}
    {'_id': ObjectId('6444ccd095bfe06993327197'), 'Serial No.': 192, 'GRE Score': 323, 'TOEFL Score': 110, 'University Rating': 5, 'SOP': 4.0, 'LOR ': 5.0, 'CGPA': 8.98, 'Research': 1, 'Chance of Admit ': 0.87}
    {'_id': ObjectId('6444ccd095bfe06993327198'), 'Serial No.': 193, 'GRE Score': 322, 'TOEFL Score': 114, 'University Rating': 5, 'SOP': 4.5, 'LOR ': 4.0, 'CGPA': 8.94, 'Research': 1, 'Chance of Admit ': 0.86}
    {'_id': ObjectId('6444ccd095bfe06993327199'), 'Serial No.': 194, 'GRE Score': 336, 'TOEFL Score': 118, 'University Rating': 5, 'SOP': 4.5, 'LOR ': 5.0, 'CGPA': 9.53, 'Research': 1, 'Chance of Admit ': 0.94}
    {'_id': ObjectId('6444ccd095bfe0699332719a'), 'Serial No.': 195, 'GRE Score': 316, 'TOEFL Score': 109, 'University Rating': 3, 'SOP': 3.5, 'LOR ': 3.0, 'CGPA': 8.76, 'Research': 0, 'Chance of Admit ': 0.77}
    {'_id': ObjectId('6444ccd095bfe0699332719b'), 'Serial No.': 196, 'GRE Score': 307, 'TOEFL Score': 107, 'University Rating': 2, 'SOP': 3.0, 'LOR ': 3.5, 'CGPA': 8.52, 'Research': 1, 'Chance of Admit ': 0.78}
    {'_id': ObjectId('6444ccd095bfe0699332719c'), 'Serial No.': 197, 'GRE Score': 306, 'TOEFL Score': 105, 'University Rating': 2, 'SOP': 3.0, 'LOR ': 2.5, 'CGPA': 8.26, 'Research': 0, 'Chance of Admit ': 0.73}
    {'_id': ObjectId('6444ccd095bfe0699332719d'), 'Serial No.': 198, 'GRE Score': 310, 'TOEFL Score': 106, 'University Rating': 2, 'SOP': 3.5, 'LOR ': 2.5, 'CGPA': 8.33, 'Research': 0, 'Chance of Admit ': 0.73}
    {'_id': ObjectId('6444ccd095bfe0699332719e'), 'Serial No.': 199, 'GRE Score': 311, 'TOEFL Score': 104, 'University Rating': 3, 'SOP': 4.5, 'LOR ': 4.5, 'CGPA': 8.43, 'Research': 0, 'Chance of Admit ': 0.7}
    {'_id': ObjectId('6444ccd095bfe0699332719f'), 'Serial No.': 200, 'GRE Score': 313, 'TOEFL Score': 107, 'University Rating': 3, 'SOP': 4.0, 'LOR ': 4.5, 'CGPA': 8.69, 'Research': 0, 'Chance of Admit ': 0.72}
    {'_id': ObjectId('6444ccd095bfe069933271a0'), 'Serial No.': 201, 'GRE Score': 317, 'TOEFL Score': 103, 'University Rating': 3, 'SOP': 2.5, 'LOR ': 3.0, 'CGPA': 8.54, 'Research': 1, 'Chance of Admit ': 0.73}
    {'_id': ObjectId('6444ccd095bfe069933271a1'), 'Serial No.': 202, 'GRE Score': 315, 'TOEFL Score': 110, 'University Rating': 2, 'SOP': 3.5, 'LOR ': 3.0, 'CGPA': 8.46, 'Research': 1, 'Chance of Admit ': 0.72}
    {'_id': ObjectId('6444ccd095bfe069933271a2'), 'Serial No.': 203, 'GRE Score': 340, 'TOEFL Score': 120, 'University Rating': 5, 'SOP': 4.5, 'LOR ': 4.5, 'CGPA': 9.91, 'Research': 1, 'Chance of Admit ': 0.97}
    {'_id': ObjectId('6444ccd095bfe069933271a3'), 'Serial No.': 204, 'GRE Score': 334, 'TOEFL Score': 120, 'University Rating': 5, 'SOP': 4.0, 'LOR ': 5.0, 'CGPA': 9.87, 'Research': 1, 'Chance of Admit ': 0.97}
    {'_id': ObjectId('6444ccd095bfe069933271a4'), 'Serial No.': 205, 'GRE Score': 298, 'TOEFL Score': 105, 'University Rating': 3, 'SOP': 3.5, 'LOR ': 4.0, 'CGPA': 8.54, 'Research': 0, 'Chance of Admit ': 0.69}
    {'_id': ObjectId('6444ccd095bfe069933271a5'), 'Serial No.': 206, 'GRE Score': 295, 'TOEFL Score': 99, 'University Rating': 2, 'SOP': 2.5, 'LOR ': 3.0, 'CGPA': 7.65, 'Research': 0, 'Chance of Admit ': 0.57}
    {'_id': ObjectId('6444ccd095bfe069933271a6'), 'Serial No.': 207, 'GRE Score': 315, 'TOEFL Score': 99, 'University Rating': 2, 'SOP': 3.5, 'LOR ': 3.0, 'CGPA': 7.89, 'Research': 0, 'Chance of Admit ': 0.63}
    {'_id': ObjectId('6444ccd095bfe069933271a7'), 'Serial No.': 208, 'GRE Score': 310, 'TOEFL Score': 102, 'University Rating': 3, 'SOP': 3.5, 'LOR ': 4.0, 'CGPA': 8.02, 'Research': 1, 'Chance of Admit ': 0.66}
    {'_id': ObjectId('6444ccd095bfe069933271a8'), 'Serial No.': 209, 'GRE Score': 305, 'TOEFL Score': 106, 'University Rating': 2, 'SOP': 3.0, 'LOR ': 3.0, 'CGPA': 8.16, 'Research': 0, 'Chance of Admit ': 0.64}
    {'_id': ObjectId('6444ccd095bfe069933271a9'), 'Serial No.': 210, 'GRE Score': 301, 'TOEFL Score': 104, 'University Rating': 3, 'SOP': 3.5, 'LOR ': 4.0, 'CGPA': 8.12, 'Research': 1, 'Chance of Admit ': 0.68}
    {'_id': ObjectId('6444ccd095bfe069933271aa'), 'Serial No.': 211, 'GRE Score': 325, 'TOEFL Score': 108, 'University Rating': 4, 'SOP': 4.5, 'LOR ': 4.0, 'CGPA': 9.06, 'Research': 1, 'Chance of Admit ': 0.79}
    {'_id': ObjectId('6444ccd095bfe069933271ab'), 'Serial No.': 212, 'GRE Score': 328, 'TOEFL Score': 110, 'University Rating': 4, 'SOP': 5.0, 'LOR ': 4.0, 'CGPA': 9.14, 'Research': 1, 'Chance of Admit ': 0.82}
    {'_id': ObjectId('6444ccd095bfe069933271ac'), 'Serial No.': 213, 'GRE Score': 338, 'TOEFL Score': 120, 'University Rating': 4, 'SOP': 5.0, 'LOR ': 5.0, 'CGPA': 9.66, 'Research': 1, 'Chance of Admit ': 0.95}
    {'_id': ObjectId('6444ccd095bfe069933271ad'), 'Serial No.': 214, 'GRE Score': 333, 'TOEFL Score': 119, 'University Rating': 5, 'SOP': 5.0, 'LOR ': 4.5, 'CGPA': 9.78, 'Research': 1, 'Chance of Admit ': 0.96}
    {'_id': ObjectId('6444ccd095bfe069933271ae'), 'Serial No.': 215, 'GRE Score': 331, 'TOEFL Score': 117, 'University Rating': 4, 'SOP': 4.5, 'LOR ': 5.0, 'CGPA': 9.42, 'Research': 1, 'Chance of Admit ': 0.94}
    {'_id': ObjectId('6444ccd095bfe069933271af'), 'Serial No.': 216, 'GRE Score': 330, 'TOEFL Score': 116, 'University Rating': 5, 'SOP': 5.0, 'LOR ': 4.5, 'CGPA': 9.36, 'Research': 1, 'Chance of Admit ': 0.93}
    {'_id': ObjectId('6444ccd095bfe069933271b0'), 'Serial No.': 217, 'GRE Score': 322, 'TOEFL Score': 112, 'University Rating': 4, 'SOP': 4.5, 'LOR ': 4.5, 'CGPA': 9.26, 'Research': 1, 'Chance of Admit ': 0.91}
    {'_id': ObjectId('6444ccd095bfe069933271b1'), 'Serial No.': 218, 'GRE Score': 321, 'TOEFL Score': 109, 'University Rating': 4, 'SOP': 4.0, 'LOR ': 4.0, 'CGPA': 9.13, 'Research': 1, 'Chance of Admit ': 0.85}
    {'_id': ObjectId('6444ccd095bfe069933271b2'), 'Serial No.': 219, 'GRE Score': 324, 'TOEFL Score': 110, 'University Rating': 4, 'SOP': 3.0, 'LOR ': 3.5, 'CGPA': 8.97, 'Research': 1, 'Chance of Admit ': 0.84}
    {'_id': ObjectId('6444ccd095bfe069933271b3'), 'Serial No.': 220, 'GRE Score': 312, 'TOEFL Score': 104, 'University Rating': 3, 'SOP': 3.5, 'LOR ': 3.5, 'CGPA': 8.42, 'Research': 0, 'Chance of Admit ': 0.74}
    {'_id': ObjectId('6444ccd095bfe069933271b4'), 'Serial No.': 221, 'GRE Score': 313, 'TOEFL Score': 103, 'University Rating': 3, 'SOP': 4.0, 'LOR ': 4.0, 'CGPA': 8.75, 'Research': 0, 'Chance of Admit ': 0.76}
    {'_id': ObjectId('6444ccd095bfe069933271b5'), 'Serial No.': 222, 'GRE Score': 316, 'TOEFL Score': 110, 'University Rating': 3, 'SOP': 3.5, 'LOR ': 4.0, 'CGPA': 8.56, 'Research': 0, 'Chance of Admit ': 0.75}
    {'_id': ObjectId('6444ccd095bfe069933271b6'), 'Serial No.': 223, 'GRE Score': 324, 'TOEFL Score': 113, 'University Rating': 4, 'SOP': 4.5, 'LOR ': 4.0, 'CGPA': 8.79, 'Research': 0, 'Chance of Admit ': 0.76}
    {'_id': ObjectId('6444ccd095bfe069933271b7'), 'Serial No.': 224, 'GRE Score': 308, 'TOEFL Score': 109, 'University Rating': 2, 'SOP': 3.0, 'LOR ': 4.0, 'CGPA': 8.45, 'Research': 0, 'Chance of Admit ': 0.71}
    {'_id': ObjectId('6444ccd095bfe069933271b8'), 'Serial No.': 225, 'GRE Score': 305, 'TOEFL Score': 105, 'University Rating': 2, 'SOP': 3.0, 'LOR ': 2.0, 'CGPA': 8.23, 'Research': 0, 'Chance of Admit ': 0.67}
    {'_id': ObjectId('6444ccd095bfe069933271b9'), 'Serial No.': 226, 'GRE Score': 296, 'TOEFL Score': 99, 'University Rating': 2, 'SOP': 2.5, 'LOR ': 2.5, 'CGPA': 8.03, 'Research': 0, 'Chance of Admit ': 0.61}
    {'_id': ObjectId('6444ccd095bfe069933271ba'), 'Serial No.': 227, 'GRE Score': 306, 'TOEFL Score': 110, 'University Rating': 2, 'SOP': 3.5, 'LOR ': 4.0, 'CGPA': 8.45, 'Research': 0, 'Chance of Admit ': 0.63}
    {'_id': ObjectId('6444ccd095bfe069933271bb'), 'Serial No.': 228, 'GRE Score': 312, 'TOEFL Score': 110, 'University Rating': 2, 'SOP': 3.5, 'LOR ': 3.0, 'CGPA': 8.53, 'Research': 0, 'Chance of Admit ': 0.64}
    {'_id': ObjectId('6444ccd095bfe069933271bc'), 'Serial No.': 229, 'GRE Score': 318, 'TOEFL Score': 112, 'University Rating': 3, 'SOP': 4.0, 'LOR ': 3.5, 'CGPA': 8.67, 'Research': 0, 'Chance of Admit ': 0.71}
    {'_id': ObjectId('6444ccd095bfe069933271bd'), 'Serial No.': 230, 'GRE Score': 324, 'TOEFL Score': 111, 'University Rating': 4, 'SOP': 3.0, 'LOR ': 3.0, 'CGPA': 9.01, 'Research': 1, 'Chance of Admit ': 0.82}
    {'_id': ObjectId('6444ccd095bfe069933271be'), 'Serial No.': 231, 'GRE Score': 313, 'TOEFL Score': 104, 'University Rating': 3, 'SOP': 4.0, 'LOR ': 4.5, 'CGPA': 8.65, 'Research': 0, 'Chance of Admit ': 0.73}
    {'_id': ObjectId('6444ccd095bfe069933271bf'), 'Serial No.': 232, 'GRE Score': 319, 'TOEFL Score': 106, 'University Rating': 3, 'SOP': 3.5, 'LOR ': 2.5, 'CGPA': 8.33, 'Research': 1, 'Chance of Admit ': 0.74}
    {'_id': ObjectId('6444ccd095bfe069933271c0'), 'Serial No.': 233, 'GRE Score': 312, 'TOEFL Score': 107, 'University Rating': 2, 'SOP': 2.5, 'LOR ': 3.5, 'CGPA': 8.27, 'Research': 0, 'Chance of Admit ': 0.69}
    {'_id': ObjectId('6444ccd095bfe069933271c1'), 'Serial No.': 234, 'GRE Score': 304, 'TOEFL Score': 100, 'University Rating': 2, 'SOP': 2.5, 'LOR ': 3.5, 'CGPA': 8.07, 'Research': 0, 'Chance of Admit ': 0.64}
    {'_id': ObjectId('6444ccd095bfe069933271c2'), 'Serial No.': 235, 'GRE Score': 330, 'TOEFL Score': 113, 'University Rating': 5, 'SOP': 5.0, 'LOR ': 4.0, 'CGPA': 9.31, 'Research': 1, 'Chance of Admit ': 0.91}
    {'_id': ObjectId('6444ccd095bfe069933271c3'), 'Serial No.': 236, 'GRE Score': 326, 'TOEFL Score': 111, 'University Rating': 5, 'SOP': 4.5, 'LOR ': 4.0, 'CGPA': 9.23, 'Research': 1, 'Chance of Admit ': 0.88}
    {'_id': ObjectId('6444ccd095bfe069933271c4'), 'Serial No.': 237, 'GRE Score': 325, 'TOEFL Score': 112, 'University Rating': 4, 'SOP': 4.0, 'LOR ': 4.5, 'CGPA': 9.17, 'Research': 1, 'Chance of Admit ': 0.85}
    {'_id': ObjectId('6444ccd095bfe069933271c5'), 'Serial No.': 238, 'GRE Score': 329, 'TOEFL Score': 114, 'University Rating': 5, 'SOP': 4.5, 'LOR ': 5.0, 'CGPA': 9.19, 'Research': 1, 'Chance of Admit ': 0.86}
    {'_id': ObjectId('6444ccd095bfe069933271c6'), 'Serial No.': 239, 'GRE Score': 310, 'TOEFL Score': 104, 'University Rating': 3, 'SOP': 2.0, 'LOR ': 3.5, 'CGPA': 8.37, 'Research': 0, 'Chance of Admit ': 0.7}
    {'_id': ObjectId('6444ccd095bfe069933271c7'), 'Serial No.': 240, 'GRE Score': 299, 'TOEFL Score': 100, 'University Rating': 1, 'SOP': 1.5, 'LOR ': 2.0, 'CGPA': 7.89, 'Research': 0, 'Chance of Admit ': 0.59}
    {'_id': ObjectId('6444ccd095bfe069933271c8'), 'Serial No.': 241, 'GRE Score': 296, 'TOEFL Score': 101, 'University Rating': 1, 'SOP': 2.5, 'LOR ': 3.0, 'CGPA': 7.68, 'Research': 0, 'Chance of Admit ': 0.6}
    {'_id': ObjectId('6444ccd095bfe069933271c9'), 'Serial No.': 242, 'GRE Score': 317, 'TOEFL Score': 103, 'University Rating': 2, 'SOP': 2.5, 'LOR ': 2.0, 'CGPA': 8.15, 'Research': 0, 'Chance of Admit ': 0.65}
    {'_id': ObjectId('6444ccd095bfe069933271ca'), 'Serial No.': 243, 'GRE Score': 324, 'TOEFL Score': 115, 'University Rating': 3, 'SOP': 3.5, 'LOR ': 3.0, 'CGPA': 8.76, 'Research': 1, 'Chance of Admit ': 0.7}
    {'_id': ObjectId('6444ccd095bfe069933271cb'), 'Serial No.': 244, 'GRE Score': 325, 'TOEFL Score': 114, 'University Rating': 3, 'SOP': 3.5, 'LOR ': 3.0, 'CGPA': 9.04, 'Research': 1, 'Chance of Admit ': 0.76}
    {'_id': ObjectId('6444ccd095bfe069933271cc'), 'Serial No.': 245, 'GRE Score': 314, 'TOEFL Score': 107, 'University Rating': 2, 'SOP': 2.5, 'LOR ': 4.0, 'CGPA': 8.56, 'Research': 0, 'Chance of Admit ': 0.63}
    {'_id': ObjectId('6444ccd095bfe069933271cd'), 'Serial No.': 246, 'GRE Score': 328, 'TOEFL Score': 110, 'University Rating': 4, 'SOP': 4.0, 'LOR ': 2.5, 'CGPA': 9.02, 'Research': 1, 'Chance of Admit ': 0.81}
    {'_id': ObjectId('6444ccd095bfe069933271ce'), 'Serial No.': 247, 'GRE Score': 316, 'TOEFL Score': 105, 'University Rating': 3, 'SOP': 3.0, 'LOR ': 3.5, 'CGPA': 8.73, 'Research': 0, 'Chance of Admit ': 0.72}
    {'_id': ObjectId('6444ccd095bfe069933271cf'), 'Serial No.': 248, 'GRE Score': 311, 'TOEFL Score': 104, 'University Rating': 2, 'SOP': 2.5, 'LOR ': 3.5, 'CGPA': 8.48, 'Research': 0, 'Chance of Admit ': 0.71}
    {'_id': ObjectId('6444ccd095bfe069933271d0'), 'Serial No.': 249, 'GRE Score': 324, 'TOEFL Score': 110, 'University Rating': 3, 'SOP': 3.5, 'LOR ': 4.0, 'CGPA': 8.87, 'Research': 1, 'Chance of Admit ': 0.8}
    {'_id': ObjectId('6444ccd095bfe069933271d1'), 'Serial No.': 250, 'GRE Score': 321, 'TOEFL Score': 111, 'University Rating': 3, 'SOP': 3.5, 'LOR ': 4.0, 'CGPA': 8.83, 'Research': 1, 'Chance of Admit ': 0.77}
    {'_id': ObjectId('6444ccd095bfe069933271d2'), 'Serial No.': 251, 'GRE Score': 320, 'TOEFL Score': 104, 'University Rating': 3, 'SOP': 3.0, 'LOR ': 2.5, 'CGPA': 8.57, 'Research': 1, 'Chance of Admit ': 0.74}
    {'_id': ObjectId('6444ccd095bfe069933271d3'), 'Serial No.': 252, 'GRE Score': 316, 'TOEFL Score': 99, 'University Rating': 2, 'SOP': 2.5, 'LOR ': 3.0, 'CGPA': 9.0, 'Research': 0, 'Chance of Admit ': 0.7}
    {'_id': ObjectId('6444ccd095bfe069933271d4'), 'Serial No.': 253, 'GRE Score': 318, 'TOEFL Score': 100, 'University Rating': 2, 'SOP': 2.5, 'LOR ': 3.5, 'CGPA': 8.54, 'Research': 1, 'Chance of Admit ': 0.71}
    {'_id': ObjectId('6444ccd095bfe069933271d5'), 'Serial No.': 254, 'GRE Score': 335, 'TOEFL Score': 115, 'University Rating': 4, 'SOP': 4.5, 'LOR ': 4.5, 'CGPA': 9.68, 'Research': 1, 'Chance of Admit ': 0.93}
    {'_id': ObjectId('6444ccd095bfe069933271d6'), 'Serial No.': 255, 'GRE Score': 321, 'TOEFL Score': 114, 'University Rating': 4, 'SOP': 4.0, 'LOR ': 5.0, 'CGPA': 9.12, 'Research': 0, 'Chance of Admit ': 0.85}
    {'_id': ObjectId('6444ccd095bfe069933271d7'), 'Serial No.': 256, 'GRE Score': 307, 'TOEFL Score': 110, 'University Rating': 4, 'SOP': 4.0, 'LOR ': 4.5, 'CGPA': 8.37, 'Research': 0, 'Chance of Admit ': 0.79}
    {'_id': ObjectId('6444ccd095bfe069933271d8'), 'Serial No.': 257, 'GRE Score': 309, 'TOEFL Score': 99, 'University Rating': 3, 'SOP': 4.0, 'LOR ': 4.0, 'CGPA': 8.56, 'Research': 0, 'Chance of Admit ': 0.76}
    {'_id': ObjectId('6444ccd095bfe069933271d9'), 'Serial No.': 258, 'GRE Score': 324, 'TOEFL Score': 100, 'University Rating': 3, 'SOP': 4.0, 'LOR ': 5.0, 'CGPA': 8.64, 'Research': 1, 'Chance of Admit ': 0.78}
    {'_id': ObjectId('6444ccd095bfe069933271da'), 'Serial No.': 259, 'GRE Score': 326, 'TOEFL Score': 102, 'University Rating': 4, 'SOP': 5.0, 'LOR ': 5.0, 'CGPA': 8.76, 'Research': 1, 'Chance of Admit ': 0.77}
    {'_id': ObjectId('6444ccd095bfe069933271db'), 'Serial No.': 260, 'GRE Score': 331, 'TOEFL Score': 119, 'University Rating': 4, 'SOP': 5.0, 'LOR ': 4.5, 'CGPA': 9.34, 'Research': 1, 'Chance of Admit ': 0.9}
    {'_id': ObjectId('6444ccd095bfe069933271dc'), 'Serial No.': 261, 'GRE Score': 327, 'TOEFL Score': 108, 'University Rating': 5, 'SOP': 5.0, 'LOR ': 3.5, 'CGPA': 9.13, 'Research': 1, 'Chance of Admit ': 0.87}
    {'_id': ObjectId('6444ccd095bfe069933271dd'), 'Serial No.': 262, 'GRE Score': 312, 'TOEFL Score': 104, 'University Rating': 3, 'SOP': 3.5, 'LOR ': 4.0, 'CGPA': 8.09, 'Research': 0, 'Chance of Admit ': 0.71}
    {'_id': ObjectId('6444ccd095bfe069933271de'), 'Serial No.': 263, 'GRE Score': 308, 'TOEFL Score': 103, 'University Rating': 2, 'SOP': 2.5, 'LOR ': 4.0, 'CGPA': 8.36, 'Research': 1, 'Chance of Admit ': 0.7}
    {'_id': ObjectId('6444ccd095bfe069933271df'), 'Serial No.': 264, 'GRE Score': 324, 'TOEFL Score': 111, 'University Rating': 3, 'SOP': 2.5, 'LOR ': 1.5, 'CGPA': 8.79, 'Research': 1, 'Chance of Admit ': 0.7}
    {'_id': ObjectId('6444ccd095bfe069933271e0'), 'Serial No.': 265, 'GRE Score': 325, 'TOEFL Score': 110, 'University Rating': 2, 'SOP': 3.0, 'LOR ': 2.5, 'CGPA': 8.76, 'Research': 1, 'Chance of Admit ': 0.75}
    {'_id': ObjectId('6444ccd095bfe069933271e1'), 'Serial No.': 266, 'GRE Score': 313, 'TOEFL Score': 102, 'University Rating': 3, 'SOP': 2.5, 'LOR ': 2.5, 'CGPA': 8.68, 'Research': 0, 'Chance of Admit ': 0.71}
    {'_id': ObjectId('6444ccd095bfe069933271e2'), 'Serial No.': 267, 'GRE Score': 312, 'TOEFL Score': 105, 'University Rating': 2, 'SOP': 2.0, 'LOR ': 2.5, 'CGPA': 8.45, 'Research': 0, 'Chance of Admit ': 0.72}
    {'_id': ObjectId('6444ccd095bfe069933271e3'), 'Serial No.': 268, 'GRE Score': 314, 'TOEFL Score': 107, 'University Rating': 3, 'SOP': 3.0, 'LOR ': 3.5, 'CGPA': 8.17, 'Research': 1, 'Chance of Admit ': 0.73}
    {'_id': ObjectId('6444ccd095bfe069933271e4'), 'Serial No.': 269, 'GRE Score': 327, 'TOEFL Score': 113, 'University Rating': 4, 'SOP': 4.5, 'LOR ': 5.0, 'CGPA': 9.14, 'Research': 0, 'Chance of Admit ': 0.83}
    {'_id': ObjectId('6444ccd095bfe069933271e5'), 'Serial No.': 270, 'GRE Score': 308, 'TOEFL Score': 108, 'University Rating': 4, 'SOP': 4.5, 'LOR ': 5.0, 'CGPA': 8.34, 'Research': 0, 'Chance of Admit ': 0.77}
    {'_id': ObjectId('6444ccd095bfe069933271e6'), 'Serial No.': 271, 'GRE Score': 306, 'TOEFL Score': 105, 'University Rating': 2, 'SOP': 2.5, 'LOR ': 3.0, 'CGPA': 8.22, 'Research': 1, 'Chance of Admit ': 0.72}
    {'_id': ObjectId('6444ccd095bfe069933271e7'), 'Serial No.': 272, 'GRE Score': 299, 'TOEFL Score': 96, 'University Rating': 2, 'SOP': 1.5, 'LOR ': 2.0, 'CGPA': 7.86, 'Research': 0, 'Chance of Admit ': 0.54}
    {'_id': ObjectId('6444ccd095bfe069933271e8'), 'Serial No.': 273, 'GRE Score': 294, 'TOEFL Score': 95, 'University Rating': 1, 'SOP': 1.5, 'LOR ': 1.5, 'CGPA': 7.64, 'Research': 0, 'Chance of Admit ': 0.49}
    {'_id': ObjectId('6444ccd095bfe069933271e9'), 'Serial No.': 274, 'GRE Score': 312, 'TOEFL Score': 99, 'University Rating': 1, 'SOP': 1.0, 'LOR ': 1.5, 'CGPA': 8.01, 'Research': 1, 'Chance of Admit ': 0.52}
    {'_id': ObjectId('6444ccd095bfe069933271ea'), 'Serial No.': 275, 'GRE Score': 315, 'TOEFL Score': 100, 'University Rating': 1, 'SOP': 2.0, 'LOR ': 2.5, 'CGPA': 7.95, 'Research': 0, 'Chance of Admit ': 0.58}
    {'_id': ObjectId('6444ccd095bfe069933271eb'), 'Serial No.': 276, 'GRE Score': 322, 'TOEFL Score': 110, 'University Rating': 3, 'SOP': 3.5, 'LOR ': 3.0, 'CGPA': 8.96, 'Research': 1, 'Chance of Admit ': 0.78}
    {'_id': ObjectId('6444ccd095bfe069933271ec'), 'Serial No.': 277, 'GRE Score': 329, 'TOEFL Score': 113, 'University Rating': 5, 'SOP': 5.0, 'LOR ': 4.5, 'CGPA': 9.45, 'Research': 1, 'Chance of Admit ': 0.89}
    {'_id': ObjectId('6444ccd095bfe069933271ed'), 'Serial No.': 278, 'GRE Score': 320, 'TOEFL Score': 101, 'University Rating': 2, 'SOP': 2.5, 'LOR ': 3.0, 'CGPA': 8.62, 'Research': 0, 'Chance of Admit ': 0.7}
    {'_id': ObjectId('6444ccd095bfe069933271ee'), 'Serial No.': 279, 'GRE Score': 308, 'TOEFL Score': 103, 'University Rating': 2, 'SOP': 3.0, 'LOR ': 3.5, 'CGPA': 8.49, 'Research': 0, 'Chance of Admit ': 0.66}
    {'_id': ObjectId('6444ccd095bfe069933271ef'), 'Serial No.': 280, 'GRE Score': 304, 'TOEFL Score': 102, 'University Rating': 2, 'SOP': 3.0, 'LOR ': 4.0, 'CGPA': 8.73, 'Research': 0, 'Chance of Admit ': 0.67}
    {'_id': ObjectId('6444ccd095bfe069933271f0'), 'Serial No.': 281, 'GRE Score': 311, 'TOEFL Score': 102, 'University Rating': 3, 'SOP': 4.5, 'LOR ': 4.0, 'CGPA': 8.64, 'Research': 1, 'Chance of Admit ': 0.68}
    {'_id': ObjectId('6444ccd095bfe069933271f1'), 'Serial No.': 282, 'GRE Score': 317, 'TOEFL Score': 110, 'University Rating': 3, 'SOP': 4.0, 'LOR ': 4.5, 'CGPA': 9.11, 'Research': 1, 'Chance of Admit ': 0.8}
    {'_id': ObjectId('6444ccd095bfe069933271f2'), 'Serial No.': 283, 'GRE Score': 312, 'TOEFL Score': 106, 'University Rating': 3, 'SOP': 4.0, 'LOR ': 3.5, 'CGPA': 8.79, 'Research': 1, 'Chance of Admit ': 0.81}
    {'_id': ObjectId('6444ccd095bfe069933271f3'), 'Serial No.': 284, 'GRE Score': 321, 'TOEFL Score': 111, 'University Rating': 3, 'SOP': 2.5, 'LOR ': 3.0, 'CGPA': 8.9, 'Research': 1, 'Chance of Admit ': 0.8}
    {'_id': ObjectId('6444ccd095bfe069933271f4'), 'Serial No.': 285, 'GRE Score': 340, 'TOEFL Score': 112, 'University Rating': 4, 'SOP': 5.0, 'LOR ': 4.5, 'CGPA': 9.66, 'Research': 1, 'Chance of Admit ': 0.94}
    {'_id': ObjectId('6444ccd095bfe069933271f5'), 'Serial No.': 286, 'GRE Score': 331, 'TOEFL Score': 116, 'University Rating': 5, 'SOP': 4.0, 'LOR ': 4.0, 'CGPA': 9.26, 'Research': 1, 'Chance of Admit ': 0.93}
    {'_id': ObjectId('6444ccd095bfe069933271f6'), 'Serial No.': 287, 'GRE Score': 336, 'TOEFL Score': 118, 'University Rating': 5, 'SOP': 4.5, 'LOR ': 4.0, 'CGPA': 9.19, 'Research': 1, 'Chance of Admit ': 0.92}
    {'_id': ObjectId('6444ccd095bfe069933271f7'), 'Serial No.': 288, 'GRE Score': 324, 'TOEFL Score': 114, 'University Rating': 5, 'SOP': 5.0, 'LOR ': 4.5, 'CGPA': 9.08, 'Research': 1, 'Chance of Admit ': 0.89}
    {'_id': ObjectId('6444ccd095bfe069933271f8'), 'Serial No.': 289, 'GRE Score': 314, 'TOEFL Score': 104, 'University Rating': 4, 'SOP': 5.0, 'LOR ': 5.0, 'CGPA': 9.02, 'Research': 0, 'Chance of Admit ': 0.82}
    {'_id': ObjectId('6444ccd095bfe069933271f9'), 'Serial No.': 290, 'GRE Score': 313, 'TOEFL Score': 109, 'University Rating': 3, 'SOP': 4.0, 'LOR ': 3.5, 'CGPA': 9.0, 'Research': 0, 'Chance of Admit ': 0.79}
    {'_id': ObjectId('6444ccd095bfe069933271fa'), 'Serial No.': 291, 'GRE Score': 307, 'TOEFL Score': 105, 'University Rating': 2, 'SOP': 2.5, 'LOR ': 3.0, 'CGPA': 7.65, 'Research': 0, 'Chance of Admit ': 0.58}
    {'_id': ObjectId('6444ccd095bfe069933271fb'), 'Serial No.': 292, 'GRE Score': 300, 'TOEFL Score': 102, 'University Rating': 2, 'SOP': 1.5, 'LOR ': 2.0, 'CGPA': 7.87, 'Research': 0, 'Chance of Admit ': 0.56}
    {'_id': ObjectId('6444ccd095bfe069933271fc'), 'Serial No.': 293, 'GRE Score': 302, 'TOEFL Score': 99, 'University Rating': 2, 'SOP': 1.0, 'LOR ': 2.0, 'CGPA': 7.97, 'Research': 0, 'Chance of Admit ': 0.56}
    {'_id': ObjectId('6444ccd095bfe069933271fd'), 'Serial No.': 294, 'GRE Score': 312, 'TOEFL Score': 98, 'University Rating': 1, 'SOP': 3.5, 'LOR ': 3.0, 'CGPA': 8.18, 'Research': 1, 'Chance of Admit ': 0.64}
    {'_id': ObjectId('6444ccd095bfe069933271fe'), 'Serial No.': 295, 'GRE Score': 316, 'TOEFL Score': 101, 'University Rating': 2, 'SOP': 2.5, 'LOR ': 2.0, 'CGPA': 8.32, 'Research': 1, 'Chance of Admit ': 0.61}
    {'_id': ObjectId('6444ccd095bfe069933271ff'), 'Serial No.': 296, 'GRE Score': 317, 'TOEFL Score': 100, 'University Rating': 2, 'SOP': 3.0, 'LOR ': 2.5, 'CGPA': 8.57, 'Research': 0, 'Chance of Admit ': 0.68}
    {'_id': ObjectId('6444ccd095bfe06993327200'), 'Serial No.': 297, 'GRE Score': 310, 'TOEFL Score': 107, 'University Rating': 3, 'SOP': 3.5, 'LOR ': 3.5, 'CGPA': 8.67, 'Research': 0, 'Chance of Admit ': 0.76}
    {'_id': ObjectId('6444ccd095bfe06993327201'), 'Serial No.': 298, 'GRE Score': 320, 'TOEFL Score': 120, 'University Rating': 3, 'SOP': 4.0, 'LOR ': 4.5, 'CGPA': 9.11, 'Research': 0, 'Chance of Admit ': 0.86}
    {'_id': ObjectId('6444ccd095bfe06993327202'), 'Serial No.': 299, 'GRE Score': 330, 'TOEFL Score': 114, 'University Rating': 3, 'SOP': 4.5, 'LOR ': 4.5, 'CGPA': 9.24, 'Research': 1, 'Chance of Admit ': 0.9}
    {'_id': ObjectId('6444ccd095bfe06993327203'), 'Serial No.': 300, 'GRE Score': 305, 'TOEFL Score': 112, 'University Rating': 3, 'SOP': 3.0, 'LOR ': 3.5, 'CGPA': 8.65, 'Research': 0, 'Chance of Admit ': 0.71}
    {'_id': ObjectId('6444ccd095bfe06993327204'), 'Serial No.': 301, 'GRE Score': 309, 'TOEFL Score': 106, 'University Rating': 2, 'SOP': 2.5, 'LOR ': 2.5, 'CGPA': 8.0, 'Research': 0, 'Chance of Admit ': 0.62}
    {'_id': ObjectId('6444ccd095bfe06993327205'), 'Serial No.': 302, 'GRE Score': 319, 'TOEFL Score': 108, 'University Rating': 2, 'SOP': 2.5, 'LOR ': 3.0, 'CGPA': 8.76, 'Research': 0, 'Chance of Admit ': 0.66}
    {'_id': ObjectId('6444ccd095bfe06993327206'), 'Serial No.': 303, 'GRE Score': 322, 'TOEFL Score': 105, 'University Rating': 2, 'SOP': 3.0, 'LOR ': 3.0, 'CGPA': 8.45, 'Research': 1, 'Chance of Admit ': 0.65}
    {'_id': ObjectId('6444ccd095bfe06993327207'), 'Serial No.': 304, 'GRE Score': 323, 'TOEFL Score': 107, 'University Rating': 3, 'SOP': 3.5, 'LOR ': 3.5, 'CGPA': 8.55, 'Research': 1, 'Chance of Admit ': 0.73}
    {'_id': ObjectId('6444ccd095bfe06993327208'), 'Serial No.': 305, 'GRE Score': 313, 'TOEFL Score': 106, 'University Rating': 2, 'SOP': 2.5, 'LOR ': 2.0, 'CGPA': 8.43, 'Research': 0, 'Chance of Admit ': 0.62}
    {'_id': ObjectId('6444ccd095bfe06993327209'), 'Serial No.': 306, 'GRE Score': 321, 'TOEFL Score': 109, 'University Rating': 3, 'SOP': 3.5, 'LOR ': 3.5, 'CGPA': 8.8, 'Research': 1, 'Chance of Admit ': 0.74}
    {'_id': ObjectId('6444ccd095bfe0699332720a'), 'Serial No.': 307, 'GRE Score': 323, 'TOEFL Score': 110, 'University Rating': 3, 'SOP': 4.0, 'LOR ': 3.5, 'CGPA': 9.1, 'Research': 1, 'Chance of Admit ': 0.79}
    {'_id': ObjectId('6444ccd095bfe0699332720b'), 'Serial No.': 308, 'GRE Score': 325, 'TOEFL Score': 112, 'University Rating': 4, 'SOP': 4.0, 'LOR ': 4.0, 'CGPA': 9.0, 'Research': 1, 'Chance of Admit ': 0.8}
    {'_id': ObjectId('6444ccd095bfe0699332720c'), 'Serial No.': 309, 'GRE Score': 312, 'TOEFL Score': 108, 'University Rating': 3, 'SOP': 3.5, 'LOR ': 3.0, 'CGPA': 8.53, 'Research': 0, 'Chance of Admit ': 0.69}
    {'_id': ObjectId('6444ccd095bfe0699332720d'), 'Serial No.': 310, 'GRE Score': 308, 'TOEFL Score': 110, 'University Rating': 4, 'SOP': 3.5, 'LOR ': 3.0, 'CGPA': 8.6, 'Research': 0, 'Chance of Admit ': 0.7}
    {'_id': ObjectId('6444ccd095bfe0699332720e'), 'Serial No.': 311, 'GRE Score': 320, 'TOEFL Score': 104, 'University Rating': 3, 'SOP': 3.0, 'LOR ': 3.5, 'CGPA': 8.74, 'Research': 1, 'Chance of Admit ': 0.76}
    {'_id': ObjectId('6444ccd095bfe0699332720f'), 'Serial No.': 312, 'GRE Score': 328, 'TOEFL Score': 108, 'University Rating': 4, 'SOP': 4.5, 'LOR ': 4.0, 'CGPA': 9.18, 'Research': 1, 'Chance of Admit ': 0.84}
    {'_id': ObjectId('6444ccd095bfe06993327210'), 'Serial No.': 313, 'GRE Score': 311, 'TOEFL Score': 107, 'University Rating': 4, 'SOP': 4.5, 'LOR ': 4.5, 'CGPA': 9.0, 'Research': 1, 'Chance of Admit ': 0.78}
    {'_id': ObjectId('6444ccd095bfe06993327211'), 'Serial No.': 314, 'GRE Score': 301, 'TOEFL Score': 100, 'University Rating': 3, 'SOP': 3.5, 'LOR ': 3.0, 'CGPA': 8.04, 'Research': 0, 'Chance of Admit ': 0.67}
    {'_id': ObjectId('6444ccd095bfe06993327212'), 'Serial No.': 315, 'GRE Score': 305, 'TOEFL Score': 105, 'University Rating': 2, 'SOP': 3.0, 'LOR ': 4.0, 'CGPA': 8.13, 'Research': 0, 'Chance of Admit ': 0.66}
    {'_id': ObjectId('6444ccd095bfe06993327213'), 'Serial No.': 316, 'GRE Score': 308, 'TOEFL Score': 104, 'University Rating': 2, 'SOP': 2.5, 'LOR ': 3.0, 'CGPA': 8.07, 'Research': 0, 'Chance of Admit ': 0.65}
    {'_id': ObjectId('6444ccd095bfe06993327214'), 'Serial No.': 317, 'GRE Score': 298, 'TOEFL Score': 101, 'University Rating': 2, 'SOP': 1.5, 'LOR ': 2.0, 'CGPA': 7.86, 'Research': 0, 'Chance of Admit ': 0.54}
    {'_id': ObjectId('6444ccd095bfe06993327215'), 'Serial No.': 318, 'GRE Score': 300, 'TOEFL Score': 99, 'University Rating': 1, 'SOP': 1.0, 'LOR ': 2.5, 'CGPA': 8.01, 'Research': 0, 'Chance of Admit ': 0.58}
    {'_id': ObjectId('6444ccd095bfe06993327216'), 'Serial No.': 319, 'GRE Score': 324, 'TOEFL Score': 111, 'University Rating': 3, 'SOP': 2.5, 'LOR ': 2.0, 'CGPA': 8.8, 'Research': 1, 'Chance of Admit ': 0.79}
    {'_id': ObjectId('6444ccd095bfe06993327217'), 'Serial No.': 320, 'GRE Score': 327, 'TOEFL Score': 113, 'University Rating': 4, 'SOP': 3.5, 'LOR ': 3.0, 'CGPA': 8.69, 'Research': 1, 'Chance of Admit ': 0.8}
    {'_id': ObjectId('6444ccd095bfe06993327218'), 'Serial No.': 321, 'GRE Score': 317, 'TOEFL Score': 106, 'University Rating': 3, 'SOP': 4.0, 'LOR ': 3.5, 'CGPA': 8.5, 'Research': 1, 'Chance of Admit ': 0.75}
    {'_id': ObjectId('6444ccd095bfe06993327219'), 'Serial No.': 322, 'GRE Score': 323, 'TOEFL Score': 104, 'University Rating': 3, 'SOP': 4.0, 'LOR ': 4.0, 'CGPA': 8.44, 'Research': 1, 'Chance of Admit ': 0.73}
    {'_id': ObjectId('6444ccd095bfe0699332721a'), 'Serial No.': 323, 'GRE Score': 314, 'TOEFL Score': 107, 'University Rating': 2, 'SOP': 2.5, 'LOR ': 4.0, 'CGPA': 8.27, 'Research': 0, 'Chance of Admit ': 0.72}
    {'_id': ObjectId('6444ccd095bfe0699332721b'), 'Serial No.': 324, 'GRE Score': 305, 'TOEFL Score': 102, 'University Rating': 2, 'SOP': 2.0, 'LOR ': 2.5, 'CGPA': 8.18, 'Research': 0, 'Chance of Admit ': 0.62}
    {'_id': ObjectId('6444ccd095bfe0699332721c'), 'Serial No.': 325, 'GRE Score': 315, 'TOEFL Score': 104, 'University Rating': 3, 'SOP': 3.0, 'LOR ': 2.5, 'CGPA': 8.33, 'Research': 0, 'Chance of Admit ': 0.67}
    {'_id': ObjectId('6444ccd095bfe0699332721d'), 'Serial No.': 326, 'GRE Score': 326, 'TOEFL Score': 116, 'University Rating': 3, 'SOP': 3.5, 'LOR ': 4.0, 'CGPA': 9.14, 'Research': 1, 'Chance of Admit ': 0.81}
    {'_id': ObjectId('6444ccd095bfe0699332721e'), 'Serial No.': 327, 'GRE Score': 299, 'TOEFL Score': 100, 'University Rating': 3, 'SOP': 2.0, 'LOR ': 2.0, 'CGPA': 8.02, 'Research': 0, 'Chance of Admit ': 0.63}
    {'_id': ObjectId('6444ccd095bfe0699332721f'), 'Serial No.': 328, 'GRE Score': 295, 'TOEFL Score': 101, 'University Rating': 2, 'SOP': 2.5, 'LOR ': 2.0, 'CGPA': 7.86, 'Research': 0, 'Chance of Admit ': 0.69}
    {'_id': ObjectId('6444ccd095bfe06993327220'), 'Serial No.': 329, 'GRE Score': 324, 'TOEFL Score': 112, 'University Rating': 4, 'SOP': 4.0, 'LOR ': 3.5, 'CGPA': 8.77, 'Research': 1, 'Chance of Admit ': 0.8}
    {'_id': ObjectId('6444ccd095bfe06993327221'), 'Serial No.': 330, 'GRE Score': 297, 'TOEFL Score': 96, 'University Rating': 2, 'SOP': 2.5, 'LOR ': 1.5, 'CGPA': 7.89, 'Research': 0, 'Chance of Admit ': 0.43}
    {'_id': ObjectId('6444ccd095bfe06993327222'), 'Serial No.': 331, 'GRE Score': 327, 'TOEFL Score': 113, 'University Rating': 3, 'SOP': 3.5, 'LOR ': 3.0, 'CGPA': 8.66, 'Research': 1, 'Chance of Admit ': 0.8}
    {'_id': ObjectId('6444ccd095bfe06993327223'), 'Serial No.': 332, 'GRE Score': 311, 'TOEFL Score': 105, 'University Rating': 2, 'SOP': 3.0, 'LOR ': 2.0, 'CGPA': 8.12, 'Research': 1, 'Chance of Admit ': 0.73}
    {'_id': ObjectId('6444ccd095bfe06993327224'), 'Serial No.': 333, 'GRE Score': 308, 'TOEFL Score': 106, 'University Rating': 3, 'SOP': 3.5, 'LOR ': 2.5, 'CGPA': 8.21, 'Research': 1, 'Chance of Admit ': 0.75}
    {'_id': ObjectId('6444ccd095bfe06993327225'), 'Serial No.': 334, 'GRE Score': 319, 'TOEFL Score': 108, 'University Rating': 3, 'SOP': 3.0, 'LOR ': 3.5, 'CGPA': 8.54, 'Research': 1, 'Chance of Admit ': 0.71}
    {'_id': ObjectId('6444ccd095bfe06993327226'), 'Serial No.': 335, 'GRE Score': 312, 'TOEFL Score': 107, 'University Rating': 4, 'SOP': 4.5, 'LOR ': 4.0, 'CGPA': 8.65, 'Research': 1, 'Chance of Admit ': 0.73}
    {'_id': ObjectId('6444ccd095bfe06993327227'), 'Serial No.': 336, 'GRE Score': 325, 'TOEFL Score': 111, 'University Rating': 4, 'SOP': 4.0, 'LOR ': 4.5, 'CGPA': 9.11, 'Research': 1, 'Chance of Admit ': 0.83}
    {'_id': ObjectId('6444ccd095bfe06993327228'), 'Serial No.': 337, 'GRE Score': 319, 'TOEFL Score': 110, 'University Rating': 3, 'SOP': 3.0, 'LOR ': 2.5, 'CGPA': 8.79, 'Research': 0, 'Chance of Admit ': 0.72}
    {'_id': ObjectId('6444ccd095bfe06993327229'), 'Serial No.': 338, 'GRE Score': 332, 'TOEFL Score': 118, 'University Rating': 5, 'SOP': 5.0, 'LOR ': 5.0, 'CGPA': 9.47, 'Research': 1, 'Chance of Admit ': 0.94}
    {'_id': ObjectId('6444ccd095bfe0699332722a'), 'Serial No.': 339, 'GRE Score': 323, 'TOEFL Score': 108, 'University Rating': 5, 'SOP': 4.0, 'LOR ': 4.0, 'CGPA': 8.74, 'Research': 1, 'Chance of Admit ': 0.81}
    {'_id': ObjectId('6444ccd095bfe0699332722b'), 'Serial No.': 340, 'GRE Score': 324, 'TOEFL Score': 107, 'University Rating': 5, 'SOP': 3.5, 'LOR ': 4.0, 'CGPA': 8.66, 'Research': 1, 'Chance of Admit ': 0.81}
    {'_id': ObjectId('6444ccd095bfe0699332722c'), 'Serial No.': 341, 'GRE Score': 312, 'TOEFL Score': 107, 'University Rating': 3, 'SOP': 3.0, 'LOR ': 3.0, 'CGPA': 8.46, 'Research': 1, 'Chance of Admit ': 0.75}
    {'_id': ObjectId('6444ccd095bfe0699332722d'), 'Serial No.': 342, 'GRE Score': 326, 'TOEFL Score': 110, 'University Rating': 3, 'SOP': 3.5, 'LOR ': 3.5, 'CGPA': 8.76, 'Research': 1, 'Chance of Admit ': 0.79}
    {'_id': ObjectId('6444ccd095bfe0699332722e'), 'Serial No.': 343, 'GRE Score': 308, 'TOEFL Score': 106, 'University Rating': 3, 'SOP': 3.0, 'LOR ': 3.0, 'CGPA': 8.24, 'Research': 0, 'Chance of Admit ': 0.58}
    {'_id': ObjectId('6444ccd095bfe0699332722f'), 'Serial No.': 344, 'GRE Score': 305, 'TOEFL Score': 103, 'University Rating': 2, 'SOP': 2.5, 'LOR ': 3.5, 'CGPA': 8.13, 'Research': 0, 'Chance of Admit ': 0.59}
    {'_id': ObjectId('6444ccd095bfe06993327230'), 'Serial No.': 345, 'GRE Score': 295, 'TOEFL Score': 96, 'University Rating': 2, 'SOP': 1.5, 'LOR ': 2.0, 'CGPA': 7.34, 'Research': 0, 'Chance of Admit ': 0.47}
    {'_id': ObjectId('6444ccd095bfe06993327231'), 'Serial No.': 346, 'GRE Score': 316, 'TOEFL Score': 98, 'University Rating': 1, 'SOP': 1.5, 'LOR ': 2.0, 'CGPA': 7.43, 'Research': 0, 'Chance of Admit ': 0.49}
    {'_id': ObjectId('6444ccd095bfe06993327232'), 'Serial No.': 347, 'GRE Score': 304, 'TOEFL Score': 97, 'University Rating': 2, 'SOP': 1.5, 'LOR ': 2.0, 'CGPA': 7.64, 'Research': 0, 'Chance of Admit ': 0.47}
    {'_id': ObjectId('6444ccd095bfe06993327233'), 'Serial No.': 348, 'GRE Score': 299, 'TOEFL Score': 94, 'University Rating': 1, 'SOP': 1.0, 'LOR ': 1.0, 'CGPA': 7.34, 'Research': 0, 'Chance of Admit ': 0.42}
    {'_id': ObjectId('6444ccd095bfe06993327234'), 'Serial No.': 349, 'GRE Score': 302, 'TOEFL Score': 99, 'University Rating': 1, 'SOP': 2.0, 'LOR ': 2.0, 'CGPA': 7.25, 'Research': 0, 'Chance of Admit ': 0.57}
    {'_id': ObjectId('6444ccd095bfe06993327235'), 'Serial No.': 350, 'GRE Score': 313, 'TOEFL Score': 101, 'University Rating': 3, 'SOP': 2.5, 'LOR ': 3.0, 'CGPA': 8.04, 'Research': 0, 'Chance of Admit ': 0.62}
    {'_id': ObjectId('6444ccd095bfe06993327236'), 'Serial No.': 351, 'GRE Score': 318, 'TOEFL Score': 107, 'University Rating': 3, 'SOP': 3.0, 'LOR ': 3.5, 'CGPA': 8.27, 'Research': 1, 'Chance of Admit ': 0.74}
    {'_id': ObjectId('6444ccd095bfe06993327237'), 'Serial No.': 352, 'GRE Score': 325, 'TOEFL Score': 110, 'University Rating': 4, 'SOP': 3.5, 'LOR ': 4.0, 'CGPA': 8.67, 'Research': 1, 'Chance of Admit ': 0.73}
    {'_id': ObjectId('6444ccd095bfe06993327238'), 'Serial No.': 353, 'GRE Score': 303, 'TOEFL Score': 100, 'University Rating': 2, 'SOP': 3.0, 'LOR ': 3.5, 'CGPA': 8.06, 'Research': 1, 'Chance of Admit ': 0.64}
    {'_id': ObjectId('6444ccd095bfe06993327239'), 'Serial No.': 354, 'GRE Score': 300, 'TOEFL Score': 102, 'University Rating': 3, 'SOP': 3.5, 'LOR ': 2.5, 'CGPA': 8.17, 'Research': 0, 'Chance of Admit ': 0.63}
    {'_id': ObjectId('6444ccd095bfe0699332723a'), 'Serial No.': 355, 'GRE Score': 297, 'TOEFL Score': 98, 'University Rating': 2, 'SOP': 2.5, 'LOR ': 3.0, 'CGPA': 7.67, 'Research': 0, 'Chance of Admit ': 0.59}
    {'_id': ObjectId('6444ccd095bfe0699332723b'), 'Serial No.': 356, 'GRE Score': 317, 'TOEFL Score': 106, 'University Rating': 2, 'SOP': 2.0, 'LOR ': 3.5, 'CGPA': 8.12, 'Research': 0, 'Chance of Admit ': 0.73}
    {'_id': ObjectId('6444ccd095bfe0699332723c'), 'Serial No.': 357, 'GRE Score': 327, 'TOEFL Score': 109, 'University Rating': 3, 'SOP': 3.5, 'LOR ': 4.0, 'CGPA': 8.77, 'Research': 1, 'Chance of Admit ': 0.79}
    {'_id': ObjectId('6444ccd095bfe0699332723d'), 'Serial No.': 358, 'GRE Score': 301, 'TOEFL Score': 104, 'University Rating': 2, 'SOP': 3.5, 'LOR ': 3.5, 'CGPA': 7.89, 'Research': 1, 'Chance of Admit ': 0.68}
    {'_id': ObjectId('6444ccd095bfe0699332723e'), 'Serial No.': 359, 'GRE Score': 314, 'TOEFL Score': 105, 'University Rating': 2, 'SOP': 2.5, 'LOR ': 2.0, 'CGPA': 7.64, 'Research': 0, 'Chance of Admit ': 0.7}
    {'_id': ObjectId('6444ccd095bfe0699332723f'), 'Serial No.': 360, 'GRE Score': 321, 'TOEFL Score': 107, 'University Rating': 2, 'SOP': 2.0, 'LOR ': 1.5, 'CGPA': 8.44, 'Research': 0, 'Chance of Admit ': 0.81}
    {'_id': ObjectId('6444ccd095bfe06993327240'), 'Serial No.': 361, 'GRE Score': 322, 'TOEFL Score': 110, 'University Rating': 3, 'SOP': 4.0, 'LOR ': 5.0, 'CGPA': 8.64, 'Research': 1, 'Chance of Admit ': 0.85}
    {'_id': ObjectId('6444ccd095bfe06993327241'), 'Serial No.': 362, 'GRE Score': 334, 'TOEFL Score': 116, 'University Rating': 4, 'SOP': 4.0, 'LOR ': 3.5, 'CGPA': 9.54, 'Research': 1, 'Chance of Admit ': 0.93}
    {'_id': ObjectId('6444ccd095bfe06993327242'), 'Serial No.': 363, 'GRE Score': 338, 'TOEFL Score': 115, 'University Rating': 5, 'SOP': 4.5, 'LOR ': 5.0, 'CGPA': 9.23, 'Research': 1, 'Chance of Admit ': 0.91}
    {'_id': ObjectId('6444ccd095bfe06993327243'), 'Serial No.': 364, 'GRE Score': 306, 'TOEFL Score': 103, 'University Rating': 2, 'SOP': 2.5, 'LOR ': 3.0, 'CGPA': 8.36, 'Research': 0, 'Chance of Admit ': 0.69}
    {'_id': ObjectId('6444ccd095bfe06993327244'), 'Serial No.': 365, 'GRE Score': 313, 'TOEFL Score': 102, 'University Rating': 3, 'SOP': 3.5, 'LOR ': 4.0, 'CGPA': 8.9, 'Research': 1, 'Chance of Admit ': 0.77}
    {'_id': ObjectId('6444ccd095bfe06993327245'), 'Serial No.': 366, 'GRE Score': 330, 'TOEFL Score': 114, 'University Rating': 4, 'SOP': 4.5, 'LOR ': 3.0, 'CGPA': 9.17, 'Research': 1, 'Chance of Admit ': 0.86}
    {'_id': ObjectId('6444ccd095bfe06993327246'), 'Serial No.': 367, 'GRE Score': 320, 'TOEFL Score': 104, 'University Rating': 3, 'SOP': 3.5, 'LOR ': 4.5, 'CGPA': 8.34, 'Research': 1, 'Chance of Admit ': 0.74}
    {'_id': ObjectId('6444ccd095bfe06993327247'), 'Serial No.': 368, 'GRE Score': 311, 'TOEFL Score': 98, 'University Rating': 1, 'SOP': 1.0, 'LOR ': 2.5, 'CGPA': 7.46, 'Research': 0, 'Chance of Admit ': 0.57}
    {'_id': ObjectId('6444ccd095bfe06993327248'), 'Serial No.': 369, 'GRE Score': 298, 'TOEFL Score': 92, 'University Rating': 1, 'SOP': 2.0, 'LOR ': 2.0, 'CGPA': 7.88, 'Research': 0, 'Chance of Admit ': 0.51}
    {'_id': ObjectId('6444ccd095bfe06993327249'), 'Serial No.': 370, 'GRE Score': 301, 'TOEFL Score': 98, 'University Rating': 1, 'SOP': 2.0, 'LOR ': 3.0, 'CGPA': 8.03, 'Research': 1, 'Chance of Admit ': 0.67}
    {'_id': ObjectId('6444ccd095bfe0699332724a'), 'Serial No.': 371, 'GRE Score': 310, 'TOEFL Score': 103, 'University Rating': 2, 'SOP': 2.5, 'LOR ': 2.5, 'CGPA': 8.24, 'Research': 0, 'Chance of Admit ': 0.72}
    {'_id': ObjectId('6444ccd095bfe0699332724b'), 'Serial No.': 372, 'GRE Score': 324, 'TOEFL Score': 110, 'University Rating': 3, 'SOP': 3.5, 'LOR ': 3.0, 'CGPA': 9.22, 'Research': 1, 'Chance of Admit ': 0.89}
    {'_id': ObjectId('6444ccd095bfe0699332724c'), 'Serial No.': 373, 'GRE Score': 336, 'TOEFL Score': 119, 'University Rating': 4, 'SOP': 4.5, 'LOR ': 4.0, 'CGPA': 9.62, 'Research': 1, 'Chance of Admit ': 0.95}
    {'_id': ObjectId('6444ccd095bfe0699332724d'), 'Serial No.': 374, 'GRE Score': 321, 'TOEFL Score': 109, 'University Rating': 3, 'SOP': 3.0, 'LOR ': 3.0, 'CGPA': 8.54, 'Research': 1, 'Chance of Admit ': 0.79}
    {'_id': ObjectId('6444ccd095bfe0699332724e'), 'Serial No.': 375, 'GRE Score': 315, 'TOEFL Score': 105, 'University Rating': 2, 'SOP': 2.0, 'LOR ': 2.5, 'CGPA': 7.65, 'Research': 0, 'Chance of Admit ': 0.39}
    {'_id': ObjectId('6444ccd095bfe0699332724f'), 'Serial No.': 376, 'GRE Score': 304, 'TOEFL Score': 101, 'University Rating': 2, 'SOP': 2.0, 'LOR ': 2.5, 'CGPA': 7.66, 'Research': 0, 'Chance of Admit ': 0.38}
    {'_id': ObjectId('6444ccd095bfe06993327250'), 'Serial No.': 377, 'GRE Score': 297, 'TOEFL Score': 96, 'University Rating': 2, 'SOP': 2.5, 'LOR ': 2.0, 'CGPA': 7.43, 'Research': 0, 'Chance of Admit ': 0.34}
    {'_id': ObjectId('6444ccd095bfe06993327251'), 'Serial No.': 378, 'GRE Score': 290, 'TOEFL Score': 100, 'University Rating': 1, 'SOP': 1.5, 'LOR ': 2.0, 'CGPA': 7.56, 'Research': 0, 'Chance of Admit ': 0.47}
    {'_id': ObjectId('6444ccd095bfe06993327252'), 'Serial No.': 379, 'GRE Score': 303, 'TOEFL Score': 98, 'University Rating': 1, 'SOP': 2.0, 'LOR ': 2.5, 'CGPA': 7.65, 'Research': 0, 'Chance of Admit ': 0.56}
    {'_id': ObjectId('6444ccd095bfe06993327253'), 'Serial No.': 380, 'GRE Score': 311, 'TOEFL Score': 99, 'University Rating': 1, 'SOP': 2.5, 'LOR ': 3.0, 'CGPA': 8.43, 'Research': 1, 'Chance of Admit ': 0.71}
    {'_id': ObjectId('6444ccd095bfe06993327254'), 'Serial No.': 381, 'GRE Score': 322, 'TOEFL Score': 104, 'University Rating': 3, 'SOP': 3.5, 'LOR ': 4.0, 'CGPA': 8.84, 'Research': 1, 'Chance of Admit ': 0.78}
    {'_id': ObjectId('6444ccd095bfe06993327255'), 'Serial No.': 382, 'GRE Score': 319, 'TOEFL Score': 105, 'University Rating': 3, 'SOP': 3.0, 'LOR ': 3.5, 'CGPA': 8.67, 'Research': 1, 'Chance of Admit ': 0.73}
    {'_id': ObjectId('6444ccd095bfe06993327256'), 'Serial No.': 383, 'GRE Score': 324, 'TOEFL Score': 110, 'University Rating': 4, 'SOP': 4.5, 'LOR ': 4.0, 'CGPA': 9.15, 'Research': 1, 'Chance of Admit ': 0.82}
    {'_id': ObjectId('6444ccd095bfe06993327257'), 'Serial No.': 384, 'GRE Score': 300, 'TOEFL Score': 100, 'University Rating': 3, 'SOP': 3.0, 'LOR ': 3.5, 'CGPA': 8.26, 'Research': 0, 'Chance of Admit ': 0.62}
    {'_id': ObjectId('6444ccd095bfe06993327258'), 'Serial No.': 385, 'GRE Score': 340, 'TOEFL Score': 113, 'University Rating': 4, 'SOP': 5.0, 'LOR ': 5.0, 'CGPA': 9.74, 'Research': 1, 'Chance of Admit ': 0.96}
    {'_id': ObjectId('6444ccd095bfe06993327259'), 'Serial No.': 386, 'GRE Score': 335, 'TOEFL Score': 117, 'University Rating': 5, 'SOP': 5.0, 'LOR ': 5.0, 'CGPA': 9.82, 'Research': 1, 'Chance of Admit ': 0.96}
    {'_id': ObjectId('6444ccd095bfe0699332725a'), 'Serial No.': 387, 'GRE Score': 302, 'TOEFL Score': 101, 'University Rating': 2, 'SOP': 2.5, 'LOR ': 3.5, 'CGPA': 7.96, 'Research': 0, 'Chance of Admit ': 0.46}
    {'_id': ObjectId('6444ccd095bfe0699332725b'), 'Serial No.': 388, 'GRE Score': 307, 'TOEFL Score': 105, 'University Rating': 2, 'SOP': 2.0, 'LOR ': 3.5, 'CGPA': 8.1, 'Research': 0, 'Chance of Admit ': 0.53}
    {'_id': ObjectId('6444ccd095bfe0699332725c'), 'Serial No.': 389, 'GRE Score': 296, 'TOEFL Score': 97, 'University Rating': 2, 'SOP': 1.5, 'LOR ': 2.0, 'CGPA': 7.8, 'Research': 0, 'Chance of Admit ': 0.49}
    {'_id': ObjectId('6444ccd095bfe0699332725d'), 'Serial No.': 390, 'GRE Score': 320, 'TOEFL Score': 108, 'University Rating': 3, 'SOP': 3.5, 'LOR ': 4.0, 'CGPA': 8.44, 'Research': 1, 'Chance of Admit ': 0.76}
    {'_id': ObjectId('6444ccd095bfe0699332725e'), 'Serial No.': 391, 'GRE Score': 314, 'TOEFL Score': 102, 'University Rating': 2, 'SOP': 2.0, 'LOR ': 2.5, 'CGPA': 8.24, 'Research': 0, 'Chance of Admit ': 0.64}
    {'_id': ObjectId('6444ccd095bfe0699332725f'), 'Serial No.': 392, 'GRE Score': 318, 'TOEFL Score': 106, 'University Rating': 3, 'SOP': 2.0, 'LOR ': 3.0, 'CGPA': 8.65, 'Research': 0, 'Chance of Admit ': 0.71}
    {'_id': ObjectId('6444ccd095bfe06993327260'), 'Serial No.': 393, 'GRE Score': 326, 'TOEFL Score': 112, 'University Rating': 4, 'SOP': 4.0, 'LOR ': 3.5, 'CGPA': 9.12, 'Research': 1, 'Chance of Admit ': 0.84}
    {'_id': ObjectId('6444ccd095bfe06993327261'), 'Serial No.': 394, 'GRE Score': 317, 'TOEFL Score': 104, 'University Rating': 2, 'SOP': 3.0, 'LOR ': 3.0, 'CGPA': 8.76, 'Research': 0, 'Chance of Admit ': 0.77}
    {'_id': ObjectId('6444ccd095bfe06993327262'), 'Serial No.': 395, 'GRE Score': 329, 'TOEFL Score': 111, 'University Rating': 4, 'SOP': 4.5, 'LOR ': 4.0, 'CGPA': 9.23, 'Research': 1, 'Chance of Admit ': 0.89}
    {'_id': ObjectId('6444ccd095bfe06993327263'), 'Serial No.': 396, 'GRE Score': 324, 'TOEFL Score': 110, 'University Rating': 3, 'SOP': 3.5, 'LOR ': 3.5, 'CGPA': 9.04, 'Research': 1, 'Chance of Admit ': 0.82}
    {'_id': ObjectId('6444ccd095bfe06993327264'), 'Serial No.': 397, 'GRE Score': 325, 'TOEFL Score': 107, 'University Rating': 3, 'SOP': 3.0, 'LOR ': 3.5, 'CGPA': 9.11, 'Research': 1, 'Chance of Admit ': 0.84}
    {'_id': ObjectId('6444ccd095bfe06993327265'), 'Serial No.': 398, 'GRE Score': 330, 'TOEFL Score': 116, 'University Rating': 4, 'SOP': 5.0, 'LOR ': 4.5, 'CGPA': 9.45, 'Research': 1, 'Chance of Admit ': 0.91}
    {'_id': ObjectId('6444ccd095bfe06993327266'), 'Serial No.': 399, 'GRE Score': 312, 'TOEFL Score': 103, 'University Rating': 3, 'SOP': 3.5, 'LOR ': 4.0, 'CGPA': 8.78, 'Research': 0, 'Chance of Admit ': 0.67}
    {'_id': ObjectId('6444ccd095bfe06993327267'), 'Serial No.': 400, 'GRE Score': 333, 'TOEFL Score': 117, 'University Rating': 4, 'SOP': 5.0, 'LOR ': 4.0, 'CGPA': 9.66, 'Research': 1, 'Chance of Admit ': 0.95}
    


```python
l=[]
for i in collection.find({'TOEFL Score':{'$lt':100}}):
    l.append(i)
print(len(l))
    
```

    43
    


```python
random_data=[
    {'_id':5,'CompanyName':'Eatclub','Faculty':'XYZ'}
]
```


```python
collection.insert_many(random_data)
```




    <pymongo.results.InsertManyResult at 0x2287ee5d888>




```python
for i in collection.find():
    print (i)
```

    {'_id': ObjectId('6444ccd095bfe069933270d8'), 'Serial No.': 1, 'GRE Score': 337, 'TOEFL Score': 118, 'University Rating': 4, 'SOP': 4.5, 'LOR ': 4.5, 'CGPA': 9.65, 'Research': 1, 'Chance of Admit ': 0.92}
    {'_id': ObjectId('6444ccd095bfe069933270d9'), 'Serial No.': 2, 'GRE Score': 324, 'TOEFL Score': 107, 'University Rating': 4, 'SOP': 4.0, 'LOR ': 4.5, 'CGPA': 8.87, 'Research': 1, 'Chance of Admit ': 0.76}
    {'_id': ObjectId('6444ccd095bfe069933270da'), 'Serial No.': 3, 'GRE Score': 316, 'TOEFL Score': 104, 'University Rating': 3, 'SOP': 3.0, 'LOR ': 3.5, 'CGPA': 8.0, 'Research': 1, 'Chance of Admit ': 0.72}
    {'_id': ObjectId('6444ccd095bfe069933270db'), 'Serial No.': 4, 'GRE Score': 322, 'TOEFL Score': 110, 'University Rating': 3, 'SOP': 3.5, 'LOR ': 2.5, 'CGPA': 8.67, 'Research': 1, 'Chance of Admit ': 0.8}
    {'_id': ObjectId('6444ccd095bfe069933270dc'), 'Serial No.': 5, 'GRE Score': 314, 'TOEFL Score': 103, 'University Rating': 2, 'SOP': 2.0, 'LOR ': 3.0, 'CGPA': 8.21, 'Research': 0, 'Chance of Admit ': 0.65}
    {'_id': ObjectId('6444ccd095bfe069933270dd'), 'Serial No.': 6, 'GRE Score': 330, 'TOEFL Score': 115, 'University Rating': 5, 'SOP': 4.5, 'LOR ': 3.0, 'CGPA': 9.34, 'Research': 1, 'Chance of Admit ': 0.9}
    {'_id': ObjectId('6444ccd095bfe069933270de'), 'Serial No.': 7, 'GRE Score': 321, 'TOEFL Score': 109, 'University Rating': 3, 'SOP': 3.0, 'LOR ': 4.0, 'CGPA': 8.2, 'Research': 1, 'Chance of Admit ': 0.75}
    {'_id': ObjectId('6444ccd095bfe069933270df'), 'Serial No.': 8, 'GRE Score': 308, 'TOEFL Score': 101, 'University Rating': 2, 'SOP': 3.0, 'LOR ': 4.0, 'CGPA': 7.9, 'Research': 0, 'Chance of Admit ': 0.68}
    {'_id': ObjectId('6444ccd095bfe069933270e0'), 'Serial No.': 9, 'GRE Score': 302, 'TOEFL Score': 102, 'University Rating': 1, 'SOP': 2.0, 'LOR ': 1.5, 'CGPA': 8.0, 'Research': 0, 'Chance of Admit ': 0.5}
    {'_id': ObjectId('6444ccd095bfe069933270e1'), 'Serial No.': 10, 'GRE Score': 323, 'TOEFL Score': 108, 'University Rating': 3, 'SOP': 3.5, 'LOR ': 3.0, 'CGPA': 8.6, 'Research': 0, 'Chance of Admit ': 0.45}
    {'_id': ObjectId('6444ccd095bfe069933270e2'), 'Serial No.': 11, 'GRE Score': 325, 'TOEFL Score': 106, 'University Rating': 3, 'SOP': 3.5, 'LOR ': 4.0, 'CGPA': 8.4, 'Research': 1, 'Chance of Admit ': 0.52}
    {'_id': ObjectId('6444ccd095bfe069933270e3'), 'Serial No.': 12, 'GRE Score': 327, 'TOEFL Score': 111, 'University Rating': 4, 'SOP': 4.0, 'LOR ': 4.5, 'CGPA': 9.0, 'Research': 1, 'Chance of Admit ': 0.84}
    {'_id': ObjectId('6444ccd095bfe069933270e4'), 'Serial No.': 13, 'GRE Score': 328, 'TOEFL Score': 112, 'University Rating': 4, 'SOP': 4.0, 'LOR ': 4.5, 'CGPA': 9.1, 'Research': 1, 'Chance of Admit ': 0.78}
    {'_id': ObjectId('6444ccd095bfe069933270e5'), 'Serial No.': 14, 'GRE Score': 307, 'TOEFL Score': 109, 'University Rating': 3, 'SOP': 4.0, 'LOR ': 3.0, 'CGPA': 8.0, 'Research': 1, 'Chance of Admit ': 0.62}
    {'_id': ObjectId('6444ccd095bfe069933270e6'), 'Serial No.': 15, 'GRE Score': 311, 'TOEFL Score': 104, 'University Rating': 3, 'SOP': 3.5, 'LOR ': 2.0, 'CGPA': 8.2, 'Research': 1, 'Chance of Admit ': 0.61}
    {'_id': ObjectId('6444ccd095bfe069933270e7'), 'Serial No.': 16, 'GRE Score': 314, 'TOEFL Score': 105, 'University Rating': 3, 'SOP': 3.5, 'LOR ': 2.5, 'CGPA': 8.3, 'Research': 0, 'Chance of Admit ': 0.54}
    {'_id': ObjectId('6444ccd095bfe069933270e8'), 'Serial No.': 17, 'GRE Score': 317, 'TOEFL Score': 107, 'University Rating': 3, 'SOP': 4.0, 'LOR ': 3.0, 'CGPA': 8.7, 'Research': 0, 'Chance of Admit ': 0.66}
    {'_id': ObjectId('6444ccd095bfe069933270e9'), 'Serial No.': 18, 'GRE Score': 319, 'TOEFL Score': 106, 'University Rating': 3, 'SOP': 4.0, 'LOR ': 3.0, 'CGPA': 8.0, 'Research': 1, 'Chance of Admit ': 0.65}
    {'_id': ObjectId('6444ccd095bfe069933270ea'), 'Serial No.': 19, 'GRE Score': 318, 'TOEFL Score': 110, 'University Rating': 3, 'SOP': 4.0, 'LOR ': 3.0, 'CGPA': 8.8, 'Research': 0, 'Chance of Admit ': 0.63}
    {'_id': ObjectId('6444ccd095bfe069933270eb'), 'Serial No.': 20, 'GRE Score': 303, 'TOEFL Score': 102, 'University Rating': 3, 'SOP': 3.5, 'LOR ': 3.0, 'CGPA': 8.5, 'Research': 0, 'Chance of Admit ': 0.62}
    {'_id': ObjectId('6444ccd095bfe069933270ec'), 'Serial No.': 21, 'GRE Score': 312, 'TOEFL Score': 107, 'University Rating': 3, 'SOP': 3.0, 'LOR ': 2.0, 'CGPA': 7.9, 'Research': 1, 'Chance of Admit ': 0.64}
    {'_id': ObjectId('6444ccd095bfe069933270ed'), 'Serial No.': 22, 'GRE Score': 325, 'TOEFL Score': 114, 'University Rating': 4, 'SOP': 3.0, 'LOR ': 2.0, 'CGPA': 8.4, 'Research': 0, 'Chance of Admit ': 0.7}
    {'_id': ObjectId('6444ccd095bfe069933270ee'), 'Serial No.': 23, 'GRE Score': 328, 'TOEFL Score': 116, 'University Rating': 5, 'SOP': 5.0, 'LOR ': 5.0, 'CGPA': 9.5, 'Research': 1, 'Chance of Admit ': 0.94}
    {'_id': ObjectId('6444ccd095bfe069933270ef'), 'Serial No.': 24, 'GRE Score': 334, 'TOEFL Score': 119, 'University Rating': 5, 'SOP': 5.0, 'LOR ': 4.5, 'CGPA': 9.7, 'Research': 1, 'Chance of Admit ': 0.95}
    {'_id': ObjectId('6444ccd095bfe069933270f0'), 'Serial No.': 25, 'GRE Score': 336, 'TOEFL Score': 119, 'University Rating': 5, 'SOP': 4.0, 'LOR ': 3.5, 'CGPA': 9.8, 'Research': 1, 'Chance of Admit ': 0.97}
    {'_id': ObjectId('6444ccd095bfe069933270f1'), 'Serial No.': 26, 'GRE Score': 340, 'TOEFL Score': 120, 'University Rating': 5, 'SOP': 4.5, 'LOR ': 4.5, 'CGPA': 9.6, 'Research': 1, 'Chance of Admit ': 0.94}
    {'_id': ObjectId('6444ccd095bfe069933270f2'), 'Serial No.': 27, 'GRE Score': 322, 'TOEFL Score': 109, 'University Rating': 5, 'SOP': 4.5, 'LOR ': 3.5, 'CGPA': 8.8, 'Research': 0, 'Chance of Admit ': 0.76}
    {'_id': ObjectId('6444ccd095bfe069933270f3'), 'Serial No.': 28, 'GRE Score': 298, 'TOEFL Score': 98, 'University Rating': 2, 'SOP': 1.5, 'LOR ': 2.5, 'CGPA': 7.5, 'Research': 1, 'Chance of Admit ': 0.44}
    {'_id': ObjectId('6444ccd095bfe069933270f4'), 'Serial No.': 29, 'GRE Score': 295, 'TOEFL Score': 93, 'University Rating': 1, 'SOP': 2.0, 'LOR ': 2.0, 'CGPA': 7.2, 'Research': 0, 'Chance of Admit ': 0.46}
    {'_id': ObjectId('6444ccd095bfe069933270f5'), 'Serial No.': 30, 'GRE Score': 310, 'TOEFL Score': 99, 'University Rating': 2, 'SOP': 1.5, 'LOR ': 2.0, 'CGPA': 7.3, 'Research': 0, 'Chance of Admit ': 0.54}
    {'_id': ObjectId('6444ccd095bfe069933270f6'), 'Serial No.': 31, 'GRE Score': 300, 'TOEFL Score': 97, 'University Rating': 2, 'SOP': 3.0, 'LOR ': 3.0, 'CGPA': 8.1, 'Research': 1, 'Chance of Admit ': 0.65}
    {'_id': ObjectId('6444ccd095bfe069933270f7'), 'Serial No.': 32, 'GRE Score': 327, 'TOEFL Score': 103, 'University Rating': 3, 'SOP': 4.0, 'LOR ': 4.0, 'CGPA': 8.3, 'Research': 1, 'Chance of Admit ': 0.74}
    {'_id': ObjectId('6444ccd095bfe069933270f8'), 'Serial No.': 33, 'GRE Score': 338, 'TOEFL Score': 118, 'University Rating': 4, 'SOP': 3.0, 'LOR ': 4.5, 'CGPA': 9.4, 'Research': 1, 'Chance of Admit ': 0.91}
    {'_id': ObjectId('6444ccd095bfe069933270f9'), 'Serial No.': 34, 'GRE Score': 340, 'TOEFL Score': 114, 'University Rating': 5, 'SOP': 4.0, 'LOR ': 4.0, 'CGPA': 9.6, 'Research': 1, 'Chance of Admit ': 0.9}
    {'_id': ObjectId('6444ccd095bfe069933270fa'), 'Serial No.': 35, 'GRE Score': 331, 'TOEFL Score': 112, 'University Rating': 5, 'SOP': 4.0, 'LOR ': 5.0, 'CGPA': 9.8, 'Research': 1, 'Chance of Admit ': 0.94}
    {'_id': ObjectId('6444ccd095bfe069933270fb'), 'Serial No.': 36, 'GRE Score': 320, 'TOEFL Score': 110, 'University Rating': 5, 'SOP': 5.0, 'LOR ': 5.0, 'CGPA': 9.2, 'Research': 1, 'Chance of Admit ': 0.88}
    {'_id': ObjectId('6444ccd095bfe069933270fc'), 'Serial No.': 37, 'GRE Score': 299, 'TOEFL Score': 106, 'University Rating': 2, 'SOP': 4.0, 'LOR ': 4.0, 'CGPA': 8.4, 'Research': 0, 'Chance of Admit ': 0.64}
    {'_id': ObjectId('6444ccd095bfe069933270fd'), 'Serial No.': 38, 'GRE Score': 300, 'TOEFL Score': 105, 'University Rating': 1, 'SOP': 1.0, 'LOR ': 2.0, 'CGPA': 7.8, 'Research': 0, 'Chance of Admit ': 0.58}
    {'_id': ObjectId('6444ccd095bfe069933270fe'), 'Serial No.': 39, 'GRE Score': 304, 'TOEFL Score': 105, 'University Rating': 1, 'SOP': 3.0, 'LOR ': 1.5, 'CGPA': 7.5, 'Research': 0, 'Chance of Admit ': 0.52}
    {'_id': ObjectId('6444ccd095bfe069933270ff'), 'Serial No.': 40, 'GRE Score': 307, 'TOEFL Score': 108, 'University Rating': 2, 'SOP': 4.0, 'LOR ': 3.5, 'CGPA': 7.7, 'Research': 0, 'Chance of Admit ': 0.48}
    {'_id': ObjectId('6444ccd095bfe06993327100'), 'Serial No.': 41, 'GRE Score': 308, 'TOEFL Score': 110, 'University Rating': 3, 'SOP': 3.5, 'LOR ': 3.0, 'CGPA': 8.0, 'Research': 1, 'Chance of Admit ': 0.46}
    {'_id': ObjectId('6444ccd095bfe06993327101'), 'Serial No.': 42, 'GRE Score': 316, 'TOEFL Score': 105, 'University Rating': 2, 'SOP': 2.5, 'LOR ': 2.5, 'CGPA': 8.2, 'Research': 1, 'Chance of Admit ': 0.49}
    {'_id': ObjectId('6444ccd095bfe06993327102'), 'Serial No.': 43, 'GRE Score': 313, 'TOEFL Score': 107, 'University Rating': 2, 'SOP': 2.5, 'LOR ': 2.0, 'CGPA': 8.5, 'Research': 1, 'Chance of Admit ': 0.53}
    {'_id': ObjectId('6444ccd095bfe06993327103'), 'Serial No.': 44, 'GRE Score': 332, 'TOEFL Score': 117, 'University Rating': 4, 'SOP': 4.5, 'LOR ': 4.0, 'CGPA': 9.1, 'Research': 0, 'Chance of Admit ': 0.87}
    {'_id': ObjectId('6444ccd095bfe06993327104'), 'Serial No.': 45, 'GRE Score': 326, 'TOEFL Score': 113, 'University Rating': 5, 'SOP': 4.5, 'LOR ': 4.0, 'CGPA': 9.4, 'Research': 1, 'Chance of Admit ': 0.91}
    {'_id': ObjectId('6444ccd095bfe06993327105'), 'Serial No.': 46, 'GRE Score': 322, 'TOEFL Score': 110, 'University Rating': 5, 'SOP': 5.0, 'LOR ': 4.0, 'CGPA': 9.1, 'Research': 1, 'Chance of Admit ': 0.88}
    {'_id': ObjectId('6444ccd095bfe06993327106'), 'Serial No.': 47, 'GRE Score': 329, 'TOEFL Score': 114, 'University Rating': 5, 'SOP': 4.0, 'LOR ': 5.0, 'CGPA': 9.3, 'Research': 1, 'Chance of Admit ': 0.86}
    {'_id': ObjectId('6444ccd095bfe06993327107'), 'Serial No.': 48, 'GRE Score': 339, 'TOEFL Score': 119, 'University Rating': 5, 'SOP': 4.5, 'LOR ': 4.0, 'CGPA': 9.7, 'Research': 0, 'Chance of Admit ': 0.89}
    {'_id': ObjectId('6444ccd095bfe06993327108'), 'Serial No.': 49, 'GRE Score': 321, 'TOEFL Score': 110, 'University Rating': 3, 'SOP': 3.5, 'LOR ': 5.0, 'CGPA': 8.85, 'Research': 1, 'Chance of Admit ': 0.82}
    {'_id': ObjectId('6444ccd095bfe06993327109'), 'Serial No.': 50, 'GRE Score': 327, 'TOEFL Score': 111, 'University Rating': 4, 'SOP': 3.0, 'LOR ': 4.0, 'CGPA': 8.4, 'Research': 1, 'Chance of Admit ': 0.78}
    {'_id': ObjectId('6444ccd095bfe0699332710a'), 'Serial No.': 51, 'GRE Score': 313, 'TOEFL Score': 98, 'University Rating': 3, 'SOP': 2.5, 'LOR ': 4.5, 'CGPA': 8.3, 'Research': 1, 'Chance of Admit ': 0.76}
    {'_id': ObjectId('6444ccd095bfe0699332710b'), 'Serial No.': 52, 'GRE Score': 312, 'TOEFL Score': 100, 'University Rating': 2, 'SOP': 1.5, 'LOR ': 3.5, 'CGPA': 7.9, 'Research': 1, 'Chance of Admit ': 0.56}
    {'_id': ObjectId('6444ccd095bfe0699332710c'), 'Serial No.': 53, 'GRE Score': 334, 'TOEFL Score': 116, 'University Rating': 4, 'SOP': 4.0, 'LOR ': 3.0, 'CGPA': 8.0, 'Research': 1, 'Chance of Admit ': 0.78}
    {'_id': ObjectId('6444ccd095bfe0699332710d'), 'Serial No.': 54, 'GRE Score': 324, 'TOEFL Score': 112, 'University Rating': 4, 'SOP': 4.0, 'LOR ': 2.5, 'CGPA': 8.1, 'Research': 1, 'Chance of Admit ': 0.72}
    {'_id': ObjectId('6444ccd095bfe0699332710e'), 'Serial No.': 55, 'GRE Score': 322, 'TOEFL Score': 110, 'University Rating': 3, 'SOP': 3.0, 'LOR ': 3.5, 'CGPA': 8.0, 'Research': 0, 'Chance of Admit ': 0.7}
    {'_id': ObjectId('6444ccd095bfe0699332710f'), 'Serial No.': 56, 'GRE Score': 320, 'TOEFL Score': 103, 'University Rating': 3, 'SOP': 3.0, 'LOR ': 3.0, 'CGPA': 7.7, 'Research': 0, 'Chance of Admit ': 0.64}
    {'_id': ObjectId('6444ccd095bfe06993327110'), 'Serial No.': 57, 'GRE Score': 316, 'TOEFL Score': 102, 'University Rating': 3, 'SOP': 2.0, 'LOR ': 3.0, 'CGPA': 7.4, 'Research': 0, 'Chance of Admit ': 0.64}
    {'_id': ObjectId('6444ccd095bfe06993327111'), 'Serial No.': 58, 'GRE Score': 298, 'TOEFL Score': 99, 'University Rating': 2, 'SOP': 4.0, 'LOR ': 2.0, 'CGPA': 7.6, 'Research': 0, 'Chance of Admit ': 0.46}
    {'_id': ObjectId('6444ccd095bfe06993327112'), 'Serial No.': 59, 'GRE Score': 300, 'TOEFL Score': 99, 'University Rating': 1, 'SOP': 3.0, 'LOR ': 2.0, 'CGPA': 6.8, 'Research': 1, 'Chance of Admit ': 0.36}
    {'_id': ObjectId('6444ccd095bfe06993327113'), 'Serial No.': 60, 'GRE Score': 311, 'TOEFL Score': 104, 'University Rating': 2, 'SOP': 2.0, 'LOR ': 2.0, 'CGPA': 8.3, 'Research': 0, 'Chance of Admit ': 0.42}
    {'_id': ObjectId('6444ccd095bfe06993327114'), 'Serial No.': 61, 'GRE Score': 309, 'TOEFL Score': 100, 'University Rating': 2, 'SOP': 3.0, 'LOR ': 3.0, 'CGPA': 8.1, 'Research': 0, 'Chance of Admit ': 0.48}
    {'_id': ObjectId('6444ccd095bfe06993327115'), 'Serial No.': 62, 'GRE Score': 307, 'TOEFL Score': 101, 'University Rating': 3, 'SOP': 4.0, 'LOR ': 3.0, 'CGPA': 8.2, 'Research': 0, 'Chance of Admit ': 0.47}
    {'_id': ObjectId('6444ccd095bfe06993327116'), 'Serial No.': 63, 'GRE Score': 304, 'TOEFL Score': 105, 'University Rating': 2, 'SOP': 3.0, 'LOR ': 3.0, 'CGPA': 8.2, 'Research': 1, 'Chance of Admit ': 0.54}
    {'_id': ObjectId('6444ccd095bfe06993327117'), 'Serial No.': 64, 'GRE Score': 315, 'TOEFL Score': 107, 'University Rating': 2, 'SOP': 4.0, 'LOR ': 3.0, 'CGPA': 8.5, 'Research': 1, 'Chance of Admit ': 0.56}
    {'_id': ObjectId('6444ccd095bfe06993327118'), 'Serial No.': 65, 'GRE Score': 325, 'TOEFL Score': 111, 'University Rating': 3, 'SOP': 3.0, 'LOR ': 3.5, 'CGPA': 8.7, 'Research': 0, 'Chance of Admit ': 0.52}
    {'_id': ObjectId('6444ccd095bfe06993327119'), 'Serial No.': 66, 'GRE Score': 325, 'TOEFL Score': 112, 'University Rating': 4, 'SOP': 3.5, 'LOR ': 3.5, 'CGPA': 8.92, 'Research': 0, 'Chance of Admit ': 0.55}
    {'_id': ObjectId('6444ccd095bfe0699332711a'), 'Serial No.': 67, 'GRE Score': 327, 'TOEFL Score': 114, 'University Rating': 3, 'SOP': 3.0, 'LOR ': 3.0, 'CGPA': 9.02, 'Research': 0, 'Chance of Admit ': 0.61}
    {'_id': ObjectId('6444ccd095bfe0699332711b'), 'Serial No.': 68, 'GRE Score': 316, 'TOEFL Score': 107, 'University Rating': 2, 'SOP': 3.5, 'LOR ': 3.5, 'CGPA': 8.64, 'Research': 1, 'Chance of Admit ': 0.57}
    {'_id': ObjectId('6444ccd095bfe0699332711c'), 'Serial No.': 69, 'GRE Score': 318, 'TOEFL Score': 109, 'University Rating': 3, 'SOP': 3.5, 'LOR ': 4.0, 'CGPA': 9.22, 'Research': 1, 'Chance of Admit ': 0.68}
    {'_id': ObjectId('6444ccd095bfe0699332711d'), 'Serial No.': 70, 'GRE Score': 328, 'TOEFL Score': 115, 'University Rating': 4, 'SOP': 4.5, 'LOR ': 4.0, 'CGPA': 9.16, 'Research': 1, 'Chance of Admit ': 0.78}
    {'_id': ObjectId('6444ccd095bfe0699332711e'), 'Serial No.': 71, 'GRE Score': 332, 'TOEFL Score': 118, 'University Rating': 5, 'SOP': 5.0, 'LOR ': 5.0, 'CGPA': 9.64, 'Research': 1, 'Chance of Admit ': 0.94}
    {'_id': ObjectId('6444ccd095bfe0699332711f'), 'Serial No.': 72, 'GRE Score': 336, 'TOEFL Score': 112, 'University Rating': 5, 'SOP': 5.0, 'LOR ': 5.0, 'CGPA': 9.76, 'Research': 1, 'Chance of Admit ': 0.96}
    {'_id': ObjectId('6444ccd095bfe06993327120'), 'Serial No.': 73, 'GRE Score': 321, 'TOEFL Score': 111, 'University Rating': 5, 'SOP': 5.0, 'LOR ': 5.0, 'CGPA': 9.45, 'Research': 1, 'Chance of Admit ': 0.93}
    {'_id': ObjectId('6444ccd095bfe06993327121'), 'Serial No.': 74, 'GRE Score': 314, 'TOEFL Score': 108, 'University Rating': 4, 'SOP': 4.5, 'LOR ': 4.0, 'CGPA': 9.04, 'Research': 1, 'Chance of Admit ': 0.84}
    {'_id': ObjectId('6444ccd095bfe06993327122'), 'Serial No.': 75, 'GRE Score': 314, 'TOEFL Score': 106, 'University Rating': 3, 'SOP': 3.0, 'LOR ': 5.0, 'CGPA': 8.9, 'Research': 0, 'Chance of Admit ': 0.74}
    {'_id': ObjectId('6444ccd095bfe06993327123'), 'Serial No.': 76, 'GRE Score': 329, 'TOEFL Score': 114, 'University Rating': 2, 'SOP': 2.0, 'LOR ': 4.0, 'CGPA': 8.56, 'Research': 1, 'Chance of Admit ': 0.72}
    {'_id': ObjectId('6444ccd095bfe06993327124'), 'Serial No.': 77, 'GRE Score': 327, 'TOEFL Score': 112, 'University Rating': 3, 'SOP': 3.0, 'LOR ': 3.0, 'CGPA': 8.72, 'Research': 1, 'Chance of Admit ': 0.74}
    {'_id': ObjectId('6444ccd095bfe06993327125'), 'Serial No.': 78, 'GRE Score': 301, 'TOEFL Score': 99, 'University Rating': 2, 'SOP': 3.0, 'LOR ': 2.0, 'CGPA': 8.22, 'Research': 0, 'Chance of Admit ': 0.64}
    {'_id': ObjectId('6444ccd095bfe06993327126'), 'Serial No.': 79, 'GRE Score': 296, 'TOEFL Score': 95, 'University Rating': 2, 'SOP': 3.0, 'LOR ': 2.0, 'CGPA': 7.54, 'Research': 1, 'Chance of Admit ': 0.44}
    {'_id': ObjectId('6444ccd095bfe06993327127'), 'Serial No.': 80, 'GRE Score': 294, 'TOEFL Score': 93, 'University Rating': 1, 'SOP': 1.5, 'LOR ': 2.0, 'CGPA': 7.36, 'Research': 0, 'Chance of Admit ': 0.46}
    {'_id': ObjectId('6444ccd095bfe06993327128'), 'Serial No.': 81, 'GRE Score': 312, 'TOEFL Score': 105, 'University Rating': 3, 'SOP': 2.0, 'LOR ': 3.0, 'CGPA': 8.02, 'Research': 1, 'Chance of Admit ': 0.5}
    {'_id': ObjectId('6444ccd095bfe06993327129'), 'Serial No.': 82, 'GRE Score': 340, 'TOEFL Score': 120, 'University Rating': 4, 'SOP': 5.0, 'LOR ': 5.0, 'CGPA': 9.5, 'Research': 1, 'Chance of Admit ': 0.96}
    {'_id': ObjectId('6444ccd095bfe0699332712a'), 'Serial No.': 83, 'GRE Score': 320, 'TOEFL Score': 110, 'University Rating': 5, 'SOP': 5.0, 'LOR ': 4.5, 'CGPA': 9.22, 'Research': 1, 'Chance of Admit ': 0.92}
    {'_id': ObjectId('6444ccd095bfe0699332712b'), 'Serial No.': 84, 'GRE Score': 322, 'TOEFL Score': 115, 'University Rating': 5, 'SOP': 4.0, 'LOR ': 4.5, 'CGPA': 9.36, 'Research': 1, 'Chance of Admit ': 0.92}
    {'_id': ObjectId('6444ccd095bfe0699332712c'), 'Serial No.': 85, 'GRE Score': 340, 'TOEFL Score': 115, 'University Rating': 5, 'SOP': 4.5, 'LOR ': 4.5, 'CGPA': 9.45, 'Research': 1, 'Chance of Admit ': 0.94}
    {'_id': ObjectId('6444ccd095bfe0699332712d'), 'Serial No.': 86, 'GRE Score': 319, 'TOEFL Score': 103, 'University Rating': 4, 'SOP': 4.5, 'LOR ': 3.5, 'CGPA': 8.66, 'Research': 0, 'Chance of Admit ': 0.76}
    {'_id': ObjectId('6444ccd095bfe0699332712e'), 'Serial No.': 87, 'GRE Score': 315, 'TOEFL Score': 106, 'University Rating': 3, 'SOP': 4.5, 'LOR ': 3.5, 'CGPA': 8.42, 'Research': 0, 'Chance of Admit ': 0.72}
    {'_id': ObjectId('6444ccd095bfe0699332712f'), 'Serial No.': 88, 'GRE Score': 317, 'TOEFL Score': 107, 'University Rating': 2, 'SOP': 3.5, 'LOR ': 3.0, 'CGPA': 8.28, 'Research': 0, 'Chance of Admit ': 0.66}
    {'_id': ObjectId('6444ccd095bfe06993327130'), 'Serial No.': 89, 'GRE Score': 314, 'TOEFL Score': 108, 'University Rating': 3, 'SOP': 4.5, 'LOR ': 3.5, 'CGPA': 8.14, 'Research': 0, 'Chance of Admit ': 0.64}
    {'_id': ObjectId('6444ccd095bfe06993327131'), 'Serial No.': 90, 'GRE Score': 316, 'TOEFL Score': 109, 'University Rating': 4, 'SOP': 4.5, 'LOR ': 3.5, 'CGPA': 8.76, 'Research': 1, 'Chance of Admit ': 0.74}
    {'_id': ObjectId('6444ccd095bfe06993327132'), 'Serial No.': 91, 'GRE Score': 318, 'TOEFL Score': 106, 'University Rating': 2, 'SOP': 4.0, 'LOR ': 4.0, 'CGPA': 7.92, 'Research': 1, 'Chance of Admit ': 0.64}
    {'_id': ObjectId('6444ccd095bfe06993327133'), 'Serial No.': 92, 'GRE Score': 299, 'TOEFL Score': 97, 'University Rating': 3, 'SOP': 5.0, 'LOR ': 3.5, 'CGPA': 7.66, 'Research': 0, 'Chance of Admit ': 0.38}
    {'_id': ObjectId('6444ccd095bfe06993327134'), 'Serial No.': 93, 'GRE Score': 298, 'TOEFL Score': 98, 'University Rating': 2, 'SOP': 4.0, 'LOR ': 3.0, 'CGPA': 8.03, 'Research': 0, 'Chance of Admit ': 0.34}
    {'_id': ObjectId('6444ccd095bfe06993327135'), 'Serial No.': 94, 'GRE Score': 301, 'TOEFL Score': 97, 'University Rating': 2, 'SOP': 3.0, 'LOR ': 3.0, 'CGPA': 7.88, 'Research': 1, 'Chance of Admit ': 0.44}
    {'_id': ObjectId('6444ccd095bfe06993327136'), 'Serial No.': 95, 'GRE Score': 303, 'TOEFL Score': 99, 'University Rating': 3, 'SOP': 2.0, 'LOR ': 2.5, 'CGPA': 7.66, 'Research': 0, 'Chance of Admit ': 0.36}
    {'_id': ObjectId('6444ccd095bfe06993327137'), 'Serial No.': 96, 'GRE Score': 304, 'TOEFL Score': 100, 'University Rating': 4, 'SOP': 1.5, 'LOR ': 2.5, 'CGPA': 7.84, 'Research': 0, 'Chance of Admit ': 0.42}
    {'_id': ObjectId('6444ccd095bfe06993327138'), 'Serial No.': 97, 'GRE Score': 306, 'TOEFL Score': 100, 'University Rating': 2, 'SOP': 3.0, 'LOR ': 3.0, 'CGPA': 8.0, 'Research': 0, 'Chance of Admit ': 0.48}
    {'_id': ObjectId('6444ccd095bfe06993327139'), 'Serial No.': 98, 'GRE Score': 331, 'TOEFL Score': 120, 'University Rating': 3, 'SOP': 4.0, 'LOR ': 4.0, 'CGPA': 8.96, 'Research': 1, 'Chance of Admit ': 0.86}
    {'_id': ObjectId('6444ccd095bfe0699332713a'), 'Serial No.': 99, 'GRE Score': 332, 'TOEFL Score': 119, 'University Rating': 4, 'SOP': 5.0, 'LOR ': 4.5, 'CGPA': 9.24, 'Research': 1, 'Chance of Admit ': 0.9}
    {'_id': ObjectId('6444ccd095bfe0699332713b'), 'Serial No.': 100, 'GRE Score': 323, 'TOEFL Score': 113, 'University Rating': 3, 'SOP': 4.0, 'LOR ': 4.0, 'CGPA': 8.88, 'Research': 1, 'Chance of Admit ': 0.79}
    {'_id': ObjectId('6444ccd095bfe0699332713c'), 'Serial No.': 101, 'GRE Score': 322, 'TOEFL Score': 107, 'University Rating': 3, 'SOP': 3.5, 'LOR ': 3.5, 'CGPA': 8.46, 'Research': 1, 'Chance of Admit ': 0.71}
    {'_id': ObjectId('6444ccd095bfe0699332713d'), 'Serial No.': 102, 'GRE Score': 312, 'TOEFL Score': 105, 'University Rating': 2, 'SOP': 2.5, 'LOR ': 3.0, 'CGPA': 8.12, 'Research': 0, 'Chance of Admit ': 0.64}
    {'_id': ObjectId('6444ccd095bfe0699332713e'), 'Serial No.': 103, 'GRE Score': 314, 'TOEFL Score': 106, 'University Rating': 2, 'SOP': 4.0, 'LOR ': 3.5, 'CGPA': 8.25, 'Research': 0, 'Chance of Admit ': 0.62}
    {'_id': ObjectId('6444ccd095bfe0699332713f'), 'Serial No.': 104, 'GRE Score': 317, 'TOEFL Score': 104, 'University Rating': 2, 'SOP': 4.5, 'LOR ': 4.0, 'CGPA': 8.47, 'Research': 0, 'Chance of Admit ': 0.57}
    {'_id': ObjectId('6444ccd095bfe06993327140'), 'Serial No.': 105, 'GRE Score': 326, 'TOEFL Score': 112, 'University Rating': 3, 'SOP': 3.5, 'LOR ': 3.0, 'CGPA': 9.05, 'Research': 1, 'Chance of Admit ': 0.74}
    {'_id': ObjectId('6444ccd095bfe06993327141'), 'Serial No.': 106, 'GRE Score': 316, 'TOEFL Score': 110, 'University Rating': 3, 'SOP': 4.0, 'LOR ': 4.5, 'CGPA': 8.78, 'Research': 1, 'Chance of Admit ': 0.69}
    {'_id': ObjectId('6444ccd095bfe06993327142'), 'Serial No.': 107, 'GRE Score': 329, 'TOEFL Score': 111, 'University Rating': 4, 'SOP': 4.5, 'LOR ': 4.5, 'CGPA': 9.18, 'Research': 1, 'Chance of Admit ': 0.87}
    {'_id': ObjectId('6444ccd095bfe06993327143'), 'Serial No.': 108, 'GRE Score': 338, 'TOEFL Score': 117, 'University Rating': 4, 'SOP': 3.5, 'LOR ': 4.5, 'CGPA': 9.46, 'Research': 1, 'Chance of Admit ': 0.91}
    {'_id': ObjectId('6444ccd095bfe06993327144'), 'Serial No.': 109, 'GRE Score': 331, 'TOEFL Score': 116, 'University Rating': 5, 'SOP': 5.0, 'LOR ': 5.0, 'CGPA': 9.38, 'Research': 1, 'Chance of Admit ': 0.93}
    {'_id': ObjectId('6444ccd095bfe06993327145'), 'Serial No.': 110, 'GRE Score': 304, 'TOEFL Score': 103, 'University Rating': 5, 'SOP': 5.0, 'LOR ': 4.0, 'CGPA': 8.64, 'Research': 0, 'Chance of Admit ': 0.68}
    {'_id': ObjectId('6444ccd095bfe06993327146'), 'Serial No.': 111, 'GRE Score': 305, 'TOEFL Score': 108, 'University Rating': 5, 'SOP': 3.0, 'LOR ': 3.0, 'CGPA': 8.48, 'Research': 0, 'Chance of Admit ': 0.61}
    {'_id': ObjectId('6444ccd095bfe06993327147'), 'Serial No.': 112, 'GRE Score': 321, 'TOEFL Score': 109, 'University Rating': 4, 'SOP': 4.0, 'LOR ': 4.0, 'CGPA': 8.68, 'Research': 1, 'Chance of Admit ': 0.69}
    {'_id': ObjectId('6444ccd095bfe06993327148'), 'Serial No.': 113, 'GRE Score': 301, 'TOEFL Score': 107, 'University Rating': 3, 'SOP': 3.5, 'LOR ': 3.5, 'CGPA': 8.34, 'Research': 1, 'Chance of Admit ': 0.62}
    {'_id': ObjectId('6444ccd095bfe06993327149'), 'Serial No.': 114, 'GRE Score': 320, 'TOEFL Score': 110, 'University Rating': 2, 'SOP': 4.0, 'LOR ': 3.5, 'CGPA': 8.56, 'Research': 0, 'Chance of Admit ': 0.72}
    {'_id': ObjectId('6444ccd095bfe0699332714a'), 'Serial No.': 115, 'GRE Score': 311, 'TOEFL Score': 105, 'University Rating': 3, 'SOP': 3.5, 'LOR ': 3.0, 'CGPA': 8.45, 'Research': 1, 'Chance of Admit ': 0.59}
    {'_id': ObjectId('6444ccd095bfe0699332714b'), 'Serial No.': 116, 'GRE Score': 310, 'TOEFL Score': 106, 'University Rating': 4, 'SOP': 4.5, 'LOR ': 4.5, 'CGPA': 9.04, 'Research': 1, 'Chance of Admit ': 0.66}
    {'_id': ObjectId('6444ccd095bfe0699332714c'), 'Serial No.': 117, 'GRE Score': 299, 'TOEFL Score': 102, 'University Rating': 3, 'SOP': 4.0, 'LOR ': 3.5, 'CGPA': 8.62, 'Research': 0, 'Chance of Admit ': 0.56}
    {'_id': ObjectId('6444ccd095bfe0699332714d'), 'Serial No.': 118, 'GRE Score': 290, 'TOEFL Score': 104, 'University Rating': 4, 'SOP': 2.0, 'LOR ': 2.5, 'CGPA': 7.46, 'Research': 0, 'Chance of Admit ': 0.45}
    {'_id': ObjectId('6444ccd095bfe0699332714e'), 'Serial No.': 119, 'GRE Score': 296, 'TOEFL Score': 99, 'University Rating': 2, 'SOP': 3.0, 'LOR ': 3.5, 'CGPA': 7.28, 'Research': 0, 'Chance of Admit ': 0.47}
    {'_id': ObjectId('6444ccd095bfe0699332714f'), 'Serial No.': 120, 'GRE Score': 327, 'TOEFL Score': 104, 'University Rating': 5, 'SOP': 3.0, 'LOR ': 3.5, 'CGPA': 8.84, 'Research': 1, 'Chance of Admit ': 0.71}
    {'_id': ObjectId('6444ccd095bfe06993327150'), 'Serial No.': 121, 'GRE Score': 335, 'TOEFL Score': 117, 'University Rating': 5, 'SOP': 5.0, 'LOR ': 5.0, 'CGPA': 9.56, 'Research': 1, 'Chance of Admit ': 0.94}
    {'_id': ObjectId('6444ccd095bfe06993327151'), 'Serial No.': 122, 'GRE Score': 334, 'TOEFL Score': 119, 'University Rating': 5, 'SOP': 4.5, 'LOR ': 4.5, 'CGPA': 9.48, 'Research': 1, 'Chance of Admit ': 0.94}
    {'_id': ObjectId('6444ccd095bfe06993327152'), 'Serial No.': 123, 'GRE Score': 310, 'TOEFL Score': 106, 'University Rating': 4, 'SOP': 1.5, 'LOR ': 2.5, 'CGPA': 8.36, 'Research': 0, 'Chance of Admit ': 0.57}
    {'_id': ObjectId('6444ccd095bfe06993327153'), 'Serial No.': 124, 'GRE Score': 308, 'TOEFL Score': 108, 'University Rating': 3, 'SOP': 3.5, 'LOR ': 3.5, 'CGPA': 8.22, 'Research': 0, 'Chance of Admit ': 0.61}
    {'_id': ObjectId('6444ccd095bfe06993327154'), 'Serial No.': 125, 'GRE Score': 301, 'TOEFL Score': 106, 'University Rating': 4, 'SOP': 2.5, 'LOR ': 3.0, 'CGPA': 8.47, 'Research': 0, 'Chance of Admit ': 0.57}
    {'_id': ObjectId('6444ccd095bfe06993327155'), 'Serial No.': 126, 'GRE Score': 300, 'TOEFL Score': 100, 'University Rating': 3, 'SOP': 2.0, 'LOR ': 3.0, 'CGPA': 8.66, 'Research': 1, 'Chance of Admit ': 0.64}
    {'_id': ObjectId('6444ccd095bfe06993327156'), 'Serial No.': 127, 'GRE Score': 323, 'TOEFL Score': 113, 'University Rating': 3, 'SOP': 4.0, 'LOR ': 3.0, 'CGPA': 9.32, 'Research': 1, 'Chance of Admit ': 0.85}
    {'_id': ObjectId('6444ccd095bfe06993327157'), 'Serial No.': 128, 'GRE Score': 319, 'TOEFL Score': 112, 'University Rating': 3, 'SOP': 2.5, 'LOR ': 2.0, 'CGPA': 8.71, 'Research': 1, 'Chance of Admit ': 0.78}
    {'_id': ObjectId('6444ccd095bfe06993327158'), 'Serial No.': 129, 'GRE Score': 326, 'TOEFL Score': 112, 'University Rating': 3, 'SOP': 3.5, 'LOR ': 3.0, 'CGPA': 9.1, 'Research': 1, 'Chance of Admit ': 0.84}
    {'_id': ObjectId('6444ccd095bfe06993327159'), 'Serial No.': 130, 'GRE Score': 333, 'TOEFL Score': 118, 'University Rating': 5, 'SOP': 5.0, 'LOR ': 5.0, 'CGPA': 9.35, 'Research': 1, 'Chance of Admit ': 0.92}
    {'_id': ObjectId('6444ccd095bfe0699332715a'), 'Serial No.': 131, 'GRE Score': 339, 'TOEFL Score': 114, 'University Rating': 5, 'SOP': 4.0, 'LOR ': 4.5, 'CGPA': 9.76, 'Research': 1, 'Chance of Admit ': 0.96}
    {'_id': ObjectId('6444ccd095bfe0699332715b'), 'Serial No.': 132, 'GRE Score': 303, 'TOEFL Score': 105, 'University Rating': 5, 'SOP': 5.0, 'LOR ': 4.5, 'CGPA': 8.65, 'Research': 0, 'Chance of Admit ': 0.77}
    {'_id': ObjectId('6444ccd095bfe0699332715c'), 'Serial No.': 133, 'GRE Score': 309, 'TOEFL Score': 105, 'University Rating': 5, 'SOP': 3.5, 'LOR ': 3.5, 'CGPA': 8.56, 'Research': 0, 'Chance of Admit ': 0.71}
    {'_id': ObjectId('6444ccd095bfe0699332715d'), 'Serial No.': 134, 'GRE Score': 323, 'TOEFL Score': 112, 'University Rating': 5, 'SOP': 4.0, 'LOR ': 4.5, 'CGPA': 8.78, 'Research': 0, 'Chance of Admit ': 0.79}
    {'_id': ObjectId('6444ccd095bfe0699332715e'), 'Serial No.': 135, 'GRE Score': 333, 'TOEFL Score': 113, 'University Rating': 5, 'SOP': 4.0, 'LOR ': 4.0, 'CGPA': 9.28, 'Research': 1, 'Chance of Admit ': 0.89}
    {'_id': ObjectId('6444ccd095bfe0699332715f'), 'Serial No.': 136, 'GRE Score': 314, 'TOEFL Score': 109, 'University Rating': 4, 'SOP': 3.5, 'LOR ': 4.0, 'CGPA': 8.77, 'Research': 1, 'Chance of Admit ': 0.82}
    {'_id': ObjectId('6444ccd095bfe06993327160'), 'Serial No.': 137, 'GRE Score': 312, 'TOEFL Score': 103, 'University Rating': 3, 'SOP': 5.0, 'LOR ': 4.0, 'CGPA': 8.45, 'Research': 0, 'Chance of Admit ': 0.76}
    {'_id': ObjectId('6444ccd095bfe06993327161'), 'Serial No.': 138, 'GRE Score': 316, 'TOEFL Score': 100, 'University Rating': 2, 'SOP': 1.5, 'LOR ': 3.0, 'CGPA': 8.16, 'Research': 1, 'Chance of Admit ': 0.71}
    {'_id': ObjectId('6444ccd095bfe06993327162'), 'Serial No.': 139, 'GRE Score': 326, 'TOEFL Score': 116, 'University Rating': 2, 'SOP': 4.5, 'LOR ': 3.0, 'CGPA': 9.08, 'Research': 1, 'Chance of Admit ': 0.8}
    {'_id': ObjectId('6444ccd095bfe06993327163'), 'Serial No.': 140, 'GRE Score': 318, 'TOEFL Score': 109, 'University Rating': 1, 'SOP': 3.5, 'LOR ': 3.5, 'CGPA': 9.12, 'Research': 0, 'Chance of Admit ': 0.78}
    {'_id': ObjectId('6444ccd095bfe06993327164'), 'Serial No.': 141, 'GRE Score': 329, 'TOEFL Score': 110, 'University Rating': 2, 'SOP': 4.0, 'LOR ': 3.0, 'CGPA': 9.15, 'Research': 1, 'Chance of Admit ': 0.84}
    {'_id': ObjectId('6444ccd095bfe06993327165'), 'Serial No.': 142, 'GRE Score': 332, 'TOEFL Score': 118, 'University Rating': 2, 'SOP': 4.5, 'LOR ': 3.5, 'CGPA': 9.36, 'Research': 1, 'Chance of Admit ': 0.9}
    {'_id': ObjectId('6444ccd095bfe06993327166'), 'Serial No.': 143, 'GRE Score': 331, 'TOEFL Score': 115, 'University Rating': 5, 'SOP': 4.0, 'LOR ': 3.5, 'CGPA': 9.44, 'Research': 1, 'Chance of Admit ': 0.92}
    {'_id': ObjectId('6444ccd095bfe06993327167'), 'Serial No.': 144, 'GRE Score': 340, 'TOEFL Score': 120, 'University Rating': 4, 'SOP': 4.5, 'LOR ': 4.0, 'CGPA': 9.92, 'Research': 1, 'Chance of Admit ': 0.97}
    {'_id': ObjectId('6444ccd095bfe06993327168'), 'Serial No.': 145, 'GRE Score': 325, 'TOEFL Score': 112, 'University Rating': 2, 'SOP': 3.0, 'LOR ': 3.5, 'CGPA': 8.96, 'Research': 1, 'Chance of Admit ': 0.8}
    {'_id': ObjectId('6444ccd095bfe06993327169'), 'Serial No.': 146, 'GRE Score': 320, 'TOEFL Score': 113, 'University Rating': 2, 'SOP': 2.0, 'LOR ': 2.5, 'CGPA': 8.64, 'Research': 1, 'Chance of Admit ': 0.81}
    {'_id': ObjectId('6444ccd095bfe0699332716a'), 'Serial No.': 147, 'GRE Score': 315, 'TOEFL Score': 105, 'University Rating': 3, 'SOP': 2.0, 'LOR ': 2.5, 'CGPA': 8.48, 'Research': 0, 'Chance of Admit ': 0.75}
    {'_id': ObjectId('6444ccd095bfe0699332716b'), 'Serial No.': 148, 'GRE Score': 326, 'TOEFL Score': 114, 'University Rating': 3, 'SOP': 3.0, 'LOR ': 3.0, 'CGPA': 9.11, 'Research': 1, 'Chance of Admit ': 0.83}
    {'_id': ObjectId('6444ccd095bfe0699332716c'), 'Serial No.': 149, 'GRE Score': 339, 'TOEFL Score': 116, 'University Rating': 4, 'SOP': 4.0, 'LOR ': 3.5, 'CGPA': 9.8, 'Research': 1, 'Chance of Admit ': 0.96}
    {'_id': ObjectId('6444ccd095bfe0699332716d'), 'Serial No.': 150, 'GRE Score': 311, 'TOEFL Score': 106, 'University Rating': 2, 'SOP': 3.5, 'LOR ': 3.0, 'CGPA': 8.26, 'Research': 1, 'Chance of Admit ': 0.79}
    {'_id': ObjectId('6444ccd095bfe0699332716e'), 'Serial No.': 151, 'GRE Score': 334, 'TOEFL Score': 114, 'University Rating': 4, 'SOP': 4.0, 'LOR ': 4.0, 'CGPA': 9.43, 'Research': 1, 'Chance of Admit ': 0.93}
    {'_id': ObjectId('6444ccd095bfe0699332716f'), 'Serial No.': 152, 'GRE Score': 332, 'TOEFL Score': 116, 'University Rating': 5, 'SOP': 5.0, 'LOR ': 5.0, 'CGPA': 9.28, 'Research': 1, 'Chance of Admit ': 0.94}
    {'_id': ObjectId('6444ccd095bfe06993327170'), 'Serial No.': 153, 'GRE Score': 321, 'TOEFL Score': 112, 'University Rating': 5, 'SOP': 5.0, 'LOR ': 5.0, 'CGPA': 9.06, 'Research': 1, 'Chance of Admit ': 0.86}
    {'_id': ObjectId('6444ccd095bfe06993327171'), 'Serial No.': 154, 'GRE Score': 324, 'TOEFL Score': 105, 'University Rating': 3, 'SOP': 3.0, 'LOR ': 4.0, 'CGPA': 8.75, 'Research': 0, 'Chance of Admit ': 0.79}
    {'_id': ObjectId('6444ccd095bfe06993327172'), 'Serial No.': 155, 'GRE Score': 326, 'TOEFL Score': 108, 'University Rating': 3, 'SOP': 3.0, 'LOR ': 3.5, 'CGPA': 8.89, 'Research': 0, 'Chance of Admit ': 0.8}
    {'_id': ObjectId('6444ccd095bfe06993327173'), 'Serial No.': 156, 'GRE Score': 312, 'TOEFL Score': 109, 'University Rating': 3, 'SOP': 3.0, 'LOR ': 3.0, 'CGPA': 8.69, 'Research': 0, 'Chance of Admit ': 0.77}
    {'_id': ObjectId('6444ccd095bfe06993327174'), 'Serial No.': 157, 'GRE Score': 315, 'TOEFL Score': 105, 'University Rating': 3, 'SOP': 2.0, 'LOR ': 2.5, 'CGPA': 8.34, 'Research': 0, 'Chance of Admit ': 0.7}
    {'_id': ObjectId('6444ccd095bfe06993327175'), 'Serial No.': 158, 'GRE Score': 309, 'TOEFL Score': 104, 'University Rating': 2, 'SOP': 2.0, 'LOR ': 2.5, 'CGPA': 8.26, 'Research': 0, 'Chance of Admit ': 0.65}
    {'_id': ObjectId('6444ccd095bfe06993327176'), 'Serial No.': 159, 'GRE Score': 306, 'TOEFL Score': 106, 'University Rating': 2, 'SOP': 2.0, 'LOR ': 2.5, 'CGPA': 8.14, 'Research': 0, 'Chance of Admit ': 0.61}
    {'_id': ObjectId('6444ccd095bfe06993327177'), 'Serial No.': 160, 'GRE Score': 297, 'TOEFL Score': 100, 'University Rating': 1, 'SOP': 1.5, 'LOR ': 2.0, 'CGPA': 7.9, 'Research': 0, 'Chance of Admit ': 0.52}
    {'_id': ObjectId('6444ccd095bfe06993327178'), 'Serial No.': 161, 'GRE Score': 315, 'TOEFL Score': 103, 'University Rating': 1, 'SOP': 1.5, 'LOR ': 2.0, 'CGPA': 7.86, 'Research': 0, 'Chance of Admit ': 0.57}
    {'_id': ObjectId('6444ccd095bfe06993327179'), 'Serial No.': 162, 'GRE Score': 298, 'TOEFL Score': 99, 'University Rating': 1, 'SOP': 1.5, 'LOR ': 3.0, 'CGPA': 7.46, 'Research': 0, 'Chance of Admit ': 0.53}
    {'_id': ObjectId('6444ccd095bfe0699332717a'), 'Serial No.': 163, 'GRE Score': 318, 'TOEFL Score': 109, 'University Rating': 3, 'SOP': 3.0, 'LOR ': 3.0, 'CGPA': 8.5, 'Research': 0, 'Chance of Admit ': 0.67}
    {'_id': ObjectId('6444ccd095bfe0699332717b'), 'Serial No.': 164, 'GRE Score': 317, 'TOEFL Score': 105, 'University Rating': 3, 'SOP': 3.5, 'LOR ': 3.0, 'CGPA': 8.56, 'Research': 0, 'Chance of Admit ': 0.68}
    {'_id': ObjectId('6444ccd095bfe0699332717c'), 'Serial No.': 165, 'GRE Score': 329, 'TOEFL Score': 111, 'University Rating': 4, 'SOP': 4.5, 'LOR ': 4.0, 'CGPA': 9.01, 'Research': 1, 'Chance of Admit ': 0.81}
    {'_id': ObjectId('6444ccd095bfe0699332717d'), 'Serial No.': 166, 'GRE Score': 322, 'TOEFL Score': 110, 'University Rating': 5, 'SOP': 4.5, 'LOR ': 4.0, 'CGPA': 8.97, 'Research': 0, 'Chance of Admit ': 0.78}
    {'_id': ObjectId('6444ccd095bfe0699332717e'), 'Serial No.': 167, 'GRE Score': 302, 'TOEFL Score': 102, 'University Rating': 3, 'SOP': 3.5, 'LOR ': 5.0, 'CGPA': 8.33, 'Research': 0, 'Chance of Admit ': 0.65}
    {'_id': ObjectId('6444ccd095bfe0699332717f'), 'Serial No.': 168, 'GRE Score': 313, 'TOEFL Score': 102, 'University Rating': 3, 'SOP': 2.0, 'LOR ': 3.0, 'CGPA': 8.27, 'Research': 0, 'Chance of Admit ': 0.64}
    {'_id': ObjectId('6444ccd095bfe06993327180'), 'Serial No.': 169, 'GRE Score': 293, 'TOEFL Score': 97, 'University Rating': 2, 'SOP': 2.0, 'LOR ': 4.0, 'CGPA': 7.8, 'Research': 1, 'Chance of Admit ': 0.64}
    {'_id': ObjectId('6444ccd095bfe06993327181'), 'Serial No.': 170, 'GRE Score': 311, 'TOEFL Score': 99, 'University Rating': 2, 'SOP': 2.5, 'LOR ': 3.0, 'CGPA': 7.98, 'Research': 0, 'Chance of Admit ': 0.65}
    {'_id': ObjectId('6444ccd095bfe06993327182'), 'Serial No.': 171, 'GRE Score': 312, 'TOEFL Score': 101, 'University Rating': 2, 'SOP': 2.5, 'LOR ': 3.5, 'CGPA': 8.04, 'Research': 1, 'Chance of Admit ': 0.68}
    {'_id': ObjectId('6444ccd095bfe06993327183'), 'Serial No.': 172, 'GRE Score': 334, 'TOEFL Score': 117, 'University Rating': 5, 'SOP': 4.0, 'LOR ': 4.5, 'CGPA': 9.07, 'Research': 1, 'Chance of Admit ': 0.89}
    {'_id': ObjectId('6444ccd095bfe06993327184'), 'Serial No.': 173, 'GRE Score': 322, 'TOEFL Score': 110, 'University Rating': 4, 'SOP': 4.0, 'LOR ': 5.0, 'CGPA': 9.13, 'Research': 1, 'Chance of Admit ': 0.86}
    {'_id': ObjectId('6444ccd095bfe06993327185'), 'Serial No.': 174, 'GRE Score': 323, 'TOEFL Score': 113, 'University Rating': 4, 'SOP': 4.0, 'LOR ': 4.5, 'CGPA': 9.23, 'Research': 1, 'Chance of Admit ': 0.89}
    {'_id': ObjectId('6444ccd095bfe06993327186'), 'Serial No.': 175, 'GRE Score': 321, 'TOEFL Score': 111, 'University Rating': 4, 'SOP': 4.0, 'LOR ': 4.0, 'CGPA': 8.97, 'Research': 1, 'Chance of Admit ': 0.87}
    {'_id': ObjectId('6444ccd095bfe06993327187'), 'Serial No.': 176, 'GRE Score': 320, 'TOEFL Score': 111, 'University Rating': 4, 'SOP': 4.5, 'LOR ': 3.5, 'CGPA': 8.87, 'Research': 1, 'Chance of Admit ': 0.85}
    {'_id': ObjectId('6444ccd095bfe06993327188'), 'Serial No.': 177, 'GRE Score': 329, 'TOEFL Score': 119, 'University Rating': 4, 'SOP': 4.5, 'LOR ': 4.5, 'CGPA': 9.16, 'Research': 1, 'Chance of Admit ': 0.9}
    {'_id': ObjectId('6444ccd095bfe06993327189'), 'Serial No.': 178, 'GRE Score': 319, 'TOEFL Score': 110, 'University Rating': 3, 'SOP': 3.5, 'LOR ': 3.5, 'CGPA': 9.04, 'Research': 0, 'Chance of Admit ': 0.82}
    {'_id': ObjectId('6444ccd095bfe0699332718a'), 'Serial No.': 179, 'GRE Score': 309, 'TOEFL Score': 108, 'University Rating': 3, 'SOP': 2.5, 'LOR ': 3.0, 'CGPA': 8.12, 'Research': 0, 'Chance of Admit ': 0.72}
    {'_id': ObjectId('6444ccd095bfe0699332718b'), 'Serial No.': 180, 'GRE Score': 307, 'TOEFL Score': 102, 'University Rating': 3, 'SOP': 3.0, 'LOR ': 3.0, 'CGPA': 8.27, 'Research': 0, 'Chance of Admit ': 0.73}
    {'_id': ObjectId('6444ccd095bfe0699332718c'), 'Serial No.': 181, 'GRE Score': 300, 'TOEFL Score': 104, 'University Rating': 3, 'SOP': 3.5, 'LOR ': 3.0, 'CGPA': 8.16, 'Research': 0, 'Chance of Admit ': 0.71}
    {'_id': ObjectId('6444ccd095bfe0699332718d'), 'Serial No.': 182, 'GRE Score': 305, 'TOEFL Score': 107, 'University Rating': 2, 'SOP': 2.5, 'LOR ': 2.5, 'CGPA': 8.42, 'Research': 0, 'Chance of Admit ': 0.71}
    {'_id': ObjectId('6444ccd095bfe0699332718e'), 'Serial No.': 183, 'GRE Score': 299, 'TOEFL Score': 100, 'University Rating': 2, 'SOP': 3.0, 'LOR ': 3.5, 'CGPA': 7.88, 'Research': 0, 'Chance of Admit ': 0.68}
    {'_id': ObjectId('6444ccd095bfe0699332718f'), 'Serial No.': 184, 'GRE Score': 314, 'TOEFL Score': 110, 'University Rating': 3, 'SOP': 4.0, 'LOR ': 4.0, 'CGPA': 8.8, 'Research': 0, 'Chance of Admit ': 0.75}
    {'_id': ObjectId('6444ccd095bfe06993327190'), 'Serial No.': 185, 'GRE Score': 316, 'TOEFL Score': 106, 'University Rating': 2, 'SOP': 2.5, 'LOR ': 4.0, 'CGPA': 8.32, 'Research': 0, 'Chance of Admit ': 0.72}
    {'_id': ObjectId('6444ccd095bfe06993327191'), 'Serial No.': 186, 'GRE Score': 327, 'TOEFL Score': 113, 'University Rating': 4, 'SOP': 4.5, 'LOR ': 4.5, 'CGPA': 9.11, 'Research': 1, 'Chance of Admit ': 0.89}
    {'_id': ObjectId('6444ccd095bfe06993327192'), 'Serial No.': 187, 'GRE Score': 317, 'TOEFL Score': 107, 'University Rating': 3, 'SOP': 3.5, 'LOR ': 3.0, 'CGPA': 8.68, 'Research': 1, 'Chance of Admit ': 0.84}
    {'_id': ObjectId('6444ccd095bfe06993327193'), 'Serial No.': 188, 'GRE Score': 335, 'TOEFL Score': 118, 'University Rating': 5, 'SOP': 4.5, 'LOR ': 3.5, 'CGPA': 9.44, 'Research': 1, 'Chance of Admit ': 0.93}
    {'_id': ObjectId('6444ccd095bfe06993327194'), 'Serial No.': 189, 'GRE Score': 331, 'TOEFL Score': 115, 'University Rating': 5, 'SOP': 4.5, 'LOR ': 3.5, 'CGPA': 9.36, 'Research': 1, 'Chance of Admit ': 0.93}
    {'_id': ObjectId('6444ccd095bfe06993327195'), 'Serial No.': 190, 'GRE Score': 324, 'TOEFL Score': 112, 'University Rating': 5, 'SOP': 5.0, 'LOR ': 5.0, 'CGPA': 9.08, 'Research': 1, 'Chance of Admit ': 0.88}
    {'_id': ObjectId('6444ccd095bfe06993327196'), 'Serial No.': 191, 'GRE Score': 324, 'TOEFL Score': 111, 'University Rating': 5, 'SOP': 4.5, 'LOR ': 4.0, 'CGPA': 9.16, 'Research': 1, 'Chance of Admit ': 0.9}
    {'_id': ObjectId('6444ccd095bfe06993327197'), 'Serial No.': 192, 'GRE Score': 323, 'TOEFL Score': 110, 'University Rating': 5, 'SOP': 4.0, 'LOR ': 5.0, 'CGPA': 8.98, 'Research': 1, 'Chance of Admit ': 0.87}
    {'_id': ObjectId('6444ccd095bfe06993327198'), 'Serial No.': 193, 'GRE Score': 322, 'TOEFL Score': 114, 'University Rating': 5, 'SOP': 4.5, 'LOR ': 4.0, 'CGPA': 8.94, 'Research': 1, 'Chance of Admit ': 0.86}
    {'_id': ObjectId('6444ccd095bfe06993327199'), 'Serial No.': 194, 'GRE Score': 336, 'TOEFL Score': 118, 'University Rating': 5, 'SOP': 4.5, 'LOR ': 5.0, 'CGPA': 9.53, 'Research': 1, 'Chance of Admit ': 0.94}
    {'_id': ObjectId('6444ccd095bfe0699332719a'), 'Serial No.': 195, 'GRE Score': 316, 'TOEFL Score': 109, 'University Rating': 3, 'SOP': 3.5, 'LOR ': 3.0, 'CGPA': 8.76, 'Research': 0, 'Chance of Admit ': 0.77}
    {'_id': ObjectId('6444ccd095bfe0699332719b'), 'Serial No.': 196, 'GRE Score': 307, 'TOEFL Score': 107, 'University Rating': 2, 'SOP': 3.0, 'LOR ': 3.5, 'CGPA': 8.52, 'Research': 1, 'Chance of Admit ': 0.78}
    {'_id': ObjectId('6444ccd095bfe0699332719c'), 'Serial No.': 197, 'GRE Score': 306, 'TOEFL Score': 105, 'University Rating': 2, 'SOP': 3.0, 'LOR ': 2.5, 'CGPA': 8.26, 'Research': 0, 'Chance of Admit ': 0.73}
    {'_id': ObjectId('6444ccd095bfe0699332719d'), 'Serial No.': 198, 'GRE Score': 310, 'TOEFL Score': 106, 'University Rating': 2, 'SOP': 3.5, 'LOR ': 2.5, 'CGPA': 8.33, 'Research': 0, 'Chance of Admit ': 0.73}
    {'_id': ObjectId('6444ccd095bfe0699332719e'), 'Serial No.': 199, 'GRE Score': 311, 'TOEFL Score': 104, 'University Rating': 3, 'SOP': 4.5, 'LOR ': 4.5, 'CGPA': 8.43, 'Research': 0, 'Chance of Admit ': 0.7}
    {'_id': ObjectId('6444ccd095bfe0699332719f'), 'Serial No.': 200, 'GRE Score': 313, 'TOEFL Score': 107, 'University Rating': 3, 'SOP': 4.0, 'LOR ': 4.5, 'CGPA': 8.69, 'Research': 0, 'Chance of Admit ': 0.72}
    {'_id': ObjectId('6444ccd095bfe069933271a0'), 'Serial No.': 201, 'GRE Score': 317, 'TOEFL Score': 103, 'University Rating': 3, 'SOP': 2.5, 'LOR ': 3.0, 'CGPA': 8.54, 'Research': 1, 'Chance of Admit ': 0.73}
    {'_id': ObjectId('6444ccd095bfe069933271a1'), 'Serial No.': 202, 'GRE Score': 315, 'TOEFL Score': 110, 'University Rating': 2, 'SOP': 3.5, 'LOR ': 3.0, 'CGPA': 8.46, 'Research': 1, 'Chance of Admit ': 0.72}
    {'_id': ObjectId('6444ccd095bfe069933271a2'), 'Serial No.': 203, 'GRE Score': 340, 'TOEFL Score': 120, 'University Rating': 5, 'SOP': 4.5, 'LOR ': 4.5, 'CGPA': 9.91, 'Research': 1, 'Chance of Admit ': 0.97}
    {'_id': ObjectId('6444ccd095bfe069933271a3'), 'Serial No.': 204, 'GRE Score': 334, 'TOEFL Score': 120, 'University Rating': 5, 'SOP': 4.0, 'LOR ': 5.0, 'CGPA': 9.87, 'Research': 1, 'Chance of Admit ': 0.97}
    {'_id': ObjectId('6444ccd095bfe069933271a4'), 'Serial No.': 205, 'GRE Score': 298, 'TOEFL Score': 105, 'University Rating': 3, 'SOP': 3.5, 'LOR ': 4.0, 'CGPA': 8.54, 'Research': 0, 'Chance of Admit ': 0.69}
    {'_id': ObjectId('6444ccd095bfe069933271a5'), 'Serial No.': 206, 'GRE Score': 295, 'TOEFL Score': 99, 'University Rating': 2, 'SOP': 2.5, 'LOR ': 3.0, 'CGPA': 7.65, 'Research': 0, 'Chance of Admit ': 0.57}
    {'_id': ObjectId('6444ccd095bfe069933271a6'), 'Serial No.': 207, 'GRE Score': 315, 'TOEFL Score': 99, 'University Rating': 2, 'SOP': 3.5, 'LOR ': 3.0, 'CGPA': 7.89, 'Research': 0, 'Chance of Admit ': 0.63}
    {'_id': ObjectId('6444ccd095bfe069933271a7'), 'Serial No.': 208, 'GRE Score': 310, 'TOEFL Score': 102, 'University Rating': 3, 'SOP': 3.5, 'LOR ': 4.0, 'CGPA': 8.02, 'Research': 1, 'Chance of Admit ': 0.66}
    {'_id': ObjectId('6444ccd095bfe069933271a8'), 'Serial No.': 209, 'GRE Score': 305, 'TOEFL Score': 106, 'University Rating': 2, 'SOP': 3.0, 'LOR ': 3.0, 'CGPA': 8.16, 'Research': 0, 'Chance of Admit ': 0.64}
    {'_id': ObjectId('6444ccd095bfe069933271a9'), 'Serial No.': 210, 'GRE Score': 301, 'TOEFL Score': 104, 'University Rating': 3, 'SOP': 3.5, 'LOR ': 4.0, 'CGPA': 8.12, 'Research': 1, 'Chance of Admit ': 0.68}
    {'_id': ObjectId('6444ccd095bfe069933271aa'), 'Serial No.': 211, 'GRE Score': 325, 'TOEFL Score': 108, 'University Rating': 4, 'SOP': 4.5, 'LOR ': 4.0, 'CGPA': 9.06, 'Research': 1, 'Chance of Admit ': 0.79}
    {'_id': ObjectId('6444ccd095bfe069933271ab'), 'Serial No.': 212, 'GRE Score': 328, 'TOEFL Score': 110, 'University Rating': 4, 'SOP': 5.0, 'LOR ': 4.0, 'CGPA': 9.14, 'Research': 1, 'Chance of Admit ': 0.82}
    {'_id': ObjectId('6444ccd095bfe069933271ac'), 'Serial No.': 213, 'GRE Score': 338, 'TOEFL Score': 120, 'University Rating': 4, 'SOP': 5.0, 'LOR ': 5.0, 'CGPA': 9.66, 'Research': 1, 'Chance of Admit ': 0.95}
    {'_id': ObjectId('6444ccd095bfe069933271ad'), 'Serial No.': 214, 'GRE Score': 333, 'TOEFL Score': 119, 'University Rating': 5, 'SOP': 5.0, 'LOR ': 4.5, 'CGPA': 9.78, 'Research': 1, 'Chance of Admit ': 0.96}
    {'_id': ObjectId('6444ccd095bfe069933271ae'), 'Serial No.': 215, 'GRE Score': 331, 'TOEFL Score': 117, 'University Rating': 4, 'SOP': 4.5, 'LOR ': 5.0, 'CGPA': 9.42, 'Research': 1, 'Chance of Admit ': 0.94}
    {'_id': ObjectId('6444ccd095bfe069933271af'), 'Serial No.': 216, 'GRE Score': 330, 'TOEFL Score': 116, 'University Rating': 5, 'SOP': 5.0, 'LOR ': 4.5, 'CGPA': 9.36, 'Research': 1, 'Chance of Admit ': 0.93}
    {'_id': ObjectId('6444ccd095bfe069933271b0'), 'Serial No.': 217, 'GRE Score': 322, 'TOEFL Score': 112, 'University Rating': 4, 'SOP': 4.5, 'LOR ': 4.5, 'CGPA': 9.26, 'Research': 1, 'Chance of Admit ': 0.91}
    {'_id': ObjectId('6444ccd095bfe069933271b1'), 'Serial No.': 218, 'GRE Score': 321, 'TOEFL Score': 109, 'University Rating': 4, 'SOP': 4.0, 'LOR ': 4.0, 'CGPA': 9.13, 'Research': 1, 'Chance of Admit ': 0.85}
    {'_id': ObjectId('6444ccd095bfe069933271b2'), 'Serial No.': 219, 'GRE Score': 324, 'TOEFL Score': 110, 'University Rating': 4, 'SOP': 3.0, 'LOR ': 3.5, 'CGPA': 8.97, 'Research': 1, 'Chance of Admit ': 0.84}
    {'_id': ObjectId('6444ccd095bfe069933271b3'), 'Serial No.': 220, 'GRE Score': 312, 'TOEFL Score': 104, 'University Rating': 3, 'SOP': 3.5, 'LOR ': 3.5, 'CGPA': 8.42, 'Research': 0, 'Chance of Admit ': 0.74}
    {'_id': ObjectId('6444ccd095bfe069933271b4'), 'Serial No.': 221, 'GRE Score': 313, 'TOEFL Score': 103, 'University Rating': 3, 'SOP': 4.0, 'LOR ': 4.0, 'CGPA': 8.75, 'Research': 0, 'Chance of Admit ': 0.76}
    {'_id': ObjectId('6444ccd095bfe069933271b5'), 'Serial No.': 222, 'GRE Score': 316, 'TOEFL Score': 110, 'University Rating': 3, 'SOP': 3.5, 'LOR ': 4.0, 'CGPA': 8.56, 'Research': 0, 'Chance of Admit ': 0.75}
    {'_id': ObjectId('6444ccd095bfe069933271b6'), 'Serial No.': 223, 'GRE Score': 324, 'TOEFL Score': 113, 'University Rating': 4, 'SOP': 4.5, 'LOR ': 4.0, 'CGPA': 8.79, 'Research': 0, 'Chance of Admit ': 0.76}
    {'_id': ObjectId('6444ccd095bfe069933271b7'), 'Serial No.': 224, 'GRE Score': 308, 'TOEFL Score': 109, 'University Rating': 2, 'SOP': 3.0, 'LOR ': 4.0, 'CGPA': 8.45, 'Research': 0, 'Chance of Admit ': 0.71}
    {'_id': ObjectId('6444ccd095bfe069933271b8'), 'Serial No.': 225, 'GRE Score': 305, 'TOEFL Score': 105, 'University Rating': 2, 'SOP': 3.0, 'LOR ': 2.0, 'CGPA': 8.23, 'Research': 0, 'Chance of Admit ': 0.67}
    {'_id': ObjectId('6444ccd095bfe069933271b9'), 'Serial No.': 226, 'GRE Score': 296, 'TOEFL Score': 99, 'University Rating': 2, 'SOP': 2.5, 'LOR ': 2.5, 'CGPA': 8.03, 'Research': 0, 'Chance of Admit ': 0.61}
    {'_id': ObjectId('6444ccd095bfe069933271ba'), 'Serial No.': 227, 'GRE Score': 306, 'TOEFL Score': 110, 'University Rating': 2, 'SOP': 3.5, 'LOR ': 4.0, 'CGPA': 8.45, 'Research': 0, 'Chance of Admit ': 0.63}
    {'_id': ObjectId('6444ccd095bfe069933271bb'), 'Serial No.': 228, 'GRE Score': 312, 'TOEFL Score': 110, 'University Rating': 2, 'SOP': 3.5, 'LOR ': 3.0, 'CGPA': 8.53, 'Research': 0, 'Chance of Admit ': 0.64}
    {'_id': ObjectId('6444ccd095bfe069933271bc'), 'Serial No.': 229, 'GRE Score': 318, 'TOEFL Score': 112, 'University Rating': 3, 'SOP': 4.0, 'LOR ': 3.5, 'CGPA': 8.67, 'Research': 0, 'Chance of Admit ': 0.71}
    {'_id': ObjectId('6444ccd095bfe069933271bd'), 'Serial No.': 230, 'GRE Score': 324, 'TOEFL Score': 111, 'University Rating': 4, 'SOP': 3.0, 'LOR ': 3.0, 'CGPA': 9.01, 'Research': 1, 'Chance of Admit ': 0.82}
    {'_id': ObjectId('6444ccd095bfe069933271be'), 'Serial No.': 231, 'GRE Score': 313, 'TOEFL Score': 104, 'University Rating': 3, 'SOP': 4.0, 'LOR ': 4.5, 'CGPA': 8.65, 'Research': 0, 'Chance of Admit ': 0.73}
    {'_id': ObjectId('6444ccd095bfe069933271bf'), 'Serial No.': 232, 'GRE Score': 319, 'TOEFL Score': 106, 'University Rating': 3, 'SOP': 3.5, 'LOR ': 2.5, 'CGPA': 8.33, 'Research': 1, 'Chance of Admit ': 0.74}
    {'_id': ObjectId('6444ccd095bfe069933271c0'), 'Serial No.': 233, 'GRE Score': 312, 'TOEFL Score': 107, 'University Rating': 2, 'SOP': 2.5, 'LOR ': 3.5, 'CGPA': 8.27, 'Research': 0, 'Chance of Admit ': 0.69}
    {'_id': ObjectId('6444ccd095bfe069933271c1'), 'Serial No.': 234, 'GRE Score': 304, 'TOEFL Score': 100, 'University Rating': 2, 'SOP': 2.5, 'LOR ': 3.5, 'CGPA': 8.07, 'Research': 0, 'Chance of Admit ': 0.64}
    {'_id': ObjectId('6444ccd095bfe069933271c2'), 'Serial No.': 235, 'GRE Score': 330, 'TOEFL Score': 113, 'University Rating': 5, 'SOP': 5.0, 'LOR ': 4.0, 'CGPA': 9.31, 'Research': 1, 'Chance of Admit ': 0.91}
    {'_id': ObjectId('6444ccd095bfe069933271c3'), 'Serial No.': 236, 'GRE Score': 326, 'TOEFL Score': 111, 'University Rating': 5, 'SOP': 4.5, 'LOR ': 4.0, 'CGPA': 9.23, 'Research': 1, 'Chance of Admit ': 0.88}
    {'_id': ObjectId('6444ccd095bfe069933271c4'), 'Serial No.': 237, 'GRE Score': 325, 'TOEFL Score': 112, 'University Rating': 4, 'SOP': 4.0, 'LOR ': 4.5, 'CGPA': 9.17, 'Research': 1, 'Chance of Admit ': 0.85}
    {'_id': ObjectId('6444ccd095bfe069933271c5'), 'Serial No.': 238, 'GRE Score': 329, 'TOEFL Score': 114, 'University Rating': 5, 'SOP': 4.5, 'LOR ': 5.0, 'CGPA': 9.19, 'Research': 1, 'Chance of Admit ': 0.86}
    {'_id': ObjectId('6444ccd095bfe069933271c6'), 'Serial No.': 239, 'GRE Score': 310, 'TOEFL Score': 104, 'University Rating': 3, 'SOP': 2.0, 'LOR ': 3.5, 'CGPA': 8.37, 'Research': 0, 'Chance of Admit ': 0.7}
    {'_id': ObjectId('6444ccd095bfe069933271c7'), 'Serial No.': 240, 'GRE Score': 299, 'TOEFL Score': 100, 'University Rating': 1, 'SOP': 1.5, 'LOR ': 2.0, 'CGPA': 7.89, 'Research': 0, 'Chance of Admit ': 0.59}
    {'_id': ObjectId('6444ccd095bfe069933271c8'), 'Serial No.': 241, 'GRE Score': 296, 'TOEFL Score': 101, 'University Rating': 1, 'SOP': 2.5, 'LOR ': 3.0, 'CGPA': 7.68, 'Research': 0, 'Chance of Admit ': 0.6}
    {'_id': ObjectId('6444ccd095bfe069933271c9'), 'Serial No.': 242, 'GRE Score': 317, 'TOEFL Score': 103, 'University Rating': 2, 'SOP': 2.5, 'LOR ': 2.0, 'CGPA': 8.15, 'Research': 0, 'Chance of Admit ': 0.65}
    {'_id': ObjectId('6444ccd095bfe069933271ca'), 'Serial No.': 243, 'GRE Score': 324, 'TOEFL Score': 115, 'University Rating': 3, 'SOP': 3.5, 'LOR ': 3.0, 'CGPA': 8.76, 'Research': 1, 'Chance of Admit ': 0.7}
    {'_id': ObjectId('6444ccd095bfe069933271cb'), 'Serial No.': 244, 'GRE Score': 325, 'TOEFL Score': 114, 'University Rating': 3, 'SOP': 3.5, 'LOR ': 3.0, 'CGPA': 9.04, 'Research': 1, 'Chance of Admit ': 0.76}
    {'_id': ObjectId('6444ccd095bfe069933271cc'), 'Serial No.': 245, 'GRE Score': 314, 'TOEFL Score': 107, 'University Rating': 2, 'SOP': 2.5, 'LOR ': 4.0, 'CGPA': 8.56, 'Research': 0, 'Chance of Admit ': 0.63}
    {'_id': ObjectId('6444ccd095bfe069933271cd'), 'Serial No.': 246, 'GRE Score': 328, 'TOEFL Score': 110, 'University Rating': 4, 'SOP': 4.0, 'LOR ': 2.5, 'CGPA': 9.02, 'Research': 1, 'Chance of Admit ': 0.81}
    {'_id': ObjectId('6444ccd095bfe069933271ce'), 'Serial No.': 247, 'GRE Score': 316, 'TOEFL Score': 105, 'University Rating': 3, 'SOP': 3.0, 'LOR ': 3.5, 'CGPA': 8.73, 'Research': 0, 'Chance of Admit ': 0.72}
    {'_id': ObjectId('6444ccd095bfe069933271cf'), 'Serial No.': 248, 'GRE Score': 311, 'TOEFL Score': 104, 'University Rating': 2, 'SOP': 2.5, 'LOR ': 3.5, 'CGPA': 8.48, 'Research': 0, 'Chance of Admit ': 0.71}
    {'_id': ObjectId('6444ccd095bfe069933271d0'), 'Serial No.': 249, 'GRE Score': 324, 'TOEFL Score': 110, 'University Rating': 3, 'SOP': 3.5, 'LOR ': 4.0, 'CGPA': 8.87, 'Research': 1, 'Chance of Admit ': 0.8}
    {'_id': ObjectId('6444ccd095bfe069933271d1'), 'Serial No.': 250, 'GRE Score': 321, 'TOEFL Score': 111, 'University Rating': 3, 'SOP': 3.5, 'LOR ': 4.0, 'CGPA': 8.83, 'Research': 1, 'Chance of Admit ': 0.77}
    {'_id': ObjectId('6444ccd095bfe069933271d2'), 'Serial No.': 251, 'GRE Score': 320, 'TOEFL Score': 104, 'University Rating': 3, 'SOP': 3.0, 'LOR ': 2.5, 'CGPA': 8.57, 'Research': 1, 'Chance of Admit ': 0.74}
    {'_id': ObjectId('6444ccd095bfe069933271d3'), 'Serial No.': 252, 'GRE Score': 316, 'TOEFL Score': 99, 'University Rating': 2, 'SOP': 2.5, 'LOR ': 3.0, 'CGPA': 9.0, 'Research': 0, 'Chance of Admit ': 0.7}
    {'_id': ObjectId('6444ccd095bfe069933271d4'), 'Serial No.': 253, 'GRE Score': 318, 'TOEFL Score': 100, 'University Rating': 2, 'SOP': 2.5, 'LOR ': 3.5, 'CGPA': 8.54, 'Research': 1, 'Chance of Admit ': 0.71}
    {'_id': ObjectId('6444ccd095bfe069933271d5'), 'Serial No.': 254, 'GRE Score': 335, 'TOEFL Score': 115, 'University Rating': 4, 'SOP': 4.5, 'LOR ': 4.5, 'CGPA': 9.68, 'Research': 1, 'Chance of Admit ': 0.93}
    {'_id': ObjectId('6444ccd095bfe069933271d6'), 'Serial No.': 255, 'GRE Score': 321, 'TOEFL Score': 114, 'University Rating': 4, 'SOP': 4.0, 'LOR ': 5.0, 'CGPA': 9.12, 'Research': 0, 'Chance of Admit ': 0.85}
    {'_id': ObjectId('6444ccd095bfe069933271d7'), 'Serial No.': 256, 'GRE Score': 307, 'TOEFL Score': 110, 'University Rating': 4, 'SOP': 4.0, 'LOR ': 4.5, 'CGPA': 8.37, 'Research': 0, 'Chance of Admit ': 0.79}
    {'_id': ObjectId('6444ccd095bfe069933271d8'), 'Serial No.': 257, 'GRE Score': 309, 'TOEFL Score': 99, 'University Rating': 3, 'SOP': 4.0, 'LOR ': 4.0, 'CGPA': 8.56, 'Research': 0, 'Chance of Admit ': 0.76}
    {'_id': ObjectId('6444ccd095bfe069933271d9'), 'Serial No.': 258, 'GRE Score': 324, 'TOEFL Score': 100, 'University Rating': 3, 'SOP': 4.0, 'LOR ': 5.0, 'CGPA': 8.64, 'Research': 1, 'Chance of Admit ': 0.78}
    {'_id': ObjectId('6444ccd095bfe069933271da'), 'Serial No.': 259, 'GRE Score': 326, 'TOEFL Score': 102, 'University Rating': 4, 'SOP': 5.0, 'LOR ': 5.0, 'CGPA': 8.76, 'Research': 1, 'Chance of Admit ': 0.77}
    {'_id': ObjectId('6444ccd095bfe069933271db'), 'Serial No.': 260, 'GRE Score': 331, 'TOEFL Score': 119, 'University Rating': 4, 'SOP': 5.0, 'LOR ': 4.5, 'CGPA': 9.34, 'Research': 1, 'Chance of Admit ': 0.9}
    {'_id': ObjectId('6444ccd095bfe069933271dc'), 'Serial No.': 261, 'GRE Score': 327, 'TOEFL Score': 108, 'University Rating': 5, 'SOP': 5.0, 'LOR ': 3.5, 'CGPA': 9.13, 'Research': 1, 'Chance of Admit ': 0.87}
    {'_id': ObjectId('6444ccd095bfe069933271dd'), 'Serial No.': 262, 'GRE Score': 312, 'TOEFL Score': 104, 'University Rating': 3, 'SOP': 3.5, 'LOR ': 4.0, 'CGPA': 8.09, 'Research': 0, 'Chance of Admit ': 0.71}
    {'_id': ObjectId('6444ccd095bfe069933271de'), 'Serial No.': 263, 'GRE Score': 308, 'TOEFL Score': 103, 'University Rating': 2, 'SOP': 2.5, 'LOR ': 4.0, 'CGPA': 8.36, 'Research': 1, 'Chance of Admit ': 0.7}
    {'_id': ObjectId('6444ccd095bfe069933271df'), 'Serial No.': 264, 'GRE Score': 324, 'TOEFL Score': 111, 'University Rating': 3, 'SOP': 2.5, 'LOR ': 1.5, 'CGPA': 8.79, 'Research': 1, 'Chance of Admit ': 0.7}
    {'_id': ObjectId('6444ccd095bfe069933271e0'), 'Serial No.': 265, 'GRE Score': 325, 'TOEFL Score': 110, 'University Rating': 2, 'SOP': 3.0, 'LOR ': 2.5, 'CGPA': 8.76, 'Research': 1, 'Chance of Admit ': 0.75}
    {'_id': ObjectId('6444ccd095bfe069933271e1'), 'Serial No.': 266, 'GRE Score': 313, 'TOEFL Score': 102, 'University Rating': 3, 'SOP': 2.5, 'LOR ': 2.5, 'CGPA': 8.68, 'Research': 0, 'Chance of Admit ': 0.71}
    {'_id': ObjectId('6444ccd095bfe069933271e2'), 'Serial No.': 267, 'GRE Score': 312, 'TOEFL Score': 105, 'University Rating': 2, 'SOP': 2.0, 'LOR ': 2.5, 'CGPA': 8.45, 'Research': 0, 'Chance of Admit ': 0.72}
    {'_id': ObjectId('6444ccd095bfe069933271e3'), 'Serial No.': 268, 'GRE Score': 314, 'TOEFL Score': 107, 'University Rating': 3, 'SOP': 3.0, 'LOR ': 3.5, 'CGPA': 8.17, 'Research': 1, 'Chance of Admit ': 0.73}
    {'_id': ObjectId('6444ccd095bfe069933271e4'), 'Serial No.': 269, 'GRE Score': 327, 'TOEFL Score': 113, 'University Rating': 4, 'SOP': 4.5, 'LOR ': 5.0, 'CGPA': 9.14, 'Research': 0, 'Chance of Admit ': 0.83}
    {'_id': ObjectId('6444ccd095bfe069933271e5'), 'Serial No.': 270, 'GRE Score': 308, 'TOEFL Score': 108, 'University Rating': 4, 'SOP': 4.5, 'LOR ': 5.0, 'CGPA': 8.34, 'Research': 0, 'Chance of Admit ': 0.77}
    {'_id': ObjectId('6444ccd095bfe069933271e6'), 'Serial No.': 271, 'GRE Score': 306, 'TOEFL Score': 105, 'University Rating': 2, 'SOP': 2.5, 'LOR ': 3.0, 'CGPA': 8.22, 'Research': 1, 'Chance of Admit ': 0.72}
    {'_id': ObjectId('6444ccd095bfe069933271e7'), 'Serial No.': 272, 'GRE Score': 299, 'TOEFL Score': 96, 'University Rating': 2, 'SOP': 1.5, 'LOR ': 2.0, 'CGPA': 7.86, 'Research': 0, 'Chance of Admit ': 0.54}
    {'_id': ObjectId('6444ccd095bfe069933271e8'), 'Serial No.': 273, 'GRE Score': 294, 'TOEFL Score': 95, 'University Rating': 1, 'SOP': 1.5, 'LOR ': 1.5, 'CGPA': 7.64, 'Research': 0, 'Chance of Admit ': 0.49}
    {'_id': ObjectId('6444ccd095bfe069933271e9'), 'Serial No.': 274, 'GRE Score': 312, 'TOEFL Score': 99, 'University Rating': 1, 'SOP': 1.0, 'LOR ': 1.5, 'CGPA': 8.01, 'Research': 1, 'Chance of Admit ': 0.52}
    {'_id': ObjectId('6444ccd095bfe069933271ea'), 'Serial No.': 275, 'GRE Score': 315, 'TOEFL Score': 100, 'University Rating': 1, 'SOP': 2.0, 'LOR ': 2.5, 'CGPA': 7.95, 'Research': 0, 'Chance of Admit ': 0.58}
    {'_id': ObjectId('6444ccd095bfe069933271eb'), 'Serial No.': 276, 'GRE Score': 322, 'TOEFL Score': 110, 'University Rating': 3, 'SOP': 3.5, 'LOR ': 3.0, 'CGPA': 8.96, 'Research': 1, 'Chance of Admit ': 0.78}
    {'_id': ObjectId('6444ccd095bfe069933271ec'), 'Serial No.': 277, 'GRE Score': 329, 'TOEFL Score': 113, 'University Rating': 5, 'SOP': 5.0, 'LOR ': 4.5, 'CGPA': 9.45, 'Research': 1, 'Chance of Admit ': 0.89}
    {'_id': ObjectId('6444ccd095bfe069933271ed'), 'Serial No.': 278, 'GRE Score': 320, 'TOEFL Score': 101, 'University Rating': 2, 'SOP': 2.5, 'LOR ': 3.0, 'CGPA': 8.62, 'Research': 0, 'Chance of Admit ': 0.7}
    {'_id': ObjectId('6444ccd095bfe069933271ee'), 'Serial No.': 279, 'GRE Score': 308, 'TOEFL Score': 103, 'University Rating': 2, 'SOP': 3.0, 'LOR ': 3.5, 'CGPA': 8.49, 'Research': 0, 'Chance of Admit ': 0.66}
    {'_id': ObjectId('6444ccd095bfe069933271ef'), 'Serial No.': 280, 'GRE Score': 304, 'TOEFL Score': 102, 'University Rating': 2, 'SOP': 3.0, 'LOR ': 4.0, 'CGPA': 8.73, 'Research': 0, 'Chance of Admit ': 0.67}
    {'_id': ObjectId('6444ccd095bfe069933271f0'), 'Serial No.': 281, 'GRE Score': 311, 'TOEFL Score': 102, 'University Rating': 3, 'SOP': 4.5, 'LOR ': 4.0, 'CGPA': 8.64, 'Research': 1, 'Chance of Admit ': 0.68}
    {'_id': ObjectId('6444ccd095bfe069933271f1'), 'Serial No.': 282, 'GRE Score': 317, 'TOEFL Score': 110, 'University Rating': 3, 'SOP': 4.0, 'LOR ': 4.5, 'CGPA': 9.11, 'Research': 1, 'Chance of Admit ': 0.8}
    {'_id': ObjectId('6444ccd095bfe069933271f2'), 'Serial No.': 283, 'GRE Score': 312, 'TOEFL Score': 106, 'University Rating': 3, 'SOP': 4.0, 'LOR ': 3.5, 'CGPA': 8.79, 'Research': 1, 'Chance of Admit ': 0.81}
    {'_id': ObjectId('6444ccd095bfe069933271f3'), 'Serial No.': 284, 'GRE Score': 321, 'TOEFL Score': 111, 'University Rating': 3, 'SOP': 2.5, 'LOR ': 3.0, 'CGPA': 8.9, 'Research': 1, 'Chance of Admit ': 0.8}
    {'_id': ObjectId('6444ccd095bfe069933271f4'), 'Serial No.': 285, 'GRE Score': 340, 'TOEFL Score': 112, 'University Rating': 4, 'SOP': 5.0, 'LOR ': 4.5, 'CGPA': 9.66, 'Research': 1, 'Chance of Admit ': 0.94}
    {'_id': ObjectId('6444ccd095bfe069933271f5'), 'Serial No.': 286, 'GRE Score': 331, 'TOEFL Score': 116, 'University Rating': 5, 'SOP': 4.0, 'LOR ': 4.0, 'CGPA': 9.26, 'Research': 1, 'Chance of Admit ': 0.93}
    {'_id': ObjectId('6444ccd095bfe069933271f6'), 'Serial No.': 287, 'GRE Score': 336, 'TOEFL Score': 118, 'University Rating': 5, 'SOP': 4.5, 'LOR ': 4.0, 'CGPA': 9.19, 'Research': 1, 'Chance of Admit ': 0.92}
    {'_id': ObjectId('6444ccd095bfe069933271f7'), 'Serial No.': 288, 'GRE Score': 324, 'TOEFL Score': 114, 'University Rating': 5, 'SOP': 5.0, 'LOR ': 4.5, 'CGPA': 9.08, 'Research': 1, 'Chance of Admit ': 0.89}
    {'_id': ObjectId('6444ccd095bfe069933271f8'), 'Serial No.': 289, 'GRE Score': 314, 'TOEFL Score': 104, 'University Rating': 4, 'SOP': 5.0, 'LOR ': 5.0, 'CGPA': 9.02, 'Research': 0, 'Chance of Admit ': 0.82}
    {'_id': ObjectId('6444ccd095bfe069933271f9'), 'Serial No.': 290, 'GRE Score': 313, 'TOEFL Score': 109, 'University Rating': 3, 'SOP': 4.0, 'LOR ': 3.5, 'CGPA': 9.0, 'Research': 0, 'Chance of Admit ': 0.79}
    {'_id': ObjectId('6444ccd095bfe069933271fa'), 'Serial No.': 291, 'GRE Score': 307, 'TOEFL Score': 105, 'University Rating': 2, 'SOP': 2.5, 'LOR ': 3.0, 'CGPA': 7.65, 'Research': 0, 'Chance of Admit ': 0.58}
    {'_id': ObjectId('6444ccd095bfe069933271fb'), 'Serial No.': 292, 'GRE Score': 300, 'TOEFL Score': 102, 'University Rating': 2, 'SOP': 1.5, 'LOR ': 2.0, 'CGPA': 7.87, 'Research': 0, 'Chance of Admit ': 0.56}
    {'_id': ObjectId('6444ccd095bfe069933271fc'), 'Serial No.': 293, 'GRE Score': 302, 'TOEFL Score': 99, 'University Rating': 2, 'SOP': 1.0, 'LOR ': 2.0, 'CGPA': 7.97, 'Research': 0, 'Chance of Admit ': 0.56}
    {'_id': ObjectId('6444ccd095bfe069933271fd'), 'Serial No.': 294, 'GRE Score': 312, 'TOEFL Score': 98, 'University Rating': 1, 'SOP': 3.5, 'LOR ': 3.0, 'CGPA': 8.18, 'Research': 1, 'Chance of Admit ': 0.64}
    {'_id': ObjectId('6444ccd095bfe069933271fe'), 'Serial No.': 295, 'GRE Score': 316, 'TOEFL Score': 101, 'University Rating': 2, 'SOP': 2.5, 'LOR ': 2.0, 'CGPA': 8.32, 'Research': 1, 'Chance of Admit ': 0.61}
    {'_id': ObjectId('6444ccd095bfe069933271ff'), 'Serial No.': 296, 'GRE Score': 317, 'TOEFL Score': 100, 'University Rating': 2, 'SOP': 3.0, 'LOR ': 2.5, 'CGPA': 8.57, 'Research': 0, 'Chance of Admit ': 0.68}
    {'_id': ObjectId('6444ccd095bfe06993327200'), 'Serial No.': 297, 'GRE Score': 310, 'TOEFL Score': 107, 'University Rating': 3, 'SOP': 3.5, 'LOR ': 3.5, 'CGPA': 8.67, 'Research': 0, 'Chance of Admit ': 0.76}
    {'_id': ObjectId('6444ccd095bfe06993327201'), 'Serial No.': 298, 'GRE Score': 320, 'TOEFL Score': 120, 'University Rating': 3, 'SOP': 4.0, 'LOR ': 4.5, 'CGPA': 9.11, 'Research': 0, 'Chance of Admit ': 0.86}
    {'_id': ObjectId('6444ccd095bfe06993327202'), 'Serial No.': 299, 'GRE Score': 330, 'TOEFL Score': 114, 'University Rating': 3, 'SOP': 4.5, 'LOR ': 4.5, 'CGPA': 9.24, 'Research': 1, 'Chance of Admit ': 0.9}
    {'_id': ObjectId('6444ccd095bfe06993327203'), 'Serial No.': 300, 'GRE Score': 305, 'TOEFL Score': 112, 'University Rating': 3, 'SOP': 3.0, 'LOR ': 3.5, 'CGPA': 8.65, 'Research': 0, 'Chance of Admit ': 0.71}
    {'_id': ObjectId('6444ccd095bfe06993327204'), 'Serial No.': 301, 'GRE Score': 309, 'TOEFL Score': 106, 'University Rating': 2, 'SOP': 2.5, 'LOR ': 2.5, 'CGPA': 8.0, 'Research': 0, 'Chance of Admit ': 0.62}
    {'_id': ObjectId('6444ccd095bfe06993327205'), 'Serial No.': 302, 'GRE Score': 319, 'TOEFL Score': 108, 'University Rating': 2, 'SOP': 2.5, 'LOR ': 3.0, 'CGPA': 8.76, 'Research': 0, 'Chance of Admit ': 0.66}
    {'_id': ObjectId('6444ccd095bfe06993327206'), 'Serial No.': 303, 'GRE Score': 322, 'TOEFL Score': 105, 'University Rating': 2, 'SOP': 3.0, 'LOR ': 3.0, 'CGPA': 8.45, 'Research': 1, 'Chance of Admit ': 0.65}
    {'_id': ObjectId('6444ccd095bfe06993327207'), 'Serial No.': 304, 'GRE Score': 323, 'TOEFL Score': 107, 'University Rating': 3, 'SOP': 3.5, 'LOR ': 3.5, 'CGPA': 8.55, 'Research': 1, 'Chance of Admit ': 0.73}
    {'_id': ObjectId('6444ccd095bfe06993327208'), 'Serial No.': 305, 'GRE Score': 313, 'TOEFL Score': 106, 'University Rating': 2, 'SOP': 2.5, 'LOR ': 2.0, 'CGPA': 8.43, 'Research': 0, 'Chance of Admit ': 0.62}
    {'_id': ObjectId('6444ccd095bfe06993327209'), 'Serial No.': 306, 'GRE Score': 321, 'TOEFL Score': 109, 'University Rating': 3, 'SOP': 3.5, 'LOR ': 3.5, 'CGPA': 8.8, 'Research': 1, 'Chance of Admit ': 0.74}
    {'_id': ObjectId('6444ccd095bfe0699332720a'), 'Serial No.': 307, 'GRE Score': 323, 'TOEFL Score': 110, 'University Rating': 3, 'SOP': 4.0, 'LOR ': 3.5, 'CGPA': 9.1, 'Research': 1, 'Chance of Admit ': 0.79}
    {'_id': ObjectId('6444ccd095bfe0699332720b'), 'Serial No.': 308, 'GRE Score': 325, 'TOEFL Score': 112, 'University Rating': 4, 'SOP': 4.0, 'LOR ': 4.0, 'CGPA': 9.0, 'Research': 1, 'Chance of Admit ': 0.8}
    {'_id': ObjectId('6444ccd095bfe0699332720c'), 'Serial No.': 309, 'GRE Score': 312, 'TOEFL Score': 108, 'University Rating': 3, 'SOP': 3.5, 'LOR ': 3.0, 'CGPA': 8.53, 'Research': 0, 'Chance of Admit ': 0.69}
    {'_id': ObjectId('6444ccd095bfe0699332720d'), 'Serial No.': 310, 'GRE Score': 308, 'TOEFL Score': 110, 'University Rating': 4, 'SOP': 3.5, 'LOR ': 3.0, 'CGPA': 8.6, 'Research': 0, 'Chance of Admit ': 0.7}
    {'_id': ObjectId('6444ccd095bfe0699332720e'), 'Serial No.': 311, 'GRE Score': 320, 'TOEFL Score': 104, 'University Rating': 3, 'SOP': 3.0, 'LOR ': 3.5, 'CGPA': 8.74, 'Research': 1, 'Chance of Admit ': 0.76}
    {'_id': ObjectId('6444ccd095bfe0699332720f'), 'Serial No.': 312, 'GRE Score': 328, 'TOEFL Score': 108, 'University Rating': 4, 'SOP': 4.5, 'LOR ': 4.0, 'CGPA': 9.18, 'Research': 1, 'Chance of Admit ': 0.84}
    {'_id': ObjectId('6444ccd095bfe06993327210'), 'Serial No.': 313, 'GRE Score': 311, 'TOEFL Score': 107, 'University Rating': 4, 'SOP': 4.5, 'LOR ': 4.5, 'CGPA': 9.0, 'Research': 1, 'Chance of Admit ': 0.78}
    {'_id': ObjectId('6444ccd095bfe06993327211'), 'Serial No.': 314, 'GRE Score': 301, 'TOEFL Score': 100, 'University Rating': 3, 'SOP': 3.5, 'LOR ': 3.0, 'CGPA': 8.04, 'Research': 0, 'Chance of Admit ': 0.67}
    {'_id': ObjectId('6444ccd095bfe06993327212'), 'Serial No.': 315, 'GRE Score': 305, 'TOEFL Score': 105, 'University Rating': 2, 'SOP': 3.0, 'LOR ': 4.0, 'CGPA': 8.13, 'Research': 0, 'Chance of Admit ': 0.66}
    {'_id': ObjectId('6444ccd095bfe06993327213'), 'Serial No.': 316, 'GRE Score': 308, 'TOEFL Score': 104, 'University Rating': 2, 'SOP': 2.5, 'LOR ': 3.0, 'CGPA': 8.07, 'Research': 0, 'Chance of Admit ': 0.65}
    {'_id': ObjectId('6444ccd095bfe06993327214'), 'Serial No.': 317, 'GRE Score': 298, 'TOEFL Score': 101, 'University Rating': 2, 'SOP': 1.5, 'LOR ': 2.0, 'CGPA': 7.86, 'Research': 0, 'Chance of Admit ': 0.54}
    {'_id': ObjectId('6444ccd095bfe06993327215'), 'Serial No.': 318, 'GRE Score': 300, 'TOEFL Score': 99, 'University Rating': 1, 'SOP': 1.0, 'LOR ': 2.5, 'CGPA': 8.01, 'Research': 0, 'Chance of Admit ': 0.58}
    {'_id': ObjectId('6444ccd095bfe06993327216'), 'Serial No.': 319, 'GRE Score': 324, 'TOEFL Score': 111, 'University Rating': 3, 'SOP': 2.5, 'LOR ': 2.0, 'CGPA': 8.8, 'Research': 1, 'Chance of Admit ': 0.79}
    {'_id': ObjectId('6444ccd095bfe06993327217'), 'Serial No.': 320, 'GRE Score': 327, 'TOEFL Score': 113, 'University Rating': 4, 'SOP': 3.5, 'LOR ': 3.0, 'CGPA': 8.69, 'Research': 1, 'Chance of Admit ': 0.8}
    {'_id': ObjectId('6444ccd095bfe06993327218'), 'Serial No.': 321, 'GRE Score': 317, 'TOEFL Score': 106, 'University Rating': 3, 'SOP': 4.0, 'LOR ': 3.5, 'CGPA': 8.5, 'Research': 1, 'Chance of Admit ': 0.75}
    {'_id': ObjectId('6444ccd095bfe06993327219'), 'Serial No.': 322, 'GRE Score': 323, 'TOEFL Score': 104, 'University Rating': 3, 'SOP': 4.0, 'LOR ': 4.0, 'CGPA': 8.44, 'Research': 1, 'Chance of Admit ': 0.73}
    {'_id': ObjectId('6444ccd095bfe0699332721a'), 'Serial No.': 323, 'GRE Score': 314, 'TOEFL Score': 107, 'University Rating': 2, 'SOP': 2.5, 'LOR ': 4.0, 'CGPA': 8.27, 'Research': 0, 'Chance of Admit ': 0.72}
    {'_id': ObjectId('6444ccd095bfe0699332721b'), 'Serial No.': 324, 'GRE Score': 305, 'TOEFL Score': 102, 'University Rating': 2, 'SOP': 2.0, 'LOR ': 2.5, 'CGPA': 8.18, 'Research': 0, 'Chance of Admit ': 0.62}
    {'_id': ObjectId('6444ccd095bfe0699332721c'), 'Serial No.': 325, 'GRE Score': 315, 'TOEFL Score': 104, 'University Rating': 3, 'SOP': 3.0, 'LOR ': 2.5, 'CGPA': 8.33, 'Research': 0, 'Chance of Admit ': 0.67}
    {'_id': ObjectId('6444ccd095bfe0699332721d'), 'Serial No.': 326, 'GRE Score': 326, 'TOEFL Score': 116, 'University Rating': 3, 'SOP': 3.5, 'LOR ': 4.0, 'CGPA': 9.14, 'Research': 1, 'Chance of Admit ': 0.81}
    {'_id': ObjectId('6444ccd095bfe0699332721e'), 'Serial No.': 327, 'GRE Score': 299, 'TOEFL Score': 100, 'University Rating': 3, 'SOP': 2.0, 'LOR ': 2.0, 'CGPA': 8.02, 'Research': 0, 'Chance of Admit ': 0.63}
    {'_id': ObjectId('6444ccd095bfe0699332721f'), 'Serial No.': 328, 'GRE Score': 295, 'TOEFL Score': 101, 'University Rating': 2, 'SOP': 2.5, 'LOR ': 2.0, 'CGPA': 7.86, 'Research': 0, 'Chance of Admit ': 0.69}
    {'_id': ObjectId('6444ccd095bfe06993327220'), 'Serial No.': 329, 'GRE Score': 324, 'TOEFL Score': 112, 'University Rating': 4, 'SOP': 4.0, 'LOR ': 3.5, 'CGPA': 8.77, 'Research': 1, 'Chance of Admit ': 0.8}
    {'_id': ObjectId('6444ccd095bfe06993327221'), 'Serial No.': 330, 'GRE Score': 297, 'TOEFL Score': 96, 'University Rating': 2, 'SOP': 2.5, 'LOR ': 1.5, 'CGPA': 7.89, 'Research': 0, 'Chance of Admit ': 0.43}
    {'_id': ObjectId('6444ccd095bfe06993327222'), 'Serial No.': 331, 'GRE Score': 327, 'TOEFL Score': 113, 'University Rating': 3, 'SOP': 3.5, 'LOR ': 3.0, 'CGPA': 8.66, 'Research': 1, 'Chance of Admit ': 0.8}
    {'_id': ObjectId('6444ccd095bfe06993327223'), 'Serial No.': 332, 'GRE Score': 311, 'TOEFL Score': 105, 'University Rating': 2, 'SOP': 3.0, 'LOR ': 2.0, 'CGPA': 8.12, 'Research': 1, 'Chance of Admit ': 0.73}
    {'_id': ObjectId('6444ccd095bfe06993327224'), 'Serial No.': 333, 'GRE Score': 308, 'TOEFL Score': 106, 'University Rating': 3, 'SOP': 3.5, 'LOR ': 2.5, 'CGPA': 8.21, 'Research': 1, 'Chance of Admit ': 0.75}
    {'_id': ObjectId('6444ccd095bfe06993327225'), 'Serial No.': 334, 'GRE Score': 319, 'TOEFL Score': 108, 'University Rating': 3, 'SOP': 3.0, 'LOR ': 3.5, 'CGPA': 8.54, 'Research': 1, 'Chance of Admit ': 0.71}
    {'_id': ObjectId('6444ccd095bfe06993327226'), 'Serial No.': 335, 'GRE Score': 312, 'TOEFL Score': 107, 'University Rating': 4, 'SOP': 4.5, 'LOR ': 4.0, 'CGPA': 8.65, 'Research': 1, 'Chance of Admit ': 0.73}
    {'_id': ObjectId('6444ccd095bfe06993327227'), 'Serial No.': 336, 'GRE Score': 325, 'TOEFL Score': 111, 'University Rating': 4, 'SOP': 4.0, 'LOR ': 4.5, 'CGPA': 9.11, 'Research': 1, 'Chance of Admit ': 0.83}
    {'_id': ObjectId('6444ccd095bfe06993327228'), 'Serial No.': 337, 'GRE Score': 319, 'TOEFL Score': 110, 'University Rating': 3, 'SOP': 3.0, 'LOR ': 2.5, 'CGPA': 8.79, 'Research': 0, 'Chance of Admit ': 0.72}
    {'_id': ObjectId('6444ccd095bfe06993327229'), 'Serial No.': 338, 'GRE Score': 332, 'TOEFL Score': 118, 'University Rating': 5, 'SOP': 5.0, 'LOR ': 5.0, 'CGPA': 9.47, 'Research': 1, 'Chance of Admit ': 0.94}
    {'_id': ObjectId('6444ccd095bfe0699332722a'), 'Serial No.': 339, 'GRE Score': 323, 'TOEFL Score': 108, 'University Rating': 5, 'SOP': 4.0, 'LOR ': 4.0, 'CGPA': 8.74, 'Research': 1, 'Chance of Admit ': 0.81}
    {'_id': ObjectId('6444ccd095bfe0699332722b'), 'Serial No.': 340, 'GRE Score': 324, 'TOEFL Score': 107, 'University Rating': 5, 'SOP': 3.5, 'LOR ': 4.0, 'CGPA': 8.66, 'Research': 1, 'Chance of Admit ': 0.81}
    {'_id': ObjectId('6444ccd095bfe0699332722c'), 'Serial No.': 341, 'GRE Score': 312, 'TOEFL Score': 107, 'University Rating': 3, 'SOP': 3.0, 'LOR ': 3.0, 'CGPA': 8.46, 'Research': 1, 'Chance of Admit ': 0.75}
    {'_id': ObjectId('6444ccd095bfe0699332722d'), 'Serial No.': 342, 'GRE Score': 326, 'TOEFL Score': 110, 'University Rating': 3, 'SOP': 3.5, 'LOR ': 3.5, 'CGPA': 8.76, 'Research': 1, 'Chance of Admit ': 0.79}
    {'_id': ObjectId('6444ccd095bfe0699332722e'), 'Serial No.': 343, 'GRE Score': 308, 'TOEFL Score': 106, 'University Rating': 3, 'SOP': 3.0, 'LOR ': 3.0, 'CGPA': 8.24, 'Research': 0, 'Chance of Admit ': 0.58}
    {'_id': ObjectId('6444ccd095bfe0699332722f'), 'Serial No.': 344, 'GRE Score': 305, 'TOEFL Score': 103, 'University Rating': 2, 'SOP': 2.5, 'LOR ': 3.5, 'CGPA': 8.13, 'Research': 0, 'Chance of Admit ': 0.59}
    {'_id': ObjectId('6444ccd095bfe06993327230'), 'Serial No.': 345, 'GRE Score': 295, 'TOEFL Score': 96, 'University Rating': 2, 'SOP': 1.5, 'LOR ': 2.0, 'CGPA': 7.34, 'Research': 0, 'Chance of Admit ': 0.47}
    {'_id': ObjectId('6444ccd095bfe06993327231'), 'Serial No.': 346, 'GRE Score': 316, 'TOEFL Score': 98, 'University Rating': 1, 'SOP': 1.5, 'LOR ': 2.0, 'CGPA': 7.43, 'Research': 0, 'Chance of Admit ': 0.49}
    {'_id': ObjectId('6444ccd095bfe06993327232'), 'Serial No.': 347, 'GRE Score': 304, 'TOEFL Score': 97, 'University Rating': 2, 'SOP': 1.5, 'LOR ': 2.0, 'CGPA': 7.64, 'Research': 0, 'Chance of Admit ': 0.47}
    {'_id': ObjectId('6444ccd095bfe06993327233'), 'Serial No.': 348, 'GRE Score': 299, 'TOEFL Score': 94, 'University Rating': 1, 'SOP': 1.0, 'LOR ': 1.0, 'CGPA': 7.34, 'Research': 0, 'Chance of Admit ': 0.42}
    {'_id': ObjectId('6444ccd095bfe06993327234'), 'Serial No.': 349, 'GRE Score': 302, 'TOEFL Score': 99, 'University Rating': 1, 'SOP': 2.0, 'LOR ': 2.0, 'CGPA': 7.25, 'Research': 0, 'Chance of Admit ': 0.57}
    {'_id': ObjectId('6444ccd095bfe06993327235'), 'Serial No.': 350, 'GRE Score': 313, 'TOEFL Score': 101, 'University Rating': 3, 'SOP': 2.5, 'LOR ': 3.0, 'CGPA': 8.04, 'Research': 0, 'Chance of Admit ': 0.62}
    {'_id': ObjectId('6444ccd095bfe06993327236'), 'Serial No.': 351, 'GRE Score': 318, 'TOEFL Score': 107, 'University Rating': 3, 'SOP': 3.0, 'LOR ': 3.5, 'CGPA': 8.27, 'Research': 1, 'Chance of Admit ': 0.74}
    {'_id': ObjectId('6444ccd095bfe06993327237'), 'Serial No.': 352, 'GRE Score': 325, 'TOEFL Score': 110, 'University Rating': 4, 'SOP': 3.5, 'LOR ': 4.0, 'CGPA': 8.67, 'Research': 1, 'Chance of Admit ': 0.73}
    {'_id': ObjectId('6444ccd095bfe06993327238'), 'Serial No.': 353, 'GRE Score': 303, 'TOEFL Score': 100, 'University Rating': 2, 'SOP': 3.0, 'LOR ': 3.5, 'CGPA': 8.06, 'Research': 1, 'Chance of Admit ': 0.64}
    {'_id': ObjectId('6444ccd095bfe06993327239'), 'Serial No.': 354, 'GRE Score': 300, 'TOEFL Score': 102, 'University Rating': 3, 'SOP': 3.5, 'LOR ': 2.5, 'CGPA': 8.17, 'Research': 0, 'Chance of Admit ': 0.63}
    {'_id': ObjectId('6444ccd095bfe0699332723a'), 'Serial No.': 355, 'GRE Score': 297, 'TOEFL Score': 98, 'University Rating': 2, 'SOP': 2.5, 'LOR ': 3.0, 'CGPA': 7.67, 'Research': 0, 'Chance of Admit ': 0.59}
    {'_id': ObjectId('6444ccd095bfe0699332723b'), 'Serial No.': 356, 'GRE Score': 317, 'TOEFL Score': 106, 'University Rating': 2, 'SOP': 2.0, 'LOR ': 3.5, 'CGPA': 8.12, 'Research': 0, 'Chance of Admit ': 0.73}
    {'_id': ObjectId('6444ccd095bfe0699332723c'), 'Serial No.': 357, 'GRE Score': 327, 'TOEFL Score': 109, 'University Rating': 3, 'SOP': 3.5, 'LOR ': 4.0, 'CGPA': 8.77, 'Research': 1, 'Chance of Admit ': 0.79}
    {'_id': ObjectId('6444ccd095bfe0699332723d'), 'Serial No.': 358, 'GRE Score': 301, 'TOEFL Score': 104, 'University Rating': 2, 'SOP': 3.5, 'LOR ': 3.5, 'CGPA': 7.89, 'Research': 1, 'Chance of Admit ': 0.68}
    {'_id': ObjectId('6444ccd095bfe0699332723e'), 'Serial No.': 359, 'GRE Score': 314, 'TOEFL Score': 105, 'University Rating': 2, 'SOP': 2.5, 'LOR ': 2.0, 'CGPA': 7.64, 'Research': 0, 'Chance of Admit ': 0.7}
    {'_id': ObjectId('6444ccd095bfe0699332723f'), 'Serial No.': 360, 'GRE Score': 321, 'TOEFL Score': 107, 'University Rating': 2, 'SOP': 2.0, 'LOR ': 1.5, 'CGPA': 8.44, 'Research': 0, 'Chance of Admit ': 0.81}
    {'_id': ObjectId('6444ccd095bfe06993327240'), 'Serial No.': 361, 'GRE Score': 322, 'TOEFL Score': 110, 'University Rating': 3, 'SOP': 4.0, 'LOR ': 5.0, 'CGPA': 8.64, 'Research': 1, 'Chance of Admit ': 0.85}
    {'_id': ObjectId('6444ccd095bfe06993327241'), 'Serial No.': 362, 'GRE Score': 334, 'TOEFL Score': 116, 'University Rating': 4, 'SOP': 4.0, 'LOR ': 3.5, 'CGPA': 9.54, 'Research': 1, 'Chance of Admit ': 0.93}
    {'_id': ObjectId('6444ccd095bfe06993327242'), 'Serial No.': 363, 'GRE Score': 338, 'TOEFL Score': 115, 'University Rating': 5, 'SOP': 4.5, 'LOR ': 5.0, 'CGPA': 9.23, 'Research': 1, 'Chance of Admit ': 0.91}
    {'_id': ObjectId('6444ccd095bfe06993327243'), 'Serial No.': 364, 'GRE Score': 306, 'TOEFL Score': 103, 'University Rating': 2, 'SOP': 2.5, 'LOR ': 3.0, 'CGPA': 8.36, 'Research': 0, 'Chance of Admit ': 0.69}
    {'_id': ObjectId('6444ccd095bfe06993327244'), 'Serial No.': 365, 'GRE Score': 313, 'TOEFL Score': 102, 'University Rating': 3, 'SOP': 3.5, 'LOR ': 4.0, 'CGPA': 8.9, 'Research': 1, 'Chance of Admit ': 0.77}
    {'_id': ObjectId('6444ccd095bfe06993327245'), 'Serial No.': 366, 'GRE Score': 330, 'TOEFL Score': 114, 'University Rating': 4, 'SOP': 4.5, 'LOR ': 3.0, 'CGPA': 9.17, 'Research': 1, 'Chance of Admit ': 0.86}
    {'_id': ObjectId('6444ccd095bfe06993327246'), 'Serial No.': 367, 'GRE Score': 320, 'TOEFL Score': 104, 'University Rating': 3, 'SOP': 3.5, 'LOR ': 4.5, 'CGPA': 8.34, 'Research': 1, 'Chance of Admit ': 0.74}
    {'_id': ObjectId('6444ccd095bfe06993327247'), 'Serial No.': 368, 'GRE Score': 311, 'TOEFL Score': 98, 'University Rating': 1, 'SOP': 1.0, 'LOR ': 2.5, 'CGPA': 7.46, 'Research': 0, 'Chance of Admit ': 0.57}
    {'_id': ObjectId('6444ccd095bfe06993327248'), 'Serial No.': 369, 'GRE Score': 298, 'TOEFL Score': 92, 'University Rating': 1, 'SOP': 2.0, 'LOR ': 2.0, 'CGPA': 7.88, 'Research': 0, 'Chance of Admit ': 0.51}
    {'_id': ObjectId('6444ccd095bfe06993327249'), 'Serial No.': 370, 'GRE Score': 301, 'TOEFL Score': 98, 'University Rating': 1, 'SOP': 2.0, 'LOR ': 3.0, 'CGPA': 8.03, 'Research': 1, 'Chance of Admit ': 0.67}
    {'_id': ObjectId('6444ccd095bfe0699332724a'), 'Serial No.': 371, 'GRE Score': 310, 'TOEFL Score': 103, 'University Rating': 2, 'SOP': 2.5, 'LOR ': 2.5, 'CGPA': 8.24, 'Research': 0, 'Chance of Admit ': 0.72}
    {'_id': ObjectId('6444ccd095bfe0699332724b'), 'Serial No.': 372, 'GRE Score': 324, 'TOEFL Score': 110, 'University Rating': 3, 'SOP': 3.5, 'LOR ': 3.0, 'CGPA': 9.22, 'Research': 1, 'Chance of Admit ': 0.89}
    {'_id': ObjectId('6444ccd095bfe0699332724c'), 'Serial No.': 373, 'GRE Score': 336, 'TOEFL Score': 119, 'University Rating': 4, 'SOP': 4.5, 'LOR ': 4.0, 'CGPA': 9.62, 'Research': 1, 'Chance of Admit ': 0.95}
    {'_id': ObjectId('6444ccd095bfe0699332724d'), 'Serial No.': 374, 'GRE Score': 321, 'TOEFL Score': 109, 'University Rating': 3, 'SOP': 3.0, 'LOR ': 3.0, 'CGPA': 8.54, 'Research': 1, 'Chance of Admit ': 0.79}
    {'_id': ObjectId('6444ccd095bfe0699332724e'), 'Serial No.': 375, 'GRE Score': 315, 'TOEFL Score': 105, 'University Rating': 2, 'SOP': 2.0, 'LOR ': 2.5, 'CGPA': 7.65, 'Research': 0, 'Chance of Admit ': 0.39}
    {'_id': ObjectId('6444ccd095bfe0699332724f'), 'Serial No.': 376, 'GRE Score': 304, 'TOEFL Score': 101, 'University Rating': 2, 'SOP': 2.0, 'LOR ': 2.5, 'CGPA': 7.66, 'Research': 0, 'Chance of Admit ': 0.38}
    {'_id': ObjectId('6444ccd095bfe06993327250'), 'Serial No.': 377, 'GRE Score': 297, 'TOEFL Score': 96, 'University Rating': 2, 'SOP': 2.5, 'LOR ': 2.0, 'CGPA': 7.43, 'Research': 0, 'Chance of Admit ': 0.34}
    {'_id': ObjectId('6444ccd095bfe06993327251'), 'Serial No.': 378, 'GRE Score': 290, 'TOEFL Score': 100, 'University Rating': 1, 'SOP': 1.5, 'LOR ': 2.0, 'CGPA': 7.56, 'Research': 0, 'Chance of Admit ': 0.47}
    {'_id': ObjectId('6444ccd095bfe06993327252'), 'Serial No.': 379, 'GRE Score': 303, 'TOEFL Score': 98, 'University Rating': 1, 'SOP': 2.0, 'LOR ': 2.5, 'CGPA': 7.65, 'Research': 0, 'Chance of Admit ': 0.56}
    {'_id': ObjectId('6444ccd095bfe06993327253'), 'Serial No.': 380, 'GRE Score': 311, 'TOEFL Score': 99, 'University Rating': 1, 'SOP': 2.5, 'LOR ': 3.0, 'CGPA': 8.43, 'Research': 1, 'Chance of Admit ': 0.71}
    {'_id': ObjectId('6444ccd095bfe06993327254'), 'Serial No.': 381, 'GRE Score': 322, 'TOEFL Score': 104, 'University Rating': 3, 'SOP': 3.5, 'LOR ': 4.0, 'CGPA': 8.84, 'Research': 1, 'Chance of Admit ': 0.78}
    {'_id': ObjectId('6444ccd095bfe06993327255'), 'Serial No.': 382, 'GRE Score': 319, 'TOEFL Score': 105, 'University Rating': 3, 'SOP': 3.0, 'LOR ': 3.5, 'CGPA': 8.67, 'Research': 1, 'Chance of Admit ': 0.73}
    {'_id': ObjectId('6444ccd095bfe06993327256'), 'Serial No.': 383, 'GRE Score': 324, 'TOEFL Score': 110, 'University Rating': 4, 'SOP': 4.5, 'LOR ': 4.0, 'CGPA': 9.15, 'Research': 1, 'Chance of Admit ': 0.82}
    {'_id': ObjectId('6444ccd095bfe06993327257'), 'Serial No.': 384, 'GRE Score': 300, 'TOEFL Score': 100, 'University Rating': 3, 'SOP': 3.0, 'LOR ': 3.5, 'CGPA': 8.26, 'Research': 0, 'Chance of Admit ': 0.62}
    {'_id': ObjectId('6444ccd095bfe06993327258'), 'Serial No.': 385, 'GRE Score': 340, 'TOEFL Score': 113, 'University Rating': 4, 'SOP': 5.0, 'LOR ': 5.0, 'CGPA': 9.74, 'Research': 1, 'Chance of Admit ': 0.96}
    {'_id': ObjectId('6444ccd095bfe06993327259'), 'Serial No.': 386, 'GRE Score': 335, 'TOEFL Score': 117, 'University Rating': 5, 'SOP': 5.0, 'LOR ': 5.0, 'CGPA': 9.82, 'Research': 1, 'Chance of Admit ': 0.96}
    {'_id': ObjectId('6444ccd095bfe0699332725a'), 'Serial No.': 387, 'GRE Score': 302, 'TOEFL Score': 101, 'University Rating': 2, 'SOP': 2.5, 'LOR ': 3.5, 'CGPA': 7.96, 'Research': 0, 'Chance of Admit ': 0.46}
    {'_id': ObjectId('6444ccd095bfe0699332725b'), 'Serial No.': 388, 'GRE Score': 307, 'TOEFL Score': 105, 'University Rating': 2, 'SOP': 2.0, 'LOR ': 3.5, 'CGPA': 8.1, 'Research': 0, 'Chance of Admit ': 0.53}
    {'_id': ObjectId('6444ccd095bfe0699332725c'), 'Serial No.': 389, 'GRE Score': 296, 'TOEFL Score': 97, 'University Rating': 2, 'SOP': 1.5, 'LOR ': 2.0, 'CGPA': 7.8, 'Research': 0, 'Chance of Admit ': 0.49}
    {'_id': ObjectId('6444ccd095bfe0699332725d'), 'Serial No.': 390, 'GRE Score': 320, 'TOEFL Score': 108, 'University Rating': 3, 'SOP': 3.5, 'LOR ': 4.0, 'CGPA': 8.44, 'Research': 1, 'Chance of Admit ': 0.76}
    {'_id': ObjectId('6444ccd095bfe0699332725e'), 'Serial No.': 391, 'GRE Score': 314, 'TOEFL Score': 102, 'University Rating': 2, 'SOP': 2.0, 'LOR ': 2.5, 'CGPA': 8.24, 'Research': 0, 'Chance of Admit ': 0.64}
    {'_id': ObjectId('6444ccd095bfe0699332725f'), 'Serial No.': 392, 'GRE Score': 318, 'TOEFL Score': 106, 'University Rating': 3, 'SOP': 2.0, 'LOR ': 3.0, 'CGPA': 8.65, 'Research': 0, 'Chance of Admit ': 0.71}
    {'_id': ObjectId('6444ccd095bfe06993327260'), 'Serial No.': 393, 'GRE Score': 326, 'TOEFL Score': 112, 'University Rating': 4, 'SOP': 4.0, 'LOR ': 3.5, 'CGPA': 9.12, 'Research': 1, 'Chance of Admit ': 0.84}
    {'_id': ObjectId('6444ccd095bfe06993327261'), 'Serial No.': 394, 'GRE Score': 317, 'TOEFL Score': 104, 'University Rating': 2, 'SOP': 3.0, 'LOR ': 3.0, 'CGPA': 8.76, 'Research': 0, 'Chance of Admit ': 0.77}
    {'_id': ObjectId('6444ccd095bfe06993327262'), 'Serial No.': 395, 'GRE Score': 329, 'TOEFL Score': 111, 'University Rating': 4, 'SOP': 4.5, 'LOR ': 4.0, 'CGPA': 9.23, 'Research': 1, 'Chance of Admit ': 0.89}
    {'_id': ObjectId('6444ccd095bfe06993327263'), 'Serial No.': 396, 'GRE Score': 324, 'TOEFL Score': 110, 'University Rating': 3, 'SOP': 3.5, 'LOR ': 3.5, 'CGPA': 9.04, 'Research': 1, 'Chance of Admit ': 0.82}
    {'_id': ObjectId('6444ccd095bfe06993327264'), 'Serial No.': 397, 'GRE Score': 325, 'TOEFL Score': 107, 'University Rating': 3, 'SOP': 3.0, 'LOR ': 3.5, 'CGPA': 9.11, 'Research': 1, 'Chance of Admit ': 0.84}
    {'_id': ObjectId('6444ccd095bfe06993327265'), 'Serial No.': 398, 'GRE Score': 330, 'TOEFL Score': 116, 'University Rating': 4, 'SOP': 5.0, 'LOR ': 4.5, 'CGPA': 9.45, 'Research': 1, 'Chance of Admit ': 0.91}
    {'_id': ObjectId('6444ccd095bfe06993327266'), 'Serial No.': 399, 'GRE Score': 312, 'TOEFL Score': 103, 'University Rating': 3, 'SOP': 3.5, 'LOR ': 4.0, 'CGPA': 8.78, 'Research': 0, 'Chance of Admit ': 0.67}
    {'_id': ObjectId('6444ccd095bfe06993327267'), 'Serial No.': 400, 'GRE Score': 333, 'TOEFL Score': 117, 'University Rating': 4, 'SOP': 5.0, 'LOR ': 4.0, 'CGPA': 9.66, 'Research': 1, 'Chance of Admit ': 0.95}
    {'_id': 5, 'CompanyName': 'Eatclub', 'Faculty': 'XYZ'}
    


```python

```
