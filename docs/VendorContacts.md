# VendorContacts

## Get the list of Vendor Contacts

### Path
GET /odata/VendorContacts

### Description
Returns a paged list of Vendor Contacts within the logged-in organization. 

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
|**includeInactiveVendors** <br> boolean default: false <br> *in query* | Include inactive Vendors. |
|**includeInactiveFacilities** <br> boolean default: false <br> *in query* | Include inactive Facilities. |
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
|**400 Bad Request** | The limit for the ```$top``` query has been exceeded. The value from the incoming request is 'N' (N is your value from the request). You can find the data on the current limit [here](Options_and_Limitations.md#top-and-skip).
|**401 Unauthorized**|Incorrect specified ```access_token``` or ```access_token``` got expired.|
|**403 Forbidden**|User doesn’t have appropriate privileges.|
|**500 Internal Server Error**|Server encountered an unexpected condition that prevented it from fulfilling the request.|


### Properties
|<div style="width:200px">Property </div> |<div style="width:420px">Explanation</div>|                      
|-----:|:-------|
|**vendorContactId**: string *(uuid)* | Unique Identifier of the Vendor Contact |
|**contactName**: string | Name of the main contact point |
|**vendorId**: string *(uuid)* | Unique Identifier of the Vendor |
|**vendorNo**: string | Code of the Supplier who sells products |
|**vendorName**: string | Name of the Vendor |
|**facilityId**: string *(uuid)* | Unique Identifier of the Facility |
|**facilityNo**: string | Identification Number of the Facility |
|**facilityName**: string | Name of the Facility |
|**title**: string | Title |
|**emailAddress**: string | Email Address of the main contact point |
|**phone**: string | Phone of the main contact point |
|**phoneExt**: string | Phone Extension of the main contact point |
|**fax**: string | Fax of the main contact point |
|**isDefault**: boolean | Is the Vendor Contact default or not? |
|**dateAdded**: string *(date-time)* | Date when the Vendor Contract was added |
|**addedBy**: string *(uuid)* | Unique Identifier of the user who added the Vendor Contact |
|**addedByName**: string | Name of the user who added the Vendor Contact |
|**lastUpdated**: string *(date-time)* | Last Date when the Vendor Contract was updated |
|**lastUpdatedBy**: string *(uuid)* | Unique Identifier of the last user who updated the Vendor Contract |
|**lastUpdatedByName**: string | Name of the last user who updated the Vendor Contract |
|**activeStatus**: boolean | Is the Status of the Vendor Contact active or not? |

``` json title="Response Content-types: APPLICATION/JSON, APPLICATION/XML<br>Response example (200 OK)"
{
    "@odata.context": "link",
    "@odata.count": "number",
    "value": [
        {
            "vendorContactId": "00000000-0000-0000-0000-000000000000",
            "contactName": "string",
            "vendorId": "00000000-0000-0000-0000-000000000000",
            "vendorNo": "string",
            "vendorName": "string",
            "facilityId": "00000000-0000-0000-0000-000000000000",
            "facilityNo": "string",
            "facilityName": "string",
            "title": "string",
            "emailAddress": "string",
            "phone": "string",
            "phoneExt": "string",
            "fax": "string",
            "isDefault": "boolean",
            "dateAdded": "string (date-time)",
            "addedBy": "00000000-0000-0000-0000-000000000000",
            "addeddByName": "string",
            "lastUpdated": "string (date-time)",
            "lastUpdatedBy": "00000000-0000-0000-0000-000000000000",
            "lastUpdatedByName": "string",
            "activeStatus": "boolean"
        }
    ],
    "@odata.nextLink": "link"
}
```



## Create a new Vendor Contact

### Path
POST /odata/Vendors({VendorId})/VendorContacts

### Description
Creates a new Vendor Contact within the logged-in organization and the specified Vendor only for active Vendors and Facilities.

### Request body
|  <div style="width:200px">Parameter</div>  |  <div style="width:420px">Explanation</div>  |                      
|-----:|:-------|
|**contactName**: string <br> <span style="color: #F05D30">**required**</span> | Name of the main contact point |
|**title**: string <br> <span style="color: #F05D30">**required**</span>| Title |
|**emailAddress**: string | Email Address of the main contact point |
|**phone**: string | Phone of the main contact point |
|**phoneExt**: string | Phone Extension of the main contact point |
|**fax**: string | Fax of the main contact point |
|**facilityId**: string *(uuid)* | Unique Identifier of the Facility |
|**isDefault**: boolean | Is the Vendor Contact default or not? <br> If ```isDefault=true```, then other contacts for this particular Facility (including Master) with ```isDefault=true``` should be updated to false.|

``` json title="Request Content-types: APPLICATION/JSON, APPLICATION/XML <br> Request Example"
{
    "contactName": "string",
    "title ": "string",
    "emailAddress ": "string",
    "phone ": "string",
    "phoneExt ": "string",
    "fax": "string",
    "facilityId ": "00000000-0000-0000-0000-000000000000",
    "isDefault ": "boolean"
}
    
```

### Request parameters
|  <div style="width:200px">Parameter</div>  |  <div style="width:380px">Explanation</div>  |                      
|-----:|:-------|
|**vendorId**: string *(uuid)* <br> <span style="color: #F05D30">**required**</span> <br> *in path* | Enter the ID of the Vendor here. |
|**api-version**: string default: 1.0 <br> *in header*|The requested API version.|      
|**Authorization**: string default: <br> Bearer access_token <br> *in header* |Specify the type of the token (bearer) and then insert the ```access_token```, which was obtained during authentication.|

### Responses
| <div style="width:200px">Response </div>|<div style="width:380px">Explanation</div>|                      
|-----:|:-------|
|**200 OK** | OK |    
|**400 Bad Request**|Incorrect input data or organization ID does not match with the organization ID user is logged in.|
|**401 Unauthorized**|Incorrect specified ```access_token``` or ```access_token``` got expired.|
|**403 Forbidden**|User doesn’t have appropriate privileges.|
|**500 Internal Server Error**|Server encountered an unexpected condition that prevented it from fulfilling the request.|

``` json title="Response Content-types: APPLICATION/JSON, APPLICATION/XML<br>Response Example (200 OK)"
"00000000-0000-0000-0000-000000000000"
```

## Get the specified Vendor Contact

### Path
GET /odata/VendorContacts({vendorContactId})

### Description
Returns the details of the Vendor Contact specified by ID within the logged-in organization.

### Request parameters
|  <div style="width:200px">Parameter</div>  |  <div style="width:380px">Explanation</div>  |                      
|-----:|:-------|
|**includeInactiveVendors** <br> boolean default: false <br> *in query* | Include inactive Vendors. |
|**includeInactiveFacilities** <br> boolean default: false <br> *in query* | Include inactive Facilities. |
|**vendorContactId**: string *(uuid)* <br> <span style="color: #F05D30">**required**</span> <br> *in path* | Enter the ID of the Vendor Contact here. |
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
|**vendorContactId**: string *(uuid)* | Unique Identifier of the Vendor Contact |
|**contactName**: string | Name of the main contact point |
|**vendorId**: string *(uuid)* | Unique Identifier of the Vendor |
|**vendorNo**: string | Code of the Supplier who sells products |
|**vendorName**: string | Name of the Vendor |
|**facilityId**: string *(uuid)* | Unique Identifier of the Facility |
|**facilityNo**: string | Identification Number of the Facility |
|**facilityName**: string | Name of the Facility |
|**title**: string | Title |
|**emailAddress**: string | Email Address of the main contact point |
|**phone**: string | Phone of the main contact point |
|**phoneExt**: string | Phone Extension of the main contact point |
|**fax**: string | Fax of the main contact point |
|**isDefault**: boolean | Is the Vendor Contact default or not? |
|**dateAdded**: string *(date-time)* | Date when the Vendor Contract was added |
|**addedBy**: string *(uuid)* | Unique Identifier of the user who added the Vendor Contact |
|**addedByName**: string | Name of the user who added the Vendor Contact |
|**lastUpdated**: string *(date-time)* | Last Date when the Vendor Contract was updated |
|**lastUpdatedBy**: string *(uuid)* | Unique Identifier of the last user who updated the Vendor Contract |
|**lastUpdatedByName**: string | Name of the last user who updated the Vendor Contract |
|**activeStatus**: boolean | Is the Status of the Vendor Contact active or not? |


``` json title="Response Content-types: APPLICATION/JSON, APPLICATION/XML<br>Response example (200 OK)"
{
    "@odata.context": "link",
    "vendorContactId": "00000000-0000-0000-0000-000000000000",
    "contactName": "string",
    "vendorId": "00000000-0000-0000-0000-000000000000",
    "vendorNo": "string",
    "vendorName": "string",
    "facilityId": "00000000-0000-0000-0000-000000000000",
    "facilityNo": "string",
    "facilityName": "string",
    "title": "string",
    "emailAddress": "string",
    "phone": "string",
    "phoneExt": "string",
    "fax": "string",
    "isDefault": "boolean",
    "dateAdded": "string (date-time)",
    "addedBy": "00000000-0000-0000-0000-000000000000",
    "addeddByName": "string",
    "lastUpdated": "string (date-time)",
    "lastUpdatedBy": "00000000-0000-0000-0000-000000000000",
    "lastUpdatedByName": "string",
    "activeStatus": "boolean"
}
```
