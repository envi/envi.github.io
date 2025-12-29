# AdjustmentItems

## Get the list of Adjustment Items

### Path
GET /odata/AdjustmentItems

### Description
Returns a paged list of existing items within all Adjustments. 

!!! note

    You can filter the results as follows:

    - For an exact match, use: ```$filter parameter–entity eq ‘string’```
    - For a partial match, use: ```$filter=contains parameter–contains(entity, ‘string’)```


!!! note
    
    This endpoint does not support logical operators (**and**, **or**, **in**, **gt**, **ge**, **lt**, **le**) for data filtering.

### Request parameters
|  <div style="width:200px">Parameter</div>  |  <div style="width:420px">Explanation</div>  |                      
|-----:|:-------|
|**from**: string *(date-time)* <br> *in query* | Enter the start date. |
|**to**: string *(date-time)* <br> *in query* | Enter the end date. |
|**api-version**: string default: 1.0 <br> *in header*| The requested API version. |         
|**$search**: string <br> *in query*  | Searches across all supported fields.|  
|**$filter**: string <br> *in query* | Filters results based on a Boolean condition.|
|**$orderby**: string <br> *in query* | Sorts results.|
|**$top**: string  <br> *in query* | Returns only the first n results.|
|**$skip**: string <br> *in query*| Skips the first n results.|
|**Authorization**: string default: <br> Bearer access_token <br> *in header* | Specify the type of the token (bearer) and insert the ```access_token``` obtained during authentication.|

### Responses
| <div style="width:200px">Response </div>|<div style="width:380px">Explanation</div>|                      
|-----:|:-------|
|**200 OK**|OK|      
|**400 Bad Request**| The request contains incorrect input data.|
|**400 Bad Request** | The limit for the ```$top``` query has been exceeded. The value from the incoming request is 'N' (N is your value from the request). You can find the data on the current limit [here](Options_and_Limitations.md#top-and-skip). |
|**401 Unauthorized**| The specified ```access_token``` is invalid or has expired. |
|**403 Forbidden**| The user doesn’t have the appropriate privileges.|
|**500 Internal Server Error**| The server encountered an unexpected condition that prevented it from fulfilling the request.|

### Properties
|<div style="width:200px">Property </div> |<div style="width:420px">Explanation</div>|                      
|-----:|:-------|
|**adjustmentItemId**: string *(uuid)* | Unique Identifier of the Adjustment Item |
|**adjustmentId**: string *(uuid)* | Unique Identifier of the Adjustment |
|**inventoryLocationId**: string *(uuid)* | Unique Identifier of the Inventory Location |
|**notes**: string |Comments about the Adjustment Item |
|**lotNo**: string | Identification Number assigned to a particular quantity or lot of material from a single Manufacturer |
|**serialNo**: string | Unique Identifier assigned incrementally or sequentially to an Item to identify it |
|**expDate**: string *(date-time)* | Previously determined date after which Item should no longer be used |
|**dateCreated**: string *(date-time)* | Date when the Adjustment Item was created |
|**createdBy**: string *(uuid)* | Unique Identifier of the user who created the Adjustment Item |
|**createdByName**: string | Name of the user who created the Adjustment Item |
|**lastUpdated**: string *(date-time)* | Last Date when the Adjustment Item was updated |
|**lastUpdatedBy**: string *(uuid)* | Unique Identifier of the last user who updated the Adjustment Item |
|**lastUpdatedByName**: string | Name of the last user who updated the Adjustment Item |
|**lineNo**: integer *(int32)* | Sequence number of the Adjustment Item in the Line Items list |
|**facilityName**: string | Name of the Facility |
|**locationName**: string | Name of the Location |
|**dateSubmitted**: string *(date-time)* | Date when the Adjustment Item was submitted |
|**inventoryNo**: string | Identification code of the Inventory Item |
|**inventoryDescription**: string | Description of the Inventory Item |
|**classificationName**: string | Name of the Category of the Item defined on the Organization level |
|**vendorName**: string | Name of the Vendor |
|**vendorItemNo**: string | Code that is used by the Vendor for the Item identification |
|**quantity**: integer *(int32)* | Quantity specified in the Line Items |
|**impactQuantity**: integer *(int32)* | Unit that is used for differentiation of the quantity change |
|**uom**: string | Unit of Measure |
|**conversionFactor**: integer *(int32)* | Number of Stock Keeping Units in another Unit of Measure |
|**adjustmentTypeText**: string | Type of transaction: Increment, Decrement, or Overwrite |
|**unitCost**: number *(double)* | Cost of the one unit of the Adjustment Item |
|**extendedCost**: number *(double)* | Total Cost of the Line |


``` json title="Response Content-types: APPLICATION/JSON, APPLICATION/XML <br> Response Example (200 OK)"
{
    "@odata.context": "link",
    "@odata.count": "number",
    "value": [
        {
            "adjustmentItemId": "00000000-0000-0000-0000-000000000000",
            "adjustmentId": "00000000-0000-0000-0000-000000000000",
            "inventoryLocationId": "00000000-0000-0000-0000-000000000000",
            "notes": "string",
            "lotNo": "string",
            "serialNo": "string",
            "expDate": "string (date-time)",
            "dateCreated": "string (date-time)",
            "createdBy": "00000000-0000-0000-0000-000000000000",
            "createdByName": "string",
            "lastUpdated": "string (date-time)",
            "lastUpdatedBy": "00000000-0000-0000-0000-000000000000",
            "lastUpdatedByName": "string",
            "lineNo": "integer (int32)",
            "facilityName": "string",
            "locationName": "string",
            "dateSubmitted": "string (date-time)",
            "inventoryNo": "string",
            "inventoryDescription": "string",
            "classificationName": "string",
            "vendorName": "string",
            "vendorItemNo": "string",
            "quantity": "integer (int32)",
            "impactQuantity": "integer (int32)",
            "uom": "string",
            "conversionFactor": "integer (int32)",
            "adjustmentTypeText": "string",
            "unitCost": "number (double)",
            "extendedCost": "number (double)"
        }
    ],
    "@odata.nextLink": "link"
}
```


## Get the specified Adjustment Item

### Path
GET /odata/AdjustmentItems({adjustmentItemId})

### Description
Returns the details of the Adjustment Item specified by ID.

### Request parameters
<style>
td, th {
   border: none!important;
}
</style>

| <div style="width:200px"> Parameter </div> |<div style="width:380px">Explanation</div> |                      
|-----:|:-------|
|**adjustmentItemId**: string *(uuid)* <br> <span style="color: #F05D30">**required**</span> <br> *in path*| Enter the ID of the Adjustment Item.|
|**api-version**: string default: 1.0 <br> *in header* | The requested API version. |
|**Authorization**: string <br> Bearer access_token <br> *in header* |Specify the type of the token (bearer) and insert the ```access_token``` obtained during authentication. |


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
|**400 Bad Request**| The request contains incorrect input data.|
|**401 Unauthorized**| The specified ```access_token``` is invalid or has expired. |
|**403 Forbidden**| The user doesn’t have the appropriate privileges.|
|**404 Not Found** | The specified ID is absent in the system. |
|**500 Internal Server Error**| The server encountered an unexpected condition that prevented it from fulfilling the request.|

### Properties
|<div style="width:200px">Property </div> |<div style="width:420px">Explanation</div>|                      
|-----:|:-------|
|**adjustmentItemId**: string *(uuid)* | Unique Identifier of the Adjustment Item |
|**adjustmentId**: string *(uuid)* | Unique Identifier of the Adjustment |
|**inventoryLocationId**: string *(uuid)* | Unique Identifier of the Inventory Location |
|**notes**: string |Comments about the Adjustment Item |
|**lotNo**: string | Identification Number assigned to a particular Quantity or Lot of material from a single Manufacturer |
|**serialNo**: string | Unique Identifier assigned incrementally or sequentially to an Item to identify it |
|**expDate**: string *(date-time)* | Previously determined date after which Item should no longer be used |
|**dateCreated**: string *(date-time)* | Date when the Adjustment Item was created |
|**createdBy**: string *(uuid)* | Unique Identifier of the user who created the Adjustment Item |
|**createdByName**: string | Name of the user who created the Adjustment Item |
|**lastUpdated**: string *(date-time)* | Last Date when the Adjustment Item was updated |
|**lastUpdatedBy**: string *(uuid)* | Unique Identifier of the last user who updated the Adjustment Item |
|**lastUpdatedByName**: string | Name of the last user who updated the Adjustment Item |
|**lineNo**: integer *(int32)* | Sequence number of the Adjustment Item in the Line Items list |
|**facilityName**: string | Name of the Facility |
|**locationName**: string | Name of the Location |
|**dateSubmitted**: string *(date-time)* | Date when the Adjustment Item was submitted |
|**inventoryNo**: string | Identification code of the Inventory Item |
|**inventoryDescription**: string | Description of the Inventory Item |
|**classificationName**: string | Name of the Category of the Item defined on the Organization level |
|**vendorName**: string | Name of the Vendor |
|**vendorItemNo**: string | Code that is used by the Vendor for the Item identification |
|**quantity**: integer *(int32)* | Quantity specified in the Line Items |
|**impactQuantity**: integer *(int32)* | Unit that is used for differentiation of the quantity change |
|**uom**: string | Unit of Measure |
|**conversionFactor**: integer *(int32)* | Number of Stock Keeping Units in another Unit of Measure |
|**adjustmentTypeText**: string | Type of transaction: Increment, Decrement, or Overwrite |
|**unitCost**: number *(double)* | Cost of the one unit of the Adjustment Item |
|**extendedCost**: number *(double)* | Total Cost of the Line |


``` json title="Response Content-types: APPLICATION/JSON, APPLICATION/XML <br> Response Example (200 OK)"
{
    "@odata.context": "link",
    "adjustmentItemId": "00000000-0000-0000-0000-000000000000",
    "adjustmentId": "00000000-0000-0000-0000-000000000000",
    "inventoryLocationId": "00000000-0000-0000-0000-000000000000",
    "notes": "string",
    "lotNo": "string",
    "serialNo": "string",
    "expDate": "string (date-time)",
    "dateCreated": "string (date-time)",
    "createdBy": "00000000-0000-0000-0000-000000000000",
    "createdByName": "string",
    "lastUpdated": "string (date-time)",
    "lastUpdatedBy": "00000000-0000-0000-0000-000000000000",
    "lastUpdatedByName": "string",
    "lineNo": "integer (int32)",
    "facilityName": "string",
    "locationName": "string",
    "dateSubmitted": "string (date-time)",
    "inventoryNo": "string",
    "inventoryDescription": "string",
    "classificationName": "string",
    "vendorName": "string",
    "vendorItemNo": "string",
    "quantity": "integer (int32)",
    "impactQuantity": "integer (int32)",
    "uom": "string",
    "conversionFactor": "integer (int32)",
    "adjustmentTypeText": "string",
    "unitCost": "number (double)",
    "extendedCost": "number (double)"
}      
```





