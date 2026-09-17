# Addresses

## Get the list of Addresses

### Path
GET /odata/Addresses

### Description
Returns a paged list of existing Addresses within the logged-in organization.

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

|  <div style="width:200px">Parameter</div>  |  <div style="width:380px">Explanation</div>  |                      
|-----:|:-------|
|**api-version**: string default: 1.0 <br> *in header*| The requested API version.|
|**$search**: string <br> *in query*  | Searches across all supported fields. |  
|**$filter**: string <br> *in query* | Filters results based on a Boolean condition.|
|**$orderby**: string <br> *in query* | Sorts results.|
|**$top**: string  <br> *in query* | Returns only the first n results.|
|**$skip**: string <br> *in query*| Skips the first n results.|
|**Authorization**: string default: <br> Bearer access_token <br> *in header* | Specify the type of the token (bearer) and insert the ```access_token``` obtained during authentication.|

### Responses
| <div style="width:200px">Response </div>|<div style="width:380px">Explanation</div>|                      
|-----:|:-------|
|**200 OK**|OK|      
|**400 Bad Request**| The request contains incorrect input data. |
|**400 Bad Request** | The limit for the ```$top``` query has been exceeded. The value from the incoming request is 'N' (N is your value from the request). You can find the data on the current limit [here](Options_and_Limitations.md#top-and-skip). |
|**401 Unauthorized**| The specified ```access_token``` is invalid or has expired. |
|**403 Forbidden**|The user doesn’t have the appropriate privileges.|
|**500 Internal Server Error**| The server encountered an unexpected condition that prevented it from fulfilling the request.|

### Properties
|<div style="width:200px">Property </div> |<div style="width:420px">Explanation</div>|                      
|-----:|:-------|
|**addressId**: string *(uuid)*| Unique identifier of the Address |
|**organizationId**: string *(uuid)*| Unique identifier of the Organization |
|**organizationNo**: string | Identification number of the Organization |
|**organizationName**: string| Name of the Organization |
|**addressNo**: string| Identification number of the Address |
|**addressName**: string| Name of the Address |
|**addressTypeId**: integer *(int32)* | Unique identifier of the Address type |
|**addressType**: string | Address type used for billing or shipping |
|**facilityId**: string *(uuid)* | Unique identifier of the Facility |
|**facilityNo**: string | Identification number of the Facility |
|**facilityName**: string | Name of the Facility |
|**addressDescription**: string | Description of the Address |
|**address1**: string | Primary address for shipping or billing purposes |
|**address2**: string | Secondary address for shipping or billing purposes |
|**city**: string | City |
|**state**: string |State |
|**zip**: string | Zip code |
|**country**: string | Country |
|**contactName**: string | Name of the main contact |
|**contactEmail**: string | Email address of the main contact |
|**phone**: string | Phone number of the main contact |
|**phoneExt**: string | Phone extension of the main contact |
|**fax**: string | Fax number of the main contact |
|**isDefaultAddress**: boolean | Is the Address used as the default address or not? |
|**activeStatus**: boolean | Is the Address active or not? |
|**dateCreated**: string *(date-time)* | Date when the Address was created |
|**createdBy**: string *(uuid)* | Unique identifier of the user who created the Address |
|**createdByName**: string | Name of the user who created the Address |
|**lastUpdated**: string *(date-time)* | Date when the Address was last updated |
|**lastUpdatedBy**: string *(uuid)* | Unique identifier of the user who last updated the Address |
|**lastUpdatedByName**: string | Name of the user who last updated the Address |


``` json title="Response example (200 OK)"
{
    "@odata.context": "link",
    "@odata.count": "number",
    "value": [
        {
            "addressId": "00000000-0000-0000-0000-000000000000",
            "organizationId": "00000000-0000-0000-0000-000000000000",
            "organizationNo": "string",
            "organizationName": "string",
            "addressNo": "string",
            "addressName": "string",
            "addressTypeId": "integer (int32)",
            "addressType": "string",
            "facilityId": "00000000-0000-0000-0000-000000000000",
            "facilityNo": "string",
            "facilityName": "string",
            "addressDescription": "string",
            "address1": "string",
            "address2": "string",
            "city": "string",
            "state": "string",
            "zip": "string",
            "country": "string",
            "contactName": "string",
            "contactEmail": "string",
            "phone": "string",
            "phoneExt": "string",
            "fax": "string",
            "isDefaultAddress": "boolean",
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

## Get the specified Address

### Path
GET /odata/Addresses({addressId})

### Description
Returns the details of the Address specified by ID.

### Request parameters
| <div style="width:200px"> Parameter </div> |<div style="width:380px">Explanation</div> |                      
|-----:|:-------|
|**addressId**: string *(uuid)* <br> <span style="color: #F05D30">**required**</span> <br> *in path*| Enter the ID of the Address.|
|**api-version**: string default: 1.0 <br> *in header*|The requested API version.|      
|**Authorization**: string default: <br> Bearer access_token <br> *in header* | Specify the type of the token (bearer) and insert the ```access_token``` obtained during authentication.|

### Responses
| <div style="width:200px">Response </div>|<div style="width:380px">Explanation</div>|                      
|-----:|:-------|
|**200 OK**|OK|      
|**400 Bad Request**| The request contains incorrect input data. |
|**401 Unauthorized**| The specified ```access_token``` is invalid or has expired. |
|**403 Forbidden**| The user doesn’t have the appropriate privileges.|
|**404 Not Found** | The specified ID is absent in the system. |
|**500 Internal Server Error**| The server encountered an unexpected condition that prevented it from fulfilling the request.|

### Properties
|<div style="width:200px">Property </div> |<div style="width:420px">Explanation</div>|                      
|-----:|:-------|
|**addressId**: string *(uuid)*| Unique identifier of the Address |
|**organizationId**: string *(uuid)*| Unique identifier of the Organization |
|**organizationNo**: string | Identification number of the Organization |
|**organizationName**: string| Name of the Organization |
|**addressNo**: string| Identification number of the Address |
|**addressName**: string| Name of the Address |
|**addressTypeId**: integer *(int32)* | Unique identifier of the Address type |
|**addressType**: string | Address type used for billing or shipping |
|**facilityId**: string *(uuid)* | Unique identifier of the Facility |
|**facilityNo**: string | Identification number of the Facility |
|**facilityName**: string | Name of the Facility |
|**addressDescription**: string | Description of the Address |
|**address1**: string | Primary address for shipping or billing purposes |
|**address2**: string | Secondary address for shipping or billing purposes |
|**city**: string | City |
|**state**: string |State |
|**zip**: string | Zip code |
|**country**: string | Country |
|**contactName**: string | Name of the main contact |
|**contactEmail**: string | Email address of the main contact |
|**phone**: string | Phone number of the main contact |
|**phoneExt**: string | Phone extension of the main contact |
|**fax**: string | Fax number of the main contact |
|**isDefaultAddress**: boolean | Is the Address used as the default address or not? |
|**activeStatus**: boolean | Is the Address active or not? |
|**dateCreated**: string *(date-time)* | Date when the Address was created |
|**createdBy**: string *(uuid)* | Unique identifier of the user who created the Address |
|**createdByName**: string | Name of the user who created the Address |
|**lastUpdated**: string *(date-time)* | Date when the Address was last updated |
|**lastUpdatedBy**: string *(uuid)* | Unique identifier of the user who last updated the Address |
|**lastUpdatedByName**: string | Name of the user who last updated the Address |

``` json title="Response example (200 OK)"
{
    "@odata.context": "link",
    "addressId": "00000000-0000-0000-0000-000000000000",
    "organizationId": "00000000-0000-0000-0000-000000000000",
    "organizationNo": "string",
    "organizationName": "string",
    "addressNo": "string",
    "addressName": "string",
    "addressTypeId": "integer (int32)",
    "addressType": "string",
    "facilityId": "00000000-0000-0000-0000-000000000000",
    "facilityNo": "string",
    "facilityName": "string",
    "addressDescription": "string",
    "address1": "string",
    "address2": "string",
    "city": "string",
    "state": "string",
    "zip": "string",
    "country": "string",
    "contactName": "string",
    "contactEmail": "string",
    "phone": "string",
    "phoneExt": "string",
    "fax": "string",
    "isDefaultAddress": "boolean",
    "activeStatus": "boolean",
    "dateCreated": "string (date-time)",
    "createdBy": "00000000-0000-0000-0000-000000000000",
    "createdByName": "string",
    "lastUpdated": "string (date-time)",
    "lastUpdatedBy": "00000000-0000-0000-0000-000000000000",
    "lastUpdatedByName": "string"
}
```