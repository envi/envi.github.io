# RequisitionFills

## Get the list of Requisition Fills

### Path
GET /odata/RequisitionFills

### Description
Returns a paged list of Requisition Fills within the logged-in organization.

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
|**api-version**: string default: 1.0 <br> *in header*| The requested API version. |
|**$filter**: string <br> *in query* | Restricts the set of items returned. Supports up to 100 expressions. |  
|**$orderby**: string <br> *in query* | Specifies the order in which items are returned. Supports up to 5 expressions. |
|**$search**: string <br> *in query*  | Searches across all supported fields. |
|**$top**: string  <br> *in query* | Returns only the first n results.|
|**$skip**: string <br> *in query*| Skips the first n results.|
|**Authorization**: string default: <br> Bearer access_token <br> *in header* | Specify the type of the token (bearer) and insert the ```access_token``` obtained during authentication. |  

### Responses
| <div style="width:200px">Response </div>|<div style="width:420px">Explanation</div>|                      
|-----:|:-------|
|**200 OK**|OK|      
|**400 Bad Request**| The request contains incorrect input data. |
|**400 Bad Request** | The limit for the ```$top``` query has been exceeded. The value from the incoming request is 'N' (N is your value from the request). You can find the data on the current limit [here](Options_and_Limitations.md#top-and-skip).
|**401 Unauthorized**| The specified ```access_token``` is invalid or has expired. |
|**403 Forbidden**|The user doesn’t have the appropriate privileges.|
|**500 Internal Server Error**| The server encountered an unexpected condition that prevented it from fulfilling the request.|

### Properties
|<div style="width:200px">Property </div> |<div style="width:420px">Explanation</div>|                      
|-----:|:-------|
|**requisitionFillId**: string *(uuid)* | Unique Identifier of the Requisition Fill |
|**requisitionFillNo**: string | Identification code of the Requisition Fill |
|**requisitionId**: string *(uuid)* | Unique Identifier of the Requisition |
|**requisitionNo**: string | Identification code of the Requisition |
|**fillDate**: string *(date-time)* | Date of the Requisition Fill |
|**fillStatus**: string | Status of the Requisition Fill |
|**lastUpdated**: string *(date-time)* | Last Date when the Requisition Fill was updated |
|**lastUpdatedBy**: string *(uuid)* | Unique Identifier of the last user who updated the Requisition Fill |
|**lastUpdatedByName**: string | Name of the last user who updated the Requisition Fill |
|**dateCreated**: string *(date-time)* | Date when the Requisition Fill was created |
|**createdBy**: string *(uuid)* | Unique Identifier of the user who created the Requisition Fill |
|**createdByName**: string | Name of the user who created the Requisition Fill |
|**dateSubmitted**: string *(uuid)* | Date when the Requisition Fill was submitted |
|**submittedBy**: string *(uuid)* | Unique Identifier of the user who submitted the Requisition Fill |
|**submittedByName**: string | Name of the user who submitted the Requisition Fill |

``` json title="Response Content-types: APPLICATION/JSON, APPLICATION/XML<br>Response example (200 OK)"
{
    "@odata.context": "link",
    "@odata.count": "number",
    "value": [
        {
            "requisitionFillId": "00000000-0000-0000-0000-000000000000",
            "requisitionFillNo": "string",
            "requisitionId": "00000000-0000-0000-0000-000000000000",
            "requisitionFillNo": "string",
            "fillDate": "string (date-time)",
            "fillStatus": "string",
            "lastUpdated": "string (date-time)",
            "lastUpdatedBy": "00000000-0000-0000-0000-000000000000",
            "lastUpdatedByName": "string",
            "dateCreated": "string (date-time)",
            "createdBy": "00000000-0000-0000-0000-000000000000",
            "createdByUserName": "string",
            "dateSubmitted": "string (date-time)",
            "submittedBy": "00000000-0000-0000-0000-000000000000",
            "submittedByName": "string"
        }
    ],
    "@odata.nextLink": "link"
}
```


## Get the specified Requisition Fill

### Path
GET /odata/RequisitionFills({requisitionFillId})

### Description
Returns the details of the Requisition Fill specified by ID within the logged-in organization.

### Request parameters
|  <div style="width:200px">Parameter</div>  |  <div style="width:380px">Explanation</div>  |                      
|-----:|:-------|
|**requisitionFillId**: string *(uuid)* <br> <span style="color: #F05D30">**required**</span> <br> *in path* | Enter the ID of the Requisition Fill. |
|**api-version**: string default: 1.0 <br> *in header*| The requested API version. |   
|**Authorization**: string default: <br> Bearer access_token <br> *in header* | Specify the type of the token (bearer) and insert the ```access_token``` obtained during authentication. |

### Responses
| <div style="width:200px">Response </div>|<div style="width:420px">Explanation</div>|                      
|-----:|:-------|
|**200 OK**| OK |      
|**400 Bad Request**| The request contains incorrect input data. |
|**401 Unauthorized**| The specified ```access_token``` is invalid or has expired. |
|**403 Forbidden**| The user doesn’t have the appropriate privileges. |
|**404 Not Found** | The specified ID is absent in the system. |
|**500 Internal Server Error**| The server encountered an unexpected condition that prevented it from fulfilling the request.|

### Properties
|<div style="width:200px">Property </div> |<div style="width:420px">Explanation</div>|                      
|-----:|:-------|
|**requisitionFillId**: string *(uuid)* | Unique Identifier of the Requisition Fill |
|**requisitionFillNo**: string | Identification code of the Requisition Fill |
|**requisitionId**: string *(uuid)* | Unique Identifier of the Requisition |
|**requisitionNo**: string | Identification code of the Requisition |
|**fillDate**: string *(date-time)* | Date of the Requisition Fill |
|**fillStatus**: string | Status of the Requisition Fill |
|**lastUpdated**: string *(date-time)* | Last Date when the Requisition Fill was updated |
|**lastUpdatedBy**: string *(uuid)* | Unique Identifier of the last user who updated the Requisition Fill |
|**lastUpdatedByName**: string | Name of the last user who updated the Requisition Fill |
|**dateCreated**: string *(date-time)* | Date when the Requisition Fill was created |
|**createdBy**: string *(uuid)* | Unique Identifier of the user who created the Requisition Fill |
|**createdByName**: string | Name of the user who created the Requisition Fill |
|**dateSubmitted**: string *(uuid)* | Date when the Requisition Fill was submitted |
|**submittedBy**: string *(uuid)* | Unique Identifier of the user who submitted the Requisition Fill |
|**submittedByName**: string | Name of the user who submitted the Requisition Fill |

``` json title="Response Content-types: APPLICATION/JSON, APPLICATION/XML<br>Response example (200 OK)"
{
    "@odata.context": "link",
    "requisitionFillId": "00000000-0000-0000-0000-000000000000",
    "requisitionFillNo": "string",
    "requisitionId": "00000000-0000-0000-0000-000000000000",
    "requisitionFillNo": "string",
    "fillDate": "string (date-time)",
    "fillStatus": "string",
    "lastUpdated": "string (date-time)",
    "lastUpdatedBy": "00000000-0000-0000-0000-000000000000",
    "lastUpdatedByName": "string",
    "dateCreated": "string (date-time)",
    "createdBy": "00000000-0000-0000-0000-000000000000",
    "createdByUserName": "string",
    "dateSubmitted": "string (date-time)",
    "submittedBy": "00000000-0000-0000-0000-000000000000",
    "submittedByName": "string"
}
```
