# FileAttachments

## Get the list of files by entity ID

### Path
GET /odata/FileAttachments({entityId})

### Description
Returns a list of files for the specified entity ID within the logged-in organization. The list will also include linked files for POs, Receipts, Matched Invoices, OCRs, and Received Invoices.

!!! info "Supported entityIds"

    The following ```entityId``` types are supported, depending on the module:

    |  <div style="width:200px">Module</div>  |  <div style="width:380px">entityId</div>  |             
    |-----:|:-------|
    | **Adjustments** | adjustmentId |
    | **Inventory** | inventoryId (for files, not for images) |
    | **Contracts** | contractId|
    | **Purchasing** | purchaseOrderId |
    | **Receiving** | purchaseOrderId |
    | **Accounts Payable**/**Received Invoice** | receivedInvoiceId |
    | **Accounts Payable**/**Matched Invoices** | purchaseOrderId |
    | **Accounts Payable**/**OCR Invoices**| ocrInvoiceId |
    | **Requisitioning** | requisitionId |
    | **Fill Requisitions** | requisitionId |
    | **Proof of Delivery** | fillRequisitionId |

    
    If you specify ```purchaseOrderId```, ```receivedInvoiceId```, and ```ocrInvoiceId```, 
    the response will include files directly associated with these IDs, along with additional files linked by PO # and Release # from POs, Received Invoices, Matched Invoices, Receipts, and OCR Invoices.

    ```mermaid
    graph RL
    A([OCR Invoice]) <--> B([Received Invoice])
    B <--> C([Matched Invoice])
    C <--> E([Receipt])
    E <--> A
    B <--> D([Purchase Order])
    B <--> E
    D <--> E
    D <--> C
    A <--> D
    A <--> C
    ``` 

    !!! note
    
        Search is not performed by ```matchedInvoiceId```, ```receiptId```, or Transef In ```adjustmentId```.



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
|**api-version**: string <br> *in query* |The requested API version.|
|**entityTypePK**:  string <br> *in query* | Filters the results based on the entity type identifier. <br> **Note**: Refer to the table below for supported ```entityTypePK``` values.|
|**$search**: string <br> *in query*  | Picks the value in all possible fields.|   
|**$filter**: string <br> *in query* | Filters the results based on a Boolean condition.|  
|**$orderby**: string <br> *in query* | Sorts the results.|
|**$top**: string  <br> *in query* | Returns only the first n results.|
|**$skip**: string <br> *in query*| Skips the first n results.|
|**Authorization**: string default: <br> Bearer access_token <br> *in header* |Specify the type of the token (bearer) and then insert the ```access_token```, which was obtained during authentication.|

!!! info "Supported entityTypePKs"

    The following ```entityTypePK```values are supported:

    |  <div style="width:200px">Entity</div>  |  <div style="width:380px">entityTypePK</div>  |  
    |-----:|:-------|
    |**Purchase Order** | 1 |
    |**Received Invoice**| 4 |
    |**Contacts** | 6 |
    |**Requisition**| 7 |
    |**Adjustments** | 8 |
    |**Proof of Delivery**| 9 |
    |**OCR Invoice** | 10 |
    |**Inventory** | 11 |


### Responses
| <div style="width:200px">Response </div>|<div style="width:380px">Explanation</div>|                      
|-----:|:-------|
|**200 OK**|OK|      
|**400 Bad Request**|Incorrect input data or organization ID does not match with the organization ID user is logged in.|
|**400 Bad Request** | The limit for the ```$top``` query has been exceeded. The value from the incoming request is 'N' (N is your value from the request). You can find the data on the current limit [here](Options_and_Limitations.md#top-and-skip). |
|**401 Unauthorized**|Incorrect specified ```access_token``` or ```access_token``` got expired.|
|**403 Forbidden**|User doesn’t have appropriate privileges.|
|**500 Internal Server Error**|Server encountered an unexpected condition that prevented it from fulfilling the request.|

### Properties
|<div style="width:200px">Property </div> |<div style="width:420px">Explanation</div>|                      
|-----:|:-------|
|**fileId**: string *(uuid)* | Unique Identifier of the file |
|**entityId**: string *(uuid)* | Unique Identifier of the entity |
|**entityNo**: string | Identification Number of the entity |
|**entityTypeValue**: string | Type of the entity |
|**fileName**: string | Name of the file |
|**fileStatus**: string | Status of the file |
|**fileSize**: integer <br> (*int64*) | Size of the file |
|**fileType**: string | Type of the file |
|**dateCreated**: string <br>*(date-time)* | Date when the file was created |
|**createdBy**: string *(uuid)* | Unique Identifier of the user who created the file |
|**createdByName**: string | First and Last Name of the user who created the file |
|**lastUpdated**: string *(date-time)* | Last Date when the file was updated |
|**lastUpdatedBy**: string *(uuid)* | Unique Identifier of the last user who updated the file |
|**lastUpdatedByName**: string | First and Last Name of the last user who updated the file |


``` json title="Response Content-types: APPLICATION/JSON, APPLICATION/XML<br>Response Example (200 OK)"
{
    "@odata.context": "link",
    "@odata.count": "number",
    "value": [
        {
            "fileId": "00000000-0000-0000-0000-000000000000",
            "entityId": "00000000-0000-0000-0000-000000000000",
            "entityNo": "string",
            "entityTypeValue": "string",
            "fileName": "string",
            "fileStatus": "string",
            "fileSize": "integer (int64)",
            "fileType": "string",
            "dateCreated": "string (date-time)",
            "createdBy": "00000000-0000-0000-0000-000000000000",
            "createdByName": "string",
            "lastUpdated": "string (date-time)",
            "lastUpdatedBy": "00000000-0000-0000-0000-000000000000",
            "lastUpdatedByName": "string"
        }
    ],
    "@odata.nextLink": "link"
}
```

## Get the specified file metadata

### Path
GET /odata/FileAttachments/{fileId}/metadata

### Description
Returns the details of the file specified by ID within the logged-in organization.

### Request parameters
|  <div style="width:200px">Parameter</div>  |  <div style="width:380px">Explanation</div>|                      
|-----:|:-------|
|**fileId**: string *(uuid)* <br> <span style="color: #F05D30">**required**</span> <br> *in path* | Enter the ID of the file  here.|
|**api-version**: string default: 1.0 <br> *in header*|The requested API version.|   
|**Authorization**: string default: <br> Bearer access_token <br> *in header* |Specify the type of the token (bearer) and then insert the ```access_token```, which was obtained during authentication.|

### Responses
| <div style="width:200px">Response </div>|<div style="width:380px">Explanation</div>|                      
|-----:|:-------|
|**200 OK**| OK |      
|**400 Bad Request**|Incorrect input data or organization ID does not match with the organization ID user is logged in.|
|**401 Unauthorized**|Incorrect specified ```access_token``` or ```access_token``` got expired.|
|**403 Forbidden**|User doesn’t have appropriate privileges.|
|**404 Not Found** | Specified ID is absent in the system. |
|**500 Internal Server Error**|Server encountered an unexpected condition that prevented it from fulfilling the request.|

### Properties
|<div style="width:200px">Property </div> |<div style="width:420px">Explanation</div>|                      
|-----:|:-------|
|**fileId**: string *(uuid)* | Unique Identifier of the file |
|**entityId**: string *(uuid)* | Unique Identifier of the entity |
|**entityNo**: string | Identification Number of the entity |
|**entityTypeValue**: string | Type of the entity |
|**fileName**: string | Name of the file |
|**fileStatus**: string | Status of the file |
|**fileSize**: integer <br> (*int64*) | Size of the file |
|**fileType**: string | Type of the file |
|**dateCreated**: string <br>*(date-time)* | Date when the file was created |
|**createdBy**: string *(uuid)* | Unique Identifier of the user who created the file |
|**createdByName**: string | First and Last Name of the user who created the file |
|**lastUpdated**: string *(date-time)* | Last Date when the file was updated |
|**lastUpdatedBy**: string *(uuid)* | Unique Identifier of the last user who updated the file |
|**lastUpdatedByName**: string | First and Last Name of the last user who updated the file |

``` json title="Response Content-types: APPLICATION/JSON, APPLICATION/XML<br>Response Example (200 OK)"
{
    "fileId": "00000000-0000-0000-0000-000000000000",
    "entityId": "00000000-0000-0000-0000-000000000000",
    "entityNo": "string",
    "entityTypeValue": "string",
    "fileName": "string",
    "fileStatus": "string",
    "fileSize": "integer (int64)",
    "fileType": "string",
    "dateCreated": "string (date-time)",
    "createdBy": "00000000-0000-0000-0000-000000000000",
    "createdByName": "string",
    "lastUpdated": "string (date-time)",
    "lastUpdatedBy": "00000000-0000-0000-0000-000000000000",
    "lastUpdatedByName": "string"
}
```