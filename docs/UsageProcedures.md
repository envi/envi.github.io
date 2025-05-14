# UsageProcedures

## Add new Procedures to existing Usages

### Path</span>
POST /odata/UsageProcedures/BulkAdd

### Description</span>
Adds new Procedures to existing Usages within the logged-in organization.

### Request body</span>
For adding Procedure(s) to Usage(s)

<style>
td, th {
   border: none!important;
}
</style>

|  <div style="width:200px">Parameter</div>  |  <div style="width:380px">Explanation</div>  |                      
|-----:|:-------|
|**usageId**: string <br> <span style="color: #F05D30">**required**</span> <br>  *in formData* | Unique Identifier of the the Usage. <br> **If not provided**: 400 Bad Request. |
|**procedureNo**: string <br> <span style="color: #F05D30">**required**</span> <br>  *in formData* | Number of the Procedure. <br> It is populated from ```procedureNo``` if it is matched by Procedure No and Facility. You can add procedures only with unique values. <br> **If not provided**: 400 Bad Request. |

``` json title="Request Content-types: APPLICATION/JSON, APPLICATION/XML <br> Request Example"
{
  "usageId": "string(uuid)",
  "procedureNo": "string",
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
|**400 Bad Request**|Incorrect input data or organization ID does not match with the organization ID user is logged in.|
|**401 Unauthorized**|Incorrect specified ```access_token``` or ```access_token``` got expired.|
|**403 Forbidden**|User doesn’t have appropriate privileges.|
|**500 Internal Server Error**|Server encountered an unexpected condition that prevented it from fulfilling the request.|

``` json title="Response Content-types: APPLICATION/JSON, APPLICATION/XML<br>Response example (200 OK)"
"object"

```



