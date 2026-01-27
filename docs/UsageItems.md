# UsageItems

## Get the list of Usage Items

### Path
GET /odata/UsageItems

### Description
Returns a paged list of existing items within all Usages. 

!!! note

    You can filter the results as follows:

    - For an exact match, use: ```$filter parameter–entity eq ‘string’```
    - For a partial match, use: ```$filter=contains parameter–contains(entity, ‘string’)```


!!! note 

    This endpoint does not support logical operators (**and**, **or**, **in**, **gt**, **ge**, **lt**, **le**) for data filtering.

### Request parameters
<style>
td, th {
   border: none!important;
}
</style>

|  <div style="width:200px">Parameter</div>  |  <div style="width:380px">Explanation</div>  |                      
|-----:|:-------|
|**summary**: boolean default: false <br> *in query* | Set to ```true``` to apply grouping. |
|**from**: string *(date-time)* <br> *in query* | Enter the start date. |
|**to**: string *(date-time)* <br> *in query* | Enter the end date. |
|**api-version**: string default: 1.0 <br> *in header* | The requested API version.| 
|**$search**: string <br> *in query*  | Searches across all supported fields. |        
|**$filter**: string <br> *in query* | Filters results based on a Boolean condition.|
|**$orderby**: string <br> *in query* | Sorts results.|
|**$top**: string  <br> *in query* | Returns only the first n results.|
|**$skip**: string <br> *in query*| Skips the first n results. |
|**Authorization**: string default: <br> Bearer access_token <br> *in header* | Specify the type of the token (bearer) and insert the ```access_token``` obtained during authentication. |

### Responses
| <div style="width:200px">Response </div>|<div style="width:420px">Explanation</div>|                      
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
|**usageItemId**: string *(uuid)* | Unique Identifier of the Usage |
|**procedureCode1**: string | First Code of the Procedure |
|**procedureName1**: string | First Name of the Procedure |
|**procedureCode2**: string | Second Code of the Procedure |
|**procedureName2**: string | Second Name of the Procedure |
|**procedure1Id**: string *(uuid)* | Unique Identifier of the first Procedure |
|**procedure2Id**: string *(uuid)* | Unique Identifier of the second Procedure |
|**date**: string *(date-time)* | Usage Date |
|**caseNo**: string | Number of the Case |
|**facilityId**: string *(uuid)* | Unique Identifier of the Facility |
|**departmentName**: string | Name of the Department |
|**departmentId**: string *(uuid)* | Unique Identifier of the Department |
|**extendedPrice**: number *(double)* | Extended Price |
|**cost**: number *(double)* | Cost |
|**extendedCost**: number *(double)* | Extended Cost |
|**patient**: string | Patient Details |
|**facilityName**: string | Name of the Facility |
|**facilityNo**: string | Identification Number of the Facility |
|**doctorName**: string | Name of the Doctor |
|**doctorId**: string *(uuid)* | Unique Identifier of the Doctor |
|**vendorItemNo**: string | Code used by the Vendor to identify the item |
|**inventoryDescription**: string | Description of the Inventory item |
|**classification**: string | Category of the item defined on the Organization level |
|**classification2**: string | Additional Category of the item defined on the Organization level |
|**quantity**: integer *(int32)* | Quantity of the Usage item |
|**uom**: string | Unit of Measure |
|**price**: number *(double)* | Price of the Usage item |
|**conversionFactor**: integer *(int32)* | Number of Stock Keeping Units in another Unit of Measure |
|**locationNo**: string | Identification Number of the Location |
|**inventoryNo**: string | Identification code of the Inventory item |
|**manufacturerNo**: string | Number of the Manufacturer |
|**manufacturerItemNo**: string | Number of the Manufacturer item |
|**lotNo**: string | Identification Number assigned to a particular Quantity or Lot of material from a single Manufacturer |
|**serialNo**: string | Unique Identifier assigned incrementally or sequentially to the item to uniquely identify it |
|**expirationDate**: string <br> *(date-time)* | Previously determined date after which the item should no longer be used |
|**itemNotes**: string | Comments about the item |
|**lineNo**: integer *(int32)* | Number of the line item |
|**usageOrdinalNo**: integer *(int32)* | Ordinal Number of the Usage |
|**usageId**: string (uuid) | Unique Identifier of the Usage |
|**usageNo**: string | Identification Number of the Location |
|**dateSubmitted**: string *(date-time)* | Date when the Usage was submitted |
|**systemTypeId**: integer *(int32)* | Unique Identifier of the System Type |
|**systemType**: string | Type of the Usage item in the scope of the system (Standard or Implant)|
|**implantSize**: string | Size of the Implant  |
|**implantPositionId**: integer *(int32)* | Unique Identifier of the Implant Position |
|**implantPosition**: string | Position of the Implant |
|**implantRemoved**: boolean | Is the Implant removed or not? |
|**implantCompleted**: boolean | Is the Implant completed or not? |

``` json title="Response Content-types: APPLICATION/JSON, APPLICATION/XML<br>Response example (200 OK)"
{
    "@odata.context": "link",
    "@odata.count": "number",
    "value": [
        {
            "usageItemId": "00000000-0000-0000-0000-000000000000",
            "procedureCode1": "string",
            "procedureName1": "string",
            "procedureCode2": "string",
            "procedureName2": "string",
            "procedure1Id": "00000000-0000-0000-0000-000000000000",
            "procedure2Id": "00000000-0000-0000-0000-000000000000",
            "date": "string (date-time)",
            "caseNo": "string",
            "facilityId": "00000000-0000-0000-0000-000000000000",
            "departmentName": "string",
            "departmentId": "00000000-0000-0000-0000-000000000000",
            "extendedPrice": "number (double)",
            "cost": "number (double)",
            "extendedCost": "number (double)",
            "patient": "string",
            "facilityName": "string",
            "facilityNo": "string",
            "doctorName": "string",
            "doctorId": "00000000-0000-0000-0000-000000000000",
            "vendorItemNo": "string",
            "inventoryDescription": "string",
            "classification": "string",
            "classification2": "string",
            "quantity": "integer (int32)",
            "uom": "string",
            "price": "number (double)",
            "conversionFactor": "integer (int32)",
            "locationNo": "string",
            "inventoryNo": "string",
            "manufacturerNo": "string",
            "manufacturerItemNo": "string",
            "lotNo": "string",
            "serialNo": "string",
            "expirationDate": "string (date-time)",
            "itemNotes": "string",
            "lineNo": "integer (int32)",
            "usageOrdinalNo": "integer (int32)",
            "usageId": "00000000-0000-0000-0000-000000000000",
            "usageNo": "string",
            "dateSubmitted": "string (date-time)",
            "systemTypeId": "integer (int32)",
            "systemType": "string",
            "implantSize": "string",
            "implantPositionId": "integer (int32)",
            "implantPosition": "string",
            "implantRemoved": "boolean",
            "implantCompleted": "boolean"
        }
    ],
    "@odata.nextLink": "link"
}
```

## Add new Items to existing Usages

### Path
POST /odata/UsageItems/BulkAdd

### Description
Adds new items to existing Usages within the logged-in organization.

### Request body
|  <div style="width:200px">Parameter</div>  |  <div style="width:420px">Explanation</div>  |                      
|-----:|:-------|
|**usageId**: string <br> <span style="color: #F05D30">**required**</span> <br>  *in formData* | Unique Identifier of the Usage. <br> **If not provided**: 400 Bad Request. |
|**lineNo**: integer *(int32)* <br> *in formData* | Number of the line item. <br> It is auto-generated and recalculated within active Usage line items. <br> **If not provided**: auto-populated. |
|**inventoryNo**: string <br> *in formData* | Identification code of the Inventory item. <br> It is validated by Facility (Inventory Group). <br> **If not provided**: empty. |
|**inventoryDescription**: string <br> *in formData* | Description of the Inventory item. <br> It is populated from the existing Inventory when mapped by the **Inventory No** and **Inventory Location** values. <br> **If not provided**: empty. |
|**locationNo**: string <br> <span style="color: #F05D30">**required**</span> <br> *in formData* | Identification Number of the Location. <br> The ```locationNo``` value is populated if the specified location exists within the Usage Facility.|
|**vendorItemNo**: string <br> *in formData* | Code used by the Vendor to identify the item. <br> It is matched with appropriate Inventory Vendor data. <br> **If the Vendor Item No is not provided**, it is populated from the active primary Vendor from a specific Facility within an Inventory. <br> If there is no specific Facility, it is populated from the active primary Master Facility Inventory Vendor within the Inventory. <br> If there is no specific Facility or Master Facility Inventory Vendor within the Inventory, the **Vendor Item No** is empty.|
|**manufacturerNo**: string <br> *in formData* | Number of the Manufacturer. <br> It is populated from Inventory Vendor if the item is matched by ```vendorItemNo```. <br> **If the Vendor Item No is not provided**, it is populated from the active primary Vendor from a specific Facility within an Inventory. <br> If there is no specific Facility, it is populated from the active primary Master Facility Inventory Vendor within the Inventory. <br> If there is no specific Facility or Master Facility Inventory Vendor within the Inventory, the **Manufacturer** is **None**.|
|**manufacturerItemNo**: string <br> *in formData* | Item Number of the Manufacturer. <br> It is populated from Inventory Vendor if the item is matched by ```vendorItemNo```. <br> **If the Vendor Item No is not provided**, it is populated from the active primary Vendor from a specific Facility within an Inventory. <br> If there is no specific Facility, it is populated from the active primary Master Facility Inventory Vendor within the Inventory. If there is no specific Facility or Master Facility Inventory Vendor within the Inventory, the **Manufacturer Item No** is empty.|
| **lotNo**: string <br> *in formData* | Identification number assigned to a specific quantity or lot of material from a single Manufacturer. <br> It is populated from `lotNo`. <br> **If not provided**: empty. |
| **serialNo**: string <br> *in formData* | Unique identifier assigned incrementally or sequentially to the item to uniquely identify it. <br> It is populated from `serialNo`. <br> **If not provided**: empty. |
| **expirationDate**: string <br> *in formData* | Previously determined date after which the item should no longer be used. <br> It is populated from `expirationDate`. <br> **If not provided**: empty. |
| **quantity**: string <br> *in formData* | Quantity specified for the line item. <br> **If not provided**: 1. |
| **uom**: string <br> *in formData* | Unit of Measure. <br> It can be matched with Inventory UOM. <br> **If not provided**: EA. |
| **conversionFactor**: string <br> *in formData* | Number of Stock Keeping Units in another Unit of Measure. <br> It is populated from the appropriate Inventory UOM Conversion Factor if the item is added as an Inventory item and the specified UOM value is matched with Inventory UOM. <br> **If not provided**: 1. |
|**itemNotes**: string <br> *in formData* | Comments about the item. <br> It is populated from Item Notes <br> **If not provided**: empty. |
|**systemTypeId**: integer *(int32)* | Unique Identifier of the System Type <br> **If not provided**: 1 (Standard). |
|**systemType**: string | Type of the Usage item in the scope of the system (Standard or Implant)|
|**implantSize**: string | Size of the Implant <br> **If not provided**: empty. |
|**implantPositionId**: integer *(int32)* | Unique Identifier of the Implant Position. <br> **If not provided**: 0 (None).|
|**implantPosition**: string | Position of the Implant |
|**implantRemoved**: boolean | Is the Implant removed or not? <br> **If not provided**: false |
|**implantCompleted**: boolean | Is the Implant completed or not? <br> **If not provided**: false |

``` json title="Request Content-types: APPLICATION/JSON, APPLICATION/XML <br> Request Example"
{
    "usageId": "string(uuid)",
    "lineNo": "integer (int32)",
    "inventoryNo": "string",
    "inventoryDescription": "string",
    "locationNo": "string",
    "vendorItemNo": "string",
    "manufacturerItemNo": "string",
    "lotNo": "string",
    "serialNo": "string",
    "expirationDate": "string",
    "quantity": "string",
    "uom": "string",
    "conversionFactor": "string",
    "itemNotes": "string",
    "systemTypeId": "integer (int32)",
    "systemType": "string",
    "implantSize": "string",
    "implantPositionId": "integer (int32)",
    "implantPosition": "string",
    "implantRemoved": "boolean",
    "implantCompleted": "boolean"
}
```


``` json title="Request Example"
{
 "usageItems":[
  {
    "usageId": "UsageId1"
  },
  {
    "usageId": "UsageId2"
  },
  {
    "usageId": "UsageId3"
  }
 ]
}
```

### Request parameters
|  <div style="width:200px">Parameter</div>  |  <div style="width:380px">Explanation</div>  |                      
|-----:|:-------|
|**api-version**: string default: 1.0 <br> *in header*| The requested API version.|   
|**Authorization**: string default: <br> Bearer access_token <br> *in header* |Specify the type of the token (bearer) and then insert the ```access_token```, which was obtained during authentication. |

### Responses
| <div style="width:200px">Response </div>|<div style="width:420px">Explanation</div>|                      
|-----:|:-------|
|**200 OK**| OK | 
|**400 Bad Request**| The request contains incorrect input data. |         
|**401 Unauthorized**| The specified ```access_token``` is invalid or has expired. |
|**403 Forbidden**| The user doesn’t have the appropriate privileges. |
|**500 Internal Server Error**| The server encountered an unexpected condition that prevented it from fulfilling the request.|


``` json title="Response Content-types: APPLICATION/JSON, APPLICATION/XML<br>Response example (200 OK)"
"object"

```