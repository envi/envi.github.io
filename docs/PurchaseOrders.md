# PurchaseOrders

## Get the list of Purchase Orders

### Path
GET /odata/PurchaseOrders

### Description
Returns a paged list of existing Purchase Orders within the logged-in organization. 

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

|  <div style="width:200px">Parameter</div>  |  <div style="width:380px">Explanation</div>  |                      
|-----:|:-------|
|**includeInactiveVendors** <br> boolean default: false <br> *in query* | Include inactive Vendors. |
|**api-version**: string default: 1.0 <br> *in header*| The requested API version.|
|**$search**: string <br> *in query*  | Searches across all supported fields. |
|**$filter**: string <br> *in query* | Filters results based on a Boolean condition.|
|**$orderby**: string <br> *in query* | Sorts results.|
|**$top**: string  <br> *in query* | Returns only the first n results.|
|**$skip**: string <br> *in query*| Skips the first n results.|
|**Authorization**: string default: <br> Bearer access_token <br> *in header* | Specify the type of the token (bearer) and insert the ```access_token``` obtained during authentication. |

### Responses
| <div style="width:200px">Response </div>|<div style="width:380px">Explanation</div>|                      
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
|**purchaseOrderId**: string *(uuid)* | Unique identifier of the Purchase Order |
|**purchaseOrderNo**: string | Number of the Purchase Order |
|**sequenceNo**: integer *(int32)* | Sequence number |
|**facilityId**: string *(uuid)* | Unique identifier of the Facility |
|**facilityNo**: string | Identification number of the Facility |
|**facilityName**: string | Name of the Facility |
|**locationId**: string *(uuid)* | Unique identifier of the Location |
|**locationNo**: string | Identification number of the Location |
|**locationName**: string | Name of the Location |
|**poTypeId**: integer *(int32)* | Unique identifier of the Purchase Order type |
|**poType**: string | Type of the Purchase Order |
|**buyerId**: string *(uuid)* | Unique identifier of the Buyer |
|**buyerUserName**: string | Name of the Buyer |
|**expectedDeliveryDate**: string <br> *(date-time)* | Expected delivery date of the Purchase Order |
|**reference**: string | Reference information for the Purchase Order |
|**orderDate**: string *(date-time)* | Date when the Purchase Order was placed |
|**sentBy**: string *(uuid)* | Unique identifier of the user who sent the Purchase Order |
|**sentByUserName**: string | Name of the user who sent the Purchase Order |
|**returnTypeId**: integer *(int32)* | Unique identifier of the Return PO type |
|**returnType**: string | Return PO type |
|**returnDate**: string *(date-time)* | Return date for a Return PO |
|**returnedBy**: string *(uuid)* | Unique identifier of the user who returned the Purchase Order |
|**returnedByUserName**: string | Name of the user who returned the Purchase Order |
|**poStatusId**: integer *(int32)* | Unique identifier of the Purchase Order status |
|**poStatus**: string | Status of the Purchase Order |
|**invoiceStatusId**: integer *(int32)* | Unique identifier of the Invoice status |
|**invoiceStatus**: string | Status of the Invoice |
|**poSourceId**: integer *(int32)* | Unique identifier of the Purchase Order source |
|**poSource**: string | Source of the Purchase Order |
|**sendMethodId**: integer *(int32)* | Unique identifier of the send method |
|**sendMethod**: string | Send method used for the Purchase Order |
|**poConfirmationFlag**: boolean | Is the Purchase Order confirmed or not? |
|**poConfirmationDate**: string <br> *(date-time)* | Date when the Purchase Order was confirmed  |
|**poConfirmationName**: string | Name of the Purchase Order confirmation  |
|**poConfirmationNumber**: string | Number of the Purchase Order confirmation |
|**cerId**: string *(uuid)* | Unique identifier of the Capital Expenditure Request |
|**cerNo**: string | Number of the Capital Expenditure Request |
|**cerNoDescription**: string | Description of the Capital Expenditure Request number |
|**paymentTerms**: string | Purchase Order payment terms |
|**paymentMethod**: string | Purchase Order payment method |
|**billToAccountNo**: string | Account number used for billing |
|**shipToAccountNo**: string | Account number used for shipping |
|**fob**: string | Free On Board (destination or ship point) |
|**shipMethod**: string | Shipping method used for the Purchase Order |
|**shipVia**: string | Shipping carrier or service used for the Purchase Order |
|**shippingName**: string | Shipping name |
|**shippingAddress1**: string | Primary shipping address |
|**shippingAddress2**: string | Secondary shipping address |
|**shippingCity**: string | City of the shipping address |
|**shippingState**: string | State of the shipping address |
|**shippingZip**: string | Zip code of the shipping address |
|**shippingContactName**: string | Name of the shipping contact |
|**shippingContactPhone**: string | Phone number of the shipping contact |
|**shippingContactExt**: string | Phone extension of the shipping contact |
|**shippingContactEmail**: string | Email address of the shipping contact |
|**shippingContactFax**: string | Fax number of the shipping contact |
|**billingName**: string | Billing name |
|**billingAddress1**: string | Primary billing address |
|**billingAddress2**: string | Secondary billing address |
|**billingCity**: string | City of the billing address |
|**billingState**: string | State of the billing address |
|**billingZip**: string | Zip code of the billing address  |
|**billingContactName**: string | Name of the billing contact |
|**billingContactPhone**: string | Phone number of the billing contact |
|**billingContactExt**: string | Phone extension of the billing contact |
|**billingContactEmail**: string | Email address of the billing contact |
|**billingContactFax**: string | Fax number of the billing contact |
|**vendorId**: string *(uuid)* | Unique identifier of the Vendor |
|**vendorNo**: string | Number of the Vendor |
|**vendorName**: string | Name of the Vendor |
|**lastUpdated**: string *(date-time)* | Date when the Purchase Order was last updated |
|**lastUpdatedBy**: string *(uuid)* | Unique identifier of the user who last updated the Purchase Order |
|**lastUpdatedByName**: string | Name of the user who last updated the Purchase Order |
|**dateCreated**: string *(date-time)* | Date when the Purchase Order was created |
|**discount**: number *(double)* | Discount for the Purchase Order |
|**discountTypeId**: integer *(int32)* | Unique identifier of the discount type |
|**discountType**: string | Type of the discount |
|**salesTax**: number *(double)* | Sales tax for the Purchase Order |
|**salesTaxId**: integer *(int32)* | Unique identifier of the sales tax |
|**salesTaxType**: string | Type of the sales tax |
|**shipping**: number *(double)* | Shipping cost |
|**shippingTypeId**: integer *(int32)* | Unique identifier of the shipping type |
|**shippingType**: string | Type of the shipping |
|**poUdfLabels**: string | User-Defined Field labels for the Purchase Order. <br> **Note**: See the [poUdfLabels](PurchaseOrders.md#poudflabels) section for more details. |
|**projectNoId**: string *(uuid)* | Unique identifier of the project number |
|**projectNo**: string | Project number for the Purchase Order |
|**projectNoDescription**: string | Description of the project number |
|**consignmentOrder**: boolean | Is the Purchase Order a Consignment order or not? |

``` json title="Response example (200 OK)"
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
            "projectNoDescription": "string",
            "consignmentOrder": "boolean"
        }
    ],
    "@odata.nextLink": "link"
}
```

#### poUdfLabels

The ```poUdfLabels``` property defines User-Defined Field labels on Purchase Orders.

The ```poUdfLabels``` property is returned in the following format: <br>
```"poUdfLabels": "[{\"Name\":\"string1\",\"Value\":\"string2\"}]"``` <br>

where: <br>

 - ```"string1"``` is the value from the **Label** field under **Organization** > **Org Configuration** > **UDF Setup**. <br>
 - ```"string2"``` is the value from the **UDF** field under **Purchasing** > **Purchase Orders** > **PO Details**. <br>
    
If the **UDF** field on the **PO Details** page is empty, the response is: <br>
```"poUdfLabels": "[{\"Name\":\"string1\",\"Value\": null}]"``` <br>

If the **Purchasing** module is **Inactive** or has not been added for an organization under **Organization** > **Org Configuration** > **UDF Setup**, the response is: <br>
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
|**includeInactiveVendors** <br> boolean default: false <br> *in query* | Include inactive Vendors. |
|**purchaseOrderId**: string *(uuid)*  <br> <span style="color: #F05D30">**required**</span> <br> *in path* | Enter the ID of the Purchase Order. |
|**api-version**: string default: 1.0 <br> *in header*| The requested API version. |   
|**Authorization**: string default: <br> Bearer access_token <br> *in header* | Specify the type of the token (bearer) and insert the ```access_token``` obtained during authentication. |

### Responses
| <div style="width:200px">Response </div>|<div style="width:380px">Explanation</div>|                      
|-----:|:-------|
|**200 OK**| OK | 
|**400 Bad Request**| The request contains incorrect input data. |         
|**401 Unauthorized**| The specified ```access_token``` is invalid or has expired. |
|**403 Forbidden**| The user doesn’t have the appropriate privileges. |
|**404 Not Found** | The specified ID is absent in the system. |
|**500 Internal Server Error**| The server encountered an unexpected condition that prevented it from fulfilling the request.|

### Properties
|<div style="width:200px">Property </div> |<div style="width:420px">Explanation</div>|                      
|-----:|:-------|
|**purchaseOrderId**: string *(uuid)* | Unique identifier of the Purchase Order |
|**purchaseOrderNo**: string |  Number of the Purchase Order |
|**sequenceNo**: integer *(int32)* | Sequence number |
|**facilityId**: string *(uuid)* | Unique identifier of the Facility |
|**facilityNo**: string | Identification number of the Facility |
|**facilityName**: string | Name of the Facility |
|**locationId**: string *(uuid)* | Unique identifier of the Location |
|**locationNo**: string | Identification number of the Location |
|**locationName**: string | Name of the Location |
|**poTypeId**: integer *(int32)* | Unique identifier of the Purchase Order type |
|**poType**: string | Type of the Purchase Order |
|**buyerId**: string *(uuid)* | Unique identifier of the Buyer |
|**buyerUserName**: string | Name of the Buyer |
|**expectedDeliveryDate**: string <br> *(date-time)* | Expected delivery date of the Purchase Order |
|**reference**: string | Reference information for the Purchase Order |
|**orderDate**: string *(date-time)* | Date when the Purchase Order was placed |
|**sentBy**: string *(uuid)* | Unique identifier of the user who sent the Purchase Order |
|**sentByUserName**: string | Name of the user who sent the Purchase Order |
|**returnTypeId**: integer *(int32)* | Unique identifier of the Return PO type |
|**returnType**: string | Return PO type |
|**returnDate**: string *(date-time)* | Return date for a Return PO |
|**returnedBy**: string *(uuid)* | Unique identifier of the user who returned the Purchase Order |
|**returnedByUserName**: string | Name of the user who returned the Purchase Order |
|**poStatusId**: integer *(int32)* | Unique identifier of the Purchase Order status |
|**poStatus**: string | Status of the Purchase Order |
|**invoiceStatusId**: integer *(int32)* | Unique identifier of the Invoice status |
|**invoiceStatus**: string | Status of the Invoice |
|**poSourceId**: integer *(int32)* | Unique identifier of the Purchase Order source |
|**poSource**: string | Source of the Purchase Order |
|**sendMethodId**: integer *(int32)* | Unique identifier of the send method |
|**sendMethod**: string | Send method used for the Purchase Order |
|**poConfirmationFlag**: boolean | Is the Purchase Order confirmed or not? |
|**poConfirmationDate**: string <br> *(date-time)* | Date when the Purchase Order was confirmed |
|**poConfirmationName**: string | Name of the Purchase Order confirmation |
|**poConfirmationNumber**: string | Number of the Purchase Order confirmation |
|**cerId**: string *(uuid)* | Unique identifier of the Capital Expenditure Request |
|**cerNo**: string | Number of the Capital Expenditure Request |
|**cerNoDescription**: string | Description of the Capital Expenditure Request number |
|**paymentTerms**: string | Purchase Order payment terms |
|**paymentMethod**: string | Purchase Order payment method |
|**billToAccountNo**: string | Account number used for billing |
|**shipToAccountNo**: string | Account number used for shipping |
|**fob**: string | Free On Board (destination or ship point) |
|**shipMethod**: string | Shipping method used for the Purchase Order |
|**shipVia**: string | Shipping carrier or service used for the Purchase Order |
|**shippingName**: string | Shipping name |
|**shippingAddress1**: string | Primary shipping address |
|**shippingAddress2**: string | Secondary shipping address |
|**shippingCity**: string | City of the shipping address | 
|**shippingState**: string | State of the shipping address |
|**shippingZip**: string | Zip code of the shipping address |
|**shippingContactName**: string | Name of the shipping contact |
|**shippingContactPhone**: string | Phone number of the shipping contact |
|**shippingContactExt**: string | Phone extension of the shipping contact |
|**shippingContactEmail**: string | Email address of the shipping contact |
|**shippingContactFax**: string | Fax number of the shipping contact |
|**billingName**: string | Billing name |
|**billingAddress1**: string | Primary billing address |
|**billingAddress2**: string | Secondary billing address |
|**billingCity**: string | City of the billing address |
|**billingState**: string | State of the billing address |
|**billingZip**: string | Zip code of the billing address  |
|**billingContactName**: string | Name of the billing contact |
|**billingContactPhone**: string | Phone number of the billing contact |
|**billingContactExt**: string | Phone extension of the billing contact |
|**billingContactEmail**: string | Email address of the billing contact |
|**billingContactFax**: string | Fax number of the billing contact |
|**vendorId**: string *(uuid)* | Unique identifier of the Vendor |
|**vendorNo**: string | Number of the Vendor |
|**vendorName**: string | Name of the Vendor |
|**lastUpdated**: string *(date-time)* | Date when the Purchase Order was last updated |
|**lastUpdatedBy**: string *(uuid)* | Unique identifier of the user who last updated the Purchase Order |
|**lastUpdatedByName**: string | Name of the user who last updated the Purchase Order |
|**dateCreated**: string *(date-time)* | Date when the Purchase Order was created |
|**discount**: number *(double)* | Discount for the Purchase Order |
|**discountTypeId**: integer *(int32)* | Unique identifier of the discount type |
|**discountType**: string | Type of the discount |
|**salesTax**: number *(double)* | Sales tax for the Purchase Order |
|**salesTaxId**: integer *(int32)* | Unique identifier of the sales tax |
|**salesTaxType**: string | Type of the sales tax |
|**shipping**: number *(double)* | Shipping cost |
|**shippingTypeId**: integer *(int32)* | Unique identifier of the shipping type |
|**shippingType**: string | Type of the shipping |
|**poUdfLabels**: string | User-Defined Field labels for the Purchase Order. <br> **Note**: See the [poUdfLabels](PurchaseOrders.md#poudflabels) section for more details. |
|**projectNoId**: string *(uuid)* | Unique identifier of the project number |
|**projectNo**: string | Project number for the Purchase Order |
|**projectNoDescription**: string | Description of the project number |
|**consignmentOrder**: boolean | Is the Purchase Order a Consignment order or not? |

``` json title="Response example (200 OK)"
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
    "projectNoDescription": "string",
    "consignmentOrder": "boolean"
}
```

## Get the list of Purchase Order items for the specified Purchase Order

### Path
GET /odata/PurchaseOrders({purchaseOrderId})/purchaseOrderItems

### Description
Returns a paged list of existing Purchase Order items for the Purchase Order specified by ID. 

!!! note

    You can filter the results as follows:

    - For an exact match, use: ```$filter=entity eq 'string'```
    - For a partial match, use: ```$filter=contains(entity, 'string')```

### Request parameters
|  <div style="width:200px">Parameter</div>  |  <div style="width:380px">Explanation</div>  |                      
|-----:|:-------|
|**purchaseOrderId**: string *(uuid)*  <br> <span style="color: #F05D30">**required**</span> <br> *in path* | Enter the ID of the Purchase Order. |
|**api-version**: string default: 1.0 <br> *in header*| The requested API version.|
|**$search**: string <br> *in query*  | Searches across all supported fields. |
|**$filter**: string <br> *in query* | Filters results based on a Boolean condition.|
|**$orderby**: string <br> *in query* | Sorts results.|
|**$top**: string  <br> *in query* | Returns only the first n results.|
|**$skip**: string <br> *in query*| Skips the first n results.|
|**Authorization**: string default: <br> Bearer access_token <br> *in header* | Specify the type of the token (bearer) and insert the ```access_token``` obtained during authentication. |

### Responses
| <div style="width:200px">Response </div>|<div style="width:380px">Explanation</div>|                      
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
|**orderConversionFactor**: integer <br> *(int32)* | Number of stock keeping units in another Unit of Measure specified in the Purchase Order |
|**stockUOM**: string | Unit of Measure used to track Inventory balance |
|**unitCost**: number *(double)* | Unit cost of the Purchase Order item |
|**departmentGLCode**: string | General Ledger code of the Department |
|**glCode**: string | General Ledger code |
|**lineItemTypeId**: integer *(int32)* | Unique identifier of the line item type |
|**itemType**: string | Type of the line item |
|**lineItemNotes**: string | Notes about the line item |
|**contractNo**: string | Number of the Contract |
|**contractExpDate**: string *(date-time)* | Expiration date of the Contract |
|**lastUpdated**: string *(date-time)* | Date when the Purchase Order was last updated |
|**lastUpdatedBy**: string *(uuid)* | Unique identifier of the user who last updated the Purchase Order |
|**lastUpdatedByName**: string | Name of the user who last updated the Purchase Order |
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

