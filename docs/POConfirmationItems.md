# POConfirmationItems

## Get the list of PO Confirmation Items

### Path
GET /odata/POConfirmationItems

### Description
Returns a paged list of PO Confirmation Items within the logged-in organization. 

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
|**api-version**: string default: 1.0 <br> *in header*| The requested API version.|
|**$search**: string <br> *in query*  | Searches across all supported fields. |
|**$filter**: string <br> *in query* | Filters results based on a Boolean condition.|
|**$orderby**: string <br> *in query* | Sorts results.|
|**$top**: string  <br> *in query* | Returns only the first n results.|
|**$skip**: string <br> *in query*| Skips the first n results.|
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
|<div style="width:200px">Property </div> |<div style="width:420px">Explanation</div>|                      
|-----:|:-------|
|**poConfirmationItemId**: string *(uuid)* | Unique Identifier of the Purchase Order Confirmation Item |
|**poConfirmationId**: string *(uuid)* | Unique Identifier of the Purchase Order Confirmation |
|**purchaseOrderId**: string *(uuid)* | Unique Identifier of the Purchase Order |
|**purchaseOrderNo**: string | Number of the Purchase Order |
|**lineItemNo**: integer *(int32)* | Number of the Line Item |
|**quantity**: integer *(int32)* | Quantity specified in the Line Items |
|**uom**: string | Unit of Measure |
|**price**: number *(double)* | Price of the Item |
|**inventoryNo**: string | Identification code of the Inventory Item |
|**vendorItemNo**: string | Code that is used by the Vendor for the Item identification |
|**manufacturer**: string | Manufacturer Name |
|**manufacturerItemNo**: string | Item Number of the Manufacturer |
|**inventoryDescription**: string | Description of the Inventory Item |
|**updatedPOPrice**: boolean | Was Purchase Order Price updated or not? |
|**updatedInventoryPrice**: boolean | Was Inventory Item Price updated or not? |
|**dateCreated**: string *(date-time)* | Date when the Purchase Order Confirmation Item was created |
|**lastUpdated**: string *(date-time)* | Last Date when the Purchase Order Confirmation Item was updated |
|**lastUpdatedBy**: string *(uuid)* | Unique Identifier of the last user who updated the Purchase Order Confirmation Item |
|**lastUpdatedByName**: string | Name of the last user who updated the Purchase Order Confirmation Item |
|**notes**: string | Comments about the Purchase Order Confirmation Item |
|**isUnresolved**: string *(boolean)* | Is the Purchase Order Confirmation Item unresolved? |

``` json title="Response Content-types: APPLICATION/JSON, APPLICATION/XML<br>Response example (200 OK)"
{
    "@odata.context": "link",
    "@odata.count": "number",
    "value": [
        {
            "poConfirmationItemId": "00000000-0000-0000-0000-000000000000",
            "poConfirmationId": "00000000-0000-0000-0000-000000000000",
            "purchaseOrderId": "00000000-0000-0000-0000-000000000000",
            "purchaseOrderNo": "string",
            "lineItemNo": "integer (int32)",
            "quantity": "integer (int32)",
            "uom": "string",
            "price": "number (double)",
            "inventoryNo": "string",
            "vendorItemNo": "string",
            "manufacturer": "string",
            "manufacturerItemNo": "string",
            "inventoryDescription": "string",
            "updatedPOPrice": "boolean",
            "updatedInventoryPrice": "boolean",
            "dateCreated": "string (date-time)",
            "lastUpdated": "string (date-time)",
            "lastUpdatedBy": "00000000-0000-0000-0000-000000000000",
            "lastUpdatedByName": "string",
            "notes": "string",
            "isUnresolved": "boolean"
        }
    ],
    "@odata.nextLink": "link"
}
```

## Get the specified PO Confirmation Item

### Path
GET /odata/POConfirmationItems({poConfirmationItemId})

### Description
Returns the details of the PO Confirmation Item specified by ID.

### Request parameters
|  <div style="width:200px">Parameter</div>  |  <div style="width:380px">Explanation</div>  |                      
|-----:|:-------|
|**poConfirmationItemId**: string *(uuid)* <br> <span style="color: #F05D30">**required**</span> <br> *in path* | Enter the ID of the PO Confirmation Item. |
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
|**poConfirmationItemId**: string *(uuid)* | Unique Identifier of the Purchase Order Confirmation Items |
|**poConfirmationId**: string *(uuid)* | Unique Identifier of the Purchase Order Confirmation |
|**purchaseOrderId**: string *(uuid)* | Unique Identifier of the Purchase Order |
|**purchaseOrderNo**: string | Number of the Purchase Order |
|**lineItemNo**: integer *(int32)* | Number of the Line Item |
|**quantity**: integer *(int32)* | Quantity specified in the Line Items |
|**uom**: string | Unit of Measure |
|**price**: number *(double)* | Price of the Item |
|**inventoryNo**: string | Identification code of the Inventory Item |
|**vendorItemNo**: string | Code that is used by the Vendor for the Item identification |
|**manufacturer**: string | Manufacturer Name |
|**manufacturerItemNo**: string | Item Number of the Manufacturer |
|**inventoryDescription**: string | Description of the Inventory Item |
|**updatedPOPrice**: boolean | Was Purchase Order Price updated or not? |
|**updatedInventoryPrice**: boolean | Was Inventory Item Price updated or not? |
|**dateCreated**: string *(date-time)* | Date when the Purchase Order Confirmation Item was created |
|**lastUpdated**: string *(date-time)* | Last Date when the Purchase Order Confirmation Item was updated |
|**lastUpdatedBy**: string *(uuid)* | Unique Identifier of the last user who updated the Purchase Order Confirmation Item |
|**lastUpdatedByName**: string | Name of the last user who updated the Purchase Order Confirmation Item |
|**notes**: string | Comments about the Purchase Order Confirmation Item |
|**isUnresolved**: string *(boolean)* | Is the Purchase Order Confirmation Item unresolved? |

``` json title="Response Content-types: APPLICATION/JSON, APPLICATION/XML<br>Response example (200 OK)"
{
    "@odata.context": "link",
    "poConfirmationItemId": "00000000-0000-0000-0000-000000000000",
    "poConfirmationId": "00000000-0000-0000-0000-000000000000",
    "purchaseOrderId": "00000000-0000-0000-0000-000000000000",
    "purchaseOrderNo": "string",
    "lineItemNo": "integer (int32)",
    "quantity": "integer (int32)",
    "uom": "string",
    "price": "number (double)",
    "inventoryNo": "string",
    "vendorItemNo": "string",
    "manufacturer": "string",
    "manufacturerItemNo": "string",
    "inventoryDescription": "string",
    "updatedPOPrice": "boolean",
    "updatedInventoryPrice": "boolean",
    "dateCreated": "string (date-time)",
    "lastUpdated": "string (date-time)",
    "lastUpdatedBy": "00000000-0000-0000-0000-000000000000",
    "lastUpdatedByName": "string",
    "notes": "string",
    "isUnresolved": "boolean"
}
```