# Envi Developer Resources
This page contains description of Envi Developer Resources. It includes all public end-points as well as description of parameters and models used. You can use this page for testing and prototyping purposes.


!!! note ""

    **API Endpoint** <br>
    ``` 
    https://api-demo.envi.net 
    ``` 
    **Schemes**: HTTP, HTTPS <br>
    **Version**: V1


# What's new
Stay up-to-date with the latest API features, improvements, and articles.

[Subscribe to our newsletter](https://news.envi.net/Signup/dev-news){ .md-button .md-button--primary }

<span style="color: #E0592A">v. 6.3.8</span>

The [Purchase Orders](PurchaseOrders.md), [Matched Invoices](MatchedInvoices.md), and [Batch](AP_Batch.md#get-the-specified-ap-batched-invoice) endpoints now include **Project Number** properties. 



<span style="color: #E0592A">v. 6.3.6</span>

The new ```poUdfLabels``` property has been added to the [Purchase Order Items](PurchaseOrderItems.md) and [Purchase Orders](PurchaseOrders.md) endpoints.


<span style="color: #E0592A">v. 6.2.8</span>
The [Matched Invoices](MatchedInvoices.md) and [Matched Invoice Items](MatchedInvoiceItems.md) endpoints support now **and**, **or**, **in**, **gt**, **ge**, **lt**, **le** [logical operators](Options_and_Limitations.md#logical-operators).

<span style="color: #E0592A">v. 6.1.7</span>

The following prorepties have been added to the [Facilities](Facilities.md) endpoints: ```poContactName```, ```poContactEmail```, ```poContactPhone```, ```poContactPhoneExt```, and ```poContactFax```.

<span style="color: #E0592A">v. 6.1.3</span>

The [Facilities](Facilities.md) endpoints now include the two additional properties: ```poContactInfoType``` and ```poContactInfo```.

<span style="color: #E0592A">v. 6.1.0</span>

You can now use a new [Classification](Classifications.md#create-a-new-classification) endpoint to create a new Classification within a logged organization.

<span style="color: #E0592A">v. 6.0.9</span>

The two new [Classifications](Classifications.md) endpoints have been added. You can now retrieve the list of Classifications and the details of a specific Classification.

<span style="color: #E0592A">v. 6.0.7</span>

The [Vendor Facilities](VendorFacilities.md) endpoints now include the ```taxableItemsOnly``` and ```takeDepartmentsIntoAccount``` properties.

<span style="color: #E0592A">v. 6.0.1</span>

[Purchase Orders](PurchaseOrders.md) support now the ```includeInactiveVendors``` optional parameter.

Starting now, every time you submit a Requisition Fill, the system will notify you via Webhook.

<span style="color: #E0592A">v. 5.9.5</span>

The two new properties have been added to the [Vendor Facilities](VendorFacilities.md) endpoints: ```ocrMatchOptionId``` and ```ocrMatchOptionValue```.

<span style="color: #E0592A">v. 5.8.4</span>

The two new properties have been added to the [Facilities](Facilities.md) endpoints: ```customField1``` and ```customField1```.

A new  [Facility](Facilities.md#partially-update-the-specified-facility) endpoint has been included, which allows you to partially update the details of the Facility based on Facility ID.

<span style="color: #E0592A">v. 5.8.3</span>

You can now use a new [Vendor Facility](VendorFacilities.md#create-a-new-vendor-facility) endpoint to create a new Vendor Facility for a specified active Location within an active Vendor logged in an organization.

We have added a new feature that enhances our Webhooks: custom headers defined in the subscription will now be sent with each Webhook.

<span style="color: #E0592A">v. 5.8.2</span>

You can now use a new [Vendor Contact](VendorContacts.md#create-a-new-vendor-contact) endpoint to create a new Vendor Contact within a logged organization.

<span style="color: #E0592A">v. 5.8.1</span>

You can now use a new [Vendor Address](VendorAddresses.md#create-a-new-vendor-address) endpoint to create a new Vendor Address within a logged organization.

<span style="color: #E0592A">v. 5.8.0</span>

The Batch Size is available within Envi, so now you have the possibility to customize the batch size for each Webhook Subscription.

<span style="color: #E0592A">v. 5.7.9</span>

We have added two new [Vendor Fax Configurations](VendorFaxConfigurations.md#get-the-list-of-vendor-fax-configurations) endpoints. You can retrieve appropriate data to get the Vendor Fax Delivery info of the Purchase Order.

<span style="color: #E0592A">v. 5.7.8</span>

[Vendor Addresses](VendorAddresses.md), [Vendor Contacts](VendorContacts.md), and [Vendor Email Configurations](VendorEmailConfigurations.md) support now the ```includeInactiveVendors``` and ```includeInactiveFacilities``` optional parameters.

<span style="color: #E0592A">v. 5.7.7</span>

Create a new Manufacturer within a logged organization by using a new [endpoint](Manufacturers.md#create-a-new-manufacturer).

<span style="color: #E0592A">v. 5.7.6</span>

New [Vendor Facilities](VendorFacilities.md) endpoints have been implemented. You can now get the list of Vendor Facilities and the details of the Vendor Facility specified by ID within a logged organization.

<span style="color: #E0592A">v. 5.7.5 </span>

The following endpoints have been added to Envi Developer Resources:

 - [Requisition Fill Items](RequisitionFillItems.md)
 - [Vendor Addresses](VendorAddresses.md)
 - [Vendor Contacts](VendorContacts.md)
 - [Vendor Email Configurations](VendorEmailConfigurations.md)
 
[Manufacturers](Manufacturers.md#get-the-list-of-manufacturers) endpoint supports now **and**, **or**, **in**, **gt**, **ge**, **lt**, **le** [logical operators](Options_and_Limitations.md#logical-operators).

<span style="color: #E0592A">v. 5.7.4</span>

[Requisition Fills](RequisitionFills.md#get-the-list-of-requisition-fills) endpoints are now available on Envi Developer Resources.

<span style="color: #E0592A">v. 5.7.3</span>

A new [Requisition Item](RequisitionItems.md#partially-update-the-specified-requisition-item) endpoint has been implemented. Thus, you can partially update the details of the Requisition Line Item specified by Requisition Item ID.

WebHook is enabled within Envi. The WebHook subscription configuration allows you to get notifications regarding affected entities of selected types.

<span style="color: #E0592A">v. 5.7.2</span>

Now, active subscribers will receive updates via WebHook when the Usage transaction status has been changed to Submitted.

<span style="color: #E0592A">v. 5.6.7</span>

A new [Requisition Item](RequisitionItems.md#add-the-specified-requisition-line-item) endpoint has been added. So, now you are able to add specified Requisition Line Items.

<span style="color: #E0592A">v. 5.5.4</span>

From now on, you can use the [Requisition Items](RequisitionItems.md#) endpoints to get a list of Requisition Items from all Requisitions within a logged organization or get specified Requisition Item by ID.

<span style="color: #E0592A">v. 5.4.7</span>

[Requisitions](Requisitions.md) endpoints are now available on Envi Developer Resources.

<span style="color: #E0592A">v. 5.4.5</span>

We have added a new [Inventory Vendor](Inventory.md#save-the-specified-inventory-vendor) endpoint that enables you to create a new Inventory Vendor within a logged organization and specified Inventory.

<span style="color: #E0592A">v. 5.4.4</span>

You can now create a new Inventory Location specified by ID using the [Inventory Locations](Inventory.md#save-the-specified-inventory-location) endpoint.

<span style="color: #E0592A">v. 5.4.0</span>

[Inventory Locations Cost and Quantity](InventoryLocationsCostAndQuantity.md) endpoints have been added to Envi Developer Resources.

<span style="color: #E0592A">v. 5.3.9</span>

[Vendors](Vendors.md#get-the-list-of-vendors) endpoint supports now **and**, **or**, **in**, **gt**, **ge**, **lt**, **le** [logical operators](Options_and_Limitations.md#logical-operators).

<span style="color: #E0592A">v. 5.3.8</span>

[Facilities](Facilities.md#get-the-list-of-facilities) endpoint supports now **and**, **or**, **in**, **gt**, **ge**, **lt**, **le** [logical operators](Options_and_Limitations.md#logical-operators).

<span style="color: #E0592A">v. 5.3.7</span>

[Addresses](Addresses.md#get-the-list-of-addresses) endpoint supports now **and**, **or**, **in**, **gt**, **ge**, **lt**, **le** [logical operators](Options_and_Limitations.md#logical-operators).

<span style="color: #E0592A">v. 5.3.6</span>

[Inventory Vendors](InventoryVendors.md#get-the-list-of-all-inventory-vendors) endpoints support **in**, **gt**, **ge**, **lt**, **le** [logical operators](Options_and_Limitations.md#logical-operators).

<span style="color: #E0592A">v. 5.3.5</span>

[Inventory](Inventory.md#get-the-list-of-inventory-items) supports now **in**, **gt**, **ge**, **lt**, **le** [logical operators](Options_and_Limitations.md#logical-operators).

<span style="color: #E0592A">v. 5.3.1</span>

[Inventory Locations](InventoryLocations.md#get-the-list-of-inventory-locations) support now **in**, **gt**, **ge**, **lt**, **le** [logical operators](Options_and_Limitations.md#logical-operators).

Additional fields are now available in the [Facilities](Facilities.md#get-the-list-of-facilities) endpoint.

<span style="color: #E0592A">v. 5.3.0</span>

[Inventory Snapshot Items](InventorySnapshotItems.md) are now available on Envi Developer Resources.

<span style="color: #E0592A">v. 5.2.9</span>

You can now get the [Inventory Snapshots](InventorySnapshots.md) data.

<span style="color: #E0592A">v. 5.2.6</span>

The [Receipts](Receipts.md) endpoints support now additional ``` receiptSourceId ```  and ``` receiptSource``` fields.


