# Departments

## Get the list of Departments

### Path
GET /odata/Departments

### Description
Returns a paged list of existing Departments within the logged-in organization.

!!! note

    You can filter the results as follows:

    - For an exact match, use: ```$filter=entity eq 'string'```
    - For a partial match, use: ```$filter=contains(entity, 'string')```

### Request parameters
<style>
td, th {
   border: none!important;
}
</style>

| Parameter | Explanation |                      
|-----:|:-------|
|**api-version**: string default: 1.0 <br> *in header*| The requested API version. |   
|**$search**: string <br> *in query*  | Searches across all supported fields. |   
|**$filter**: string <br> *in query* | Filters results based on a Boolean condition. |  
|**$orderby**: string <br> *in query* | Sorts results. |
|**$top**: string  <br> *in query* | Returns only the first n results. |
|**$skip**: string <br> *in query*| Skips the first n results. |
|**Authorization**: string default: <br> Bearer access_token <br> *in header* | Specify the type of the token (bearer) and insert the ```access_token``` obtained during authentication. |

### Responses
| Response | Explanation |                      
|-----:|:-------|
|**200 OK**| OK | 
|**400 Bad Request**| The request contains incorrect input data. |         
|**400 Bad Request** | The limit for the ```$top``` query has been exceeded. The value from the incoming request is 'N' (N is your value from the request). You can find the data on the current limit [here](Options_and_Limitations.md#top-and-skip). |
|**401 Unauthorized**| The specified ```access_token``` is invalid or has expired. |
|**403 Forbidden**| The user doesn’t have the appropriate privileges. |
|**500 Internal Server Error**| The server encountered an unexpected condition that prevented it from fulfilling the request.|

### Properties
| Property | Explanation |                      
|-----:|:-------|
|**departmentId**: string *(uuid)* | Unique identifier of the Department |
|**departmentNo**: string | Identification number of the Department |
|**departmentName**: string | Name of the Department |
|**organizationId**: string *(uuid)* | Unique identifier of the Organization |
|**organizationNo**: string | Identification number of the Organization |
|**organizationName**: string | Name of the Organization |
|**facilityId**: string *(uuid)* | Unique identifier of the Facility |
|**facilityName**: string | Name of the Facility |
|**facilityNo**: string | Identification number of the Facility |
|**glCode**: string | General Ledger code of the Department |
|**address1**: string | Primary address of the Department for shipping or billing purposes |
|**address2**: string | Secondary address of the Department for shipping or billing purposes |
|**city**: string | City of the Department address |
|**state**: string | State of the Department address |
|**zip**: string | Zip code of the Department address |
|**contactName**: string | Name of the main contact |
|**contactPhone**: string | Phone number of the main contact |
|**contactPhoneExt**: string | Phone extension of the main contact |
|**contactFax**: string | Fax number of the main contact |
|**contactEmail**: string | Email address of the main contact |
|**notes**: string | Notes about the Department |
|**activeStatus**: boolean | Is the Department active or not? |
|**reportCompanyNo**: string | Identification number of the company report |
|**createdBy**: string *(uuid)* | Unique identifier of the user who created the Department |
|**createdByName**: string | Name of the user who created the Department |
|**dateCreated**: string <br>*(date-time)* | Date when the Department was created |
|**lastUpdatedBy**: string *(uuid)* | Unique identifier of the user who last updated the Department |
|**lastUpdatedByName**: string | Name of the user who last updated the Department |
|**lastUpdated**: string *(date-time)* | Date when the Department was last updated |

``` json title="Response example (200 OK)"
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
            "lastUpdatedByName": "string",
            "lastUpdated": "string (date-time)"
        }
    ],
    "@odata.nextLink": "link"
}
```

## Get the specified Department

### Path
GET /odata/Departments({departmentId})

### Description
Returns the details of the Department specified by ID within the logged-in organization.

### Request parameters
| Parameter | Explanation |                      
|-----:|:-------|
|**departmentId**: string *(uuid)* <br> <span style="color: #F05D30">**required**</span> <br> *in path* | Enter the ID of the Department. |
|**api-version**: string default: 1.0 <br> *in header*| The requested API version. |   
|**Authorization**: string default: <br> Bearer access_token <br> *in header* | Specify the type of the token (bearer) and insert the ```access_token``` obtained during authentication. |

### Responses
| Response | Explanation |                      
|-----:|:-------|
|**200 OK**| OK |
|**400 Bad Request**| The request contains incorrect input data. |            
|**401 Unauthorized**| The specified ```access_token``` is invalid or has expired. |
|**403 Forbidden**| The user doesn’t have the appropriate privileges. |
|**404 Not Found** | The specified ID is absent in the system. |
|**500 Internal Server Error**| The server encountered an unexpected condition that prevented it from fulfilling the request. |

### Properties
| Property | Explanation |                      
|-----:|:-------|
|**departmentId**: string *(uuid)* | Unique identifier of the Department |
|**departmentNo**: string | Identification number of the Department |
|**departmentName**: string | Name of the Department |
|**organizationId**: string *(uuid)* | Unique identifier of the Organization |
|**organizationNo**: string | Identification number of the Organization |
|**organizationName**: string | Name of the Organization |
|**facilityId**: string *(uuid)* | Unique identifier of the Facility |
|**facilityName**: string | Name of the Facility |
|**facilityNo**: string | Identification number of the Facility |
|**glCode**: string | General Ledger code of the Department |
|**address1**: string | Primary address of the Department for shipping or billing purposes |
|**address2**: string | Secondary address of the Department for shipping or billing purposes |
|**city**: string | City of the Department address |
|**state**: string | State of the Department address |
|**zip**: string | Zip code of the Department address |
|**contactName**: string | Name of the main contact |
|**contactPhone**: string | Phone number of the main contact |
|**contactPhoneExt**: string | Phone extension of the main contact |
|**contactFax**: string | Fax number of the main contact |
|**contactEmail**: string | Email address of the main contact |
|**notes**: string | Notes about the Department |
|**activeStatus**: boolean | Is the Department active or not? |
|**reportCompanyNo**: string | Identification number of the company report |
|**createdBy**: string *(uuid)* | Unique identifier of the user who created the Department |
|**createdByName**: string | Name of the user who created the Department |
|**dateCreated**: string <br>*(date-time)* | Date when the Department was created |
|**lastUpdatedBy**: string *(uuid)* | Unique identifier of the user who last updated the Department |
|**lastUpdatedByName**: string | Name of the user who last updated the Department |
|**lastUpdated**: string *(date-time)* | Date when the Department was last updated |

``` json title="Response example (200 OK)"
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
    "lastUpdatedByName": "string",
    "lastUpdated": "string (date-time)"
}
``` 