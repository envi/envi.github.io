# PurchaseOrders

## Get the list of Purchase Orders

### Path
GET /odata/PurchaseOrders

### Description
Returns a paged list of existing Purchase Orders within the logged-in organization. 


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
|**includeInactiveVendors** <br> boolean default: false <br> *in query* | Include inactive Vendors. |
|**api-version**: string default: 1.0 <br> *in header*| The requested API version.|   
|**$search**: string <br> *in query*  | Picks the value in all possible fields.|
|**$filter**: string <br> *in query* | Filters the results, based on a Boolean condition. | 
|**$orderby**: string <br> *in query* | Sorts the results.| 
|**$top**: string  <br> *in query* | Returns only the first n results.|
|**$skip**: string <br> *in query*| Skips the first n results.|
|**Authorization**: string default: <br> Bearer access_token <br> *in header* |Specify the type of the token (bearer) and then insert the ```access_token```, which was obtained during authentication.|

### Responses
| <div style="width:200px">Response </div>|<div style="width:380px">Explanation</div>|                      
|-----:|:-------|
|**200 OK**|OK|      
|**400 Bad Request**|Incorrect input data or organization ID does not match with the organization ID user is logged in.|
|**400 Bad Request** | The limit for the ```$top``` query has been exceeded. The value from the incoming request is 'N' (N is your value from the request). You can find the data on the current limit [here](Options_and_Limitations.md#top-and-skip).
|**401 Unauthorized**|Incorrect specified ```access_token``` or ```access_token``` got expired.|
|**403 Forbidden**|User doesn’t have appropriate privileges.|
|**500 Internal Server Error**|Server encountered an unexpected condition that prevented it from fulfilling the request.|

### Properties
|<div style="width:200px">Property </div> |<div style="width:420px">Explanation</div>|                      
|-----:|:-------|
|**purchaseOrderId**: string *(uuid)* | Unique Identifier of the Purchase Order |
|**purchaseOrderNo**: string | Number of the Purchase Order |
|**sequenceNo**: integer *(int32)* | Number of the Sequence |
|**facilityId**: string *(uuid)* | Unique Identifier of the Facility |
|**facilityNo**: string | Identification Number of the Facility |
|**facilityName**: string | Name of the Facility |
|**locationId**: string *(uuid)* | Unique Identifier of the Location |
|**locationNo**: string | Identification Number of the Location |
|**locationName**: string | Name of the Location |
|**poTypeId**: integer *(int32)* | Unique Identifier of the Purchase Order Type |
|**poType**: string | Type of the Purchase Order |
|**buyerId**: string *(uuid)* | Unique Identifier of the Buyer |
|**buyerUserName**: string | Name of the Buyer |
|**expectedDeliveryDate**: string <br> *(date-time)* | Expected Delivery Date of the Purchase Order |
|**reference**: string | Information concerning the Transaction |
|**orderDate**: string *(date-time)* | Date when the Order was made |
|**sentBy**: string *(uuid)* | Unique Identifier of the user who sent the Purchase Order |
|**sentByUserName**: string | Name of the user who sent the Purchase Order |
|**returnTypeId**: integer *(int32)* | Unique Identifier of the Return Type |
|**returnType**: string | Type of the Return |
|**returnDate**: string *(date-time)* | Date of the Return |
|**returnedBy**: string *(uuid)* | Unique Identifier of the user who returned the Purchase Order |
|**returnedByUserName**: string | Name of the user who returned the Purchase Order |
|**poStatusId**: integer *(int32)* | Unique Identifier of Purchase Order Status |
|**poStatus**: string | Status of the Purchase Order |
|**invoiceStatusId**: integer *(int32)* | Unique Identifier of the Invoice Status |
|**invoiceStatus**: string | Status of the Invoice |
|**poSourceId**: integer *(int32)* | Unique Identifier of the Purchase Order Source |
|**poSource**: string | Source of the Purchase Order |
|**sendMethodId**: integer *(int32)* | Unique Identifier of the Sending Method |
|**sendMethod**: string | Method of Sending |
|**poConfirmationFlag**: boolean | Is the Purchase Order confirmed or not? |
|**poConfirmationDate**: string <br> *(date-time)* | Date when the Purchase Order was confirmed |
|**poConfirmationName**: string | Name of the Purchase Order Confirmation |
|**poConfirmationNumber**: string | Number of the Purchase Order Confirmation |
|**cerId**: string *(uuid)* | Unique Identifier of the Capital Expenditure Request |
|**cerNo**: string | Number of the Capital Expenditure Request |
|**cerNoDescription**: string | Description of the Capital Expenditure Request Number |
|**paymentTerms**: string | Purchase Order Payment Terms |
|**paymentMethod**: string | Purchase Order Payment Method |
|**billToAccountNo**: string | Number of the Account for sending the Invoice |
|**shipToAccountNo**: string | Number of the Account for sending the Item |
|**fob**: string | Free On Board (Destination or Ship Point) |
|**shipMethod**: string | Method of the Shipment |
|**shipVia**: string | Way of the Shipment |
|**shippingName**: string | Name of the Shipping |
|**shippingAddress1**: string | First Address for sending the product |
|**shippingAddress2**: string | Second Address for sending the product |
|**shippingCity**: string | City for sending the product |
|**shippingState**: string | State for sending the product |
|**shippingZip**: string | Zip for sending the product |
|**shippingContactName**: string | Name of the main contact point for sending the product |
|**shippingContactPhone**: string | Phone of the main contact point for sending the product |
|**shippingContactExt**: string | External phone of the main contact point for sending the product |
|**shippingContactEmail**: string | Email of the main contact point for sending the product |
|**shippingContactFax**: string | Fax of the main contact point for sending the product |
|**billingName**: string | Name of the Billing |
|**billingAddress1**: string | First Address for sending the Invoice |
|**billingAddress2**: string | Second Address for sending the Invoice |
|**billingCity**: string | City for sending the Invoice |
|**billingState**: string | State for sending the Invoice |
|**billingZip**: string | Zip for sending the Invoice |
|**billingContactName**: string | Name of the main contact point for sending the Invoice |
|**billingContactPhone**: string | Phone of the main contact point for sending the Invoice |
|**billingContactExt**: string | External phone of the main contact point for sending the Invoice |
|**billingContactEmail**: string | Email of the main contact point for sending the Invoice |
|**billingContactFax**: string | Fax of the main contact point for sending the Invoice |
|**vendorId**: string *(uuid)* | Unique Identifier of the Vendor |
|**vendorNo**: string | Code of the Supplier who sells products |
|**vendorName**: string | Name of the Vendor |
|**lastUpdated**: string *(date-time)* | Last Date when the Purchase Order was updated |
|**lastUpdatedBy**: string *(uuid)* | Unique Identifier of the last user who updated the Purchase Order |
|**lastUpdatedByUserName**: string | Name of the last user who updated the Purchase Order |
|**dateCreated**: string *(date-time)* | Date when the Purchase Order was created |
|**discount**: number *(double)* | Discount for the Purchase Order |
|**discountTypeId**: integer *(int32)* | Unique Identifier of the Discount Type for the Purchase Order |
|**discountType**: string | Type of the discount for the Purchase Order |
|**salesTax**: number *(double)* | Tax for the Sales |
|**salesTaxId**: integer *(int32)* | Unique Identifier of the Tax for the Sales |
|**salesTaxType**: string | Type of the Tax for the Sales |
|**shipping**: number *(double)* | Number of the Shipping |
|**shippingTypeId**: integer *(int32)* | Unique Identifier of the Shipping Type |
|**shippingType**: string | Type of the Shipping |
|**poUdfLabels**: string | Purchase Order User Defined Field labels |
|**projectNoId**: string *(uuid)* | Unique Identifier of the Project Number |
|**projectNo**: string | Project Number for the Purchase Order|
|**projectNoDescription**: string | Description of the Project Number |

``` json title="Response Content-types: APPLICATION/JSON, APPLICATION/XML<br>Response example (200 OK)"
{
    "@odata.context": "link",
    "@odata.count": "number",
    "value": [
        {
            "purchaseOrderId": "00000000-0000-0000-0000-000000000000",
            "purchaseOrderNo": "string",
            "sequenceNo": "integer (int32)",
            "facilityId": "00000000-0000-0000-0000-000000000000",
            "facilityNo": "string",
            "facilityName": "string",
            "locationId": "00000000-0000-0000-0000-000000000000",
            "locationNo": "string",
            "locationName": "string",
            "poTypeId": "integer (int32)",
            "poType": "string",
            "buyerId": "00000000-0000-0000-0000-000000000000",
            "buyerUserName": "string",
            "expectedDeliveryDate": "string (date-time)",
            "reference": "string",
            "orderDate": "string (date-time)",
            "sentBy": "00000000-0000-0000-0000-000000000000",
            "sentByUserName": "string",
            "returnTypeId": "integer (int32)",
            "returnType": "string",
            "returnDate": "string (date-time)",
            "returnedBy": "00000000-0000-0000-0000-000000000000",
            "returnedByUserName": "string",
            "poStatusId": "integer (int32)",
            "poStatus": "string",
            "invoiceStatusId": "integer (int32)",
            "invoiceStatus": "string",
            "poSourceId": "integer (int32)",
            "poSource": "string",
            "sendMethodId": "integer (int32)",
            "sendMethod": "string",
            "poConfirmationFlag": "boolean",
            "poConfirmationDate": "string (date-time)",
            "poConfirmationName": "string",
            "poConfirmationNumber": "string",
            "cerId": "00000000-0000-0000-0000-000000000000",
            "cerNo": "string",
            "cerNoDescription": "string",
            "paymentTerms": "string",
            "paymentMethod": "string",
            "billToAccountNo": "string",
            "shipToAccountNo": "string",
            "fob": "string",
            "shipMethod": "string",
            "shipVia": "string",
            "shippingName": "string",
            "shippingAddress1": "string",
            "shippingAddress2": "string",
            "shippingCity": "string",
            "shippingState": "string",
            "shippingZip": "string",
            "shippingContactName": "string",
            "shippingContactPhone": "string",
            "shippingContactExt": "string",
            "shippingContactEmail": "string",
            "shippingContactFax": "string",
            "billingName": "string",
            "billingAddress1": "string",
            "billingAddress2": "string",
            "billingCity": "string",
            "billingState": "string",
            "billingZip": "string",
            "billingContactName": "string",
            "billingContactPhone": "string",
            "billingContactExt": "string",
            "billingContactEmail": "string",
            "billingContactFax": "string",
            "vendorId": "00000000-0000-0000-0000-000000000000",
            "vendorNo": "string",
            "vendorName": "string",
            "lastUpdated": "string (date-time)",
            "lastUpdatedBy": "00000000-0000-0000-0000-000000000000",
            "lastUpdatedByUserName": "string",
            "dateCreated": "string (date-time)",
            "discount": "number (double)",
            "discountTypeId": "integer (int32)",
            "discountType": "string",
            "salesTax": "number (double)",
            "salesTaxId": "integer (int32)",
            "salesTaxType": "string",
            "shipping": "number (double)",
            "shippingTypeId": "integer (int32)",
            "shippingType": "string",
            "poUdfLabels": "[{\"Name\":\"string1\",\"Value\":\"string2\"}]",
            "projectNoId": "00000000-0000-0000-0000-000000000000",
            "projectNo": "string",
            "projectNoDescription": "string"
        }
    ],
    "@odata.nextLink": "link"
}
```

#### poUdfLabels property overview

The ```poUdfLabels``` property defines User Defined Field (UDF) labels on Purchase Orders. This section explains the property details.

The response for the ```poUdfLabels``` property is as follows: <br>
```"poUdfLabels": "[{\"Name\":\"string1\",\"Value\":\"string2\"}]"``` <br>
 Where: <br>

 - ```"string1"``` is the value from the **Label** field under **Organization** > **Org Configuration** > **UDF Setup**. <br>
 - ```"string2"``` is the value from the **UDF** field under **Purchasing** > **Purchase Orders** > **PO Details**. <br>
    
If the **UDF** field on the **PO Details** page is empty, the response is: <br>
```"poUdfLabels": "[{\"Name\":\"string1\",\"Value\": null}]"``` <br>

If the **Purchasing** module is **Inactive** or not added for an organization under **Organization** > **Org Configuration** > **UDF Setup**, the response is: <br>
```"poUdfLabels": "[]"``` <br>

Filters (```$equals```, ```$contains```, ```$skip```, ```$top```) and logical operators (```in```, ```or```, ```and```) apply only to **UDF** field values.



## Get the specified Purchase Order

### Path
GET /odata/PurchaseOrders({purchaseOrderId})

### Description
Returns the details of the Purchase Order specified by ID.

### Request parameters
|  <div style="width:200px">Parameter</div>  |  <div style="width:380px">Explanation</div>  |                      
|-----:|:-------|
|**includeInactiveVendors** <br> boolean default: false <br> *in query* | Include inactive Vendors.|
|**purchaseOrderId**: string *(uuid)*  <br> <span style="color: #F05D30">**required**</span> <br> *in path* | Enter the ID of the Purchase Order here. |
|**api-version**: string default: 1.0 <br> *in header*| The requested API version.|   
|**Authorization**: string default: <br> Bearer access_token <br> *in header* |Specify the type of the token (bearer) and then insert the ```access_token```, which was obtained during authentication. |

### Responses
| <div style="width:200px">Response </div>|<div style="width:380px">Explanation</div>|                      
|-----:|:-------|
|**200 OK**|OK|      
|**400 Bad Request**|Incorrect input data or organization ID does not match with the organization ID user is logged in.|
|**401 Unauthorized**|Incorrect specified ```access_token``` or ```access_token``` got expired.|
|**403 Forbidden**|User doesn’t have appropriate privileges.|
|**404 Not Found** | Specified ID is absent in the system. |
|**500 Internal Server Error**|Server encountered an unexpected condition that prevented it from fulfilling the request.|

### Properties
|<div style="width:200px">Property </div> |<div style="width:420px">Explanation</div>|                      
|-----:|:-------|
|**purchaseOrderId**: string *(uuid)* | Unique Identifier of the Purchase Order |
|**purchaseOrderNo**: string | Number of the Purchase Order |
|**sequenceNo**: integer *(int32)* | Number of the Sequence |
|**facilityId**: string *(uuid)* | Unique Identifier of the Facility |
|**facilityNo**: string | Identification Number of the Facility |
|**facilityName**: string | Name of the Facility |
|**locationId**: string *(uuid)* | Unique Identifier of the Location |
|**locationNo**: string | Identification Number of the Location |
|**locationName**: string | Name of the Location |
|**poTypeId**: integer *(int32)* | Unique Identifier of the Purchase Order Type |
|**poType**: string | Type of the Purchase Order |
|**buyerId**: string *(uuid)* | Unique Identifier of the Buyer |
|**buyerUserName**: string | Name of the Buyer |
|**expectedDeliveryDate**: string <br> *(date-time)* | Expected Delivery Date of the Purchase Order |
|**reference**: string | Information concerning the Transaction |
|**orderDate**: string *(date-time)* | Date when the Order was made |
|**sentBy**: string *(uuid)* | Unique Identifier of the user who sent the Purchase Order |
|**sentByUserName**: string | Name of the user who sent the Purchase Order |
|**returnTypeId**: integer *(int32)* | Unique Identifier of the Return Type |
|**returnType**: string | Type of the Return |
|**returnDate**: string *(date-time)* | Date of the Return |
|**returnedBy**: string *(uuid)* | Unique Identifier of the user who returned the Purchase Order |
|**returnedByUserName**: string | Name of the user who returned the Purchase Order |
|**poStatusId**: integer *(int32)* | Unique Identifier of Purchase Order Status |
|**poStatus**: string | Status of the Purchase Order |
|**invoiceStatusId**: integer *(int32)* | Unique Identifier of the Invoice Status |
|**invoiceStatus**: string | Status of the Invoice |
|**poSourceId**: integer *(int32)* | Unique Identifier of the Purchase Order Source |
|**poSource**: string | Source of the Purchase Order |
|**sendMethodId**: integer *(int32)* | Unique Identifier of the Sending Method |
|**sendMethod**: string | Method of Sending |
|**poConfirmationFlag**: boolean | Is the Purchase Order confirmed or not? |
|**poConfirmationDate**: string <br> *(date-time)* | Date when the Purchase Order was confirmed |
|**poConfirmationName**: string | Name of the Purchase Order Confirmation |
|**poConfirmationNumber**: string | Number of the Purchase Order Confirmation |
|**cerId**: string *(uuid)* | Unique Identifier of the Capital Expenditure Request |
|**cerNo**: string | Number of the Capital Expenditure Request |
|**cerNoDescription**: string | Description of the Capital Expenditure Request Number |
|**paymentTerms**: string | Purchase Order Payment Terms |
|**paymentMethod**: string | Purchase Order Payment Method |
|**billToAccountNo**: string | Number of the Account for sending the Invoice |
|**shipToAccountNo**: string | Number of the Account for sending the Item |
|**fob**: string | Free On Board (Destination or Ship Point) |
|**shipMethod**: string | Method of the Shipment |
|**shipVia**: string | Way of the Shipment |
|**shippingName**: string | Name of the Shipping |
|**shippingAddress1**: string | First Address for sending the product |
|**shippingAddress2**: string | Second Address for sending the product |
|**shippingCity**: string | City for sending the product |
|**shippingState**: string | State for sending the product |
|**shippingZip**: string | Zip for sending the product |
|**shippingContactName**: string | Name of the main contact point for sending the product |
|**shippingContactPhone**: string | Phone of the main contact point for sending the product |
|**shippingContactExt**: string | External phone of the main contact point for sending the product |
|**shippingContactEmail**: string | Email of the main contact point for sending the product |
|**shippingContactFax**: string | Fax of the main contact point for sending the product |
|**billingName**: string | Name of the Billing |
|**billingAddress1**: string | First Address for sending the Invoice |
|**billingAddress2**: string | Second Address for sending the Invoice |
|**billingCity**: string | City for sending the Invoice |
|**billingState**: string | State for sending the Invoice |
|**billingZip**: string | Zip for sending the Invoice |
|**billingContactName**: string | Name of the main contact point for sending the Invoice |
|**billingContactPhone**: string | Phone of the main contact point for sending the Invoice |
|**billingContactExt**: string | External phone of the main contact point for sending the Invoice |
|**billingContactEmail**: string | Email of the main contact point for sending the Invoice |
|**billingContactFax**: string | Fax of the main contact point for sending the Invoice |
|**vendorId**: string *(uuid)* | Unique Identifier of the Vendor |
|**vendorNo**: string | Code of the Supplier who sells products |
|**vendorName**: string | Name of the Vendor |
|**lastUpdated**: string *(date-time)* | Last Date when the Purchase Order was updated |
|**lastUpdatedBy**: string *(uuid)* | Unique Identifier of the last user who updated the Purchase Order |
|**lastUpdatedByUserName**: string | Name of the last user who updated the Purchase Order |
|**dateCreated**: string *(date-time)* | Date when the Purchase Order was created |
|**discount**: number *(double)* | Discount for the Purchase Order |
|**discountTypeId**: integer *(int32)* | Unique Identifier of the Discount Type for the Purchase Order |
|**discountType**: string | Type of the discount for the Purchase Order |
|**salesTax**: number *(double)* | Tax for the Sales |
|**salesTaxId**: integer *(int32)* | Unique Identifier of the Tax for the Sales |
|**salesTaxType**: string | Type of the Tax for the Sales |
|**shipping**: number *(double)* | Number of the Shipping |
|**shippingTypeId**: integer *(int32)* | Unique Identifier of the Shipping Type |
|**shippingType**: string | Type of the Shipping |
|**poUdfLabels**: string | Purchase Order User Defined Field labels |
|**projectNoId**: string *(uuid)* | Unique Identifier of the Project Number |
|**projectNo**: string | Project Number for the Purchase Order|
|**projectNoDescription**: string | Description of the Project Number |

``` json title="Response Content-types: APPLICATION/JSON, APPLICATION/XML<br>Response example (200 OK)"
{
    "@odata.context": "link",
    "purchaseOrderId": "00000000-0000-0000-0000-000000000000",
    "purchaseOrderNo": "string",
    "sequenceNo": "integer (int32)",
    "facilityId": "00000000-0000-0000-0000-000000000000",
    "facilityNo": "string",
    "facilityName": "string",
    "locationId": "00000000-0000-0000-0000-000000000000",
    "locationNo": "string",
    "locationName": "string",
    "poTypeId": "integer (int32)",
    "poType": "string",
    "buyerId": "00000000-0000-0000-0000-000000000000",
    "buyerUserName": "string",
    "expectedDeliveryDate": "string (date-time)",
    "reference": "string",
    "orderDate": "string (date-time)",
    "sentBy": "00000000-0000-0000-0000-000000000000",
    "sentByUserName": "string",
    "returnTypeId": "integer (int32)",
    "returnType": "string",
    "returnDate": "string (date-time)",
    "returnedBy": "00000000-0000-0000-0000-000000000000",
    "returnedByUserName": "string",
    "poStatusId": "integer (int32)",
    "poStatus": "string",
    "invoiceStatusId": "integer (int32)",
    "invoiceStatus": "string",
    "poSourceId": "integer (int32)",
    "poSource": "string",
    "sendMethodId": "integer (int32)",
    "sendMethod": "string",
    "poConfirmationFlag": "boolean",
    "poConfirmationDate": "string (date-time)",
    "poConfirmationName": "string",
    "poConfirmationNumber": "string",
    "cerId": "00000000-0000-0000-0000-000000000000",
    "cerNo": "string",
    "cerNoDescription": "string",
    "paymentTerms": "string",
    "paymentMethod": "string",
    "billToAccountNo": "string",
    "shipToAccountNo": "string",
    "fob": "string",
    "shipMethod": "string",
    "shipVia": "string",
    "shippingName": "string",
    "shippingAddress1": "string",
    "shippingAddress2": "string",
    "shippingCity": "string",
    "shippingState": "string",
    "shippingZip": "string",
    "shippingContactName": "string",
    "shippingContactPhone": "string",
    "shippingContactExt": "string",
    "shippingContactEmail": "string",
    "shippingContactFax": "string",
    "billingName": "string",
    "billingAddress1": "string",
    "billingAddress2": "string",
    "billingCity": "string",
    "billingState": "string",
    "billingZip": "string",
    "billingContactName": "string",
    "billingContactPhone": "string",
    "billingContactExt": "string",
    "billingContactEmail": "string",
    "billingContactFax": "string",
    "vendorId": "00000000-0000-0000-0000-000000000000",
    "vendorNo": "string",
    "vendorName": "string",
    "lastUpdated": "string (date-time)",
    "lastUpdatedBy": "00000000-0000-0000-0000-000000000000",
    "lastUpdatedByUserName": "string",
    "dateCreated": "string (date-time)",
    "discount": "number (double)",
    "discountTypeId": "integer (int32)",
    "discountType": "string",
    "salesTax": "number (double)",
    "salesTaxId": "integer (int32)",
    "salesTaxType": "string",
    "shipping": "number (double)",
    "shippingTypeId": "integer (int32)",
    "shippingType": "string",
    "poUdfLabels": "[{\"Name\":\"string1\",\"Value\":\"string2\"}]",
    "projectNoId": "00000000-0000-0000-0000-000000000000",
    "projectNo": "string",
    "projectNoDescription": "string"
}
```

!!! note

    For more details on ```poUdfLabels``` property, refer to the [poUdfLabels property overview](#poudflabels-property-overview) section.

## Get the list of Purchase Order Items for the specified Purchase Order

### Path
GET /odata/PurchaseOrders({purchaseOrderId})/purchaseOrderItems

### Description
Returns a paged list of existing Purchase Order Items within the Purchase Order specified by ID. 

!!! note

    You can filter the results as follows:

    - For an exact match, use: ```$filter parameter–entity eq ‘string’```
    - For a partial match, use: ```$filter=contains parameter–contains(entity, ‘string’)```

### Request parameters
|  <div style="width:200px">Parameter</div>  |  <div style="width:380px">Explanation</div>  |                      
|-----:|:-------|
|**purchaseOrderId**: string *(uuid)*  <br> <span style="color: #F05D30">**required**</span> <br> *in path* | Enter the ID of the Purchase Order here. |
|**api-version**: string default: 1.0 <br> *in header*| The requested API version.|   
|**$search**: string <br> *in query*  | Picks the value in all possible fields.|
|**$filter**: string <br> *in query* | Filters the results, based on a Boolean condition. | 
|**$orderby**: string <br> *in query* | Sorts the results.| 
|**$top**: string  <br> *in query* | Returns only the first n results.|
|**$skip**: string <br> *in query*| Skips the first n results.|
|**Authorization**: string default: <br> Bearer access_token <br> *in header* |Specify the type of the token (bearer) and then insert the ```access_token```, which was obtained during authentication.|

### Responses
| <div style="width:200px">Response </div>|<div style="width:380px">Explanation</div>|                      
|-----:|:-------|
|**200 OK**|OK|      
|**400 Bad Request**|Incorrect input data or organization ID does not match with the organization ID user is logged in.|
|**400 Bad Request** | The limit for the ```$top``` query has been exceeded. The value from the incoming request is 'N' (N is your value from the request). You can find the data on the current limit [here](Options_and_Limitations.md#top-and-skip).
|**401 Unauthorized**|Incorrect specified ```access_token``` or ```access_token``` got expired.|
|**403 Forbidden**|User doesn’t have appropriate privileges.|
|**500 Internal Server Error**|Server encountered an unexpected condition that prevented it from fulfilling the request.|

### Properties
|<div style="width:200px">Property </div> |<div style="width:420px">Explanation</div>|                      
|-----:|:-------|
|**purchaseOrderItemId**: string *(uuid)* | Unique Identifier of the Purchase Order Item |
|**purchaseOrderNo**: string | Number of the Purchase Order Item |
|**sequenceNo**: integer *(int32)* | Number of the Sequence |
|**purchaseOrderId**: string *(uuid)* | Unique Identifier of the Purchase Order |
|**facilityId**: string *(uuid)* | Unique Identifier of the Facility |
|**facilityNo**: string | Identification Number of the Facility |
|**facilityName**: string | Name of the Facility |
|**lineItemNo**: integer *(int32)* | Number of the Line Item |
|**locationNo**: string | Identification Number of the Location |
|**locationName**: string | Name of the Location |
|**inventoryLocationId**: string *(uuid)* | Unique Identifier of the Inventory Location |
|**inventoryVendorId**: string *(uuid)* | Unique Identifier of the Inventory Vendor |
|**vendorNo**: string | Code of the Supplier who sells products |
|**vendorName**: string | Name of the Vendor |
|**vendorPriority**: integer *(int32)* | Priority of the Vendor |
|**inventoryNo**: string | Identification code of the Inventory Item |
|**classificationId**: string *(uuid)* | Unique Identifier of the Inventory Category defined on the Organization level |
|**classificationName**: string | Name of the Category of the Inventory defined on the Organization level |
|**classification2Id**: string *(uuid)* | Second Unique Identifier of the Inventory Category defined on the Organization level |
|**classification2Name**: string | Name of the second Category of the Inventory defined on the Organization level |
|**inventoryDescription**: string | Description of the Inventory Item |
|**vendorItemNo**: string | Code that is used by the Vendor for the Item identification |
|**manufacturerId**: string *(uuid)* | Unique Identifier of the Manufacturer |
|**manufacturerNo**: string | Number of the Manufacturer |
|**manufacturerName**: string | Name of the Manufacturer |
|**manufacturerItemNo**: string | Item Number of the Manufacturer |
|**orderQuantity**: integer *(int32)* | Quantity specified in the Order |
|**orderUOM**: string | Unit of Measure specified in the Order |
|**orderConversionFactor**: integer <br> *(int32)* | Number of Stock Keeping Units in another Unit of Measure specified in the Order |
|**stockUOM**: | string Unit of Measure to track Inventory Balance |
|**unitCost**: number *(double)* | Cost of the one unit of Purchase Order Item |
|**departmentGLCode**: string | General Ledger Code of the Department |
|**glCode**: string | General Ledger Code |
|**lineItemTypeId**: integer *(int32)* | Unique Identifier of the Line Item Type |
|**itemType**: string | Type of the Line Item |
|**lineItemNotes**: string | Comments about the Line Item |
|**contractNo**: string | Number of the Contract |
|**contractExpDate**: string *(date-time)* | Expiration Date of the Contract |
|**lastUpdated**: string *(date-time)* | Last Date when the Purchase Order Item was updated |
|**lastUpdatedBy**: string *(uuid)* | Unique Identifier of the last user who updated the Purchase Order Item |
|**lastUpdatedByUserName**: string | Name of the last user who updated the Purchase Order Item |
|**dateCreated**: string *(date-time)* | Date when the Purchase Order Item was created 
|**createdBy**: string *(uuid)* | Unique Identifier of the user who created the Purchase Order Item |
|**createdByUserName**: string | Name of the user who created the Purchase Order Item |
|**isTaxable**: boolean | Is Purchase Order Item Taxable or not? |
|**returnPOItemId**: string *(uuid)* | Unique Identifier of the return Purchase Order Item |
|**internalNotes**: string | Internal Comments about the Purchase Order Item |
|**lotNo**: string | Identification Number assigned to a particular Quantity or Lot of material from a single Manufacturer |
|**serialNo**: string | Unique Identifier assigned incrementally or sequentially to an Item to uniquely identify it |
|**expirationDate**: string <br> *(date-time)* | Previously determined date after which Item should no longer be used |
|**activeStatus**: boolean | Is Purchase Order Item active or not? |
|**activeStatusLastUpdated**: string <br> *(date-time)* | Last Date when the Active Status of the Purchase Order Item was updated |
|**activeStatusLastUpdatedBy**: <br> string *(uuid)* | Unique Identifier of the last user who updated the Active Status of the Purchase Order Item |
|**activeStatusLastUpdatedBy<br>UserName**: string | Name of the last user who updated the Active Status of the Purchase Order Item |
|**supplierPartAuxiliaryID**: string | Unique Identifier of the Supplier Part Auxiliary |
|**submittedUnitCost**: number *(double)* | Cost of the one unit of item that was submitted for the Purchase Order Item |
|**departmentId**: string *(uuid)* | Unique Identifier of the Department |
|**departmentNo**: string | Number of the Department |
|**departmentName**: string | Name of the Department |
|**poUdfLabels**: string | Purchase Order User Defined Field labels |

``` json title="Response Content-types: APPLICATION/JSON, APPLICATION/XML<br>Response example (200 OK)"
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
            "poUdfLabels": "[{\"Name\":\"string1\",\"Value\":\"string2\"}]"
        }
    ],
    "@odata.nextLink": "link"
}
```

!!! note

    For more details on ```poUdfLabels``` property, refer to the [poUdfLabels property overview](#poudflabels-property-overview) section.

