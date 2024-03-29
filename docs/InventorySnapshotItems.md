# InventorySnapshotItems

## Get the list of Inventory Snapshot Items

### <span style="color: #F05D30">Path</span>
GET /odata/InventorySnapshotItems

### <span style="color: #F05D30">Description</span>
Returns the list of Inventory Snapshot Items within a logged organization. You can filter the results by the strict match using the ```$filter``` parameter–entity eq ‘string’. Or filter the results by the partial match using ```$filter```=contains parameter–contains(entity, ‘string’).

### <span style="color: #F05D30">Request parameters</span>
<style>
td, th {
   border: none!important;
}
</style>

|  <div style="width:200px">Parameter</div>  |  <div style="width:380px">Explanation</div>  |                      
|-----:|:-------|
|**api-version**: string default: 1.0 <br> *in header*| The requested API version.|     
|**$filter**: string <br> *in query* | Restricts the set of Items returned. The maximum number of expressions is 100.|  
|**$orderby**: string <br> *in query* | Specifies the order in which Items are returned. The maximum number of expressions is 5.|
|**$search**: string <br> *in query*  | Picks the value in all possible fields.|
|**$top**: string  <br> *in query* | Returns only the first n results.|
|**$skip**: string <br> *in query*| Skips the first n results.|
|**Authorization**: string default: <br> Bearer access_token <br> *in header* |Specify the type of the token (bearer) and then insert the ```access_token```, which was obtained during authentication.|

### <span style="color: #F05D30">Responses</span>
| <div style="width:200px">Response </div>|<div style="width:380px">Explanation</div>|                      
|-----:|:-------|
|**200 OK**|OK|      
|**400 Bad Request**| Incorrect input data or organization ID does not match with the organization ID user is logged in. |
|**400 Bad Request** | The limit for the ```$top``` query has been exceeded. The value from the incoming request is 'N' (N is your value from the request). You can find the data on the current limit [here](Options_and_Limitations.md#top-and-skip). |
|**401 Unauthorized**|Incorrect specified ```access_token``` or ```access_token``` got expired.|
|**403 Forbidden**|User doesn’t have appropriate privileges.|
|**500 Internal Server Error**|Server encountered an unexpected condition that prevented it from fulfilling the request.|

### <span style="color: #F05D30">Properties</span>
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
  "items": [
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
  "nextPageLink": "string",
  "count": "integer (int64)"
}
```


## Get the details of the specified Inventory Snapshot Item

### <span style="color: #F05D30">Path</span>
GET /odata/InventorySnapshotItems({inventorySnapshotItemId})

### <span style="color: #F05D30">Description</span>
Returns the details of the Inventory Snapshot Item specified by ID.

### <span style="color: #F05D30">Request parameters</span>
|  <div style="width:200px">Parameter</div>  |  <div style="width:380px">Explanation</div>  |                      
|-----:|:-------|
|**inventorySnapshotItemId**: <br> string *(uuid)* <br> <span style="color: #F05D30">**required**</span> <br> *in path* | Enter the ID of the Inventory Snapshot Item here.|
|**api-version**: string default: 1.0 <br> *in header*| The requested API version.|     
|**Authorization**: string default: <br> Bearer access_token <br> *in header* |Specify the type of the token (bearer) and then insert the ```access_token```, which was obtained during authentication.|

### <span style="color: #F05D30">Responses</span>
| <div style="width:200px">Response </div>|<div style="width:380px">Explanation</div>|                      
|-----:|:-------|
|**200 OK**|OK|      
|**400 Bad Request**| Incorrect input data or organization ID does not match with the organization ID user is logged in.|
|**401 Unauthorized**| Incorrect specified ```access_token``` or ```access_token``` got expired.|
|**403 Forbidden**| User doesn’t have appropriate privileges.|
|**404 Not Found** | Specified ID is absent in the system. |
|**500 Internal Server Error**| Server encountered an unexpected condition that prevented it from fulfilling the request.|

### <span style="color: #F05D30">Properties</span>
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