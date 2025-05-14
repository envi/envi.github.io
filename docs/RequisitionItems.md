# RequisitionItems

## Get the list of Requisition Items

### Path
GET /odata/RequisitionItems

### Description
Returns a paged list of existing Requisition Items.

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
|**$filter**: string <br> *in query* | Filters the results, based on a Boolean condition. | 
|**$orderby**: string <br> *in query* | Sorts the results.| 
|**$search**: string <br> *in query*  | Picks the value in all possible fields.|
|**$top**: string  <br> *in query* | Returns only the first n results.|
|**$skip**: string <br> *in query*| Skips the first n results.|
|**Authorization**: string default: <br> Bearer access_token <br> *in header* |Specify the type of the token (bearer) and then insert the ```access_token```, which was obtained during authentication.|

### Responses
| <div style="width:200px">Response </div>|<div style="width:420px">Explanation</div>|                      
|-----:|:-------|
|**200 OK**|OK|   
|**400 Bad Request**| Incorrect input data or organization ID does not match with the organization ID user is logged in. |      
|**400 Bad Request** | The limit for the ```$top``` query has been exceeded. The value from the incoming request is 'N' (N is your value from the request). You can find the data on the current limit [here](Options_and_Limitations.md#top-and-skip).
|**401 Unauthorized**|Incorrect specified ```access_token``` or ```access_token``` got expired.|
|**403 Forbidden**|User doesn’t have appropriate privileges.|
|**500 Internal Server Error**|Server encountered an unexpected condition that prevented it from fulfilling the request.|


### Properties
|<div style="width:200px">Property </div> |<div style="width:420px">Explanation</div>|                      
|-----:|:-------|
|**requisitionItemId**: string *(uuid)* | Unique Identifier of the Requisition Item |
|**requisitionId**: string *(uuid)* | Unique Identifier of the Requisition |
|**requisitionNo**: string | Identification code of the Requisition |
|**lineItemNo**: integer *(int32)* | Number of the Line Item |
|**inventoryNo**: string | Identification code of the Inventory Item |
|**inventoryDescription**: string | Description of the Inventory Item |
|**vendorItemNo**: string | Code that is used by the Vendor for the Item identification |
|**lineItemTypeId**: integer *(int32)* | Unique Identifier of the Line Item Type |
|**lineItemType**: string | Type of the Line Item |
|**quantity**: integer *(int32)* | Quantity specified in the Line Items |
|**UOM**: string | Unit of Measure |
|**conversionFactor**: <br> integer *(int32)* | Number of Stock Keeping Units in another Unit of Measure |
|**price**: number *(double)* | Price of the Line Item |
|**inventoryLocationId**: <br> string *(uuid)* | Unique Identifier of the Inventory Location |
|**notes**: string | Comments about the Requisition Item |
|**manufacturerId**: string *(uuid)* | Unique Identifier of the Manufacturer |
|**manufacturerItemNo**: string | Item Number of the Manufacturer |
|**suggestedVendorId**: <br> string *(uuid)* | Suggested Unique Identifier of the Vendor |
|**stockUOM**: string | Unit of Measure to track Inventory Balance |
|**vendorId**: string *(uuid)* | Unique Identifier of the Vendor |
|**poConversionStatusId**: <br> integer *(int32)* | Unique Identifier of Purchase Order Conversion Status |
|**poConversionStatus**: string | Conversion Status of Purchase Order |
|**purchaseOrderItemId**: <br> string *(uuid)* | Unique Identifier of the Purchase Order Item |
|**inventoryVendorId**: string *(uuid)* | Unique Identifier of the Inventory Item Vendor |
|**activeStatus**: boolean | Is the Requisition Item active or not? |
|**dateCreated**: string *(date-time)* | Date when the Requisition Item was created |
|**createdBy**: string *(uuid)* | Unique Identifier of the user who created the Requisition Item |
|**createdByUserName**: string | Name of the user who created the Requisition Item |
|**lastUpdated**: string *(date-time)* | Last Date when the Requisition Item was updated |
|**lastUpdatedBy**: string *(uuid)* | Unique Identifier of the last user who updated the Requisition Item |
|**lastUpdatedByUserName**: <br> string | Name of the last user who updated the Requisition Item |
|**locationId**: string *(uuid)* | Unique Identifier of the Location |
|**isTaxable**: boolean | Is the Location Taxable or not? |
|**contractNo**: string | Number of the Contract |
|**contractExpDate**: string <br> *(date-time)* | Expiration Date of the Contract |
|**isPrinted**: boolean | Is the Pick Ticket printed or not? |
|**supplierPartAuxiliaryId**: string | Unique Identifier of the Supplier Part Auxiliary |

``` json title="Response Content-types: APPLICATION/JSON, APPLICATION/XML<br>Response example (200 OK)"
{
    "@odata.context": "link",
    "@odata.count": "number",
    "value": [
        {
            "requisitionItemId": "00000000-0000-0000-0000-000000000000",
            "requisitionId": "00000000-0000-0000-0000-000000000000",
            "requisitionNo": "string",
            "lineItemNo": "integer (int32)",
            "inventoryNo": "string",
            "inventoryDescription": "string",
            "vendorItemNo": "string",
            "lineItemTypeId": "integer (int32)",
            "lineItemType": "string",
            "quantity": "integer (int32)",
            "uom": "string",
            "conversionFactor": "integer (int32)",
            "price": "number (double)",
            "inventoryLocationId": "00000000-0000-0000-0000-000000000000",
            "notes": "string",
            "manufacturerId": "00000000-0000-0000-0000-000000000000",
            "manufacturerItemNo": "string",
            "suggestedVendorId": "00000000-0000-0000-0000-000000000000",
            "stockUOM": "string",
            "vendorId": "00000000-0000-0000-0000-000000000000",
            "poConversionStatusId": "integer (int32)",
            "poConversionStatus": "string",
            "purchaseOrderItemId": "00000000-0000-0000-0000-000000000000",
            "inventoryVendorId": "00000000-0000-0000-0000-000000000000",
            "activeStatus": "boolean",
            "dateCreated": "string (date-time)",
            "createdBy": "00000000-0000-0000-0000-000000000000",
            "createdByUserName": "string",
            "lastUpdated": "string (date-time)",
            "lastUpdatedBy": "00000000-0000-0000-0000-000000000000",
            "lastUpdatedByUserName": "string",
            "locationId": "00000000-0000-0000-0000-000000000000",
            "isTaxable": "boolean",
            "contractNo": "string",
            "contractExpDate": "string (date-time)",
            "isPrinted": "boolean",
            "supplierPartAuxiliaryId": "string"
        }
    ],
    "@odata.nextLink": "link"
}  
```

## Get the specified Requisition Item

### Path
GET /odata/RequisitionItems({requisitionItemId})

### Description
Returns the details of the Requisition Item specified by ID.

### Request parameters
|  <div style="width:200px">Parameter</div>  |  <div style="width:380px">Explanation</div>  |                      
|-----:|:-------|
|**requisitionItemId**: string *(uuid)* <br> <span style="color: #F05D30">**required**</span> <br> *in path* | Enter the ID of the Requisition Item here. |
|**api-version**: string default: 1.0 <br> *in header*| The requested API version.|   
|**Authorization**: string default: <br> Bearer access_token <br> *in header* |Specify the type of the token (bearer) and then insert the ```access_token```, which was obtained during authentication. |

### Responses
| <div style="width:200px">Response </div>|<div style="width:420px">Explanation</div>|                      
|-----:|:-------|
|**200 OK**|OK|      
|**400 Bad Request**| Incorrect input data or organization ID does not match with the organization ID user is logged in.|
|**401 Unauthorized**| Incorrect specified ```access_token``` or ```access_token``` got expired.|
|**403 Forbidden**| User doesn’t have appropriate privileges.|
|**404 Not Found** | Specified ID is absent in the system.|
|**500 Internal Server Error**|Server encountered an unexpected condition that prevented it from fulfilling the request.|

### Properties
|<div style="width:200px">Property </div> |<div style="width:420px">Explanation</div>|                      
|-----:|:-------|
|**requisitionItemId**: string *(uuid)* | Unique Identifier of the Requisition Item |
|**requisitionId**: string *(uuid)* | Unique Identifier of the Requisition |
|**requisitionNo**: string | Identification code of the Requisition |
|**lineItemNo**: integer *(int32)* | Number of the Line Item |
|**inventoryNo**: string | Identification code of the Inventory Item |
|**inventoryDescription**: string | Description of the Inventory Item |
|**vendorItemNo**: string | Code that is used by the Vendor for the Item identification |
|**lineItemTypeId**: integer *(int32)* | Unique Identifier of the Line Item Type |
|**lineItemType**: string | Type of the Line Item |
|**quantity**: integer *(int32)* | Quantity specified in the Line Items |
|**UOM**: string | Unit of Measure |
|**conversionFactor**: <br> integer *(int32)* | Number of Stock Keeping Units in another Unit of Measure |
|**price**: number *(double)* | Price of the Line Item |
|**inventoryLocationId**: <br> string *(uuid)* | Unique Identifier of the Inventory Location |
|**notes**: string | Comments about the Requisition Item |
|**manufacturerId**: string *(uuid)* | Unique Identifier of the Manufacturer |
|**manufacturerItemNo**: string | Item Number of the Manufacturer |
|**suggestedVendorId**: <br> string *(uuid)* | Suggested Unique Identifier of the Vendor |
|**stockUOM**: string | Unit of Measure to track Inventory Balance |
|**vendorId**: string *(uuid)* | Unique Identifier of the Vendor |
|**poConversionStatusId**: <br> integer *(int32)* | Unique Identifier of Purchase Order Conversion Status |
|**poConversionStatus**: string | Conversion Status of Purchase Order |
|**purchaseOrderItemId**: <br> string *(uuid)* | Unique Identifier of the Purchase Order Item |
|**inventoryVendorId**: string *(uuid)* | Unique Identifier of the Inventory Item Vendor |
|**activeStatus**: boolean | Is the Requisition Item active or not? |
|**dateCreated**: string *(date-time)* | Date when the Requisition Item was created |
|**createdBy**: string *(uuid)* | Unique Identifier of the user who created the Requisition Item |
|**createdByUserName**: string | Name of the user who created the Requisition Item |
|**lastUpdated**: string *(date-time)* | Last Date when the Requisition Item was updated |
|**lastUpdatedBy**: string *(uuid)* | Unique Identifier of the last user who updated the Requisition Item |
|**lastUpdatedByUserName**: <br> string | Name of the last user who updated the Requisition Item |
|**locationId**: string *(uuid)* | Unique Identifier of the Location |
|**isTaxable**: boolean | Is the Location Taxable or not? |
|**contractNo**: string | Number of the Contract |
|**contractExpDate**: string <br> *(date-time)* | Expiration Date of the Contract |
|**isPrinted**: boolean | Is the Pick Ticket printed or not? |
|**supplierPartAuxiliaryId**: string | Unique Identifier of the Supplier Part Auxiliary |


``` json title="Response Content-types: APPLICATION/JSON, APPLICATION/XML<br>Response example (200 OK)"
{
    "@odata.context": "link",
    "requisitionItemId": "00000000-0000-0000-0000-000000000000",
    "requisitionId": "00000000-0000-0000-0000-000000000000",
    "requisitionNo": "string",
    "lineItemNo": "integer (int32)",
    "inventoryNo": "string",
    "inventoryDescription": "string",
    "vendorItemNo": "string",
    "lineItemTypeId": "integer (int32)",
    "lineItemType": "string",
    "quantity": "integer (int32)",
    "uom": "string",
    "conversionFactor": "integer (int32)",
    "price": "number (double)",
    "inventoryLocationId": "00000000-0000-0000-0000-000000000000",
    "notes": "string",
    "manufacturerId": "00000000-0000-0000-0000-000000000000",
    "manufacturerItemNo": "string",
    "suggestedVendorId": "00000000-0000-0000-0000-000000000000",
    "stockUOM": "string",
    "vendorId": "00000000-0000-0000-0000-000000000000",
    "poConversionStatusId": "integer (int32)",
    "poConversionStatus": "string",
    "purchaseOrderItemId": "00000000-0000-0000-0000-000000000000",
    "inventoryVendorId": "00000000-0000-0000-0000-000000000000",
    "activeStatus": "boolean",
    "dateCreated": "string (date-time)",
    "createdBy": "00000000-0000-0000-0000-000000000000",
    "createdByUserName": "string",
    "lastUpdated": "string (date-time)",
    "lastUpdatedBy": "00000000-0000-0000-0000-000000000000",
    "lastUpdatedByUserName": "string",
    "locationId": "00000000-0000-0000-0000-000000000000",
    "isTaxable": "boolean",
    "contractNo": "string",
    "contractExpDate": "string (date-time)",
    "isPrinted": "boolean",
    "supplierPartAuxiliaryId": "string"
}
```

## Add the specified Requisition Line Item

### Path
POST /odata/Requisitions({requisitionID})/RequisitionItems

### Description
Adds a new Requisition Line Item within the logged-in organization and the specified Requisition (applicable only for the **Standard** Requisition type).

### Request body
For adding item(s) to requisition(s)

|  <div style="width:200px">Parameter</div>  |  <div style="width:420px">Explanation</div>  |                      
|-----:|:-------|
|**inventoryNo**: string | Identification code of the Inventory. <br> It is validated by Facility (Inventory Group). <br> **If not provided**: Item is added as Free-Form. |
|**inventoryDescription**: string | Inventory Description of the Requisition Line Item. <br> It is populated from matched Inventory if it is mapped with Inventory Vendor by ```vendor```, ```vendorItemNo```, ```uom```, and ```facility```. <br> **Optional**: for Item that matches Inventory Master. <br> **Required**: for Free-Form.|
|**vendorItemNo**: string | Code that is used by the Vendor for the Item identification. <br> It is matched with appropriate Inventory Vendor data. |
|**quantity**: <br> integer *(int32)* <br> <span style="color: #F05D30">**required**</span> | Quantity specified in the Line Items |
|**uom**: string <br> <span style="color: #F05D30">**required**</span> | Unit of Measure. <br> It is matched with appropriate Inventory Vendor data. |
|**conversionFactor**: <br> integer *(int32)* <br> <span style="color: #F05D30">**required**</span> | Number of Stock Keeping Units in another Unit of Measure. <br> It is populated from appropriate Inventory UOM Conversion Factor if Item is added as Inventory Item and the specified UOM value is matched with Inventory UOM. |
|**price**: string | Price. <br> It is populated from matched Inventory Location if it exists. <br> If Inventory Location doesn't exist, it is populated from matched Inventory Vendor. <br> If it isn't matched with Inventory Vendor, then is populated from the request. <br> **If not provided for the Free-Form type**: the **0** value will be set by default. |
|**notes**: string | Comments about Requisition Items. <br> It is empty by default if is matched with appropriate Inventory Vendor data. <br> It is populated from the request if is added as Free-Form. |
|**manufacturerNo**: string | Number of the Manufacturer. <br> It is populated from matched Inventory Vendor. <br> It is populated from matched Manufacturer if it is added as Free-Form.|
|**manufacturerItemNo**: string | Item Number of the Manufacturer. <br> It is populated from matched Inventory Vendor. <br> It is populated from the request if it is added as Free-Form. |
|**vendorNo**: string <br> <span style="color: #F05D30">**required**</span> | Code of the Supplier who sells products |
|**locationNo**: string | Identification Number of the Location. <br> It is populated from mapped Inventory Location.<br> If Inventory Location doesn't exist, ```none``` by default for Item mapped with Inventory Vendor. <br> For **Free-Form**—the Location is added in the request. <br> If Item is added as Free-From but its Facility differs from RequisitionFacility, then ```locationNo``` is required.
|**facilityNo**: string <br> <span style="color: #F05D30">**required**</span> | Identification Number of the Facility |
|**isTaxable**: boolean | Is Requisiton Item Taxable or not? <br> It is populated from Inventory Location if Item is mapped with Inventory Vendor. <br> If Inventory Location doesn't exist, ```no``` by default for Item mapped with Inventory Vendor. <br> For **Free-Form**—```no``` by default.

``` json title="Request Content-types: APPLICATION/JSON, APPLICATION/XML <br> Request Example"
{
    "inventoryNo": "string",
    "inventoryDescription": "string",
    "vendorItemNo": "string",
    "quantity": "integer (int32)",
    "uom": "string",
    "conversionFactor": "integer (int32)",
    "price": "string",
    "notes": "string",
    "manufacturerNo": "string",
    "manufacturerItemNo": "string",
    "vendorNo": "string",
    "locationNo": "string",
    "facilityNo": "string",
    "isTaxable": "boolean",
}
```

### Request parameters
|  <div style="width:200px">Parameter</div>  |  <div style="width:380px">Explanation</div>  |                      
|-----:|:-------|
|**requisitionId**: string *(uuid)* <br> <span style="color: #F05D30">**required**</span> <br> *in path* | Enter the ID of the Requisition here. |
|**api-version**: string default: 1.0 <br> *in header*| The requested API version.|   
|**Authorization**: string default: <br> Bearer access_token <br> *in header* |Specify the type of the token (bearer) and then insert the ```access_token```, which was obtained during authentication. |

### Responses
| <div style="width:200px">Response </div>|<div style="width:420px">Explanation</div>|                      
|-----:|:-------|
|**200 OK**|OK|      
|**400 Bad Request**|Incorrect input data or organization ID does not match with the organization ID user is logged in.|
|**400 Bad Request** | The limit for the ```$top``` query has been exceeded. The value from the incoming request is 'N' (N is your value from the request). You can find the data on the current limit [here](Options_and_Limitations.md#top-and-skip).
|**401 Unauthorized**|Incorrect specified ```access_token``` or ```access_token``` got expired.|
|**403 Forbidden**|User doesn’t have appropriate privileges.|
|**500 Internal Server Error**|Server encountered an unexpected condition that prevented it from fulfilling the request.|

``` json title="Response Content-types: APPLICATION/JSON, APPLICATION/XML<br>Response Example (200 OK)"
"00000000-0000-0000-0000-000000000000"

```

## Partially update the specified Requisition Item

### Path
PATCH /odata/RequisitionItems({requisitionItemId})

### Description
Partially updates the details of the Requisition Line Item specified by ID (applicable only for the **Standard** Requisition type).

### Properties
For Inventory Item (Item with Location and Vendor):

|<div style="width:200px">Property </div> |<div style="width:420px">Explanation</div>|                      
|-----:|:-------|
|**activeStatus**: boolean | Is the Requisition Item active or not? |
|**notes**: string | Comments about the Requisition Item |
|**quantity**: integer *(int8)* | Quantity specified in the Line Items |
|**uom**: string | Unit of Measure |
|**conversionFactor**: integer *(int8)* | Number of Stock Keeping Units in another Unit of Measure |
|**price**: number *(double)* | Price of the Line Item |

``` json title="Request Content-types: APPLICATION/JSON, APPLICATION/XML<br>Request example (200 OK)"
{
    "activeStatus": "boolean",
    "notes": "string",
    "quantity": "integer (int8)",
    "uom": "string",
    "conversionFactor": "integer (int8)",
    "price": "number (double)"
}  
```
<br>

For Non-Stock Item (Item with Vendor):

|<div style="width:200px">Property </div> |<div style="width:420px">Explanation</div>|                      
|-----:|:-------|
|**locationId**: string *(uuid)* | Unique Identifier of the Location |
|**activeStatus**: boolean | Is the Requisition Item active or not? |
|**notes**: string | Comments about the Requisition Item |
|**quantity**: integer *(int8)* | Quantity specified in the Line Items |
|**uom**: string | Unit of Measure |
|**conversionFactor**: integer *(int8)* | Number of Stock Keeping Units in another Unit of Measure |
|**price**: number *(double)* | Price of the Line Item |

``` json title="Request Content-types: APPLICATION/JSON, APPLICATION/XML<br>Request Example (200 OK)"
{
    "locationId": "00000000-0000-0000-0000-000000000000",
    "activeStatus": "boolean",
    "notes": "string",
    "quantity": "integer (int8)",
    "uom": "string",
    "conversionFactor": "integer (int8)",
    "price": "number (double)"
} 
```

<br>

For Free-Form Item:

|<div style="width:200px">Property </div> |<div style="width:420px">Explanation</div>|                      
|-----:|:-------|
|**inventoryNo**: string | Identification code of the Inventory Item |
|**inventoryDescription**: string | Description of the Inventory Item |
|**locationId**: string *(uuid)* | Unique Identifier of the Location |
|**vendorId**: string *(uuid)* | Unique Identifier of the Vendor |
|**vendorItemNo**: string | Code that is used by the Vendor for the Item identification |
|**manufacturerId**: string *(uuid)* | Unique Identifier of the Manufacturer |
|**manufacturerItemNo**: string | Item Number of the Manufacturer |
|**activeStatus**: boolean | Is the Requisition Item active or not? |
|**notes**: string | Comments about the Requisition Item |
|**quantity**: integer *(int8)* | Quantity specified in the Line Items |
|**uom**: string | Unit of Measure |
|**conversionFactor**: integer *(int8)* | Number of Stock Keeping Units in another Unit of Measure |
|**price**: number *(double)* | Price of the Line Item |
|**isTaxable**: boolean | Is Requisiton Item taxable or not? |


``` json title="Request Content-types: APPLICATION/JSON, APPLICATION/XML<br>Request Example (200 OK)"
{
    "inventoryNo": "string",
    "inventoryDescription": "string",
    "locationId": "00000000-0000-0000-0000-000000000000",
    "vendorId": "00000000-0000-0000-0000-000000000000",
    "vendorItemNo": "string",
    "manufacturerId": "00000000-0000-0000-0000-000000000000",
    "manufacturerItemNo": "string",
    "activeStatus": "boolean",
    "notes": "string",
    "quantity": "integer (int8)",
    "uom": "string",
    "conversionFactor": "integer (int8)",
    "price": "number (double)",
    "isTaxable": "boolean"
}
```  

### Request parameters
|  <div style="width:200px">Parameter</div>  |  <div style="width:380px">Explanation</div>  |                      
|-----:|:-------|
|**requisitionItemId**: string *(uuid)* <br> <span style="color: #F05D30">**required**</span> <br> *in path* | Enter the ID of the Requisition Item here. |
|**api-version**: string default: 1.0 <br> *in header*| The requested API version.|   
|**Authorization**: string default: <br> Bearer access_token <br> *in header* |Specify the type of the token (bearer) and then insert the ```access_token```, which was obtained during authentication. |


### Responses
| <div style="width:200px">Response </div>|<div style="width:420px">Explanation</div>|                      
|-----:|:-------|
|**200 OK**|OK|      
|**400 Bad Request**|Incorrect input data or organization ID does not match with the organization ID user is logged in.|
|**401 Unauthorized**|Incorrect specified ```access_token``` or ```access_token``` got expired.|
|**403 Forbidden**|User doesn’t have appropriate privileges.|
|**404 Not Found** | Specified ID is absent in the system. |
|**500 Internal Server Error**|Server encountered an unexpected condition that prevented it from fulfilling the request.|