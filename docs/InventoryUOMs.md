# InventoryUOMs

## Get the specified Inventory UOM

### Path
GET /odata/InventoryUOMs({inventoryUOMId})

### Description
Returns the details of the Inventory UOM specified by ID.

### Request parameters
<style>
td, th {
   border: none!important;
}
</style>

|  <div style="width:200px">Parameter</div>  |  <div style="width:380px">Explanation</div>  |                      
|-----:|:-------|
|**inventoryUOMId**: string *(uuid)*  <br> <span style="color: #F05D30">**required**</span> <br> *in path*  | Enter the ID of the Inventory UOM. |
|**api-version**: string default: 1.0 <br> *in header*| The requested API version. |
|**Authorization**: string default: <br> Bearer access_token <br> *in header* | Specify the type of the token (bearer) and insert the ```access_token``` obtained during authentication. |

### Responses
| <div style="width:200px">Response </div>|<div style="width:380px">Explanation</div>|                      
|-----:|:-------|
|**200 OK**| OK |
|**400 Bad Request**| The request contains incorrect input data. |
|**401 Unauthorized**| The specified ```access_token``` is incorrect, or the ```access_token``` has expired. |
|**403 Forbidden**| The user doesn’t have the appropriate privileges. |
|**500 Internal Server Error**| The server encountered an unexpected condition that prevented it from fulfilling the request. |

### Properties
|<div style="width:200px">Property </div> |<div style="width:420px">Explanation</div>|                      
|-----:|:-------|
|**inventoryUOMId**: string *(uuid)* | Unique Identifier of the Inventory Item Unit of Measure |
|**inventoryId**: string *(uuid)* | Unique Identifier of the Inventory Item |
|**inventoryNo**: string | Identification code of the Inventory Item |
|**uom**: string | Unit of Measure |
|**conversionFactor**: integer <br> *(int32)* | Number of Stock Keeping Units in another Unit of Measure |
|**dateAdded**: string *(date-time)* | Date when the Inventory Item Unit of Measure was added |
|**addedId**: string *(uuid)* | Unique Identifier of the user who added the Inventory Item Unit of Measure |
|**lastUpdated**: string *(date-time)* | Last Date when the Inventory Item Unit of Measure was updated |
|**lastUpdatedId**: string *(uuid)* | Unique Identifier of the last user who updated the Inventory Item Unit of Measure |

``` json title="Response Content-types: APPLICATION/JSON, APPLICATION/XML<br>Response example (200 OK)"
{
    "@odata.context": "link",
    "inventoryUOMId": "00000000-0000-0000-0000-000000000000",
    "inventoryId": "00000000-0000-0000-0000-000000000000",
    "inventoryNo": "string",
    "uom": "string",
    "conversionFactor": "integer (int32)",
    "dateAdded": "string (date-time)",
    "addedId": "00000000-0000-0000-0000-000000000000",
    "lastUpdated": "string (date-time)",
    "lastUpdatedId": "00000000-0000-0000-0000-000000000000"
}
```