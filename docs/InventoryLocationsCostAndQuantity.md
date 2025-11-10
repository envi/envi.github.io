# InventoryLocationsCostAndQuantity

## Get the list of Inventory Locations cost and quantity

### Path
GET /odata/InventoryLocationsCostAndQuantity

### Description
Returns a paged list of existing Inventory Locations cost and quantity within the logged-in organization.

!!! note

    You can filter the results as follows:

    - For an exact match, use: ```$filter parameter–entity eq ‘string’```
    - For a partial match, use: ```$filter=contains parameter–contains(entity, ‘string’)```

### Request parameters
|  <div style="width:200px">Parameter</div>  |  <div style="width:380px">Explanation</div>  |                      
|-----:|:-------|
|**includeInactiveInventory**: <br> boolean default: false <br> *in query* | Include Inactive Inventory Items. |
|**includeInactiveLocations**: <br> boolean default: false <br> *in query* | Include Inactive Locations. |
|**includeInactiveInventoryLocations**: <br> boolean default: false <br> *in query* | Include Inactive Inventory Locations. |
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
|**inventoryLocationId**: string *(uuid)* | Unique Identifier of the Inventory Location |
|**inventoryId**: string *(uuid)* | Unique Identifier of the Inventory Item |
|**inventoryNo**: string | Identification code of the Inventory Item |
|**locationNo**: string | Identification Number of the Location |
|**cost**: number *(double)* | Cost for the Location |
|**quantityOnHand**: integer *(int32)*  | The total number of stock-keeping Inventory Items that are physically located in the Location |
|**activeStatus**: boolean | Is Location active or not? |
|**dateAdded**: string *(date-time)* | Date when the Location was added |
|**addedBy**: string *(uuid)* | Unique Identifier of the user who added the Location |
|**lastUpdated**: string *(date-time)* | Last Date when the Location was updated |
|**lastUpdatedBy**: string *(uuid)* | Unique Identifier of the last user who updated the Location |
|**costLastUpdated**: string <br> *(date-time)*  | Last Date when the Cost was updated |
|**costLastUpdatedBy**: string *(uuid)* | Unique Identifier of the last user who updated the Cost |


``` json title="Response Content-types: APPLICATION/JSON, APPLICATION/XML<br>Response example (200 OK)"
{
    "@odata.context": "link",
    "@odata.count": "number",
    "value": [
        {
            "inventoryLocationId": "00000000-0000-0000-0000-000000000000",
            "inventoryId": "00000000-0000-0000-0000-000000000000",
            "inventoryNo": "string",
            "locationNo": "string",
            "cost": "number (double)",
            "quantityOnHand": "integer (int32)",
            "activeStatus": "boolean",
            "dateAdded": "string (date-time)",
            "addedBy": "00000000-0000-0000-0000-000000000000",
            "lastUpdated": "string (date-time)",
            "lastUpdatedBy": "00000000-0000-0000-0000-000000000000",
            "costLastUpdated": "string (date-time)",
            "costLastUpdatedBy": "00000000-0000-0000-0000-000000000000"
        }
    ],
    "@odata.nextLink": "link"
}
```

## Get the specified Inventory Location cost and quantity

### Path
GET /odata/InventoryLocationsCostAndQuantity({inventoryLocationId})

### Description
Returns the details of the Inventory Location cost and quantity specified by ID.

### Request parameters
<style>
td, th {
   border: none!important;
}
</style>

|  <div style="width:200px">Parameter</div>  |  <div style="width:380px">Explanation</div>  |                      
|-----:|:-------|
|**inventoryLocationId**: string *(uuid)* <br> <span style="color: #F05D30">**required**</span> <br> *in path* | Enter the ID of the Inventory Location. |
|**api-version**: string default: 1.0 <br> *in header*| The requested API version. |  
|**Authorization**: string default: <br> Bearer access_token <br> *in header* | Specify the type of the token (bearer) and insert the ```access_token``` obtained during authentication. |

### Responses
| <div style="width:200px">Response </div>|<div style="width:380px">Explanation</div>|                      
|-----:|:-------|
|**200 OK**| OK |
|**400 Bad Request**| The request contains incorrect input data. |
|**401 Unauthorized**| The specified ```access_token``` is incorrect, or the ```access_token``` has expired. |
|**403 Forbidden**| The user doesn’t have the appropriate privileges. |
|**500 Internal Server Error**| The server encountered an unexpected condition that prevented it from fulfilling the request.|

### Properties
|<div style="width:200px">Property </div> |<div style="width:380px">Explanation</div>|                      
|-----:|:-------|
|**inventoryLocationId**: string *(uuid)* | Unique Identifier of the Inventory Location |
|**inventoryId**: string *(uuid)* | Unique Identifier of the Inventory Item |
|**inventoryNo**: string | Identification code of the Inventory Item  |
|**locationNo**: string | Identification Number of the Location |
|**cost**: number *(double)* | Cost for the Location |
|**quantityOnHand**: integer *(int32)*  | The total number of stock-keeping Inventory Items that are physically located in the Location |
|**activeStatus**: boolean | Is Location active or not? |
|**dateAdded**: string *(date-time)* | Date when the Location was added |
|**addedBy**: string *(uuid)* | Unique Identifier of the user who added the Location |
|**lastUpdated**: string *(date-time)* | Last Date when the Location was updated |
|**lastUpdatedBy**: string *(uuid)* | Unique Identifier of the last user who updated the Location |
|**costLastUpdated**: string <br> *(date-time)*  | Last Date when the Cost was updated |
|**costLastUpdatedBy**: string *(uuid)* | Unique Identifier of the last user who updated the Cost |


``` json title="Response Content-types: APPLICATION/JSON, APPLICATION/XML<br>Response example (200 OK)"
{
    "@odata.context": "link",
    "inventoryLocationId": "00000000-0000-0000-0000-000000000000",
    "inventoryId": "00000000-0000-0000-0000-000000000000",
    "inventoryNo": "string",
    "locationNo": "string",
    "cost": "number (double)",
    "quantityOnHand": "integer (int32)",
    "activeStatus": "boolean",
    "dateAdded": "string (date-time)",
    "addedBy": "00000000-0000-0000-0000-000000000000",
    "lastUpdated": "string (date-time)",
    "lastUpdatedBy": "00000000-0000-0000-0000-000000000000",
    "costLastUpdated": "string (date-time)",
    "costLastUpdatedBy": "00000000-0000-0000-0000-000000000000"
}  
```






