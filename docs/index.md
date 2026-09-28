# Envi Developer Resources

The **Envi Developer Resources** provides information about all public endpoints and descriptions of the parameters and models used. It can also be used for testing and prototyping.

!!! note ""

    **API Endpoint**: https://api-demo.envi.net <br>
    **Schemes**: HTTP, HTTPS <br>
    **Version**: v1


# What's New
Stay up to date with the latest API features, improvements, and articles.

[Subscribe to our newsletter](https://news.envi.net/Signup/dev-news){ .md-button .md-button--primary }

**v. 6.7.6**

A new [Purchase Order](PurchaseOrders.md#cancel-an-existing-purchase-order) endpoint has been added to cancel the Purchase Order specified by ID.

The ```requireMfg``` and ```requireMfgItemNo``` properties have been added to the [Vendors](Vendors.md) endpoints.

**v. 6.7.5**

A new [Purchase Order](PurchaseOrders.md#partially-update-the-specified-purchase-order) endpoint has been added to partially update the Purchase Order specified by ID.

**v. 6.7.4**

A new [Purchase Order](PurchaseOrders.md#create-a-new-purchase-order) endpoint has been added to create a new PO within the logged-in organization.

You can now set the Unit Price via API when adding new items to existing Usages using the new ```unitPrice``` and ```useApiUnitPrice``` parameters in the [POST Usage Items](UsageItems.md#add-new-items-to-existing-usages) endpoint.

**v. 6.7.2**

The ```gpoMemberID```, ```gpoNameId```, and ```gpoNameValue``` properties have been added to the [Facilities](Facilities.md) endpoints.

**v. 6.6.9**

A new [AP Batch](AP_Batch.md#create-a-new-export-history-record) endpoint has been added for creating Export History records.

**v. 6.6.8**

The [Matched Invoices](MatchedInvoices.md) endpoints and the [AP Batch](AP_Batch.md#get-invoices-from-the-specified-ap-batch) endpoint now include the ```shippingGLCode``` property.

**v. 6.6.4**

The ```poPrefix``` property has been added to the [Facilities](Facilities.md) endpoints.

**v. 6.5.9**

The [Usage Items](UsageItems.md) endpoints have been updated to include implant-related properties.

**v. 6.5.7**

Searching and filtering have been enhanced for ```fileSize``` and ```entityTypeValue``` for the [File Attachments](FileAttachments.md#get-the-list-of-files-by-entity-id) endpoint:

 - Search and filter ```fileSize``` using bytes.
 - Search and filter by ```entityTypeValue``` in addition to ```entityTypePK```.

**v. 6.4.7**

You can now partially update a Classification by ID using the [new](Classifications.md#partially-update-the-specified-classification) endpoint.

**v. 6.4.5**

The new ```poglCodeDisplayTemplate``` property has been added to the [Vendor Facilities](VendorFacilities.md) endpoints.

