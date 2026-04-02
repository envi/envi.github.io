# PurchasingUnits

## Get the specified Purchasing Unit

### Path
GET /odata/PurchasingUnits({inventoryVendorPurchasingUnitId})

### Description
Returns the details of the Purchasing Unit specified by ID.

### Request parameters
<style>
td, th {
   border: none!important;
}
</style>

|  <div style="width:200px">Parameter</div>  |  <div style="width:380px">Explanation</div>  |                      
|-----:|:-------|
|**inventoryVendorPurchasing<br>UnitId**: string *(uuid)* <br> <span style="color: #F05D30">**required**</span> <br> *in path* | Enter the ID of the Purchasing Unit. |
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
|<div style="width:200px">Property </div> |<div style="width:420px">Explanation</div>|                      
|-----:|:-------|
|**inventoryVendorPurchasing<br>UnitId**: <br> string *(uuid)* | Unique Identifier of the Inventory Vendor Purchasing Unit |
|**inventoryVendorId**: string *(uuid)* | Unique Identifier of the Inventory Vendor |
|**vendorName**: string | Name of the Vendor |
|**vendorNo**: string | Code of the Supplier who sells products |
|**vendorUOM**: string | Vendor's Unit of Measure |
|**vendorConversionFactor**: integer <br> *(int32)* | Number of Stock Keeping Units in another Vendor's Unit of Measure |
|**vendorCost**: number *(double)* | Cost of the Vendor |
|**activeStatus**: boolean | Is the status of Purchasing Unit active or not? |
|**lastVendorCost**: number *(double)* | Last Cost of the Vendor |
|**costLastUpdated**: string <br> *(date-time)* | Last Date when the Cost was updated |
|**costLastUpdatedBy**: string *(uuid)* | Unique Identifier of the last user who updated the Cost |
|**costLastUpdatedByName**: string | Name of the last user who updated the Cost |
|**dateAdded**: string *(date-time)* | Date when the Purchasing Unit was added |
|**addedBy**: string *(uuid)* | Unique Identifier of the user who added the Purchasing Unit |
|**addedByName**: string | Name of the last user who added the Purchasing Unit |
|**lastUpdated**: string *(date-time)* | Last Date when the Purchasing Unit was updated |
|**lastUpdatedBy**: string *(uuid)* | Unique Identifier of the last user who updated the Purchasing Unit |
|**lastUpdatedByName**: string | Name of the last user who updated the Purchasing Unit |


``` json title="Response Content-types: APPLICATION/JSON, APPLICATION/XML<br>Response example (200 OK)"
{
    "@odata.context": "link",
    "inventoryVendorPurchasingUnitId": "00000000-0000-0000-0000-000000000000",
    "inventoryVendorId": "00000000-0000-0000-0000-000000000000",
    "vendorName": "string",
    "vendorNo": "string",
    "vendorUOM": "string",
    "vendorConversionFactor": "integer (int32)",
    "vendorCost": "number (double)",
    "activeStatus": "boolean",
    "lastVendorCost": "number (double)",
    "costLastUpdated": "string (date-time)",
    "costLastUpdatedBy": "00000000-0000-0000-0000-000000000000",
    "costLastUpdatedByName": "string",
    "dateAdded": "string (date-time)",
    "addedBy": "00000000-0000-0000-0000-000000000000",
    "addedByName": "string",
    "lastUpdated": "string (date-time)",
    "lastUpdatedBy": "00000000-0000-0000-0000-000000000000",
    "lastUpdatedByName": "string"
}
```