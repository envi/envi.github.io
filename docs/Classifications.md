# Classifications 

## Get the list of Classifications 

### Path
GET /odata/Classifications

### Description
Returns a paged list of existing Classifications within the logged-in organization.

!!! note

    You can filter the results as follows:

    - For an exact match, use: ```$filter parameter–entity eq ‘string’```
    - For a partial match, use: ```$filter=contains parameter–contains(entity, ‘string’)```


### Request parameters
<style>
td, th {
   border: none!important;
}
</style>

|  <div style="width:200px">Parameter</div>  |  <div style="width:380px">Explanation</div>  |                      
|-----:|:-------|
|**api-version**: string default: 1.0 <br> *in header*| The requested API version.| 
|**$filter**: string <br> *in query* | Restricts the set of items returned. The maximum number of expressions is 100. | 
|**$orderby**: string <br> *in query* | Specifies the order in which items are returned. The maximum number of expressions is 5. | 
|**$search**: string <br> *in query*  | Picks the value in all possible fields.|
|**$top**: string  <br> *in query* | Returns only the first n results.|
|**$skip**: string <br> *in query*| Skips the first n results.|
|**Authorization**: string default: <br> Bearer access_token <br> *in header* | Specify the type of the token (bearer) and then insert the ```access_token```, which was obtained during authentication.|


### Responses
| <div style="width:200px">Response </div>|<div style="width:420px">Explanation</div>|                      
|-----:|:-------|
|**200 OK**|OK|
|**400 Bad Request**|Incorrect input data or organization ID does not match with the organization ID user is logged in.|      
|**401 Unauthorized**|Incorrect specified ```access_token``` or ```access_token``` got expired.|
|**403 Forbidden**|User doesn’t have appropriate privileges.|
|**500 Internal Server Error**|Server encountered an unexpected condition that prevented it from fulfilling the request.|


### Properties
|<div style="width:200px">Property </div> |<div style="width:420px">Explanation</div>|                      
|-----:|:-------|
|**classificationId**: string *(uuid)* | Unique Identifier of the Сlassification |
|**classificationName**: string | Name of the Сlassification |
|**classificationTypeId**: tiny int| Unique Identifier of the Classification Type |
|**classificationTypeValue**: string | Type Value of the Classification |
|**organizationId**: string *(uuid)* | Unique Identifier of the Organization |
|**organizationNo**: string | Identification Number of the Organization |
|**organizationName**: string | Name of the Organization |
|**activeStatus**: boolean | Is the Classification active or not? |
|**dateCreated**: string <br>*(date-time)* | Date when the Classification was created |
|**createdBy**: string *(uuid)* | Unique Identifier of the user who created the Classification |
|**createdByName**: string | Name of the user who created the Classification |
|**lastUpdated**: string *(date-time)* | Last Date when the Classification was updated |
|**lastUpdatedBy**: string *(uuid)* | Unique Identifier of the last user who updated the Classification |
|**lastUpdatedByName**: string | Name of the last user who updated the Classification |

``` json title="Response Content-types: APPLICATION/JSON, APPLICATION/XML<br>Response example (200 OK)"
{
    "@odata.context": "link",
    "@odata.count": "number",
    "value": [
        {
            "classificationId": "00000000-0000-0000-0000-000000000000",
            "classificationName": "string",
            "classificationTypeId": "tiny int",
            "classificationTypeValue": "string",
            "organizationId": "00000000-0000-0000-0000-000000000000",
            "organizationNo": "string",
            "organizationName": "string",
            "activeStatus": "boolean",
            "dateCreated": "string (date-time)",
            "createdBy": "00000000-0000-0000-0000-000000000000",
            "createdByName": "string",
            "lastUpdated": "string (date-time)",
            "lastUpdatedBy": "00000000-0000-0000-0000-000000000000",
            "lastUpdatedByName": "string"
        }
    ],
    "@odata.nextLink": "link"
}
```

## Create a new Classification

### Path
POST /odata/Classifications

### Description
Creates a new Classification within the logged-in organization.

### Request body
| <div style="width:200px">Parameter</div>|<div style="width:420px">Explanation</div>|                      
|-----:|:-------|
|**classificationName**: string <br> <span style="color: #F05D30">**required**</span> | Name of the Сlassification |
|**classificationTypeId**: tiny int <br> <span style="color: #F05D30">**required**</span> | Unique Identifier of the Classification Type |


``` json title="Request Content-types: APPLICATION/JSON, APPLICATION/XML<br>Request Example"
{
    "classificationName": "string",
    "classificationTypeId": "tiny int"
}
```

### Request parameters
|  <div style="width:200px">Parameter</div>  |  <div style="width:380px">Explanation</div>  |                      
|-----:|:-------|
|**api-version**: string default: 1.0 <br> *in header*| The requested API version.|   
|**Authorization**: string default: <br> Bearer access_token <br> *in header* |Specify the type of the token (bearer) and then insert the ```access_token```, which was obtained during authentication.|

### Responses
| <div style="width:200px">Response </div>|<div style="width:380px">Explanation</div>|                      
|-----:|:-------|
|**200 OK**|OK|   
|**400 Bad Request**| Incorrect input data or organization ID does not match with the organization ID user is logged in.|
|**401 Unauthorized**| Incorrect specified ```access_token``` or ```access_token``` got expired.|
|**403 Forbidden**| User doesn’t have appropriate privileges.|
|**500 Internal Server Error**| Server encountered an unexpected condition that prevented it from fulfilling the request.|

``` json title="Response Content-types: APPLICATION/JSON, APPLICATION/XML<br>Response Example (200 OK)"
"00000000-0000-0000-0000-000000000000"
```


## Get the specified Classification

### Path
GET /odata/Classifications({ClassificationId})

### Description
Returns the details of the Classification specified by ID within the logged-in organization.

### Request parameters
|  <div style="width:200px">Parameter</div>  |  <div style="width:380px">Explanation</div>  |                      
|-----:|:-------|
|**classificationId**: string *(uuid)* <br> <span style="color: #F05D30">**required**</span> <br> *in path* | Enter the ID of the Classification here. |
|**api-version**: string default: 1.0 <br> *in header*| The requested API version. |   
|**Authorization**: string default: <br> Bearer access_token <br> *in header* |Specify the type of the token (bearer) and then insert the ```access_token```, which was obtained during authentication. |

### Responses
| <div style="width:200px">Response </div>|<div style="width:420px">Explanation</div>|                      
|-----:|:-------|
|**200 OK**|OK|      
|**400 Bad Request**| Incorrect input data or organization ID does not match with the organization ID user is logged in.|
|**401 Unauthorized**| Incorrect specified ```access_token``` or ```access_token``` got expired.|
|**403 Forbidden**| User doesn’t have appropriate privileges.|
|**404 Not Found** | Specified ID is absent in the system. |
|**500 Internal Server Error**| Server encountered an unexpected condition that prevented it from fulfilling the request. |

### Properties
|<div style="width:200px">Property </div> |<div style="width:420px">Explanation</div>|                      
|-----:|:-------|
|**classificationId**: string *(uuid)* | Unique Identifier of the Сlassification |
|**classificationName**: string | Name of the Сlassification |
|**classificationTypeId**: tiny int | Unique Identifier of the Classification Type |
|**classificationTypeValue**: string | Type Value of the Classification |
|**organizationId**: string *(uuid)* | Unique Identifier of the Organization |
|**organizationNo**: string | Identification Number of the Organization |
|**organizationName**: string | Name of the Organization |
|**activeStatus**: boolean | Is the Classification active or not? |
|**dateCreated**: string <br>*(date-time)* | Date when the Classification was created |
|**createdBy**: string *(uuid)* | Unique Identifier of the user who created the Classification |
|**createdByName**: string | Name of the user who created the Classification |
|**lastUpdated**: string *(date-time)* | Last Date when the Classification was updated |
|**lastUpdatedBy**: string *(uuid)* | Unique Identifier of the last user who updated the Classification |
|**lastUpdatedByName**: string | Name of the last user who updated the Classification |


``` json title="Response Content-types: APPLICATION/JSON, APPLICATION/XML<br>Response example (200 OK)"
{
    "@odata.context": "link",
    "classificationId": "00000000-0000-0000-0000-000000000000",
    "classificationName": "string",
    "classificationTypeId": "tiny int",
    "classificationTypeValue": "string",
    "organizationId": "00000000-0000-0000-0000-000000000000",
    "organizationNo": "string",
    "organizationName": "string",
    "activeStatus": "boolean",
    "dateCreated": "string (date-time)",
    "createdBy": "00000000-0000-0000-0000-000000000000",
    "createdByName": "string",
    "lastUpdated": "string (date-time)",
    "lastUpdatedBy": "00000000-0000-0000-0000-000000000000",
    "lastUpdatedByName": "string"
}
```

## Partially update the specified Classification

### Path
PATCH /odata/Classifications({сlassificationId})

### Description
Partially updates the details of the Classification specified by ID.

### Request body
| <div style="width:200px">Parameter</div>|<div style="width:420px">Explanation</div>|                      
|-----:|:-------|
|**classificationName**: string | Name of the Сlassification |
|**classificationTypeId**: tiny int | Unique Identifier of the Classification Type |
|**activeStatus**: boolean | Is the Status of the Classification active or not? |

``` json title="Request Content-types: APPLICATION/JSON, APPLICATION/XML<br>Request Example"
{
    "classificationName": "string",
    "classificationTypeId": "tiny int",
    "activeStatus": "boolean"
}
```
### Request parameters
| <div style="width:200px">Parameter</div>|<div style="width:380px">Explanation</div>|                       
|-----:|:-------|
|**classificationId**: string *(uuid)* <br> <span style="color: #F05D30">**required**</span> <br> *in path* | Enter the ID of the Classification here. |
|**api-version**: string default: 1.0 <br> *in header*| The requested API version.|      
|**Authorization**: string default: <br> Bearer access_token <br> *in header* | Specify the type of the token (bearer) and then insert the ```access_token```, which was obtained during authentication.|


### Responses
| <div style="width:200px">Response </div>|<div style="width:380px">Explanation</div>|                      
|-----:|:-------|
|**200 OK**|OK|      
|**400 Bad Request**|Incorrect input data or organization ID does not match with the organization ID user is logged in.|
|**401 Unauthorized**|Incorrect specified ```access_token``` or ```access_token``` got expired.|
|**403 Forbidden**|User doesn’t have appropriate privileges.|
|**404 Not Found** | Specified ID is absent in the system. |
|**500 Internal Server Error**|Server encountered an unexpected condition that prevented it from fulfilling the request.|
