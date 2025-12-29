# Manufacturers

## Get the list of Manufacturers

### Path
GET /odata/Manufacturers

### Description
Returns a paged list of Manufacturers. Contains the link to the next page and information about overall entities count in the database. Supports Query options.

### Request parameters
<style>
td, th {
   border: none!important;
}
</style>
| <div style="width:200px">Parameter</div>|<div style="width:380px">Explanation</div>|                       
|-----:|:-------|
|**api-version**: string default: 1.0 <br> *in header*| The requested API version.| 
|**$search**: string <br> *in query*  | Searches across all supported fields. |        
|**$filter**: string <br> *in query* | Filters results based on a Boolean condition.|
|**$orderby**: string <br> *in query* | Sorts results.|
|**$top**: string  <br> *in query* | Returns only the first n results.|
|**$skip**: string <br> *in query*| Skips the first n results. |
|**Authorization**: string default: <br> Bearer access_token <br> *in header* | Specify the type of the token (bearer) and insert the ```access_token``` obtained during authentication. |

### Responses
| <div style="width:200px">Response </div>|<div style="width:380px">Explanation</div>|                      
|-----:|:-------|
|**200 OK**| OK | 
|**400 Bad Request**| The request contains incorrect input data. |         
|**400 Bad Request** | The limit for the ```$top``` query has been exceeded. The value from the incoming request is 'N' (N is your value from the request). You can find the data on the current limit [here](Options_and_Limitations.md#top-and-skip). |
|**401 Unauthorized**| The specified ```access_token``` is invalid or has expired. |
|**403 Forbidden**| The user doesn’t have the appropriate privileges. |
|**500 Internal Server Error**| The server encountered an unexpected condition that prevented it from fulfilling the request.|

### Properties
| <div style="width:200px">Property </div>|<div style="width:420px">Explanation</div>|                      
|-----:|:-------|
|**organizationId**: string *(uuid)* | Unique Identifier of the Organization |
|**organizationNo**: string | Identification Number of the Organization |
|**organizationName**: string | Name of the Organization |
|**manufacturerId**: string *(uuid)* | Unique Identifier of the Manufacturer |
|**manufacturerNo**: string | Number of the Manufacturer |
|**manufacturerName**: string | Name of the Manufacturer |
|**activeStatus**: boolean | Is the status of the Manufacturer active or not? |
|**dateCreated**: string *(date-time)* | Date when the Manufacturer was added |
|**createdBy**: string *(uuid)* | Unique Identifier of the user who added Manufacturer |
|**createdByName**: string | Name of the user who added Manufacturer |
|**lastUpdated**: string *(date-time)* | Last Date when the Manufacturer was updated |
|**lastUpdatedBy**: string *(uuid)* | Unique Identifier of the last user who updated the Manufacturer |
|**lastUpdatedByName**: string | Name of the last user who updated the Manufacturer |
|**externalMfgNo**: string | External Manufacturer Number |


``` json title="Response Content-types: APPLICATION/JSON, APPLICATION/XML<br>Response Example (200 OK)"
{
    "@odata.context": "link",
    "@odata.count": "number",
    "value": [
        {
            "organizationId": "00000000-0000-0000-0000-000000000000",
            "organizationNo": "string",
            "organizationName": "string",
            "manufacturerId": "00000000-0000-0000-0000-000000000000",
            "manufacturerNo": "string",
            "manufacturerName": "string",
            "activeStatus": "boolean",
            "dateCreated": "string (date-time)",
            "createdBy": "00000000-0000-0000-0000-000000000000",
            "createdByName": "string",
            "lastUpdated": "string (date-time)",
            "lastUpdatedBy": "00000000-0000-0000-0000-000000000000",
            "lastUpdatedByName": "string",
            "externalMfgNo": "string"
        }
    ],
    "@odata.nextLink": "link"
}
```

## Create a new Manufacturer

### Path
POST /odata/Manufacturers

### Description
Creates a new Manufacturer within the logged-in organization.

### Request body
If **Auto ID** is configured for a manufacturer, then ```manufacturerNo``` is optional.

| <div style="width:200px">Parameter</div>|<div style="width:420px">Explanation</div>|                      
|-----:|:-------|
|**manufacturerNo**: string  | Number of the Manufacturer |
|**manufacturerName**: string <br> <span style="color: #F05D30">**required**</span> | Name of the Manufacturer |


If **Auto ID** is not configured for a manufacturer, then ```manufacturerNo``` and ```manufacturerName``` are required.

| <div style="width:200px">Parameter</div>|<div style="width:420px">Explanation</div>|                      
|-----:|:-------|
|**manufacturerNo**: string <br> <span style="color: #F05D30">**required**</span> | Number of the Manufacturer |
|**manufacturerName**: string <br> <span style="color: #F05D30">**required**</span>  | Name of the Manufacturer |

``` json title="Request Content-types: APPLICATION/JSON, APPLICATION/XML<br>Request Example"
{
    "manufacturerNo": "string",
    "manufacturerName": "string",
}
```
!!! note 

    The request with ```externalMfgNo``` could be sent only by System users.


| <div style="width:200px">Parameter</div>|<div style="width:420px">Explanation</div>|                      
|-----:|:-------|
|**manufacturerNo**: string <br> <span style="color: #F05D30">**required**</span> | Number of the Manufacturer |
|**manufacturerName**: string <br> <span style="color: #F05D30">**required**</span>  | Name of the Manufacturer |
|**externalMfgNo**: string | External Manufacturer Number |

### Request parameters
|  <div style="width:200px">Parameter</div>  |  <div style="width:380px">Explanation</div>  |                      
|-----:|:-------|
|**api-version**: string default: 1.0 <br> *in header*| The requested API version.|   
|**Authorization**: string default: <br> Bearer access_token <br> *in header* | Specify the type of the token (bearer) and insert the ```access_token``` obtained during authentication. |

### Responses
| <div style="width:200px">Response </div>|<div style="width:380px">Explanation</div>|                      
|-----:|:-------|
|**200 OK**| OK | 
|**400 Bad Request**| The request contains incorrect input data. |         
|**401 Unauthorized**| The specified ```access_token``` is invalid or has expired. |
|**403 Forbidden**| The user doesn’t have the appropriate privileges. |
|**500 Internal Server Error**| The server encountered an unexpected condition that prevented it from fulfilling the request.|

``` json title="Response Content-types: APPLICATION/JSON, APPLICATION/XML<br>Response Example (200 OK)"
"00000000-0000-0000-0000-000000000000"

```

## Get the specified Manufacturer

### Path
GET /odata/Manufacturers({manufacturerId})

### Description
Returns the details of the Manufacturer specified by ID.

### Request parameters
|  <div style="width:200px">Parameter</div>  |  <div style="width:380px">Explanation</div>  |                      
|-----:|:-------|
|**manufacturerId**: string *(uuid)* <br> <span style="color: #F05D30">**required**</span> <br> *in path* | Enter the ID of the Manufacturer.|
|**api-version**: string default: 1.0 <br> *in header*| The requested API version.|   
|**Authorization**: string default: <br> Bearer access_token <br> *in header* | Specify the type of the token (bearer) and insert the ```access_token``` obtained during authentication. |

### Responses
| <div style="width:200px">Response </div>|<div style="width:380px">Explanation</div>|                      
|-----:|:-------|
|**200 OK**| OK | 
|**400 Bad Request**| The request contains incorrect input data. |         
|**401 Unauthorized**| The specified ```access_token``` is invalid or has expired. |
|**403 Forbidden**| The user doesn’t have the appropriate privileges. |
|**404 Not Found** | The specified ID is absent in the system. |
|**500 Internal Server Error**| The server encountered an unexpected condition that prevented it from fulfilling the request.|

### Properties
| <div style="width:200px">Property </div>|<div style="width:420px">Explanation</div>|                      
|-----:|:-------|
|**organizationId**: string *(uuid)* | Unique Identifier of the Organization |
|**organizationNo**: string | Identification Number of the Organization |
|**organizationName**: string | Name of the Organization |
|**manufacturerId**: string *(uuid)* | Unique Identifier of the Manufacturer |
|**manufacturerNo**: string | Number of the Manufacturer |
|**manufacturerName**: string | Name of the Manufacturer |
|**activeStatus**: boolean | Is the status of the Manufacturer active or not? |
|**dateCreated**: string *(date-time)* | Date when the Manufacturer was added |
|**createdBy**: string *(uuid)* | Unique Identifier of the user who added Manufacturer |
|**createdByName**: string | Name of the user who added Manufacturer |
|**lastUpdated**: string *(date-time)* | Last Date when the Manufacturer was updated |
|**lastUpdatedBy**: string *(uuid)* | Unique Identifier of the last user who updated the Manufacturer |
|**lastUpdatedByName**: string | Name of the last user who updated the Manufacturer |
|**externalMfgNo**: string | External Manufacturer Number |

``` json title="Response Content-types: APPLICATION/JSON, APPLICATION/XML<br>Response Example (200 OK)"
{
    "@odata.context": "link",
    "organizationId": "00000000-0000-0000-0000-000000000000",
    "organizationNo": "string",
    "organizationName": "string",
    "manufacturerId": "00000000-0000-0000-0000-000000000000",
    "manufacturerNo": "string",
    "manufacturerName": "string",
    "activeStatus": "boolean",
    "dateCreated": "string (date-time)",
    "createdBy": "00000000-0000-0000-0000-000000000000",
    "createdByName": "string",
    "lastUpdated": "string (date-time)",
    "lastUpdatedBy": "00000000-0000-0000-0000-000000000000",
    "lastUpdatedByName": "string",
    "externalMfgNo": "string"
}
```
