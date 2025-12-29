# InventoryTrackings

## Get the specified Inventory tracking setting

### Path
GET /odata/InventoryTrackings({inventoryTrackingId})

### Description
Returns the details of the Inventory tracking setting specified by ID.

### Request parameters
<style>
td, th {
   border: none!important;
}
</style>

|  <div style="width:200px">Parameter</div>  |  <div style="width:380px">Explanation</div>  |                      
|-----:|:-------|
|**inventoryTrackingId**: string *(uuid)* <span style="color: #F05D30">**required**</span> <br> *in path*  | Enter the ID of the Inventory Tracking. |
|**api-version**: string default: 1.0 <br> *in header*| The requested API version. |
|**Authorization**: string default: <br> Bearer access_token <br> *in header* | Specify the type of the token (bearer) and insert the ```access_token``` obtained during authentication. |

### Responses
| <div style="width:200px">Response </div>|<div style="width:380px">Explanation</div>|                      
|-----:|:-------|
|**200 OK**| OK |
|**400 Bad Request**| The request contains incorrect input data. |
|**401 Unauthorized**| The specified ```access_token``` is invalid or has expired. |
|**403 Forbidden**| The user doesn’t have the appropriate privileges. |
|**500 Internal Server Error**| The server encountered an unexpected condition that prevented it from fulfilling the request. |

### Properties
|<div style="width:200px">Property </div> |<div style="width:420px">Explanation</div>|                      
|-----:|:-------|
|**inventoryTrackingId**: string <br> *(uuid)* | Unique Identifier of the Inventory Item Tracking |
|**inventoryId**: string *(uuid)* | Unique Identifier of the Inventory Item |
|**inventoryNo**: string | Identification code of the Inventory Item |
|**facilityId**: string *(uuid)* | Unique Identifier of the Facility |
|**facilityNo**: string | Identification Number of the Facility |
|**facilityName**: string | Name of the Facility |
|**trackLot**: boolean | Is Tracking performed by Lot Number or not? |
|**trackExpiration**: boolean | Is Tracking performed by Expiration Date or not? |
|**trackSerialNo**: boolean | Is Tracking performed by Serial Number or not? |
|**isOptional**: boolean | Is Tracking optional or not? |
|**dateAdded**: string *(date-time)* | Date when the Inventory Item Tracking was added |
|**addedBy**: string *(uuid)* | Unique Identifier of the user who added the Inventory Item Tracking |
|**addedByName**: string | Name of the user who added the Inventory Item Tracking |
|**lastUpdated**: string *(date-time)* | Last Date when the Inventory Item Tracking was updated |
|**lastUpdatedBy**: string *(uuid)* | Unique Identifier of the last user who updated Inventory Item Tracking |
|**lastUpdatedByName**: string | Name of the last user who updated Inventory Item Tracking |

``` json title="Response Content-types: APPLICATION/JSON, APPLICATION/XML<br>Response example (200 OK)"
{
    "@odata.context": "link",
    "inventoryTrackingId": "00000000-0000-0000-0000-000000000000",
    "inventoryId": "00000000-0000-0000-0000-000000000000",
    "inventoryNo": "string",
    "facilityId": "00000000-0000-0000-0000-000000000000",
    "facilityNo": "string",
    "facilityName": "string",
    "trackLot": "boolean",
    "trackExpiration": "boolean",
    "trackSerialNo": "boolean",
    "isOptional": "boolean",
    "dateAdded": "string (date-time)",
    "addedBy": "00000000-0000-0000-0000-000000000000",
    "addedByName": "string",
    "lastUpdated": "string (date-time)",
    "lastUpdatedBy": "00000000-0000-0000-0000-000000000000",
    "lastUpdatedByName": "string"
}
```