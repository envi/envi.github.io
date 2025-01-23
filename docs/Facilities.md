# Facilities

## Get the list of Facilities

### <span style="color: #F05D30">Path</span>
GET /odata/Facilities

### <span style="color: #F05D30">Description</span>
Returns the paged list of the existing Facilities within a logged organization. You can filter the results by the strict match using the ```$filter``` parameter–entity eq ‘string’. Or filter the results by the partial match using ```$filter```=contains parameter–contains(entity, ‘string’).

### <span style="color: #F05D30">Request parameters</span>
<style>
td, th {
   border: none!important;
}
</style>

|  <div style="width:200px">Parameter</div>  |  <div style="width:380px">Explanation</div>  |                      
|-----:|:-------|
|**api-version**: string default: 1.0 <br> *in header*|The requested API version.|   
|**$search**: string <br> *in query*  | Picks the value in all possible fields.|   
|**$filter**: string <br> *in query* | Filters the results, based on a Boolean condition.|  
|**$orderby**: string <br> *in query* | Sorts the results.|
|**$top**: string  <br> *in query* | Returns only the first n results.|
|**$skip**: string <br> *in query*| Skips the first n results.|
|**Authorization**: string default: <br> Bearer access_token <br> *in header* |Specify the type of the token (bearer) and then insert the ```access_token```, which was obtained during authentication.|

### <span style="color: #F05D30">Responses</span>
| <div style="width:200px">Response </div>|<div style="width:380px">Explanation</div>|                      
|-----:|:-------|
|**200 OK**|OK|      
|**400 Bad Request**|Incorrect input data or organization ID does not match with the organization ID user is logged in.|
|**400 Bad Request** | The limit for the ```$top``` query has been exceeded. The value from the incoming request is 'N' (N is your value from the request). You can find the data on the current limit [here](Options_and_Limitations.md#top-and-skip). |
|**401 Unauthorized**|Incorrect specified ```access_token``` or ```access_token``` got expired.|
|**403 Forbidden**|User doesn’t have appropriate privileges.|
|**500 Internal Server Error**|Server encountered an unexpected condition that prevented it from fulfilling the request.|


### <span style="color: #F05D30">Properties</span>
|<div style="width:200px">Property </div> |<div style="width:380px">Explanation</div>|                      
|-----:|:-------|
|**facilityId**: string *(uuid)* | Unique Identifier of the Facility |
|**organizationId**: string *(uuid)* | Unique Identifier of the Organization |
|**organizationNo**: string | Identification Number of the Organization |
|**organizationName**: string | Name of the Organization |
|**facilityName**: string | Number of the Facility |
|**facilityNo**: string | Identification Number of the Facility |
|**address1**: string | The first Address for shipping or billing purposes |
|**address2**: string | The second Address for shipping or billing purposes |
|**city**: string | City |
|**state**: string | State |
|**zip**: string | Zip |
|**country**: string | Country |
|**taxExpenseCodeTemplate**:<br> string | Template for displaying the General Ledger sequence for a Facility's tax expense account |
|**taxAccrualCodeTemplate**: string | Template for displaying the General Ledger sequence for a Facility's tax accrual account |
|**discountCodeTemp**: string | Template for displaying the Discount Code |
|**shippingCodeTemplate**: string | Template for displaying the Shipping Code |
|**offsetCodeTemplate**: string | Template for displaying the Offset Code |
|**patientDisplayTemplate**: string | Template for displaying the Patient |
|**poglCodeDisplayTemplate**: <br> string | Template for displaying the Purchase Order General Ledger Code |
|**poDeptDisplayTemplate**: string | Template for displaying the Purchase Order Department |
|**activeStatus**: boolean | Is the Facility active or not? |
|**inventoryGroupId**: string *(uuid)* | Unique Identifier of the Group that contains related Inventory items |
|**inventoryGroupNo**: string | Number of the Group that contains related Inventory items |
|**inventoryGroupName**: string | Name of the Group that contains related Inventory items |
|**apToleranceLevel**: number <br> *(double)* | Discrepancy between the original PO and the Invoice sent by the Vendor |
|**apToleranceLevelType**: integer <br> *(int32)* | Type of the Discrepancy between the original PO and the Invoice sent <br> by the Vendor |
|**apToleranceLevelTypeValue**: <br> string | Type Value of the Discrepancy between the original PO and the Invoice <br> sent by the Vendor |
|**apToleranceLevel2**: <br> number *(double)* | Discrepancy2 between the original PO and the Invoice sent by the Vendor |
|**apToleranceLevel2Type**: integer <br> *(int32)* | Type of the Dicrepancy2 between the original PO and the Invoice <br> sent by the Vendor |
|**apToleranceLevel2TypeValue**: <br> string | Type Value of the Dicrepancy2 between the original PO and the Invoice sent by the Vendor |
|**apFreeFormedToleranceLevel**: <br> number *(double)* | Tolerance Level for Free-Form of the Account Payable |
|**apFreeFormedToleranceLevel<br>Type**: integer *(int32)* | Type of the Account Payable Free-Formed Tolerance Level |
|**apFreeFormedToleranceLevel<br>TypeValue**: string | Value of the Account Payable Free-Formed Tolerance Level Type |
|**apFreeFormedToleranceLevel2**: <br> number *(double)* | Second Tolerance Level for Free-Form of the Account Payable |
|**apFreeFormedToleranceLevel2<br>Type**: integer *(int32)* | Second Type of the Account Payable Free-Formed Tolerance Level |
|**apFreeFormedToleranceLevel2<br>TypeValue**: string | Second Value of the Account Payable Free-Formed Tolerance Level Type |
|**apOffsetTolerance**: <br> number *(double)* | Account Payable Offset Tolerance |
|**apOffsetToleranceType**: <br> integer *(int32)* | Type of the Account Payable Offset Tolerance |
|**apOffsetToleranceType<br>Value**: string | Value of the Account Payable Offset Tolerance Type |
|**taxType**: integer *(int32)* | Type of the Tax |
|**taxTypeValue**: string | Value of the Tax Type |
|**taxAmount**: number *(double)* | Amount of the Tax |
|**taxExpenseType**: integer *(int32)* | Type of the Tax Expense |
|**taxExpenseTypeValue**: string | Value of the Tax Expense Type |
|**taxExpenseAmount**: number <br> *(double)* | Amount of the Tax Expense |
|**facilityNoXref**: string | Cross Reference Number of the Facility |
|**taxShipping**: boolean | Is the Shipping taxable or not? |
|**poInvoiceGlValidation**: string | Validation for the Purchase Order and Invoice General Ledger |
|**poInvoiceGlValidationMsg**: string | Message for the Purchase Order and Invoice General Ledger |
|**capitalPOInvoiceGlValidation**: string | Validation for the Capital Purchase Order and Invoice General Ledger |
|**capitalPOInvoiceGlValidationMsg**: <br>string | Message for the Capital Purchase Order and Invoice General Ledger |
|**timeZoneId**: string *(uuid)* | Unique Identifier of the Time Zone |
|**timeZone**: string | Time Zone |
|**preferenceCardMatching**: <br> integer *(int32)* |  Matching of the Preference Card |
|**preferenceCardMatching<br>Value**: string | Value of the Preference Card Matching |
|**dateCreated**: string <br>*(date-time)* | Date when the Facility was created |
|**createdBy**: string *(uuid)* | Unique Identifier of the user who created the Facility |
|**createdByName**: string | Name of the user who created the Facility |
|**lastUpdated**: string *(date-time)* | Last Date when the Facility was updated |
|**lastUpdatedBy**: string *(uuid)* | Unique Identifier of the last user who updated the Facility |
|**lastUpdatedByName**: string | Name of the last user who updated the Facility |
|**memberID**: string | Unique Identifier of the Facility for external use |
|**capitalTaxExpenseCode<br>Template**: string | Capital Tax Expense Code Template |
|**capitalTaxAccrualCode<br>Template**: string | Capital Tax Accrual Code Template |
|**capitalDiscountCodeTemplate**: <br> string | Capital Discount Code Template |
|**capitalShippingCodeTemplate**: <br> string | Capital Shipping Code Template |
|**capitalOffsetCodeTemplate**: <br> string | Capital Offset Code Template |
|**customField1**: string | Custom Field 1 |
|**customField2**: string | Custom Field 2 |
|**customField3**: string | Custom Field 3 |
|**customField4**: string | Custom Field 4 |
|**poContactInfoType**: integer <br> *(int32)* | Type of the PO Contact Info |
|**poContactInfo**: string | PO Contact Info |
|**poContactName**: string | Name of the main contact point for the PO |
|**poContactEmail**: string | Email of the main contact point for the PO |
|**poContactPhone**: string | Phone of the main contact point for the PO |
|**poContactPhoneExt**: string | Phone Extension of the main contact point for the PO |
|**poContactFax**: string | Fax of the main contact point for the PO |


``` json title="Response Content-types: APPLICATION/JSON, APPLICATION/XML <br> Response Example (200 OK)"
{
  "items": [
    {
      "facilityId": "00000000-0000-0000-0000-000000000000",
      "organizationId": "00000000-0000-0000-0000-000000000000",
      "organizationNo": "string",
      "organizationName": "string",
      "facilityName": "string",
      "facilityNo": "string",
      "address1": "string",
      "address2": "string",
      "city": "string",
      "state": "string",
      "zip": "string",
      "country": "string",
      "taxExpenseCodeTemplate": "string",
      "taxAccrualCodeTemplate": "string",
      "discountCodeTemp": "string",
      "shippingCodeTemplate": "string",
      "offsetCodeTemplate": "string",
      "patientDisplayTemplate": "string",
      "poglCodeDisplayTemplate": "string",
      "poDeptDisplayTemplate": "string",
      "activeStatus": "boolean",
      "inventoryGroupId": "00000000-0000-0000-0000-000000000000",
      "inventoryGroupNo": "string",
      "inventoryGroupName": "string",
      "apToleranceLevel": "number (double)",
      "apToleranceLevelType": "integer (int32)",
      "apToleranceLevelTypeValue": "string",
      "apToleranceLevel2": "number (double)",
      "apToleranceLevel2Type": "integer (int32)",
      "apToleranceLevel2TypeValue": "string",
      "apFreeFormedToleranceLevel": "number (double)",
      "apFreeFormedToleranceLevelType": "integer (int32)",
      "apFreeFormedToleranceLevelTypeValue": "string",
      "apFreeFormedToleranceLevel2": "number (double)",
      "apFreeFormedToleranceLevel2Type": "integer (int32)",
      "apFreeFormedToleranceLevel2TypeValue": "string",
      "apOffsetTolerance": "number (double)",
      "apOffsetToleranceType": "integer (int32)",
      "apOffsetToleranceTypeValue": "string",
      "taxType": "integer (int32)",
      "taxTypeValue": "string",
      "taxAmount": "number (double)",
      "taxExpenseType": "integer (int32)",
      "taxExpenseTypeValue": "string",
      "taxExpenseAmount": "number (double)",
      "facilityNoXref": "string",
      "taxShipping": "boolean",
      "poInvoiceGlValidation": "string",
      "poInvoiceGlValidationMsg": "string",
      "capitalPOInvoiceGlValidation": "string",
      "capitalPOInvoiceGlValidationMsg": "string",
      "timeZoneId": "00000000-0000-0000-0000-000000000000",
      "timeZone": "string",
      "preferenceCardMatching": "integer (int32)",
      "preferenceCardMatchingValue": "string",
      "dateCreated": "string (date-time)",
      "createdBy": "00000000-0000-0000-0000-000000000000",
      "createdByName": "string",
      "lastUpdated": "string (date-time)",
      "lastUpdatedBy": "00000000-0000-0000-0000-000000000000",
      "lastUpdatedByName": "string",
      "memberID": "string",
      "capitalTaxExpenseCodeTemplate": "string",
      "capitalTaxAccrualCodeTemplate": "string",
      "capitalDiscountCodeTemplate": "string",
      "capitalShippingCodeTemplate": "string",
      "capitalOffsetCodeTemplate": "string",
      "customField1": "string",
      "customField2": "string",
      "customField3": "string",
      "customField4": "string",
      "poContactInfoType": "integer (int32)",
      "poContactInfo": "string",
      "poContactName": "string",
      "poContactEmail": "string",
      "poContactPhone": "string",
      "poContactPhoneExt": "string",
      "poContactFax": "string"
    }
  ],
  "nextPageLink": "string",
  "count": "integer (int64)"
}
    
```

## Partially update the specified Facility

### <span style="color: #F05D30">Path</span>
PATCH /odata/Facilities({facilityId})

### <span style="color: #F05D30">Description</span>
Partially updates the details of the Facility specified by the Facility ID.

### <span style="color: #F05D30">Request body</span>
| <div style="width:200px">Parameter</div>|<div style="width:380px">Explanation</div>|                      
|-----:|:-------|
|**facilityNo**: string | Identification Number of the Facility |
|**facilityName**: string | Number of the Facility |
|**address1**: string | The first Address for shipping or billing purposes |
|**address2**:| The second Address for shipping or billing purposes |
|**city**: string | City |
|**state**: string | State |
|**zip**: string | Zip |
|**country**: string | Country |
|**taxExpenseCodeTemplate**:<br> string | Template for displaying the General Ledger sequence for a Facility's tax expense account |
|**capitalTaxExpenseCode<br>Template**: string | Capital Tax Expense Code Template |
|**taxAccrualCodeTemplate**: string | Template for displaying the General Ledger sequence for a Facility's tax accrual account |
|**capitalTaxAccrualCode<br>Template**: string | Capital Tax Accrual Code Template |
|**discountCodeTemp**: string | Template for displaying the Discount Code |
|**capitalDiscountCodeTemplate**: <br> string | Capital Discount Code Template |
|**shippingCodeTemplate**: string | Template for displaying the Shipping Code |
|**capitalShippingCodeTemplate**: <br> string | Capital Shipping Code Template |
|**offsetCodeTemplate**: string | Template for displaying the Offset Code |
|**capitalOffsetCodeTemplate**: <br> string | Capital Offset Code Template |
|**patientDisplayTemplate**: string | Template for displaying the Patient |
|**poglCodeDisplayTemplate**: <br> string | Template for displaying the Purchase Order General Ledger Code |
|**poDeptDisplayTemplate**: string | Template for displaying the Purchase Order Department |
|**poContactInfoType**: integer <br> *(int32)* | Type of the PO Contact Info |
|**poContactName**: string | Name of the main contact point for the PO |
|**poContactEmail**: string | Email of the main contact point for the PO |
|**poContactPhone**: string | Phone of the main contact point for the PO |
|**poContactPhoneExt**: string | Phone Extension of the main contact point for the PO |
|**poContactFax**: string | Fax of the main contact point for the PO |
|**activeStatus**: boolean | Is the Facility active or not? |
|**inventoryGroupId**: string *(uuid)* | Unique Identifier of the Group that contains related Inventory items |
|**apToleranceLevel**: number <br> *(double)* | Discrepancy between the original PO and the Invoice sent by the Vendor |
|**apToleranceLevelType**: integer <br> *(int32)* | Type of the Discrepancy between the original PO and the Invoice sent <br> by the Vendor |
|**apToleranceLevel2**: <br> number *(double)* | Discrepancy2 between the original PO and the Invoice sent by the Vendor |
|**apToleranceLevel2Type**: integer <br> *(int32)* | Type of the Dicrepancy2 between the original PO and the Invoice <br> sent by the Vendor |
|**apFreeFormedToleranceLevel**: <br> number *(double)* | Tolerance Level for Free-Form of the Account Payable |
|**apFreeFormedToleranceLevel<br>Type**: integer *(int32)* | Type of the Account Payable Free-Formed Tolerance Level |
|**apFreeFormedToleranceLevel2**: <br> number *(double)* | Second Tolerance Level for Free-Form of the Account Payable |
|**apFreeFormedToleranceLevel2<br>Type**: integer *(int32)* | Second Type of the Account Payable Free-Formed Tolerance Level |
|**apOffsetTolerance**: <br> number *(double)* | Account Payable Offset Tolerance |
|**apOffsetToleranceType**: <br> integer *(int32)* | Type of the Account Payable Offset Tolerance |
|**taxAmount**: number *(double)* | Amount of the Tax |
|**taxType**: integer *(int32)* | Type of the Tax |
|**taxExpenseAmount**: number <br> *(double)* | Amount of the Tax Expense |
|**taxExpenseType**: integer *(int32)* | Type of the Tax Expense |
|**facilityNoXref**: string | Cross Reference Number of the Facility |
|**taxShipping**: boolean | Is the Shipping taxable or not? |
|**poInvoiceGlValidation**: string | Validation for the Purchase Order and Invoice General Ledger |
|**poInvoiceGlValidationMsg**: string | Message for the Purchase Order and Invoice General Ledger |
|**capitalPOInvoiceGlValidation**: string | Validation for the Capital Purchase Order and Invoice General Ledger |
|**capitalPOInvoiceGlValidationMsg**: <br>string | Message for the Capital Purchase Order and Invoice General Ledger |
|**timeZoneId**: string *(uuid)* | Unique Identifier of the Time Zone |
|**preferenceCardMatching**: <br> integer *(int32)* |  Matching of the Preference Card |
|**memberID**: string | Unique Identifier of the Facility for external use. <br> **Note**: The field requires special privileges to modify. |
|**customField1**: string | Custom Field 1 |
|**customField2**: string | Custom Field 2 |
|**customField3**: string | Custom Field 3 |
|**customField4**: string | Custom Field 4 |


``` json title="Request Content-types: APPLICATION/JSON, APPLICATION/XML<br>Request Example"
{
  "facilityNo": "string",
  "facilityName": "string",
  "address1": "string",
  "address2": "string",
  "city": "string",
  "state": "string",
  "zip": "string",
  "country": "string",
  "taxExpenseCodeTemplate": "string",
  "capitalTaxExpenseCodeTemplate": "string",
  "taxAccrualCodeTemplate": "string",
  "capitalTaxAccrualCodeTemplate": "string",
  "discountCodeTemp": "string",
  "capitalDiscountCodeTemplate": "string",
  "shippingCodeTemplate": "string",
  "capitalShippingCodeTemplate": "string",
  "offsetCodeTemplate": "string",
  "capitalOffsetCodeTemplate": "string",
  "patientDisplayTemplate": "string",
  "poglCodeDisplayTemplate": "string",
  "poDeptDisplayTemplate": "string",
  "poContactInfoType": "integer (int32)",
  "poContactName": "string",
  "poContactEmail": "string",
  "poContactPhone": "string",
  "poContactPhoneExt": "string",
  "poContactFax": "string",
  "activeStatus": "boolean",
  "inventoryGroupId": "00000000-0000-0000-0000-000000000000",
  "apToleranceLevel": "number (double)",
  "apToleranceLevelType": "integer (int32)",
  "apToleranceLevel2": "number (double)",
  "apToleranceLevel2Type": "integer (int32)",
  "apFreeFormedToleranceLevel": "number (double)",
  "apFreeFormedToleranceLevelType": "integer (int32)",
  "apFreeFormedToleranceLevel2": "number (double)",
  "apFreeFormedToleranceLevel2Type": "integer (int32)",
  "apOffsetTolerance": "number (double)",
  "apOffsetToleranceType": "integer (int32)",
  "taxAmount": "number (double)",
  "taxType": "integer (int32)",
  "taxExpenseAmount": "number (double)",
  "taxExpenseType": "integer (int32)",
  "facilityNoXref": "string",
  "taxShipping": "boolean",
  "poInvoiceGlValidation": "string",
  "poInvoiceGlValidationMsg": "string",
  "capitalPOInvoiceGlValidation": "string",
  "capitalPOInvoiceGlValidationMsg": "string",
  "timeZoneId": "00000000-0000-0000-0000-000000000000",
  "preferenceCardMatching": "integer (int32)",
  "memberID": "string",
  "customField1": "string",
  "customField2": "string",
  "customField3": "string",
  "customField4": "string",
}
```

### <span style="color: #F05D30">Request parameters</span>
| <div style="width:200px">Parameter</div>|<div style="width:380px">Explanation</div>|                       
|-----:|:-------|
|**facilityId**: string *(uuid)* <br> <span style="color: #F05D30">**required**</span> <br> *in path* | Unique Identifier of the Facility. |
|**api-version**: string default: 1.0 <br> *in header*| The requested API version.|      
|**Authorization**: string default: <br> Bearer access_token <br> *in header* | Specify the type of the token (bearer) and then insert the ```access_token```, which was obtained during authentication.|

### <span style="color: #F05D30">Responses</span>
| <div style="width:200px">Response </div>|<div style="width:380px">Explanation</div>|                      
|-----:|:-------|
|**200 OK**|OK|      
|**400 Bad Request**|Incorrect input data or organization ID does not match with the organization ID user is logged in.|
|**401 Unauthorized**|Incorrect specified ```access_token``` or ```access_token``` got expired.|
|**403 Forbidden**|User doesn’t have appropriate privileges.|
|**404 Not Found** | Specified ID is absent in the system. |
|**500 Internal Server Error**|Server encountered an unexpected condition that prevented it from fulfilling the request.|



## Get the specified Facility

### <span style="color: #F05D30">Path</span>
GET /odata/Facilities({facilityId})

### <span style="color: #F05D30">Description</span>
Returns the details of the Facility specified by ID.

### <span style="color: #F05D30">Request parameters</span>
|  <div style="width:200px">Parameter</div>  |  <div style="width:380px">Explanation</div>|                      
|-----:|:-------|
|**facilityId**: string *(uuid)* <br> <span style="color: #F05D30">**required**</span> <br> *in path* | Enter the ID of the Facility here. |
|**api-version**: string default: 1.0 <br> *in header*|The requested API version.|   
|**Authorization**: string default: <br> Bearer access_token <br> *in header* |Specify the type of the token (bearer) and then insert the ```access_token```, which was obtained during authentication.|

### <span style="color: #F05D30">Responses</span>
| <div style="width:200px">Response </div>|<div style="width:380px">Explanation</div>|                      
|-----:|:-------|
|**200 OK**| OK |      
|**400 Bad Request**|Incorrect input data or organization ID does not match with the organization ID user is logged in.|
|**401 Unauthorized**|Incorrect specified ```access_token``` or ```access_token``` got expired.|
|**403 Forbidden**|User doesn’t have appropriate privileges.|
|**404 Not Found** | Specified ID is absent in the system. |
|**500 Internal Server Error**|Server encountered an unexpected condition that prevented it from fulfilling the request.|

### <span style="color: #F05D30">Properties</span>
|<div style="width:200px">Property </div> |<div style="width:380px">Explanation</div>|                      
|-----:|:-------|
|**facilityId**: string *(uuid)* | Unique Identifier of the Facility |
|**organizationId**: string *(uuid)* | Unique Identifier of the Organization |
|**organizationNo**: string | Identification Number of the Organization |
|**organizationName**: string | Name of the Organization |
|**facilityName**: string | Number of the Facility |
|**facilityNo**: string | Identification Number of the Facility |
|**address1**: string | The first Address for shipping or billing purposes |
|**address2**: string | The second Address for shipping or billing purposes |
|**city**: string | City |
|**state**: string | State |
|**zip**: string | Zip |
|**country**: string | Country |
|**taxExpenseCodeTemplate**:<br> string | Template for displaying the General Ledger sequence for a Facility's tax expense account |
|**taxAccrualCodeTemplate**: string | Template for displaying the General Ledger sequence for a Facility's tax accrual account |
|**discountCodeTemp**: string | Template for displaying the Discount Code |
|**shippingCodeTemplate**: string | Template for displaying the Shipping Code |
|**offsetCodeTemplate**: string | Template for displaying the Offset Code |
|**patientDisplayTemplate**: string | Template for displaying the Patient |
|**poglCodeDisplayTemplate**: <br> string | Template for displaying the Purchase Order General Ledger Code |
|**poDeptDisplayTemplate**: string | Template for displaying the Purchase Order Department |
|**activeStatus**: boolean | Is the Facility active or not? |
|**inventoryGroupId**: string *(uuid)* | Unique Identifier of the Group that contains related Inventory items |
|**inventoryGroupNo**: string | Number of the Group that contains related Inventory items |
|**inventoryGroupName**: string | Name of the Group that contains related Inventory items |
|**apToleranceLevel**: number <br> *(double)* | Discrepancy between the original PO and the Invoice sent by the Vendor |
|**apToleranceLevelType**: integer <br> *(int32)* | Type of the Discrepancy between the original PO and the Invoice sent <br> by the Vendor |
|**apToleranceLevelTypeValue**: <br> string | Type Value of the Discrepancy between the original PO and the Invoice <br> sent by the Vendor |
|**apToleranceLevel2**: <br> number *(double)* | Discrepancy2 between the original PO and the Invoice sent by the Vendor |
|**apToleranceLevel2Type**: integer <br> *(int32)* | Type of the Dicrepancy2 between the original PO and the Invoice <br> sent by the Vendor |
|**apToleranceLevel2TypeValue**: <br> string | Type Value of the Dicrepancy2 between the original PO and the Invoice sent by the Vendor |
|**apFreeFormedToleranceLevel**: <br> number *(double)* | Tolerance Level for Free-Form of the Account Payable |
|**apFreeFormedToleranceLevel<br>Type**: integer *(int32)* | Type of the Account Payable Free-Formed Tolerance Level |
|**apFreeFormedToleranceLevel<br>TypeValue**: string | Value of the Account Payable Free-Formed Tolerance Level Type |
|**apFreeFormedToleranceLevel2**: <br> number *(double)* | Second Tolerance Level for Free-Form of the Account Payable |
|**apFreeFormedToleranceLevel2<br>Type**: integer *(int32)* | Second Type of the Account Payable Free-Formed Tolerance Level |
|**apFreeFormedToleranceLevel2<br>TypeValue**: string | Second Value of the Account Payable Free-Formed Tolerance Level Type |
|**apOffsetTolerance**: <br> number *(double)* | Account Payable Offset Tolerance |
|**apOffsetToleranceType**: <br> integer *(int32)* | Type of the Account Payable Offset Tolerance |
|**apOffsetToleranceType<br>Value**: string | Value of the Account Payable Offset Tolerance Type |
|**taxType**: integer *(int32)* | Type of the Tax |
|**taxTypeValue**: string | Value of the Tax Type |
|**taxAmount**: number *(double)* | Amount of the Tax |
|**taxExpenseType**: integer *(int32)* | Type of the Tax Expense |
|**taxExpenseTypeValue**: string | Value of the Tax Expense Type |
|**taxExpenseAmount**: number <br> *(double)* | Amount of the Tax Expense |
|**facilityNoXref**: string | Cross Reference Number of the Facility |
|**taxShipping**: boolean | Is the Shipping taxable or not? |
|**poInvoiceGlValidation**: string | Validation for the Purchase Order and Invoice General Ledger |
|**poInvoiceGlValidationMsg**: string | Message for the Purchase Order and Invoice General Ledger |
|**capitalPOInvoiceGlValidation**: string | Validation for the Capital Purchase Order and Invoice General Ledger |
|**capitalPOInvoiceGlValidationMsg**: <br>string | Message for the Capital Purchase Order and Invoice General Ledger |
|**timeZoneId**: string *(uuid)* | Unique Identifier of the Time Zone |
|**timeZone**: string | Time Zone |
|**preferenceCardMatching**: <br> integer *(int32)* |  Matching of the Preference Card |
|**preferenceCardMatching<br>Value**: string | Value of the Preference Card Matching |
|**dateCreated**: string <br>*(date-time)* | Date when the Facility was created |
|**createdBy**: string *(uuid)* | Unique Identifier of the user who created the Facility |
|**createdByName**: string | Name of the user who created the Facility |
|**lastUpdated**: string *(date-time)* | Last Date when the Facility was updated |
|**lastUpdatedBy**: string *(uuid)* | Unique Identifier of the last user who updated the Facility |
|**lastUpdatedByName**: string | Name of the last user who updated the Facility |
|**memberID**: string | Unique Identifier of the Facility for external use |
|**capitalTaxExpenseCode<br>Template**: string | Capital Tax Expense Code Template |
|**capitalTaxAccrualCode<br>Template**: string | Capital Tax Accrual Code Template |
|**capitalDiscountCodeTemplate**: <br> string | Capital Discount Code Template |
|**capitalShippingCodeTemplate**: <br> string | Capital Shipping Code Template |
|**capitalOffsetCodeTemplate**: <br> string | Capital Offset Code Template |
|**customField1**: string | Custom Field 1 |
|**customField2**: string | Custom Field 2 |
|**customField3**: string | Custom Field 3 |
|**customField4**: string | Custom Field 4 |
|**poContactInfoType**: integer <br> *(int32)* | Type of the PO Contact Info |
|**poContactInfo**: string| PO Contact Info |
|**poContactName**: string | Name of the main contact point for the PO |
|**poContactEmail**: string | Email of the main contact point for the PO |
|**poContactPhone**: string | Phone of the main contact point for the PO |
|**poContactPhoneExt**: string | Phone Extension of the main contact point for the PO |
|**poContactFax**: string | Fax of the main contact point for the PO |


``` json title="Response Content-types: APPLICATION/JSON, APPLICATION/XML <br> Response Example (200 OK)"
{
  "facilityId": "00000000-0000-0000-0000-000000000000",
  "organizationId": "00000000-0000-0000-0000-000000000000",
  "organizationNo": "string",
  "organizationName": "string",
  "facilityName": "string",
  "facilityNo": "string",
  "address1": "string",
  "address2": "string",
  "city": "string",
  "state": "string",
  "zip": "string",
  "country": "string",
  "taxExpenseCodeTemplate": "string",
  "taxAccrualCodeTemplate": "string",
  "discountCodeTemp": "string",
  "shippingCodeTemplate": "string",
  "offsetCodeTemplate": "string",
  "patientDisplayTemplate": "string",
  "poglCodeDisplayTemplate": "string",
  "poDeptDisplayTemplate": "string",
  "activeStatus": "boolean",
  "inventoryGroupId": "00000000-0000-0000-0000-000000000000",
  "inventoryGroupNo": "string",
  "inventoryGroupName": "string",
  "apToleranceLevel": "number (double)",
  "apToleranceLevelType": "integer (int32)",
  "apToleranceLevelTypeValue": "string",
  "apToleranceLevel2": "number (double)",
  "apToleranceLevel2Type": "integer (int32)",
  "apToleranceLevel2TypeValue": "string",
  "apFreeFormedToleranceLevel": "number (double)",
  "apFreeFormedToleranceLevelType": "integer (int32)",
  "apFreeFormedToleranceLevelTypeValue": "string",
  "apFreeFormedToleranceLevel2": "number (double)",
  "apFreeFormedToleranceLevel2Type": "integer (int32)",
  "apFreeFormedToleranceLevel2TypeValue": "string",
  "apOffsetTolerance": "number (double)",
  "apOffsetToleranceType": "integer (int32)",
  "apOffsetToleranceTypeValue": "string",
  "taxType": "integer (int32)",
  "taxTypeValue": "string",
  "taxAmount": "number (double)",
  "taxExpenseType": "integer (int32)",
  "taxExpenseTypeValue": "string",
  "taxExpenseAmount": "number (double)",
  "facilityNoXref": "string",
  "taxShipping": "boolean",
  "poInvoiceGlValidation": "string",
  "poInvoiceGlValidationMsg": "string",
  "capitalPOInvoiceGlValidation": "string",
  "capitalPOInvoiceGlValidationMsg": "string",
  "timeZoneId": "00000000-0000-0000-0000-000000000000",
  "timeZone": "string",
  "preferenceCardMatching": "integer (int32)",
  "preferenceCardMatchingValue": "string",
  "dateCreated": "string (date-time)",
  "createdBy": "00000000-0000-0000-0000-000000000000",
  "createdByName": "string",
  "lastUpdated": "string (date-time)",
  "lastUpdatedBy": "00000000-0000-0000-0000-000000000000",
  "lastUpdatedByName": "string",
  "memberID": "string",
  "capitalTaxExpenseCodeTemplate": "string",
  "capitalTaxAccrualCodeTemplate": "string",
  "capitalDiscountCodeTemplate": "string",
  "capitalShippingCodeTemplate": "string",
  "capitalOffsetCodeTemplate": "string",
  "customField1": "string",
  "customField2": "string",
  "customField3": "string",
  "customField4": "string",
  "poContactInfoType": "integer (int32)",
  "poContactInfo": "string",
  "poContactName": "string",
  "poContactEmail": "string",
  "poContactPhone": "string",
  "poContactPhoneExt": "string",
  "poContactFax": "string"
}
```


