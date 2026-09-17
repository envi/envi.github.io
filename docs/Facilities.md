# Facilities

## Get the list of Facilities

### Path
GET /odata/Facilities

### Description
Returns a paged list of existing Facilities within the logged-in organization.

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

| Parameter | Explanation |                      
|-----:|:-------|
|**api-version**: string default: 1.0 <br> *in header*| The requested API version. |   
|**$search**: string <br> *in query*  | Searches across all supported fields. |   
|**$filter**: string <br> *in query* | Filters results based on a Boolean condition.|  
|**$orderby**: string <br> *in query* | Sorts results.|
|**$top**: string  <br> *in query* | Returns only the first n results.|
|**$skip**: string <br> *in query*| Skips the first n results.|
|**Authorization**: string default: <br> Bearer access_token <br> *in header* | Specify the type of the token (bearer) and insert the ```access_token``` obtained during authentication. |

### Responses
| Response | Explanation |                      
|-----:|:-------|
|**200 OK**| OK |     
|**400 Bad Request**| The request contains incorrect input data. |      
|**400 Bad Request** | The limit for the ```$top``` query has been exceeded. The value from the incoming request is 'N' (N is your value from the request). You can find the data on the current limit [here](Options_and_Limitations.md#top-and-skip). |
|**401 Unauthorized**| The specified ```access_token``` is invalid or has expired. |
|**403 Forbidden**| The user doesn’t have the appropriate privileges. |
|**500 Internal Server Error**| The server encountered an unexpected condition that prevented it from fulfilling the request.|

### Properties
| Property | Explanation |                      
|-----:|:-------|
|**facilityId**: string *(uuid)* | Unique identifier of the Facility |
|**organizationId**: string *(uuid)* | Unique identifier of the Organization |
|**organizationNo**: string | Identification number of the Organization |
|**organizationName**: string | Name of the Organization |
|**facilityName**: string | Name of the Facility |
|**facilityNo**: string | Identification number of the Facility |
|**address1**: string | Primary address of the Facility for shipping or billing purposes |
|**address2**: string | Secondary address of the Facility for shipping or billing purposes |
|**city**: string | City of the Facility address |
|**state**: string | State of the Facility address |
|**zip**: string | Zip code of the Facility address |
|**country**: string | Country of the Facility address |
|**taxExpenseCodeTemplate**:<br> string | Template for a tax expense code |
|**taxAccrualCodeTemplate**: string | Template for a tax accrual code |
|**discountCodeTemp**: string | Template for a discount code |
|**shippingCodeTemplate**: string | Template for a shipping code |
|**offsetCodeTemplate**: string | Template for an offset code |
|**patientDisplayTemplate**: string | Template for displaying patient information |
|**poglCodeDisplayTemplate**:<br> string | Template for displaying a Purchase Order General Ledger code |
|**poDeptDisplayTemplate**: string | Template for displaying a Purchase Order Department |
|**activeStatus**: boolean | Is the Facility active or not? |
|**inventoryGroupId**: string *(uuid)* | Unique identifier of the Inventory Group that contains related Inventory items |
|**inventoryGroupNo**: string | Number of the Inventory Group that contains related Inventory items |
|**inventoryGroupName**: string | Name of the Inventory Group that contains related Inventory items |
|**apToleranceLevel**: number <br> *(double)* | Accounts Payable tolerance level of the Facility |
|**apToleranceLevelType**: integer <br> *(int32)* | Type of the Accounts Payable tolerance level |
|**apToleranceLevelTypeValue**:<br> string | Value of the Accounts Payable tolerance level type |
|**apToleranceLevel2**:<br> number *(double)* | Second Accounts Payable tolerance level of the Facility |
|**apToleranceLevel2Type**: integer <br> *(int32)* | Type of the second Accounts Payable tolerance level |
|**apToleranceLevel2TypeValue**:<br> string | Value of the second Accounts Payable tolerance level type |
|**apFreeFormedToleranceLevel**: <br> number *(double)* | Accounts Payable Free-Form tolerance level of the Facility |
|**apFreeFormedToleranceLevel<br>Type**: integer *(int32)* | Type of the Accounts Payable Free-Form tolerance level |
|**apFreeFormedToleranceLevel<br>TypeValue**: string | Value of the Accounts Payable Free-Form tolerance level type |
|**apFreeFormedToleranceLevel2**: <br> number *(double)* | Second Accounts Payable Free-Form tolerance level of the Facility |
|**apFreeFormedToleranceLevel2<br>Type**: integer *(int32)* | Type of the second Accounts Payable Free-Form tolerance level |
|**apFreeFormedToleranceLevel2<br>TypeValue**: string | Value of the second Accounts Payable Free-Form tolerance level type |
|**apOffsetTolerance**: <br> number *(double)* | Accounts Payable offset tolerance of the Facility |
|**apOffsetToleranceType**: <br> integer *(int32)* | Type of the Accounts Payable offset tolerance |
|**apOffsetToleranceType<br>Value**: string | Value of the Accounts Payable offset tolerance type |
|**taxType**: integer *(int32)* | Type of the tax |
|**taxTypeValue**: string | Value of the tax type |
|**taxAmount**: number *(double)* | Amount of the tax |
|**taxExpenseType**: integer *(int32)* | Type of the tax expense |
|**taxExpenseTypeValue**: string | Value of the tax expense type |
|**taxExpenseAmount**: number <br> *(double)* | Amount of the tax expense |
|**facilityNoXref**: string | Cross-reference number of the Facility |
|**taxShipping**: boolean | Is shipping taxable or not? |
|**poInvoiceGlValidation**: string | General Ledger validation for the Purchase Order and Invoice |
|**poInvoiceGlValidationMsg**: string | General Ledger validation message for the Purchase Order and Invoice |
|**capitalPOInvoiceGlValidation**: string | General Ledger validation for the Capital Purchase Order and Invoice |
|**capitalPOInvoiceGlValidationMsg**: <br> string | General Ledger validation message for the Capital Purchase Order and Invoice |
|**timeZoneId**: string *(uuid)* | Unique identifier of the time zone |
|**timeZone**: string | Time zone |
|**preferenceCardMatching**: <br> integer *(int32)* | Preference Card matching |
|**preferenceCardMatching<br>Value**: string | Value of the Preference Card matching |
|**dateCreated**: string <br>*(date-time)* | Date when the Facility was created |
|**createdBy**: string *(uuid)* | Unique identifier of the user who created the Facility |
|**createdByName**: string | Name of the user who created the Facility |
|**lastUpdated**: string *(date-time)* | Date when the Facility was last updated |
|**lastUpdatedBy**: string *(uuid)* | Unique identifier of the user who last updated the Facility |
|**lastUpdatedByName**: string | Name of the user who last updated the Facility |
|**gpoMemberID**: string | Unique identifier of the Facility within the Group Purchasing Organization |
|**gpoNameId**: string *(uuid)* | Unique identifier of the Group Purchasing Organization |
|**gpoNameValue**: string | Name of the Group Purchasing Organization |
|**capitalTaxExpenseCode<br>Template**: string | Template for a Capital tax expense code |
|**capitalTaxAccrualCode<br>Template**: string | Template for a Capital tax accrual code |
|**capitalDiscountCodeTemplate**: <br> string | Template for a Capital discount code |
|**capitalShippingCodeTemplate**: <br> string | Template for a Capital shipping code |
|**capitalOffsetCodeTemplate**: <br> string | Template for a Capital offset code |
|**customField1**: string | Custom field 1 |
|**customField2**: string | Custom field 2 |
|**customField3**: string | Custom field 3 |
|**customField4**: string | Custom field 4 |
|**poContactInfoType**: integer <br> *(int32)* | Type of the PO contact info |
|**poContactInfo**: string | PO contact info |
|**poContactName**: string | Name of the main PO contact |
|**poContactEmail**: string | Email address of the main PO contact |
|**poContactPhone**: string | Phone number of the main PO contact |
|**poContactPhoneExt**: string | Phone extension of the main PO contact |
|**poContactFax**: string | Fax number of the main PO contact |
|**poPrefix**: string | Purchase Order prefix |

``` json title="Response example (200 OK)"
{
    "@odata.context": "link",
    "@odata.count": "number",
    "value": [
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
            "gpoMemberID": "string",
            "gpoNameId": "00000000-0000-0000-0000-000000000000",
            "gpoNameValue": "string",
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
            "poContactFax": "string",
            "poPrefix": "string"
        }
    ],
    "@odata.nextLink": "link"
}
   
```

## Partially update the specified Facility

### Path
PATCH /odata/Facilities({facilityId})

### Description
Partially updates the Facility specified by ID.

### Request body
| Parameter | Explanation |                      
|-----:|:-------|
|**facilityNo**: string | Identification number of the Facility |
|**facilityName**: string | Name of the Facility |
|**address1**: string | Primary address of the Facility for shipping or billing purposes |
|**address2**: string | Secondary address of the Facility for shipping or billing purposes |
|**city**: string | City of the Facility address |
|**state**: string | State of the Facility address |
|**zip**: string | Zip code of the Facility address |
|**country**: string | Country of the Facility address |
|**taxExpenseCodeTemplate**:<br> string | Template for a tax expense code |
|**capitalTaxExpenseCode<br>Template**: string | Template for a Capital tax expense code |
|**taxAccrualCodeTemplate**: string | Template for a tax accrual code |
|**capitalTaxAccrualCode<br>Template**: string | Template for a Capital tax accrual code |
|**discountCodeTemp**: string | Template for a discount code |
|**capitalDiscountCodeTemplate**: <br> string | Template for a Capital discount code |
|**shippingCodeTemplate**: string | Template for a shipping code |
|**capitalShippingCodeTemplate**: <br> string | Template for a Capital shipping code |
|**offsetCodeTemplate**: string | Template for an offset code |
|**capitalOffsetCodeTemplate**: <br> string | Template for a Capital offset code |
|**patientDisplayTemplate**: string | Template for displaying patient information |
|**poglCodeDisplayTemplate**: <br> string | Template for displaying a Purchase Order General Ledger code |
|**poDeptDisplayTemplate**: string | Template for displaying a Purchase Order Department |
|**poContactInfoType**: integer <br> *(int32)* | Type of the PO contact info |
|**poContactName**: string | Name of the main PO contact |
|**poContactEmail**: string | Email address of the main PO contact |
|**poContactPhone**: string | Phone number of the main PO contact |
|**poContactPhoneExt**: string | Phone extension of the main PO contact |
|**poContactFax**: string | Fax number of the main PO contact | 
|**activeStatus**: boolean | Is the Facility active or not? |
|**inventoryGroupId**: string *(uuid)* | Unique identifier of the Inventory Group that contains related Inventory items |
|**apToleranceLevel**: number <br> *(double)* | Accounts Payable tolerance level of the Facility |
|**apToleranceLevelType**: integer <br> *(int32)* | Type of the Accounts Payable tolerance level |
|**apToleranceLevel2**:<br> number *(double)* | Second Accounts Payable tolerance level of the Facility |
|**apToleranceLevel2Type**: integer <br> *(int32)* | Type of the second Accounts Payable tolerance level |
|**apFreeFormedToleranceLevel**: <br> number *(double)* | Accounts Payable Free-Form tolerance level of the Facility |
|**apFreeFormedToleranceLevel<br>Type**: integer *(int32)* | Type of the Accounts Payable Free-Form tolerance level |
|**apFreeFormedToleranceLevel2**: <br> number *(double)* | Second Accounts Payable Free-Form tolerance level of the Facility |
|**apFreeFormedToleranceLevel2<br>Type**: integer *(int32)* | Type of the second Accounts Payable Free-Form tolerance level |
|**apOffsetTolerance**: <br> number *(double)* | Accounts Payable offset tolerance of the Facility |
|**apOffsetToleranceType**: <br> integer *(int32)* | Type of the Accounts Payable offset tolerance |
|**taxAmount**: number *(double)* | Amount of the tax |
|**taxType**: integer *(int32)* | Type of the tax |
|**taxExpenseAmount**: number <br> *(double)* | Amount of the tax expense |
|**taxExpenseType**: integer *(int32)* | Type of the tax expense |
|**facilityNoXref**: string | Cross-reference number of the Facility |
|**taxShipping**: boolean | Is shipping taxable or not? |
|**poInvoiceGlValidation**: string | General Ledger validation for the Purchase Order and Invoice |
|**poInvoiceGlValidationMsg**: string | General Ledger validation message for the Purchase Order and Invoice |
|**capitalPOInvoiceGlValidation**: string | General Ledger validation for the Capital Purchase Order and Invoice |
|**capitalPOInvoiceGlValidationMsg**: <br> string | General Ledger validation message for the Capital Purchase Order and Invoice |
|**timeZoneId**: string *(uuid)* | Unique identifier of the time zone |
|**preferenceCardMatching**: <br> integer *(int32)* | Preference Card matching |
|**gpoMemberID**: string | Unique identifier of the Facility within the Group Purchasing Organization |
|**gpoNameId**: string *(uuid)* | Unique identifier of the Group Purchasing Organization. <br> **Note**: The ```gpoMemberID``` and ```gpoNameId``` fields require special privileges to modify. <br> **Note**: See the table below for ```gpoNameId``` values. |
|**customField1**: string | Custom field 1 |
|**customField2**: string | Custom field 2 |
|**customField3**: string | Custom field 3 |
|**customField4**: string | Custom field 4 |
|**poPrefix**: string | Purchase Order prefix |

!!! info "gpoNameIds"

    Use the following ```gpoNameId``` values:

    | GPO Name | gpoNameId |  
    |-----:|:-------|
    |**Other** | 00000000-0000-0000-0000-000000000002 |
    |**Provista/Vizient**| 00000000-0000-0000-0000-000000000001 |
    |**None** | null |

``` json title="Request example"
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
    "gpoMemberID": "string",
    "gpoNameId": "00000000-0000-0000-0000-000000000000",
    "customField1": "string",
    "customField2": "string",
    "customField3": "string",
    "customField4": "string",
    "poPrefix": "string"
}
```

### Request parameters
| Parameter | Explanation |                       
|-----:|:-------|
|**facilityId**: string *(uuid)* <br> <span style="color: #F05D30">**required**</span> <br> *in path* | Unique identifier of the Facility. |
|**api-version**: string default: 1.0 <br> *in header*| The requested API version.|      
|**Authorization**: string default: <br> Bearer access_token <br> *in header* | Specify the type of the token (bearer) and insert the ```access_token``` obtained during authentication. |

### Responses
| Response | Explanation |                      
|-----:|:-------|
|**200 OK**| OK |
|**400 Bad Request**| The request contains incorrect input data. | 
|**401 Unauthorized**| The specified ```access_token``` is invalid or has expired. |
|**403 Forbidden**| The user doesn’t have the appropriate privileges. |
|**404 Not Found** | The specified ID is absent in the system. |
|**500 Internal Server Error**| The server encountered an unexpected condition that prevented it from fulfilling the request.|

## Get the specified Facility

### Path
GET /odata/Facilities({facilityId})

### Description
Returns the details of the Facility specified by ID.

### Request parameters
| Parameter | Explanation |                      
|-----:|:-------|
|**facilityId**: string *(uuid)* <br> <span style="color: #F05D30">**required**</span> <br> *in path* | Enter the ID of the Facility. |
|**api-version**: string default: 1.0 <br> *in header*| The requested API version. |   
|**Authorization**: string default: <br> Bearer access_token <br> *in header* | Specify the type of the token (bearer) and insert the ```access_token``` obtained during authentication. |

### Responses
| Response | Explanation |                      
|-----:|:-------|
|**200 OK**| OK | 
|**400 Bad Request**| The request contains incorrect input data. |        
|**401 Unauthorized**| The specified ```access_token``` is invalid or has expired. |
|**403 Forbidden**| The user doesn’t have the appropriate privileges. |
|**404 Not Found** | The specified ID is absent in the system. |
|**500 Internal Server Error**| The server encountered an unexpected condition that prevented it from fulfilling the request.|

### Properties
| Property | Explanation |                      
|-----:|:-------|
|**facilityId**: string *(uuid)* | Unique identifier of the Facility |
|**organizationId**: string *(uuid)* | Unique identifier of the Organization |
|**organizationNo**: string | Identification number of the Organization |
|**organizationName**: string | Name of the Organization |
|**facilityName**: string | Name of the Facility |
|**facilityNo**: string | Identification number of the Facility |
|**address1**: string | Primary address of the Facility for shipping or billing purposes |
|**address2**: string | Secondary address of the Facility for shipping or billing purposes |
|**city**: string | City of the Facility address |
|**state**: string | State of the Facility address |
|**zip**: string | Zip code of the Facility address |
|**country**: string | Country of the Facility address |
|**taxExpenseCodeTemplate**:<br> string | Template for a tax expense code |
|**taxAccrualCodeTemplate**: string | Template for a tax accrual code |
|**discountCodeTemp**: string | Template for a discount code |
|**shippingCodeTemplate**: string | Template for a shipping code |
|**offsetCodeTemplate**: string | Template for an offset code |
|**patientDisplayTemplate**: string | Template for displaying patient information |
|**poglCodeDisplayTemplate**:<br> string | Template for displaying a Purchase Order General Ledger code |
|**poDeptDisplayTemplate**: string | Template for displaying a Purchase Order Department |
|**activeStatus**: boolean | Is the Facility active or not? |
|**inventoryGroupId**: string *(uuid)* | Unique identifier of the Inventory Group that contains related Inventory items |
|**inventoryGroupNo**: string | Number of the Inventory Group that contains related Inventory items |
|**inventoryGroupName**: string | Name of the Inventory Group that contains related Inventory items |
|**apToleranceLevel**: number <br> *(double)* | Accounts Payable tolerance level of the Facility |
|**apToleranceLevelType**: integer <br> *(int32)* | Type of the Accounts Payable tolerance level |
|**apToleranceLevelTypeValue**:<br> string | Value of the Accounts Payable tolerance level type |
|**apToleranceLevel2**:<br> number *(double)* | Second Accounts Payable tolerance level of the Facility |
|**apToleranceLevel2Type**: integer <br> *(int32)* | Type of the second Accounts Payable tolerance level |
|**apToleranceLevel2TypeValue**:<br> string | Value of the second Accounts Payable tolerance level type |
|**apFreeFormedToleranceLevel**: <br> number *(double)* | Accounts Payable Free-Form tolerance level of the Facility |
|**apFreeFormedToleranceLevel<br>Type**: integer *(int32)* | Type of the Accounts Payable Free-Form tolerance level |
|**apFreeFormedToleranceLevel<br>TypeValue**: string | Value of the Accounts Payable Free-Form tolerance level type |
|**apFreeFormedToleranceLevel2**: <br> number *(double)* | Second Accounts Payable Free-Form tolerance level of the Facility |
|**apFreeFormedToleranceLevel2<br>Type**: integer *(int32)* | Type of the second Accounts Payable Free-Form tolerance level |
|**apFreeFormedToleranceLevel2<br>TypeValue**: string | Value of the second Accounts Payable Free-Form tolerance level type |
|**apOffsetTolerance**: <br> number *(double)* | Accounts Payable offset tolerance of the Facility |
|**apOffsetToleranceType**: <br> integer *(int32)* | Type of the Accounts Payable offset tolerance |
|**apOffsetToleranceType<br>Value**: string | Value of the Accounts Payable offset tolerance type |
|**taxType**: integer *(int32)* | Type of the tax |
|**taxTypeValue**: string | Value of the tax type |
|**taxAmount**: number *(double)* | Amount of the tax |
|**taxExpenseType**: integer *(int32)* | Type of the tax expense |
|**taxExpenseTypeValue**: string | Value of the tax expense type |
|**taxExpenseAmount**: number <br> *(double)* | Amount of the tax expense |
|**facilityNoXref**: string | Cross-reference number of the Facility |
|**taxShipping**: boolean | Is shipping taxable or not? |
|**poInvoiceGlValidation**: string | General Ledger validation for the Purchase Order and Invoice |
|**poInvoiceGlValidationMsg**: string | General Ledger validation message for the Purchase Order and Invoice |
|**capitalPOInvoiceGlValidation**: string | General Ledger validation for the Capital Purchase Order and Invoice |
|**capitalPOInvoiceGlValidationMsg**: <br> string | General Ledger validation message for the Capital Purchase Order and Invoice |
|**timeZoneId**: string *(uuid)* | Unique identifier of the time zone |
|**timeZone**: string | Time zone |
|**preferenceCardMatching**: <br> integer *(int32)* | Preference Card matching |
|**preferenceCardMatching<br>Value**: string | Value of the Preference Card matching |
|**dateCreated**: string <br>*(date-time)* | Date when the Facility was created |
|**createdBy**: string *(uuid)* | Unique identifier of the user who created the Facility |
|**createdByName**: string | Name of the user who created the Facility |
|**lastUpdated**: string *(date-time)* | Date when the Facility was last updated |
|**lastUpdatedBy**: string *(uuid)* | Unique identifier of the user who last updated the Facility |
|**lastUpdatedByName**: string | Name of the user who last updated the Facility |
|**gpoMemberID**: string | Unique identifier of the Facility within the Group Purchasing Organization |
|**gpoNameId**: string *(uuid)* | Unique identifier of the Group Purchasing Organization |
|**gpoNameValue**: string | Name of the Group Purchasing Organization |
|**capitalTaxExpenseCode<br>Template**: string | Template for a Capital tax expense code |
|**capitalTaxAccrualCode<br>Template**: string | Template for a Capital tax accrual code |
|**capitalDiscountCodeTemplate**: <br> string | Template for a Capital discount code |
|**capitalShippingCodeTemplate**: <br> string | Template for a Capital shipping code |
|**capitalOffsetCodeTemplate**: <br> string | Template for a Capital offset code |
|**customField1**: string | Custom field 1 |
|**customField2**: string | Custom field 2 |
|**customField3**: string | Custom field 3 |
|**customField4**: string | Custom field 4 |
|**poContactInfoType**: integer <br> *(int32)* | Type of the PO contact info |
|**poContactInfo**: string | PO contact info |
|**poContactName**: string | Name of the main PO contact |
|**poContactEmail**: string | Email address of the main PO contact |
|**poContactPhone**: string | Phone number of the main PO contact |
|**poContactPhoneExt**: string | Phone extension of the main PO contact |
|**poContactFax**: string | Fax number of the main PO contact |
|**poPrefix**: string | Purchase Order prefix |

``` json title="Response example (200 OK)" 
{
    "@odata.context": "link",
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
    "gpoMemberID": "string",
    "gpoNameId": "00000000-0000-0000-0000-000000000000",
    "gpoNameValue": "string",
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
    "poContactFax": "string",
    "poPrefix": "string"
}
```
