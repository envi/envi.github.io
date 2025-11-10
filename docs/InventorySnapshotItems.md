# InventorySnapshotItems

## Get the list of Inventory Snapshot Items

### Path
GET /odata/InventorySnapshotItems

### Description
Returns a paged list of Inventory Snapshot Items within a logged-in organization. 

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
|**$filter**: string <br> *in query* | Restricts the set of items returned. Supports up to 100 expressions. |  
|**$orderby**: string <br> *in query* | Specifies the order in which items are returned. Supports up to 5 expressions. |
|**$search**: string <br> *in query*  | Searches across all supported fields. |
|**$top**: string  <br> *in query* | Returns only the first n results.|
|**$skip**: string <br> *in query*| Skips the first n results.|
|**Authorization**: string default: <br> Bearer access_token <br> *in header* | Specify the type of the token (bearer) and insert the ```access_token``` obtained during authentication. |

### Responses
| <div style="width:200px">Response </div>|<div style="width:380px">Explanation</div>|                      
|-----:|:-------|
|**200 OK**| OK |
|**400 Bad Request**| The request contains incorrect input data. |
|**400 Bad Request** | The limit for the ```$top``` query has been exceeded. The value from the incoming request is 'N' (N is your value from the request). You can find the data on the current limit [here](Options_and_Limitations.md#top-and-skip). |
|**401 Unauthorized**| The specified ```access_token``` is incorrect, or the ```access_token``` has expired. |
|**403 Forbidden**| The user doesn’t have the appropriate privileges. |
|**500 Internal Server Error**| The server encountered an unexpected condition that prevented it from fulfilling the request.|

### Properties
|<div style="width:200px">Property </div> |<div style="width:380px">Explanation</div>|                      
|-----:|:-------|
|**inventorySnapshotItemId**: <br> string *(uuid)* | Unique Identifier of the Inventory Snapshot Item |
|**inventorySnapshotId**: string *(uuid)* | Unique Identifier of the Inventory Snapshot |
|**reference**: string | Information concerning the Inventory Snapshot |
|**inventoryId**: string *(uuid)* | Unique Identifier of the Inventory Item |
|**inventoryNo**: string | Identification code of the Inventory Item |
|**inventoryDescription**: string | Description of the Inventory Item |
|**inventoryLocationId**: string *(uuid)* | Unique Identifier of the Inventory Location |
|**locationNo**: string | Identification Number of the Location |
|**locationName**: string | Name of the Location |
|**cost**: number *(double)* | Cost for the Inventory Item |
|**quantity**: integer *(int32)* | Quantity on hand of the Inventory Location when the Inventory Snapshot was created |
|**itemTypeId**: integer *(int32)* | Unique identifier of the Item type |
|**itemTypeName**: string | Name of the Item type |
|**dateCreated**: string <br> *(date-time)* | Date when the Inventory Snapshot Item was created |

``` json title="Response Content-types: APPLICATION/JSON, APPLICATION/XML<br>Response example (200 OK)"
{
    "@odata.context": "link",
    "@odata.count": "number",
    "value": [
        {
            "inventorySnapshotItemId": "00000000-0000-0000-0000-000000000000",
            "inventorySnapshotId": "00000000-0000-0000-0000-000000000000",
            "reference": "string",
            "inventoryId": "00000000-0000-0000-0000-000000000000",
            "inventoryNo": "string",
            "inventoryDescription": "string",
            "inventoryLocationId": "00000000-0000-0000-0000-000000000000",
            "locationNo": "string",
            "locationName": "string",
            "cost": "number (double)",
            "quantity": "integer (int32)",
            "itemTypeId": "integer (int32)",
            "itemTypeName": "string",
            "dateCreated": "string (date-time)"
        }
    ],
    "@odata.nextLink": "link"
}
```


## Get the details of the specified Inventory Snapshot Item

### Path
GET /odata/InventorySnapshotItems({inventorySnapshotItemId})

### Description
Returns the details of the Inventory Snapshot Item specified by ID.

### Request parameters
|  <div style="width:200px">Parameter</div>  |  <div style="width:380px">Explanation</div>  |                      
|-----:|:-------|
|**inventorySnapshotItemId**: <br> string *(uuid)* <br> <span style="color: #F05D30">**required**</span> <br> *in path* | Enter the ID of the Inventory Snapshot Item.|
|**api-version**: string default: 1.0 <br> *in header*| The requested API version.|
|**Authorization**: string default: <br> Bearer access_token <br> *in header* | Specify the type of the token (bearer) and insert the ```access_token``` obtained during authentication. | 

### Responses
| <div style="width:200px">Response </div>|<div style="width:380px">Explanation</div>|                      
|-----:|:-------|
|**200 OK**| OK |
|**400 Bad Request**| The request contains incorrect input data. |
|**401 Unauthorized**| The specified ```access_token``` is incorrect, or the ```access_token``` has expired. |
|**403 Forbidden**| The user doesn’t have the appropriate privileges. |
|**404 Not Found** | The specified ID is absent in the system. |
|**500 Internal Server Error**| The server encountered an unexpected condition that prevented it from fulfilling the request.|

### Properties
|<div style="width:200px">Property </div> |<div style="width:380px">Explanation</div>|                      
|-----:|:-------|
|**inventorySnapshotItemId**: <br> string *(uuid)* | Unique Identifier of the Inventory Snapshot Item |
|**inventorySnapshotId**: string *(uuid)* | Unique Identifier of the Inventory Snapshot |
|**reference**: string | Information concerning the Inventory Snapshot |
|**inventoryId**: string *(uuid)* | Unique Identifier of the Inventory Item |
|**inventoryNo**: string | Identification code of the Inventory Item |
|**inventoryDescription**: string | Description of the Inventory Item |
|**inventoryLocationId**: string *(uuid)* | Unique Identifier of the Inventory Location |
|**locationNo**: string | Identification Number of the Location |
|**locationName**: string | Name of the Location |
|**cost**: number *(double)* | Cost for the Inventory Item |
|**quantity**: integer *(int32)* | Quantity on hand of the Inventory Location when the Inventory Snapshot was created |
|**itemTypeId**: integer *(int32)* | Unique identifier of the Item type |
|**itemTypeName**: string | Name of the Item type |
|**dateCreated**: string <br> *(date-time)* | Date when the Inventory Snapshot Item was created |

``` json title="Response Content-types: APPLICATION/JSON, APPLICATION/XML<br>Response example (200 OK)"
{
    "@odata.context": "link",
    "inventorySnapshotItemId": "00000000-0000-0000-0000-000000000000",
    "inventorySnapshotId": "00000000-0000-0000-0000-000000000000",
    "reference": "string",
    "inventoryId": "00000000-0000-0000-0000-000000000000",
    "inventoryNo": "string",
    "inventoryDescription": "string",
    "inventoryLocationId": "00000000-0000-0000-0000-000000000000",
    "locationNo": "string",
    "locationName": "string",
    "cost": "number (double)",
    "quantity": "integer (int32)",
    "itemTypeId": "integer (int32)",
    "itemTypeName": "string",
    "dateCreated": "string (date-time)"
}
```