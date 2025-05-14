# Usages

## Create new Usages

### Path</span>
POST /odata/Usages/BulkAdd

### Description</span>
Creates new Usages within the logged-in organization.

### Request body</span>
For usage(s) creation

<style>
td, th {
   border: none!important;
}
</style>

|  <div style="width:200px">Parameter</div>  |  <div style="width:420px">Explanation</div>  |                      
|-----:|:-------|
|**facilityNo**: string <br> <span style="color: #F05D30">**required**</span> <br>  *in formData* | Identification Number of the Facility. <br> **If not provided**: 400 Bad Request. |
|**usageDate**: string <br> *in formData* | Date of the Usage. <br> **If not provided**: Date according to the user Time Zone. |
|**departmentNo**: string <br> <span style="color: #F05D30">**required**</span> <br>  *in formData* | Number of the Department. <br> **If not provided**: User Default Department if it is set and matches with user Default Facility. Otherwise, ```none```. 
|**patientNo**: string <br> *in formData* | Number of the Patient. <br> **If not provided**: ```none```. |
|**reference**: string <br> *in formData* | Information concerning the Usage.<br> **If not provided**: Empty. |
|**caseNo**: string <br> *in formData* | Number of the Case. <br> **If not provided**: Empty. |
|**trackingCode**: string <br> *in formData* | Code for Tracking. <br> **If not provided**: Empty. |
|**physicianNo**: string <br> *in formData* | Number of the Physician. <br> **If not provided**: The ```none``` value if it is not specified or it doesn't match the specified Facility. |
|**usageType**: string <br> *in formData* | Standard <br> **Auto-Populated** |
|**source**: string <br> *in formData* | Auto <br> **Auto-Populated** |


``` json title="Request Content-types: APPLICATION/JSON, APPLICATION/XML <br> Request Example"
{
  "facilityNo": "string",
  "usageDate": "string (date-time)",
  "departmentNo": "string",
  "patientNo": "string",
  "reference": "string",
  "caseNo": "string",
  "trackingCode": "string",
  "physicianNo": "string",
  "usageType": "string",
  "source": "string",
}
```

``` json title="Request Example"
{
  "usages":[
   {
     "facilityNo": facilityNo1,
     "departmentNo": departmentNo1
   },
   {
     "facilityNo": facilityNo3,
     "departmentNo": departmentNo3
   },
   {
     "facilityNo": facilityNo2,
     "departmentNo": departmentNo2
   }
  ]
}
```

### Request parameters</span>
|  <div style="width:200px">Parameter</div>  |  <div style="width:380px">Explanation</div>  |                      
|-----:|:-------|
|**api-version**: string default: 1.0 <br> *in header*| The requested API version.|   
|**Authorization**: string default: <br> Bearer access_token <br> *in header* |Specify the type of the token (bearer) and then insert the ```access_token```, which was obtained during authentication. |

### Responses</span>
| <div style="width:200px">Response </div>|<div style="width:420px">Explanation</div>|                      
|-----:|:-------|
|**200 OK**|OK|      
|**400 Bad Request**| Incorrect input data or organization ID does not match with the organization ID user is logged in.|
|**401 Unauthorized**| Incorrect specified ```access_token``` or ```access_token``` got expired.|
|**403 Forbidden**| User doesn’t have appropriate privileges.|
|**500 Internal Server Error**| Server encountered an unexpected condition that prevented it from fulfilling the request.|

``` json title="Response Content-types: APPLICATION/JSON, APPLICATION/XML<br>Response example (200 OK)"
"00000000-0000-0000-0000-000000000000"

```

## Submit Usages

### Path</span>
POST /odata/Usages/BulkSubmit

### Description</span>
Submits Usages within the logged-in organization.

### Request body</span>
For Usage(s) submition

|  <div style="width:200px">Parameter</div>  |  <div style="width:420px">Explanation</div>  |                      
|-----:|:-------|
|**usageId**: string <br> <span style="color: #F05D30">**required**</span> <br>  *in formData* | Unique Identifier of the the Usage. <br> **If not provided**: 400 Bad Request. |

``` json title="Request Content-types: APPLICATION/JSON, APPLICATION/XML <br> Request Example"
{
  "usageId": "string(uuid)",
}
```

``` json title="Request Example"
{
 "usageIds":
 [
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
### Request parameters</span>

|  <div style="width:200px">Parameter</div>  |  <div style="width:380px">Explanation</div>  |                      
|-----:|:-------|
|**api-version**: string default: 1.0 <br> *in header*| The requested API version.|   
|**Authorization**: string default: <br> Bearer access_token <br> *in header* |Specify the type of the token (bearer) and then insert the ```access_token```, which was obtained during authentication. |



### Responses</span>
| <div style="width:200px">Response </div>|<div style="width:420px">Explanation</div>|                      
|-----:|:-------|
|**200 OK**|OK|      
|**400 Bad Request**| Incorrect input data or organization ID does not match with the organization ID user is logged in.|
|**401 Unauthorized**| Incorrect specified ```access_token``` or ```access_token``` got expired.|
|**403 Forbidden**| User doesn’t have appropriate privileges.|
|**500 Internal Server Error**| Server encountered an unexpected condition that prevented it from fulfilling the request.|

``` json title="Response Content-types: APPLICATION/JSON, APPLICATION/XML<br>Response example (200 OK)"
"Usage has been submitted successfully."
```
### Custom errors</span>
| <div style="width:200px">Response </div>|<div style="width:420px">Explanation</div>|                      
|-----:|:-------|
|**200 OK** | There is at least one Line Item with the Quantity 0 (zero) on the Line Items tab.|

``` json title="Response Example"
At least one line item has zero quantity.
```


| <div style="width:200px"> </div>|<div style="width:420px"></div>|                      
|-----:|:-------|
|**200 OK** | Usage contains Line Item with a negative Quantity and required Tracking.|

``` json title="Response Example"

At least one Item with Tracking values has negative Quantity.

```

| <div style="width:200px"> </div>|<div style="width:420px"></div>|                      
|-----:|:-------|
|**200 OK** | Usage has been already submitted by another user.|

``` json title="Response Example"

Usage has been already processed, submitted, or canceled.

```

| <div style="width:200px"> </div>|<div style="width:420px"></div>|                      
|-----:|:-------|
|**200 OK** | Usage has completed Line Item with Tracking by Serial Number and Quantity/CF larger than 1.|

``` json title="Response Example"

At least one line item requires serial number tracking and has a quantity larger than one.

```

| <div style="width:200px"> </div>|<div style="width:420px"></div>|                      
|-----:|:-------|
|**200 OK** | Usage contains Line Item with not unique Serial Number. |

``` json title="Response Example"

Usage contains not unique serial number. 

```

| <div style="width:200px"> </div>|<div style="width:420px"></div>|                      
|-----:|:-------|
|**200 OK** | Usage contains Line Item with Tracking by Expiration Date and Quantity larger than Expiration Date quantity. |

``` json title="Response Example"

Line items with Tracking by Expiration Date have insufficient quantity.

```

| <div style="width:200px"> </div>|<div style="width:420px"></div>|                      
|-----:|:-------|
|**200 OK** | Usage contains Line Item with Tracking by Lot No with Quantity larger than Lot No Quantity. |

``` json title="Response Example"

Line items with tracking by Lot No have insufficient quantity.

```

| <div style="width:200px"> </div>|<div style="width:420px"></div>|                      
|-----:|:-------|
|**200 OK** | Usage contains Line Item with Tracking by Serial No with Quantity larger than Serial No Quantity. |

``` json title="Response Example"

Line items with tracking by Serial No have insufficient quantity.

```

| <div style="width:200px"> </div>|<div style="width:420px"></div>|                      
|-----:|:-------|
|**200 OK** | Some arithmetic overflow errors occurred during the Usage submission. |

``` json title="Response Example"

Arithmetic Overflow Error(s) occurred during submission process.

```

| <div style="width:200px"> </div>|<div style="width:420px"></div>|                      
|-----:|:-------|
|**200 OK** | Usage contains at least one Implant Line Item with **Implant Completed**—**No**. |

``` json title="Response Example"

At least one implant line item is not completed.

```

| <div style="width:200px"> </div>|<div style="width:420px"></div>|                      
|-----:|:-------|
|**200 OK** | Usage contains failed Line Item(s).|

``` json title="Response Example"

Usage has failed line item(s).

```

| <div style="width:200px"> </div>|<div style="width:420px"></div>|                      
|-----:|:-------|
|**200 OK** | Patient field is not specified, but Usage requires a selected Facility option of the Patient.|

``` json title="Response Example"

Usage requires a patient.

```


| <div style="width:200px"> </div>|<div style="width:420px"></div>|                      
|-----:|:-------|
|**200 OK** | Case Number is not unique within a Facility or is not set.|

``` json title="Response Example"

Usage requires a unique case number.

```

| <div style="width:200px"> </div>|<div style="width:420px"></div>|                      
|-----:|:-------|
|**200 OK** | Department field of the Usage is not specified (“None”).|

``` json title="Response Example"

Department is required.

```

| <div style="width:200px"> </div>|<div style="width:420px"></div>|                      
|-----:|:-------|
|**200 OK** | Patient, Procedure, Physician, Case Number, and Schedule fields of the Usage are not specified and the **Usage requires a procedure**, **Usage requires a doctor**, **Usage requires a case number**, **Usage requires a schedule number**, and **Usage requires a patient** Facility settings are enabled. |

``` json title="Response Example"

Usage requires a case number.

```

``` json title="Response Example"

Usage requires a doctor.

```


``` json title="Response Example"

Usage requires a procedure.

```

``` json title="Response Example"

Usage requires a schedule number.

```

| <div style="width:200px"> </div>|<div style="width:420px"></div>|                      
|-----:|:-------|
|**200 OK** |**Enable block billable supplies for Usage** Facility option is selected, <br> Usage is created for a current Facility and contains Line Item with <br> **Is Billable**—**Yes**.|

``` json title="Response Example"

At least one line item is billable.

```

| <div style="width:200px"> </div>|<div style="width:420px"></div>|                      
|-----:|:-------|
|**200 OK** |**Do Not Allow Negative On-hand Quantity** Facility option is selected, <br> Quantity on Hand is less than Qty*CF of the Usage <br> Inventory Item.|

``` json title="Response Example"

At least one line item doesn't have required Qty on Hand.

```