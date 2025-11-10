# Departments

## Get the list of Departments

### Path
GET /odata/Departments

### Description
Returns a paged list of existing Departments within the logged-in organization.

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
|**401 Unauthorized**| The specified ```access_token``` is incorrect, or the ```access_token``` has expired. |
|**403 Forbidden**| The user doesn’t have the appropriate privileges. |
|**500 Internal Server Error**| The server encountered an unexpected condition that prevented it from fulfilling the request.|

### Properties
|<div style="width:200px">Property </div> |<div style="width:380px">Explanation</div>|                      
|-----:|:-------|
|**departmentId**: string *(uuid)* | Unique Identifier of the Department |
|**departmentNo**: string | Identification Number of the Department |
|**departmentName**: string | Name of the Department |
|**organizationId**: string *(uuid)* | Unique Identifier of the Organization |
|**organizationNo**: string | Identification Number of the Organization |
|**organizationName**: string | Name of the Organization |
|**facilityId**: string *(uuid)* | Unique Identifier of the Facility |
|**facilityName**: string | Name of the Facility |
|**facilityNo**: string | Identification Number of the Facility |
|**glCode**: string | General Ledger Code of the Department |
|**address1**: string | The first Address of the Department for shipping or billing purposes |
|**address2**: string | The second Address of the Department for shipping or billing purposes |
|**city**: string | City |
|**state**: string | State |
|**zip**: string | Zip |
|**contactName**: string | Name of the main contact point |
|**contactPhone**: string | Phone of the main contact point |
|**сontactPhoneExt**: string | Phone Extension of the main contact point|
|**contactFax**: string | Fax of the main contact point |
|**contactEmail**: string | Email of the main contact point |
|**notes**: string | Comments about the Department |
|**activeStatus**: boolean | Is the Department active or not? |
|**reportCompanyNo**: string | Identification Number of the company report |
|**createdBy**: string *(uuid)* | Unique Identifier of the user who created the Department |
|**createdByName**: string | First and Last Name of the user who created the Department |
|**dateCreated**: string <br>*(date-time)* | Date when the Department was created |
|**lastUpdatedBy**: string *(uuid)* | Unique Identifier of the last user who updated the Department |
|**lastUpdatedByName**: string | First and Last Name of the last user who updated the Department |
|**lastUpdated**: string *(date-time)* | Last Date when the Department was updated |


``` json title="Response Content-types: APPLICATION/JSON, APPLICATION/XML<br>Response Example (200 OK)"
{
    "@odata.context": "link",
    "@odata.count": "number",
    "value": [
        {
            "departmentId": "00000000-0000-0000-0000-000000000000",
            "departmentNo": "string",
            "departmentName": "string",
            "organizationId": "00000000-0000-0000-0000-000000000000",
            "organizationNo": "string",
            "organizationName": "string",
            "facilityId": "00000000-0000-0000-0000-000000000000",
            "facilityName": "string",
            "facilityNo": "string",
            "glCode": "string",
            "address1": "string",
            "address2": "string",
            "city": "string",
            "state": "string",
            "zip": "string",
            "contactName": "string",
            "contactPhone": "string",
            "contactPhoneExt": "string",
            "contactFax": "string",
            "contactEmail": "string",
            "notes": "string",
            "activeStatus": "boolean",
            "reportCompanyNo": "string",
            "createdBy": "00000000-0000-0000-0000-000000000000",
            "createdByName": "string",
            "dateCreated": "string (date-time)",
            "lastUpdatedBy": "00000000-0000-0000-0000-000000000000",
            "lastUpdatedByName’": "string",
            "lastUpdated": "string (date-time)"
        }
    ],
    "@odata.nextLink": "link"
}
```

## Get the specified Department

### Path
GET /odata/Departments({DepartmentID})

### Description
Returns the details of the Department specified by ID within the logged-in organization.

### Request parameters
|  <div style="width:200px">Parameter</div>  |  <div style="width:380px">Explanation</div>|                      
|-----:|:-------|
|**departmentId**: string *(uuid)* <br> <span style="color: #F05D30">**required**</span> <br> *in path* | Enter the ID of the Department. |
|**api-version**: string default: 1.0 <br> *in header*| The requested API version. |   
|**Authorization**: string default: <br> Bearer access_token <br> *in header* | Specify the type of the token (bearer) and insert the ```access_token``` obtained during authentication. |

### Responses
| <div style="width:200px">Response </div>|<div style="width:380px">Explanation</div>|                      
|-----:|:-------|
|**200 OK**| OK |
|**400 Bad Request**| The request contains incorrect input data. |            
|**401 Unauthorized**| The specified ```access_token``` is incorrect, or the ```access_token``` has expired. |
|**403 Forbidden**| The user doesn’t have the appropriate privileges. |
|**404 Not Found** | The specified ID is absent in the system. |
|**500 Internal Server Error**| The server encountered an unexpected condition that prevented it from fulfilling the request.|

### Properties
|<div style="width:200px">Property </div> |<div style="width:380px">Explanation</div>|                      
|-----:|:-------|
|**departmentId**: string *(uuid)* | Unique Identifier of the Department |
|**departmentNo**: string | Identification Number of the Department |
|**departmentName**: string | Name of the Department |
|**organizationId**: string *(uuid)* | Unique Identifier of the Organization |
|**organizationNo**: string | Identification Number of the Organization |
|**organizationName**: string | Name of the Organization |
|**facilityId**: string *(uuid)* | Unique Identifier of the Facility |
|**facilityName**: string | Name of the Facility |
|**facilityNo**: string | Identification Number of the Facility |
|**glCode**: string | General Ledger Code of the Department |
|**address1**: string | The first Address of the Department for shipping or billing purposes |
|**address2**: string | The second Address of the Department for shipping or billing purposes |
|**city**: string | City |
|**state**: string | State |
|**zip**: string | Zip |
|**contactName**: string | Name of the main contact point |
|**contactPhone**: string | Phone of the main contact point |
|**сontactPhoneExt**: string | Phone Extension of the main contact point|
|**contactFax**: string | Fax of the main contact point |
|**contactEmail**: string | Email of the main contact point |
|**notes**: string | Comments about the Department |
|**activeStatus**: boolean | Is the Department active or not? |
|**reportCompanyNo**: string | Identification Number of the company report |
|**createdBy**: string *(uuid)* | Unique Identifier of the user who created the Department |
|**createdByName**: string | First and Last Name of the user who created the Department |
|**dateCreated**: string <br>*(date-time)* | Date when the Department was created |
|**lastUpdatedBy**: string *(uuid)* | Unique Identifier of the last user who updated the Department |
|**lastUpdatedByName**: string | First and Last Name of the last user who updated the Department |
|**lastUpdated**: string *(date-time)* | Last Date when the Department was updated |

``` json title="Response Content-types: APPLICATION/JSON, APPLICATION/XML <br> Response Example (200 OK)"
{
    "@odata.context": "link",
    "departmentId": "00000000-0000-0000-0000-000000000000",
    "departmentNo": "string",
    "departmentName": "string",
    "organizationId": "00000000-0000-0000-0000-000000000000",
    "organizationNo": "string",
    "organizationName": "string",
    "facilityId": "00000000-0000-0000-0000-000000000000",
    "facilityName": "string",
    "facilityNo": "string",
    "glCode": "string",
    "address1": "string",
    "address2": "string",
    "city": "string",
    "state": "string",
    "zip": "string",
    "contactName": "string",
    "contactPhone": "string",
    "contactPhoneExt": "string",
    "contactFax": "string",
    "contactEmail": "string",
    "notes": "string",
    "activeStatus": "boolean",
    "reportCompanyNo": "string",
    "createdBy": "00000000-0000-0000-0000-000000000000",
    "createdByName": "string",
    "dateCreated": "string (date-time)",
    "lastUpdatedBy": "00000000-0000-0000-0000-000000000000",
    "lastUpdatedByName’": "string",
    "lastUpdated": "string (date-time)"
}
```