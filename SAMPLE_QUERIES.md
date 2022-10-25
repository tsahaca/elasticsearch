# Sample Queries

* OR is spelled should
* AND is spelled must
* NOR is spelled should_not
* GET /INDEX_NAME/_count


```
GET /INDEX_NAME/_search
 {
   "query": {
     "bool": {
       "must": [
         { "match": { "ID_ONE": 1 } }
       ]
     }
   }
 }

GET /INDEX_NAME/_search
 {
   "query": {
     "bool": {
       "must": [
         { "match": { "ID_ONE": 1228373 } }
       ]
     }
   }
 }
 
 GET /INDEX_NAME/_search
 {
   "query": {
     "bool": {
       "should": [
         { "match": { "ID_ONE": 1228373 } },
         { "match": { "ID_ONE": 675857 } }
       ]
     }
   }
 }

GET /INDEX_NAME/_search
 {
   "query": {
     "bool": {
       "must": [
         { "match": { "ID_TWO": "1307956R3" } }
       ]
     }
   }
 }

GET /INDEX_NAME/_search
 {
   "query": {
     "bool": {
       "must": [
         { "match": { "ID_ONE": 1557539 } }
       ]
     }
   },
   "_source": [
    "ID_TWO",
    "BB*",   
    "ID_ONE"
   ]
 }

GET /INDEX_NAME_TWO/_search
 
 GET /INDEX_NAME_TWO/_count?q=*

GET /INDEX_NAME_TWO/_search
{
   "query": {
     "bool": {
       "must": [
         { "match": { "pfId": 7617 } }

       ]
     }
   }
}

GET /INDEX_NAME_TWO/_search
{
   "query": {
     "nested": {
       "path": "buckets",
       "query": {
         "bool": {
           "must": [
             { "match": { "buckets.amountUsd": 3294080.93 } }
           ]
       }
       }
     }
   }
}

GET /INDEX_NAME_TWO/_search
{
   "query": {
     "nested": {
       "path": "buckets",
       "query": {
         "bool": {
           "must": [
             { "match": { "buckets.amountUsd": 2094029.79 } }
           ]
       }
       }
     }
   }
}

POST INDEX_NAME_TWO/_delete_by_query?conflicts=proceed
{
 "query": {
 "match_all": {}
 }
}
 
```
