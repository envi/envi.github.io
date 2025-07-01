# Envi Developer Resources

The **Envi Developer Resources** provides information about all public endpoints and descriptions of the parameters and models used. It can also be used for testing and prototyping.

!!! note ""

    **API Endpoint**: https://api-demo.envi.net <br>
    **Schemes**: HTTP, HTTPS <br>
    **Version**: v1


# What's new
Stay up-to-date with the latest API features, improvements, and articles.

[Subscribe to our newsletter](https://news.envi.net/Signup/dev-news){ .md-button .md-button--primary }

**v. 6.4.4**

You can now retrieve file content by file ID using a new endpoint in [File Attachments](FileAttachments.md#get-the-specified-file-content).

**v. 6.4.3**

With the new [File Attachments](FileAttachments.md#get-the-specified-file-metadata) endpoint, you can now retrieve file details by file ID for your organization.

**v. 6.4.1**

A new [File Attachments](FileAttachments.md#get-the-list-of-files-by-entity-id) endpoint is now available to retrieve the list of files for the specified entity ID in the logged-in organization.

**v. 6.3.8**

You can now retrieve the list of Departments and view the details of a specific Department via the new [Departments](Departments.md) endpoints.

**v. 6.3.8**

The [Purchase Orders](PurchaseOrders.md), [Matched Invoices](MatchedInvoices.md), and [Batch](AP_Batch.md#get-invoices-from-the-specified-ap-batch) endpoints now include **Project Number** properties. 

**v. 6.3.6**

The new ```poUdfLabels``` property has been added to the [Purchase Order Items](PurchaseOrderItems.md) and [Purchase Orders](PurchaseOrders.md) endpoints.


**v. 6.2.8**

The [Matched Invoices](MatchedInvoices.md) and [Matched Invoice Items](MatchedInvoiceItems.md) endpoints support now **and**, **or**, **in**, **gt**, **ge**, **lt**, **le** [logical operators](Options_and_Limitations.md#logical-operators).

**v. 6.1.7**

The following prorepties have been added to the [Facilities](Facilities.md) endpoints: ```poContactName```, ```poContactEmail```, ```poContactPhone```, ```poContactPhoneExt```, and ```poContactFax```.

**v. 6.1.3**

The [Facilities](Facilities.md) endpoints now include the two additional properties: ```poContactInfoType``` and ```poContactInfo```.

**v. 6.1.0**

You can now use a new [Classification](Classifications.md#create-a-new-classification) endpoint to create a new Classification within the logged-in organization.

**v. 6.0.9**

The two new [Classifications](Classifications.md) endpoints have been added. You can now retrieve the list of Classifications and the details of a specific Classification.

**v. 6.0.7**

The [Vendor Facilities](VendorFacilities.md) endpoints now include the ```taxableItemsOnly``` and ```takeDepartmentsIntoAccount``` properties.

**v. 6.0.1**

[Purchase Orders](PurchaseOrders.md) support now the ```includeInactiveVendors``` optional parameter.

Starting now, every time you submit a Requisition Fill, the system will notify you via Webhook.
of the Purchase Order.
**v. 5.9.5**

The two new properties have been added to the [Vendor Facilities](VendorFacilities.md) endpoints: ```ocrMatchOptionId``` and ```ocrMatchOptionValue```.

**v. 5.8.4**

The two new properties have been added to the [Facilities](Facilities.md) endpoints: ```customField1``` and ```customField1```.

A new  [Facility](Facilities.md#partially-update-the-specified-facility) endpoint has been included, which allows you to update the details of the Facility based on the Facility ID.

**v. 5.8.3**

You can now use a new [Vendor Facility](VendorFacilities.md#create-a-new-vendor-facility) endpoint to create a new Vendor Facility for a specified active Location within an active Vendor logged in an organization.

We have added a new feature that enhances our Webhooks: custom headers defined in the subscription will now be sent with each Webhook.

**v. 5.8.2**

You can now use a new [Vendor Contact](VendorContacts.md#create-a-new-vendor-contact) endpoint to create a new Vendor Contact within the logged-in organization.

**v. 5.8.1**

You can now use a new [Vendor Address](VendorAddresses.md#create-a-new-vendor-address) endpoint to create a new Vendor Address within the logged-in organization.

**v. 5.8.0**

The Batch Size is available within Envi, so now you have the possibility to customize the batch size for each Webhook Subscription.

**v. 5.7.9**

We have added two new [Vendor Fax Configurations](VendorFaxConfigurations.md#get-the-list-of-vendor-fax-configurations) endpoints. You can retrieve appropriate data to get the Vendor Fax Delivery info for a Purchase Order.

**v. 5.7.8**

[Vendor Addresses](VendorAddresses.md), [Vendor Contacts](VendorContacts.md), and [Vendor Email Configurations](VendorEmailConfigurations.md) support now the ```includeInactiveVendors``` and ```includeInactiveFacilities``` optional parameters.

**v. 5.7.7**

You can now create a new Manufacturer within the logged-in organization using a new [endpoint](Manufacturers.md#create-a-new-manufacturer).

**v. 5.7.6**

New [Vendor Facilities](VendorFacilities.md) endpoints have been implemented. You can now get the list of Vendor Facilities and the details of the Vendor Facility specified by ID within the logged-in organization.

**v. 5.7.5**

The following endpoints have been added to Envi Developer Resources:

 - [Requisition Fill Items](RequisitionFillItems.md)
 - [Vendor Addresses](VendorAddresses.md)
 - [Vendor Contacts](VendorContacts.md)
 - [Vendor Email Configurations](VendorEmailConfigurations.md)
 
[Manufacturers](Manufacturers.md#get-the-list-of-manufacturers) endpoint supports now **and**, **or**, **in**, **gt**, **ge**, **lt**, **le** [logical operators](Options_and_Limitations.md#logical-operators).

**v. 5.7.4**

[Requisition Fills](RequisitionFills.md#get-the-list-of-requisition-fills) endpoints are now available on Envi Developer Resources.

**v. 5.7.3**

A new [Requisition Item](RequisitionItems.md#partially-update-the-specified-requisition-item) endpoint has been implemented. Thus, you can partially update the details of the Requisition Line Item specified by the Requisition Item ID.

WebHook is enabled within Envi. The WebHook subscription configuration allows you to get notifications regarding affected entities of selected types.

**v. 5.7.2**

Now, active subscribers will receive updates via WebHook when the Usage transaction status has been changed to Submitted.

**v. 5.6.7**

A new [Requisition Item](RequisitionItems.md#add-the-specified-requisition-line-item) endpoint has been added. So, now you are able to add specified Requisition Line Items.

**v. 5.5.4**

From now on, you can use the [Requisition Items](RequisitionItems.md#) endpoints to get a list of Requisition Items from all Requisitions within the logged-in organization or get specified Requisition Item by ID.

**v. 5.4.7**

[Requisitions](Requisitions.md) endpoints are now available on Envi Developer Resources.

**v. 5.4.5**

We have added a new [Inventory Vendor](Inventory.md#save-the-specified-inventory-vendor) endpoint that enables you to create a new Inventory Vendor within the logged-in organization and specified Inventory.

**v. 5.4.4**

You can now create a new Inventory Location specified by ID using the [Inventory Locations](Inventory.md#save-the-specified-inventory-location) endpoint.

**v. 5.4.0**

[Inventory Locations Cost and Quantity](InventoryLocationsCostAndQuantity.md) endpoints have been added to Envi Developer Resources.

**v. 5.3.9**

[Vendors](Vendors.md#get-the-list-of-vendors) endpoint supports now **and**, **or**, **in**, **gt**, **ge**, **lt**, **le** [logical operators](Options_and_Limitations.md#logical-operators).

**v. 5.3.8**

[Facilities](Facilities.md#get-the-list-of-facilities) endpoint supports now **and**, **or**, **in**, **gt**, **ge**, **lt**, **le** [logical operators](Options_and_Limitations.md#logical-operators).

**v. 5.3.7**

[Addresses](Addresses.md#get-the-list-of-addresses) endpoint supports now **and**, **or**, **in**, **gt**, **ge**, **lt**, **le** [logical operators](Options_and_Limitations.md#logical-operators).

**v. 5.3.6**

[Inventory Vendors](InventoryVendors.md#get-the-list-of-all-inventory-vendors) endpoints support **in**, **gt**, **ge**, **lt**, **le** [logical operators](Options_and_Limitations.md#logical-operators).

**v. 5.3.5**

[Inventory](Inventory.md#get-the-list-of-inventory-items) supports now **in**, **gt**, **ge**, **lt**, **le** [logical operators](Options_and_Limitations.md#logical-operators).

**v. 5.3.1**

[Inventory Locations](InventoryLocations.md#get-the-list-of-inventory-locations) support now **in**, **gt**, **ge**, **lt**, **le** [logical operators](Options_and_Limitations.md#logical-operators).

Additional fields are now available in the [Facilities](Facilities.md#get-the-list-of-facilities) endpoint.

**v. 5.3.0**

[Inventory Snapshot Items](InventorySnapshotItems.md) are now available on Envi Developer Resources.

**v. 5.2.9**

You can now get the [Inventory Snapshots](InventorySnapshots.md) data.

**v. 5.2.6**

The [Receipts](Receipts.md) endpoints now support additional ``` receiptSourceId ```  and ``` receiptSource``` fields.


