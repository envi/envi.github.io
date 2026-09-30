# Vendors

## Get the list of Vendors

### Path
GET /odata/Vendors

### Description
Returns a paged list of existing Vendors within the logged-in organization.

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
|**api-version**: string default: 1.0 <br> *in header*| The requested API version.|
|**$search**: string <br> *in query*  | Searches across all supported fields. |  
|**$filter**: string <br> *in query* | Filters results based on a Boolean condition. |  
|**$orderby**: string <br> *in query* | Sorts results.|
|**$top**: string  <br> *in query* | Returns only the first n results.|
|**$skip**: string <br> *in query*| Skips the first n results.|
|**Authorization**: string default: <br> Bearer access_token <br> *in header* | Specify the type of the token (bearer) and insert the ```access_token``` obtained during authentication.|

### Responses
<style>
td, th {
   border: none!important;
}
</style>

| Response | Explanation |                      
|-----:|:-------|
|**200 OK**|OK|      
|**400 Bad Request**| The request contains incorrect input data. |
|**400 Bad Request** | The limit for the ```$top``` query has been exceeded. The value from the incoming request is 'N' (N is your value from the request). You can find the data on the current limit [here](Options_and_Limitations.md#top-and-skip). |
|**401 Unauthorized**| The specified ```access_token``` is invalid or has expired. |
|**403 Forbidden**|The user doesn’t have the appropriate privileges.|
|**500 Internal Server Error**| The server encountered an unexpected condition that prevented it from fulfilling the request.|

### Properties
| Property | Explanation |                      
|-----:|:-------|
|**vendorId**: string *(uuid)* | Unique identifier of the Vendor |
|**vendorNo**: string | Number of the Vendor |
|**vendorName**: string | Name of the Vendor |
|**organizationId**: string *(uuid)* | Unique identifier of the Organization |
|**organizationNo**: string | Identification number of the Organization |
|**organizationName**: string | Name of the Organization |
|**vendorNotes**: string | Notes about the Vendor |
|**dateAdded**: string *(date-time)* | Date when the Vendor was added |
|**addedBy**: string *(uuid)* | Unique identifier of the user who added the Vendor |
|**addedByName**: string | Name of the user who added the Vendor |
|**lastUpdated**: string *(date-time)* | Date when the Vendor was last updated |
|**lastUpdatedBy**: string *(uuid)* | Unique identifier of the user who last updated the Vendor |
|**lastUpdatedByName**: string | Name of the user who last updated the Vendor |
|**activeStatus**: boolean | Is the Vendor active or not? |
|**url**: string | Website address of the Vendor |
|**systemVendorName**: string | Name of the System Vendor |
|**ediVendorNo**: string | EDI Vendor number |
|**allowConsignmentOrders**: boolean | Is Consignment Order sending enabled for the Vendor or not? |
|**requireMfg**: boolean | Is the Manufacturer required for the Vendor or not? |
|**requireMfgItemNo**: boolean | Is the Manufacturer Item Number required for the Vendor or not? |


``` json title="Response example (200 OK)"
{
    "@odata.context": "link",
    "@odata.count": "number",
    "value": [
        {
            "vendorId": "00000000-0000-0000-0000-000000000000",
            "vendorNo": "string",
            "vendorName": "string",
            "organizationId": "00000000-0000-0000-0000-000000000000",
            "organizationNo": "string",
            "organizationName": "string",
            "vendorNotes": "string",
            "dateAdded": "string (date-time)",
            "addedBy": "00000000-0000-0000-0000-000000000000",
            "addedByName": "string",
            "lastUpdated": "string (date-time)",
            "lastUpdatedBy": "00000000-0000-0000-0000-000000000000",
            "lastUpdatedByName": "string",
            "activeStatus": "boolean",
            "url": "string",
            "systemVendorName": "string",
            "ediVendorNo": "string",
            "allowConsignmentOrders": "boolean",
            "requireMfg": "boolean",
            "requireMfgItemNo": "boolean"
        }
    ],
    "@odata.nextLink": "link"
}
```

## Get the specified Vendor

### Path
GET /odata/Vendors({vendorId})

### Description
Returns the details of the Vendor specified by ID.

### Request body
|  Parameter | Explanation |                      
|-----:|:-------|
|**vendorId**: string *(uuid)* <br> <span style="color: #F05D30">**required**</span> <br> *in path* | Enter the ID of the Vendor. |
|**api-version**: string default: 1.0 <br> *in header*| The requested API version.|   
|**Authorization**: string default: <br> Bearer access_token <br> *in header* | Specify the type of the token (bearer) and insert the ```access_token``` obtained during authentication.|

### Responses
| Response | Explanation |                      
|-----:|:-------|
|**200 OK**|OK|      
|**400 Bad Request**| The request contains incorrect input data. |
|**401 Unauthorized**| The specified ```access_token``` is invalid or has expired. |
|**403 Forbidden**| The user doesn’t have the appropriate privileges.|
|**404 Not Found** | The specified ID is absent in the system. |
|**500 Internal Server Error**| The server encountered an unexpected condition that prevented it from fulfilling the request.|

### Properties
| Property | Explanation |                      
|-----:|:-------|
|**vendorId**: string *(uuid)* | Unique identifier of the Vendor |
|**vendorNo**: string | Number of the Vendor |
|**vendorName**: string | Name of the Vendor |
|**organizationId**: string *(uuid)* | Unique identifier of the Organization |
|**organizationNo**: string | Identification number of the Organization |
|**organizationName**: string | Name of the Organization |
|**vendorNotes**: string | Notes about the Vendor |
|**dateAdded**: string *(date-time)* | Date when the Vendor was added |
|**addedBy**: string *(uuid)* | Unique identifier of the user who added the Vendor |
|**addedByName**: string | Name of the user who added the Vendor |
|**lastUpdated**: string *(date-time)* | Date when the Vendor was last updated |
|**lastUpdatedBy**: string *(uuid)* | Unique identifier of the user who last updated the Vendor |
|**lastUpdatedByName**: string | Name of the user who last updated the Vendor |
|**activeStatus**: boolean | Is the Vendor active or not? |
|**url**: string | Website address of the Vendor |
|**systemVendorName**: string | Name of the System Vendor |
|**ediVendorNo**: string | EDI Vendor number |
|**allowConsignmentOrders**: boolean | Is Consignment Order sending enabled for the Vendor or not? |
|**requireMfg**: boolean | Is the Manufacturer required for the Vendor or not? |
|**requireMfgItemNo**: boolean | Is the Manufacturer Item Number required for the Vendor or not? |

``` json title="Response example (200 OK)"
{
    "@odata.context": "link",
    "vendorId": "00000000-0000-0000-0000-000000000000",
    "vendorNo": "string",
    "vendorName": "string",
    "organizationId": "00000000-0000-0000-0000-000000000000",
    "organizationNo": "string",
    "organizationName": "string",
    "vendorNotes": "string",
    "dateAdded": "string (date-time)",
    "addedBy": "00000000-0000-0000-0000-000000000000",
    "addedByName": "string",
    "lastUpdated": "string (date-time)",
    "lastUpdatedBy": "00000000-0000-0000-0000-000000000000",
    "lastUpdatedByName": "string",
    "activeStatus": "boolean",
    "url": "string",
    "systemVendorName": "string",
    "ediVendorNo": "string",
    "allowConsignmentOrders": "boolean",
    "requireMfg": "boolean",
    "requireMfgItemNo": "boolean"
}
```

## Get the list of Vendors

### Path
POST /odata/Vendors/GetVendorsInfo(facilityId={facilityId})

### Description
Returns the details of the predefined Vendor(s) within the Facility specified by ID.

### Request body
Enter the value of the vendor(s) from the existing template.

### Request parameters
|  Parameter | Explanation |                      
|-----:|:-------|
|**facilityId**: string *(uuid)* <br> <span style="color: #F05D30">**required**</span> <br> *in path* | Enter the ID of the Facility. |
|**api-version**: string default: 1.0 <br> *in header*| The requested API version.|   
|**Authorization**: string default: <br> Bearer access_token <br> *in header* | Specify the type of the token (bearer) and insert the ```access_token``` obtained during authentication.|

``` json title="Request example"
{
"value": ["00000000-0000-0000-0000-000000000000"]
}
```

### Responses
| Response | Explanation |                      
|-----:|:-------|
|**200 OK**|OK|      
|**400 Bad Request**| The request contains incorrect input data. |
|**401 Unauthorized**| The specified ```access_token``` is invalid or has expired. |
|**403 Forbidden**| The user doesn’t have the appropriate privileges.|
|**500 Internal Server Error**| The server encountered an unexpected condition that prevented it from fulfilling the request.|

### Properties
| Property | Explanation |                      
|-----:|:-------|
|**vendorId**: string *(uuid)* | Unique identifier of the Vendor |
|**vendorName**: string | Name of the Vendor |
|**vendorNo**: string | Number of the Vendor |
|**address1**: string | Primary address of the Vendor for shipping or billing purposes |
|**address2**: string | Secondary address of the Vendor for shipping or billing purpose |
|**city**: string | City of the Vendor address |
|**state**: string | State of the Vendor address |
|**zip**: string | Zip code of the Vendor address |
|**country**: string | Country of the Vendor address |
|**url**: string | Website address of the Vendor |
|**accountNumber**: string | Number of the Vendor account |
|**activeStatus**: boolean | Is the Vendor active or not? |
|**lastUpdated**: string *(date-time)* | Date when the Vendor was last updated |
|**leadTime**: integer *(int32)* | Lead time for the Vendor |

``` json title="Response example (200 OK)"
[
  {
    "vendorId": "00000000-0000-0000-0000-000000000000",
    "vendorName": "string",
    "vendorNo": "string",
    "address1": "string",
    "address2": "string",
    "city": "string",
    "state": "string",
    "zip": "string",
    "country": "string",
    "url": "string",
    "accountNumber": "string",
    "activeStatus": "boolean",
    "lastUpdated": "string (date-time)",
    "leadTime": "integer (int32)"
  }
]
```

## Create a new Vendor

### Path
POST /odata/Vendors

### Description
Creates a new Vendor within the logged-in organization.

### Request body
| Parameter | Explanation |                      
|-----:|:-------|
|**vendorNo**: string | Number of the Vendor. <br> **Note**: If Auto ID is configured for a Vendor, ```vendorNo``` is optional. |
|**vendorName**: string <br> <span style="color: #F05D30">**required**</span> | Name of the Vendor |
|**externalVendorNo**: string | External Vendor Number. <br> **Note**: A request with ```externalVendorNo``` can be sent only by System users. |
|**url**: string | Website address of the Vendor |

``` json title="Request example"
{
    "vendorNo": "string",
    "vendorName": "string",
    "externalVendorNo": "string",
    "url": "string"
}
``` 

### Request parameters
| Parameter | Explanation |                      
|-----:|:-------|
|**api-version**: string default: 1.0 <br> *in header*| The requested API version.|   
|**Authorization**: string default: <br> Bearer access_token <br> *in header* | Specify the type of the token (bearer) and insert the ```access_token``` obtained during authentication. |


### Responses
| Response | Explanation |                      
|-----:|:-------|
|**200 OK**|OK|   
|**400 Bad Request**| The request contains incorrect input data. |      
|**401 Unauthorized**| The specified ```access_token``` is invalid or has expired. |
|**403 Forbidden**| The user doesn’t have the appropriate privileges. |
|**500 Internal Server Error**| The server encountered an unexpected condition that prevented it from fulfilling the request.|

``` json title="Response example (200 OK)"
"00000000-0000-0000-0000-000000000000"

```





