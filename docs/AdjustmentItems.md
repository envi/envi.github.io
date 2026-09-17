# AdjustmentItems

## Get the list of Adjustment items

### Path
GET /odata/AdjustmentItems

### Description
Returns a paged list of existing Adjustment items.

!!! note

    You can filter the results as follows:

    - For an exact match, use: ```$filter=entity eq 'string'```
    - For a partial match, use: ```$filter=contains(entity, 'string')```


!!! note
    
    This endpoint does not support logical operators (**and**, **or**, **in**, **gt**, **ge**, **lt**, **le**) for data filtering.

### Request parameters
| Parameter | Explanation |                      
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
| Response | Explanation |                      
|-----:|:-------|
|**200 OK**|OK|      
|**400 Bad Request**| The request contains incorrect input data.|
|**400 Bad Request** | The limit for the ```$top``` query has been exceeded. The value from the incoming request is 'N' (N is your value from the request). You can find the data on the current limit [here](Options_and_Limitations.md#top-and-skip). |
|**401 Unauthorized**| The specified ```access_token``` is invalid or has expired. |
|**403 Forbidden**| The user doesn’t have the appropriate privileges.|
|**500 Internal Server Error**| The server encountered an unexpected condition that prevented it from fulfilling the request.|

### Properties
| Property | Explanation |                      
|-----:|:-------|
|**adjustmentItemId**: string *(uuid)* | Unique identifier of the Adjustment item |
|**adjustmentId**: string *(uuid)* | Unique identifier of the Adjustment |
|**inventoryLocationId**: string *(uuid)* | Unique identifier of the Inventory Location |
|**notes**: string | Notes about the Adjustment item |
|**lotNo**: string | Lot number assigned to the item |
|**serialNo**: string | Serial number assigned to uniquely identify the item |
|**expDate**: string <br> *(date-time)* | Expiration date of the item |
|**dateCreated**: string *(date-time)* | Date when the Adjustment item was created |
|**createdBy**: string *(uuid)* | Unique identifier of the user who created the Adjustment item |
|**createdByName**: string | Name of the user who created the Adjustment item |
|**lastUpdated**: string *(date-time)* | Date when the Adjustment item was last updated |
|**lastUpdatedBy**: string *(uuid)* | Unique identifier of the user who last updated the Adjustment item |
|**lastUpdatedByName**: string | Name of the user who last updated the Adjustment item |
|**lineNo**: integer *(int32)* | Sequence number of the Adjustment item in the line items list |
|**facilityName**: string | Name of the Facility |
|**locationName**: string | Name of the Location |
|**dateSubmitted**: string *(date-time)* | Date when the Adjustment item was submitted |
|**inventoryNo**: string | Identification number of the Inventory item |
|**inventoryDescription**: string | Description of the Inventory item |
|**classificationName**: string | Name of the Inventory Category defined at the Organization level |
|**vendorName**: string | Name of the Vendor |
|**vendorItemNo**: string | Item number defined by the Vendor |
|**quantity**: integer *(int32)* | Quantity specified for the line item |
|**impactQuantity**: integer *(int32)* | Unit used to differentiate the quantity change |
|**uom**: string | Unit of Measure of the Adjustment item |
|**conversionFactor**: integer *(int32)* | Conversion factor of the Adjustment item |
|**adjustmentTypeText**: string | Type of the Adjustment: Increment, Decrement, or Overwrite. |
|**unitCost**: number *(double)* | Unit cost of the Adjustment item |
|**extendedCost**: number *(double)* | Total cost of the Adjustment item |

``` json title="Response example (200 OK)"
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

## Get the specified Adjustment item

### Path
GET /odata/AdjustmentItems({adjustmentItemId})

### Description
Returns the details of the Adjustment item specified by ID.

### Request parameters
<style>
td, th {
   border: none!important;
}
</style>

| Parameter | Explanation |                      
|-----:|:-------|
|**adjustmentItemId**: string *(uuid)* <br> <span style="color: #F05D30">**required**</span> <br> *in path*| Enter the ID of the Adjustment Item.|
|**api-version**: string default: 1.0 <br> *in header* | The requested API version. |
|**Authorization**: string <br> Bearer access_token <br> *in header* |Specify the type of the token (bearer) and insert the ```access_token``` obtained during authentication. |

| Parameter |  Explanation |                      
|-----:|:-------|
|**api-version**: string default: 1.0 <br> *in header*| The requested API version.|
|**$search**: string <br> *in query*  | Searches across all supported fields. |  
|**$filter**: string <br> *in query* | Filters results based on a Boolean condition.|
|**$orderby**: string <br> *in query* | Sorts results.|
|**$top**: string  <br> *in query* | Returns only the first n results.|
|**$skip**: string <br> *in query*| Skips the first n results.|
|**Authorization**: string default: <br> Bearer access_token <br> *in header* | Specify the type of the token (bearer) and insert the ```access_token``` obtained during authentication.|

### Responses
| Response | Explanation |                      
|-----:|:-------|
|**200 OK**|OK|      
|**400 Bad Request**| The request contains incorrect input data.|
|**401 Unauthorized**| The specified ```access_token``` is invalid or has expired. |
|**403 Forbidden**| The user doesn’t have the appropriate privileges.|
|**404 Not Found** | The specified ID is absent in the system. |
|**500 Internal Server Error**| The server encountered an unexpected condition that prevented it from fulfilling the request.|

### Properties
| Property  | Explanation |                      
|-----:|:-------|
|**adjustmentItemId**: string *(uuid)* | Unique identifier of the Adjustment item |
|**adjustmentId**: string *(uuid)* | Unique identifier of the Adjustment |
|**inventoryLocationId**: string *(uuid)* | Unique identifier of the Inventory Location |
|**notes**: string | Notes about the Adjustment item |
|**lotNo**: string | Lot number assigned to the item |
|**serialNo**: string | Serial number assigned to uniquely identify the item |
|**expDate**: string <br> *(date-time)* | Expiration date of the item |
|**dateCreated**: string *(date-time)* | Date when the Adjustment item was created |
|**createdBy**: string *(uuid)* | Unique identifier of the user who created the Adjustment item |
|**createdByName**: string | Name of the user who created the Adjustment item |
|**lastUpdated**: string *(date-time)* | Date when the Adjustment item was last updated |
|**lastUpdatedBy**: string *(uuid)* | Unique identifier of the user who last updated the Adjustment item |
|**lastUpdatedByName**: string | Name of the user who last updated the Adjustment item |
|**lineNo**: integer *(int32)* | Sequence number of the Adjustment item in the line items list |
|**facilityName**: string | Name of the Facility |
|**locationName**: string | Name of the Location |
|**dateSubmitted**: string *(date-time)* | Date when the Adjustment item was submitted |
|**inventoryNo**: string | Identification number of the Inventory item |
|**inventoryDescription**: string | Description of the Inventory item |
|**classificationName**: string | Name of the Inventory Category defined at the Organization level |
|**vendorName**: string | Name of the Vendor |
|**vendorItemNo**: string | Item number defined by the Vendor |
|**quantity**: integer *(int32)* | Quantity specified for the line item |
|**impactQuantity**: integer *(int32)* | Unit used to differentiate the quantity change |
|**uom**: string | Unit of Measure of the Adjustment item |
|**conversionFactor**: integer *(int32)* | Conversion factor of the Adjustment item |
|**adjustmentTypeText**: string | Type of the Adjustment: Increment, Decrement, or Overwrite. |
|**unitCost**: number *(double)* | Unit cost of the Adjustment item |
|**extendedCost**: number *(double)* | Total cost of the Adjustment item |

``` json title="Response example (200 OK)"
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
