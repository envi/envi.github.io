# VendorFaxConfigurations

## Get the list of Vendor Fax Configurations 

### Path</span>
GET /odata/VendorFaxConfigurations

### Description</span>
Returns a paged list with active/inactive Fax Configurations of active Vendors related to active Facilities within the logged-in organization. 

!!! note

    You can filter the results as follows:

    - For an exact match, use: ```$filter parameter–entity eq ‘string’```
    - For a partial match, use: ```$filter=contains parameter–contains(entity, ‘string’)```


### Request parameters</span>
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


### Responses</span>
| <div style="width:200px">Response </div>|<div style="width:420px">Explanation</div>|                      
|-----:|:-------|
|**200 OK**|OK|
|**400 Bad Request**|Incorrect input data or organization ID does not match with the organization ID user is logged in.|      
|**400 Bad Request** | The limit for the ```$top``` query has been exceeded. The value from the incoming request is 'N' (N is your value from the request). You can find the data on the current limit [here](Options_and_Limitations.md#top-and-skip).
|**401 Unauthorized**|Incorrect specified ```access_token``` or ```access_token``` got expired.|
|**403 Forbidden**|User doesn’t have appropriate privileges.|
|**500 Internal Server Error**|Server encountered an unexpected condition that prevented it from fulfilling the request.|


### Properties</span>
|<div style="width:200px">Property </div> |<div style="width:420px">Explanation</div>|                      
|-----:|:-------|
|**vendorFaxId**: string *(uuid)* | Unique Identifier of the Vendor Fax |
|**vendorId**: string *(uuid)* | Unique Identifier of the Vendor |
|**vendorNo**: string | Code of the Supplier who sells products |
|**vendorName**: string | Name of the Vendor |
|**facilityId**: string *(uuid)* | Unique Identifier of the Facility |
|**facilityNo**: string | Identification Number of the Facility |
|**facilityName**: string | Name of the Facility |
|**faxDescription**: string | Description of the Vendor Fax |
|**csid**: string | Called Subscriber Identification |
|**faxNumber**: string | Number of the Fax |
|**useCoverPage**: boolean | Use Cover Page or not?|
|**coverPageBody**: string | Body Cover Page |
|**activeStatus**: boolean | Is the Status of the Vendor Fax active or not? |
|**dateAdded**: string *(date-time)* | Date when the Vendor Fax was added |
|**addedBy**: string *(uuid)* | Unique Identifier of the user who added the Vendor Fax |
|**addedByName**: string | Name of the user who added the Vendor Fax |
|**lastUpdated**: string *(date-time)* | Last Date when the Vendor Fax was updated |
|**lastUpdatedBy**: string *(uuid)* | Unique Identifier of the last user who updated the Vendor Fax |
|**lastUpdatedByName**: string | Name of the last user who updated the Vendor Fax |

``` json title="Response Content-types: APPLICATION/JSON, APPLICATION/XML<br>Response example (200 OK)"
{
    "@odata.context": "link",
    "@odata.count": "number",
    "value": [
        {
            "vendorFaxId": "00000000-0000-0000-0000-000000000000",
            "vendorId": "00000000-0000-0000-0000-000000000000",
            "vendorNo": "string",
            "vendorName": "string",
            "facilityId": "00000000-0000-0000-0000-000000000000",
            "facilityNo": "string",
            "facilityName": "string",
            "faxDescription": "string",
            "csid": "string",
            "faxNumber": "string",
            "useCoverPage": "boolean",
            "coverPageBody": "string",
            "activeStatus": "boolean",
            "dateAdded": "string (date-time)",
            "addedBy": "00000000-0000-0000-0000-000000000000",
            "addedByName": "string",
            "lastUpdated": "string (date-time)",
            "lastUpdatedBy": "00000000-0000-0000-0000-000000000000",
            "lastUpdatedByName": "string"
        }
    ],
    "@odata.nextLink": "link"
}
```


## Get the specified Vendor Fax Configuration

### Path</span>
GET /odata/VendorFaxConfigurations({vendorFaxConfigurationId})

### Description</span>
Returns the details of active/inactive, specified by ID Vendor Fax Configuration with active Vendors related to active Facilities within the logged-in organization.

### Request parameters</span>
|  <div style="width:200px">Parameter</div>  |  <div style="width:380px">Explanation</div>  |                      
|-----:|:-------|
|**includeInactiveVendors** <br> boolean default: false <br> *in query* | Include inactive Vendors. |
|**includeInactiveFacilities** <br> boolean default: false <br> *in query* | Include inactive Facilities. |
|**vendorFaxConfigurationId**: string *(uuid)*  <br> <span style="color: #F05D30">**required**</span> <br> *in path* | Enter the ID of the Vendor Fax Configuration here. |
|**api-version**: string default: 1.0 <br> *in header*| The requested API version. |   
|**Authorization**: string default: <br> Bearer access_token <br> *in header* |Specify the type of the token (bearer) and then insert the ```access_token```, which was obtained during authentication. |


### Responses</span>
| <div style="width:200px">Response </div>|<div style="width:420px">Explanation</div>|                      
|-----:|:-------|
|**200 OK**|OK|      
|**400 Bad Request**| Incorrect input data or organization ID does not match with the organization ID user is logged in.|
|**401 Unauthorized**| Incorrect specified ```access_token``` or ```access_token``` got expired.|
|**403 Forbidden**| User doesn’t have appropriate privileges.|
|**404 Not Found** | Specified ID is absent in the system. |
|**500 Internal Server Error**| Server encountered an unexpected condition that prevented it from fulfilling the request. |


### Properties</span>
|<div style="width:200px">Property </div> |<div style="width:420px">Explanation</div>|                      
|-----:|:-------|
|**vendorFaxId**: string *(uuid)* | Unique Identifier of the Vendor Fax |
|**vendorId**: string *(uuid)* | Unique Identifier of the Vendor |
|**vendorNo**: string | Code of the Supplier who sells products |
|**vendorName**: string | Name of the Vendor |
|**facilityId**: string *(uuid)* | Unique Identifier of the Facility |
|**facilityNo**: string | Identification Number of the Facility |
|**facilityName**: string | Name of the Facility |
|**faxDescription**: string | Description of the Vendor Fax |
|**csid**: string | Called Subscriber Identification |
|**faxNumber**: string | Number of the Fax |
|**useCoverPage**: boolean | Use Cover Page or not?|
|**coverPageBody**: string | Body Cover Page |
|**activeStatus**: boolean | Is the Status of the Vendor Fax active or not? |
|**dateAdded**: string *(date-time)* | Date when the Vendor Fax was added |
|**addedBy**: string *(uuid)* | Unique Identifier of the user who added the Vendor Fax |
|**addedByName**: string | Name of the user who added the Vendor Fax |
|**lastUpdated**: string *(date-time)* | Last Date when the Vendor Fax was updated |
|**lastUpdatedBy**: string *(uuid)* | Unique Identifier of the last user who updated the Vendor Fax |
|**lastUpdatedByName**: string | Name of the last user who updated the Vendor Fax |


``` json title="Response Content-types: APPLICATION/JSON, APPLICATION/XML<br>Response example (200 OK)"
{
    "@odata.context": "link",
    "vendorFaxId": "00000000-0000-0000-0000-000000000000",
    "vendorId": "00000000-0000-0000-0000-000000000000",
    "vendorNo": "string",
    "vendorName": "string",
    "facilityId": "00000000-0000-0000-0000-000000000000",
    "facilityNo": "string",
    "facilityName": "string",
    "faxDescription": "string",
    "csid": "string",
    "faxNumber": "string",
    "useCoverPage": "boolean",
    "coverPageBody": "string",
    "activeStatus": "boolean",
    "dateAdded": "string (date-time)",
    "addedBy": "00000000-0000-0000-0000-000000000000",
    "addedByName": "string",
    "lastUpdated": "string (date-time)",
    "lastUpdatedBy": "00000000-0000-0000-0000-000000000000",
    "lastUpdatedByName": "string"
}
```
