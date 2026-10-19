# PurchaseOrderItems

## Get the list of Purchase Order Items

### Path
GET /odata/PurchaseOrderItems

### Description
Returns a paged list of existing Purchase Order items within the logged-in organization. 

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

| Parameter| Explanation |                      
|-----:|:-------|
|**api-version**: string default: 1.0 <br> *in header*| The requested API version.|
|**$search**: string <br> *in query*  | Searches across all supported fields. |
|**$filter**: string <br> *in query* | Filters results based on a Boolean condition.|
|**$orderby**: string <br> *in query* | Sorts results.|
|**$top**: string  <br> *in query* | Returns only the first n results.|
|**$skip**: string <br> *in query*| Skips the first n results.|
|**Authorization**: string default: <br> Bearer access_token <br> *in header* | Specify the type of the token (bearer) and insert the ```access_token``` obtained during authentication. |

### Responses
| Response | Explanation |                      
|-----:|:-------|
|**200 OK**| OK | 
|**400 Bad Request**| The request contains incorrect input data. |         
|**400 Bad Request** | The limit for the ```$top``` query has been exceeded. The value from the incoming request is 'N' (N is your value from the request). You can find the data on the current limit [here](Options_and_Limitations.md#top-and-skip). |
|**401 Unauthorized**| The specified ```access_token``` is invalid or has expired. |
|**403 Forbidden**| The user doesn't have the appropriate privileges. |
|**500 Internal Server Error**| The server encountered an unexpected condition that prevented it from fulfilling the request.|

### Properties
| Property | Explanation |                      
|-----:|:-------|
|**purchaseOrderItemId**: string *(uuid)* | Unique identifier of the Purchase Order item |
|**purchaseOrderNo**: string | Number of the Purchase Order |
|**sequenceNo**: integer *(int32)* | Sequence number |
|**purchaseOrderId**: string *(uuid)* | Unique identifier of the Purchase Order |
|**facilityId**: string *(uuid)* | Unique identifier of the Facility |
|**facilityNo**: string | Identification number of the Facility |
|**facilityName**: string | Name of the Facility |
|**lineItemNo**: integer *(int32)* | Number of the line item |
|**locationNo**: string | Identification number of the Location |
|**locationName**: string | Name of the Location |
|**inventoryLocationId**: string *(uuid)* | Unique identifier of the Inventory Location |
|**inventoryVendorId**: string *(uuid)* | Unique identifier of the Inventory Vendor |
|**vendorNo**: string | Number of the Vendor |
|**vendorName**: string | Name of the Vendor |
|**vendorPriority**: integer *(int32)* | Priority of the Vendor |
|**inventoryNo**: string | Identification number of the Inventory item |
|**classificationId**: string *(uuid)* | Unique identifier of the Inventory Category defined at the Organization level |
|**classificationName**: string | Name of the Inventory Category defined at the Organization level |
|**classification2Id**: string *(uuid)* | Unique identifier of the second Inventory Category defined at the Organization level |
|**classification2Name**: string | Name of the second Inventory Category defined at the Organization level |
|**inventoryDescription**: string | Description of the Inventory item |
|**vendorItemNo**: string | Item number defined by the Vendor |
|**manufacturerId**: string *(uuid)* | Unique identifier of the Manufacturer |
|**manufacturerNo**: string | Number of the Manufacturer |
|**manufacturerName**: string | Name of the Manufacturer |
|**manufacturerItemNo**: string | Item number defined by the Manufacturer |
|**orderQuantity**: integer *(int32)* | Quantity specified in the Purchase Order |
|**orderUOM**: string | Unit of Measure specified in the Purchase Order |
|**orderConversionFactor**: integer <br> *(int32)* | Conversion factor of the Purchase Order |
|**stockUOM**: string | Unit of Measure used to track Inventory balance |
|**unitCost**: number *(double)* | Unit cost of the Purchase Order item |
|**departmentGLCode**: string | General Ledger code of the Department |
|**glCode**: string | General Ledger code |
|**lineItemTypeId**: integer *(int32)* | Unique identifier of the line item type |
|**itemType**: string | Type of the line item |
|**lineItemNotes**: string | Notes about the line item |
|**contractNo**: string | Number of the Contract |
|**contractExpDate**: string *(date-time)* | Expiration date of the Contract |
|**lastUpdated**: string *(date-time)* | Date when the Purchase Order item was last updated |
|**lastUpdatedBy**: string *(uuid)* | Unique identifier of the user who last updated the Purchase Order item |
|**lastUpdatedByUserName**: string | Name of the user who last updated the Purchase Order item |
|**dateCreated**: string *(date-time)* | Date when the Purchase Order item was created |
|**createdBy**: string *(uuid)* | Unique identifier of the user who created the Purchase Order item |
|**createdByUserName**: string | Name of the user who created the Purchase Order item |
|**isTaxable**: boolean | Is the Purchase Order item taxable or not? |
|**returnPOItemId**: string *(uuid)* | Unique identifier of the Return PO item |
|**internalNotes**: string | Internal notes about the Purchase Order item |
|**lotNo**: string | Lot number assigned to the item |
|**serialNo**: string | Serial number assigned to uniquely identify the item |
|**expirationDate**: string <br> *(date-time)* | Expiration date of the item |
|**activeStatus**: boolean | Is the Purchase Order item Active or not? |
|**activeStatusLastUpdated**: string <br> *(date-time)* | Last date when the Active status of the Purchase Order item was updated |
|**activeStatusLastUpdatedBy**: <br> string *(uuid)* | Unique identifier of the last user who updated the Active status of the Purchase Order item |
|**activeStatusLastUpdatedBy<br>UserName**: string | Name of the last user who updated the Active status of the Purchase Order item |
|**supplierPartAuxiliaryID**: string | Unique identifier of the Supplier Part Auxiliary |
|**submittedUnitCost**: number *(double)* | Unit cost submitted for the Purchase Order item |
|**departmentId**: string *(uuid)* | Unique identifier of the Department |
|**departmentNo**: string | Number of the Department |
|**departmentName**: string | Name of the Department |
|**poUdfLabels**: string | User-Defined Field labels for the Purchase Order.  <br> **Note**: See the [poUdfLabels](PurchaseOrders.md#poudflabels) section for more details. |
|**consignmentOrder**: boolean | Is the Purchase Order a Consignment order or not? |
|**consignmentSerialNo**: string | Consignment serial number of the line item |

``` json title="Response example (200 OK)"
{
    "@odata.context": "link",
    "@odata.count": "number",
    "value": [
        {
            "purchaseOrderItemId": "00000000-0000-0000-0000-000000000000",
            "purchaseOrderNo": "string",
            "sequenceNo": "integer (int32)",
            "purchaseOrderId": "00000000-0000-0000-0000-000000000000",
            "facilityId": "00000000-0000-0000-0000-000000000000",
            "facilityNo": "string",
            "facilityName": "string",
            "lineItemNo": "integer (int32)",
            "locationNo": "string",
            "locationName": "string",
            "inventoryLocationId": "00000000-0000-0000-0000-000000000000",
            "inventoryVendorId": "00000000-0000-0000-0000-000000000000",
            "vendorNo": "string",
            "vendorName": "string",
            "vendorPriority": "integer (int32)",
            "inventoryNo": "string",
            "classificationId": "00000000-0000-0000-0000-000000000000",
            "classificationName": "string",
            "classification2Id": "00000000-0000-0000-0000-000000000000",
            "classification2Name": "string",
            "inventoryDescription": "string",
            "vendorItemNo": "string",
            "manufacturerId": "00000000-0000-0000-0000-000000000000",
            "manufacturerNo": "string",
            "manufacturerName": "string",
            "manufacturerItemNo": "string",
            "orderQuantity": "integer (int32)",
            "orderUOM": "string",
            "orderConversionFactor": "integer (int32)",
            "stockUOM": "string",
            "unitCost": "number (double)",
            "departmentGLCode": "string",
            "glCode": "string",
            "lineItemTypeId": "integer (int32)",
            "itemType": "string",
            "lineItemNotes": "string",
            "contractNo": "string",
            "contractExpDate": "string (date-time)",
            "lastUpdated": "string (date-time)",
            "lastUpdatedBy": "00000000-0000-0000-0000-000000000000",
            "lastUpdatedByUserName": "string",
            "dateCreated": "string (date-time)",
            "createdBy": "00000000-0000-0000-0000-000000000000",
            "createdByUserName": "string",
            "isTaxable": "boolean",
            "returnPOItemId": "00000000-0000-0000-0000-000000000000",
            "internalNotes": "string",
            "lotNo": "string",
            "serialNo": "string",
            "expirationDate": "string (date-time)",
            "activeStatus": "boolean",
            "activeStatusLastUpdated": "string (date-time)",
            "activeStatusLastUpdatedBy": "00000000-0000-0000-0000-000000000000",
            "activeStatusLastUpdatedByUserName": "string",
            "supplierPartAuxiliaryID": "string",
            "submittedUnitCost": "number (double)",
            "departmentId": "00000000-0000-0000-0000-000000000000",
            "departmentNo": "string",
            "departmentName": "string",
            "poUdfLabels": "[{\"Name\":\"string1\",\"Value\":\"string2\"}]",
            "consignmentOrder": "boolean",
            "consignmentSerialNo": "string"
        }
    ],
    "@odata.nextLink": "link"
}
```

## Get the specified Purchase Order Item 

### Path
GET /odata/PurchaseOrderItems({purchaseOrderItemId})

### Description
Returns the details of the Purchase Order Item specified by ID.

### Request parameters
| Parameter  | Explanation |                      
|-----:|:-------|
|**purchaseOrderItemId**: string *(uuid)*  <br> <span style="color: #F05D30">**required**</span> <br> *in path* | Enter the ID of the Purchase Order Item. |
|**api-version**: string default: 1.0 <br> *in header*| The requested API version.|   
|**Authorization**: string default: <br> Bearer access_token <br> *in header* | Specify the type of the token (bearer) and insert the ```access_token``` obtained during authentication. |

### Responses
| Response | Explanation |                      
|-----:|:-------|
|**200 OK**| OK | 
|**400 Bad Request**| The request contains incorrect input data. |         
|**401 Unauthorized**| The specified ```access_token``` is invalid or has expired. |
|**403 Forbidden**| The user doesn’t have the appropriate privileges. |
|**404 Not Found** | The specified ID is absent in the system. |
|**500 Internal Server Error**| The server encountered an unexpected condition that prevented it from fulfilling the request.|

### Properties
| Property | Explanation |                      
|-----:|:-------|
|**purchaseOrderItemId**: string *(uuid)* | Unique identifier of the Purchase Order item |
|**purchaseOrderNo**: string | Number of the Purchase Order |
|**sequenceNo**: integer *(int32)* | Sequence number |
|**purchaseOrderId**: string *(uuid)* | Unique identifier of the Purchase Order |
|**facilityId**: string *(uuid)* | Unique identifier of the Facility |
|**facilityNo**: string | Identification number of the Facility |
|**facilityName**: string | Name of the Facility |
|**lineItemNo**: integer *(int32)* | Number of the line item |
|**locationNo**: string | Identification number of the Location |
|**locationName**: string | Name of the Location |
|**inventoryLocationId**: string *(uuid)* | Unique identifier of the Inventory Location |
|**inventoryVendorId**: string *(uuid)* | Unique identifier of the Inventory Vendor |
|**vendorNo**: string | Number of the Vendor |
|**vendorName**: string | Name of the Vendor |
|**vendorPriority**: integer *(int32)* | Priority of the Vendor |
|**inventoryNo**: string | Identification number of the Inventory item |
|**classificationId**: string *(uuid)* | Unique identifier of the Inventory Category defined at the Organization level |
|**classificationName**: string | Name of the Inventory Category defined at the Organization level |
|**classification2Id**: string *(uuid)* | Unique identifier of the second Inventory Category defined at the Organization level |
|**classification2Name**: string | Name of the second Inventory Category defined at the Organization level |
|**inventoryDescription**: string | Description of the Inventory item |
|**vendorItemNo**: string | Item number defined by the Vendor |
|**manufacturerId**: string *(uuid)* | Unique identifier of the Manufacturer |
|**manufacturerNo**: string | Number of the Manufacturer |
|**manufacturerName**: string | Name of the Manufacturer |
|**manufacturerItemNo**: string | Item number defined by the Manufacturer |
|**orderQuantity**: integer *(int32)* | Quantity specified in the Purchase Order |
|**orderUOM**: string | Unit of Measure specified in the Purchase Order |
|**orderConversionFactor**: integer <br> *(int32)* | Conversion factor of the Purchase Order |
|**stockUOM**: string | Unit of Measure used to track Inventory balance |
|**unitCost**: number *(double)* | Unit cost of the Purchase Order item |
|**departmentGLCode**: string | General Ledger code of the Department |
|**glCode**: string | General Ledger code |
|**lineItemTypeId**: integer *(int32)* | Unique identifier of the line item type |
|**itemType**: string | Type of the line item |
|**lineItemNotes**: string | Notes about the line item |
|**contractNo**: string | Number of the Contract |
|**contractExpDate**: string *(date-time)* | Expiration date of the Contract |
|**lastUpdated**: string *(date-time)* | Date when the Purchase Order item was last updated |
|**lastUpdatedBy**: string *(uuid)* | Unique identifier of the user who last updated the Purchase Order item |
|**lastUpdatedByUserName**: string | Name of the user who last updated the Purchase Order item |
|**dateCreated**: string *(date-time)* | Date when the Purchase Order item was created |
|**createdBy**: string *(uuid)* | Unique identifier of the user who created the Purchase Order item |
|**createdByUserName**: string | Name of the user who created the Purchase Order item |
|**isTaxable**: boolean | Is the Purchase Order item taxable or not? |
|**returnPOItemId**: string *(uuid)* | Unique identifier of the Return PO item |
|**internalNotes**: string | Internal notes about the Purchase Order item |
|**lotNo**: string | Lot number assigned to the item |
|**serialNo**: string | Serial number assigned to uniquely identify the item |
|**expirationDate**: string <br> *(date-time)* | Expiration date of the item |
|**activeStatus**: boolean | Is the Purchase Order item Active or not? |
|**activeStatusLastUpdated**: string <br> *(date-time)* | Last date when the Active status of the Purchase Order item was updated |
|**activeStatusLastUpdatedBy**: <br> string *(uuid)* | Unique identifier of the last user who updated the Active status of the Purchase Order item |
|**activeStatusLastUpdatedBy<br>UserName**: string | Name of the last user who updated the Active status of the Purchase Order item |
|**supplierPartAuxiliaryID**: string | Unique identifier of the Supplier Part Auxiliary |
|**submittedUnitCost**: number *(double)* | Unit cost submitted for the Purchase Order item |
|**departmentId**: string *(uuid)* | Unique identifier of the Department |
|**departmentNo**: string | Number of the Department |
|**departmentName**: string | Name of the Department |
|**poUdfLabels**: string | User-Defined Field labels for the Purchase Order. <br> **Note**: See the [poUdfLabels](PurchaseOrders.md#poudflabels) section for more details. |
|**consignmentOrder**: boolean | Is the Purchase Order a Consignment order or not? |
|**consignmentSerialNo**: string | Consignment serial number of the line item |

``` json title="Response example (200 OK)"
{
    "@odata.context": "link",
    "purchaseOrderItemId": "00000000-0000-0000-0000-000000000000",
    "purchaseOrderNo": "string",
    "sequenceNo": "integer (int32)",
    "purchaseOrderId": "00000000-0000-0000-0000-000000000000",
    "facilityId": "00000000-0000-0000-0000-000000000000",
    "facilityNo": "string",
    "facilityName": "string",
    "lineItemNo": "integer (int32)",
    "locationNo": "string",
    "locationName": "string",
    "inventoryLocationId": "00000000-0000-0000-0000-000000000000",
    "inventoryVendorId": "00000000-0000-0000-0000-000000000000",
    "vendorNo": "string",
    "vendorName": "string",
    "vendorPriority": "integer (int32)",
    "inventoryNo": "string",
    "classificationId": "00000000-0000-0000-0000-000000000000",
    "classificationName": "string",
    "classification2Id": "00000000-0000-0000-0000-000000000000",
    "classification2Name": "string",
    "inventoryDescription": "string",
    "vendorItemNo": "string",
    "manufacturerId": "00000000-0000-0000-0000-000000000000",
    "manufacturerNo": "string",
    "manufacturerName": "string",
    "manufacturerItemNo": "string",
    "orderQuantity": "integer (int32)",
    "orderUOM": "string",
    "orderConversionFactor": "integer (int32)",
    "stockUOM": "string",
    "unitCost": "number (double)",
    "departmentGLCode": "string",
    "glCode": "string",
    "lineItemTypeId": "integer (int32)",
    "itemType": "string",
    "lineItemNotes": "string",
    "contractNo": "string",
    "contractExpDate": "string (date-time)",
    "lastUpdated": "string (date-time)",
    "lastUpdatedBy": "00000000-0000-0000-0000-000000000000",
    "lastUpdatedByUserName": "string",
    "dateCreated": "string (date-time)",
    "createdBy": "00000000-0000-0000-0000-000000000000",
    "createdByUserName": "string",
    "isTaxable": "boolean",
    "returnPOItemId": "00000000-0000-0000-0000-000000000000",
    "internalNotes": "string",
    "lotNo": "string",
    "serialNo": "string",
    "expirationDate": "string (date-time)",
    "activeStatus": "boolean",
    "activeStatusLastUpdated": "string (date-time)",
    "activeStatusLastUpdatedBy": "00000000-0000-0000-0000-000000000000",
    "activeStatusLastUpdatedByUserName": "string",
    "supplierPartAuxiliaryID": "string",
    "submittedUnitCost": "number (double)",
    "departmentId": "00000000-0000-0000-0000-000000000000",
    "departmentNo": "string",
    "departmentName": "string",
    "poUdfLabels": "[{\"Name\":\"string1\",\"Value\":\"string2\"}]",
    "consignmentOrder": "boolean",
    "consignmentSerialNo": "string"
}
```

## Add new items to an existing Purchase Order in bulk

### Path
POST /odata/PurchaseOrders({purchaseOrderId})/BulkAddPurchaseOrderItems

### Description
Adds new items to an existing Purchase Order in bulk within the logged-in organization.

### Request body
| Parameter | Explanation |                      
|-----:|:-------|
|**inventoryNo**: string | Identification number of the Inventory item |
|**inventoryDescription**: string | Description of the Inventory item |
|**vendorItemNo**: string | Item number defined by the Vendor |
|**manufacturerNo**: string | Number of the Manufacturer |
|**manufacturerItemNo**: string | Item number defined by the Manufacturer |
|**orderQuantity**: integer *(int32)* | Quantity specified in the Purchase Order |
|**orderUOM**: string | Unit of Measure specified in the Purchase Order |
|**orderConversionFactor**: integer <br> *(int32)* | Conversion factor of the Purchase Order |
|**unitCost**: number *(double)* | Unit cost of the Purchase Order item |
|**lineItemNotes**: string | Notes about the line item |
|**internalNotes**: string | Internal notes about the Purchase Order item |
|**departmentGLCode**: string | General Ledger code of the Department |
|**glCode**: string | General Ledger code |
|**isTaxable**: boolean | Is the Purchase Order item taxable or not? |
|**consignmentSerialNo**: string | Consignment serial number of the line item |

``` json title="Request example"
{
  "purchaseOrderItems": [
    {
      "inventoryNo": "string",
      "inventoryDescription": "string",
      "vendorItemNo": "string",
      "manufacturerNo": "string",
      "manufacturerItemNo": "string",
      "orderQuantity": "integer (int32)",
      "orderUOM": "string",
      "orderConversionFactor": "integer (int32)",
      "unitCost": "number (double)",
      "lineItemNotes": "string",
      "internalNotes": "string",
      "departmentGLCode": "string",
      "glCode": "string",
      "isTaxable": "boolean",
      "consignmentSerialNo": "string"
    }
  ]
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
|**200 OK**| OK | 
|**400 Bad Request**| The request contains incorrect input data. |         
|**401 Unauthorized**| The specified ```access_token``` is invalid or has expired. |
|**403 Forbidden**| The user doesn't have the appropriate privileges. |
|**500 Internal Server Error**| The server encountered an unexpected condition that prevented it from fulfilling the request.|


``` json title="Response example"
{
  "value": [
    "00000000-0000-0000-0000-000000000001",
    "00000000-0000-0000-0000-000000000002"
  ]
}
```