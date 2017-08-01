---
layout: default
group: release-notes
subgroup: 2.2.0 Release Candidate
title: Magento CE 2.2 Release Candidate Release Notes
menu_title: Magento CE 2.2 Release Candidate Release Notes
menu_order: 500
level3_menu_node:
level3_subgroup:
github_link: release-notes/release-notes-2-2-prerelease1-CE.md
---

*	TOC
{:toc}

*Release date: July 28, 2017*

*Notes updated: July 28, 2017*


Magento Community Edition 2.2.0 Release Candidate includes significant new features as well as many bug fixes.

Looking for information about how the Magento 2.2.0 Release Candidate evaluation program works? Check out the [Magento 2.2.0 Release Candidate QuickStart Guide]({{page.baseurl}}release-notes/release-candidate/quick-start.html) for more information.  This guide provides a handy overview of [Component Status]({{page.baseurl}}release-notes/release-candidate/component-status.html), too.

## Highlights

Look for the following highlights in this release:


* **Significant enhancements in platform security and developer experience**. Security improvements include the removal of specific un-serialize calls and changes to hashing algorithm to improve security for sensitive values. Developers will appreciate  improvements in debugging, customizations, and logging.



* **Upgraded technology stack.**  We've dropped support for PHP 5.6 and Varnish 3.  We now support PHP 7.1, along with Redis 3.2, MySQL 5.7, and Varnish 5 support. All third-party libraries have been upgraded to the latest stable version.


* **Pipeline deployment**, a new deployment process, enables separate build and deployment stages that can run separately. Resource-intensive processes can run on the build server. Pipeline deployment supports easy management of configuration between environments, too. Read more about pipleine deployment [here]({{page.baseurl}}config-guide/deployment/pipeline/).


* **Substantial performance gains from improvements in indexing, cart, and cache operations**. Customers can browse and shop on a storefront while indexers are running. (Long-running indexers operate in batches to better manage memory and run times.) Cart improvements enable a
buyer to create a cart with more than 300 line items, and merchants can process a cart with at least 300 line items.


## Issues fixed in this Release Candidate
The following fixed and open issues have been logged against the Magento 2.2.0 RC1.x release.


### Installation and Configuration 

<!--- 69675 -->* We’ve fixed problems with the upgrade process from 2.1.7 EE to 2.2.0 EE. (RC1.6)


<!--- 69854 -->* You can now successfully use the `config:set` command to set allowed or default currencies. 


<!--- 67299, 67315 -->* The `catalog_url_rewrite_product_category` table is the same whether you’ve freshly installed or updated Magento 2.2. 


<!--- 70314 -->* The `cron:install` command now works as expected in Magento 2.2.0 RC1.x. Previously, the configuration for `crontab` commands contained double quotes that were not escaped, which caused invalid commands to be written to the `crontab` file. [GitHub-10040](https://github.com/magento/magento2/issues/10040)


<!--- 70318 -->* You can now generate static content without a database connection. [GitHub-10041](https://github.com/magento/magento2/issues/10041) (RC1.5) 

<!--- 67020 -->* Magento now handles the `catalog_product_entity_media_gallery_value.position`  value the same whether you’ve installed or upgraded the product. Previously, these values differed depending upon whether you upgraded or freshly installed your Magento code. (RC1.5)







### Catalog

<!--- 70066 -->* We’ve improved the performance of the CatalogPermissions indexer in installations that contain many customer groups.

<!--- 66480 -->* You can now successfully create a product  and assign it to a store without encountering the following error: `Unique constraint violation found`. [GitHub-6671](https://github.com/magento/magento2/issues/6671)

<!--- 62637 -->* You can now successfully set the **Enable Product** attribute to **no**. 

<!--- 70790 -->* You can now remove custom options from simple products. Previously, when you tried to remove a custom option from a product, Magento did not remove the options, and displayed an error message. (RC1.6) 

### Checkout

<!--- 70618 -->* Errors in shipping rates no longer occur when a customer changes the country during guest checkout and DHL is enabled. Previously,  a customer changing country during guest checkout resulted in inaccurate shipping rates. (RC1.6)



<!--- 70646 -->* You can now save the settings you enter when creating a shipping label on an existing shipment.  Previously, clicking the Save button resulted in an error, and the shipping label was not saved. (RC1.5)



### Import/export

<!--- 67240 -->* Magento now displays more verbose information about duplicated information with links to action for troubleshooting the import process.  Previously, Magento displayed duplicated or incomplete information on the product page after import. (RC1.5)

<!--- 65667 -->* Magento now successfully imports customer multiselect attributes. Previously, when you imported a CSV file with either the option's ID numbers or the option's values, Magento returned an error. (RC1.5)







### Magento Business Intelligence

<!--- 69615 -->* Requests for data transfer from Magento to MBI data now complete successfully. 




### Miscellaneous

<!--- 69657 -->* Credit card information now persists as expected after a user enters a promotion code during checkout. Previously, After an user enters credit card information, then discount code and then press "Place Order". The credit card information fields are emptied and user has to enter the credit card information again to proceed with  the order transaction.

<!--- 56062 -->* The Recently Viewed Products block now appears as expected when the full page cache is enabled. [GitHub-3890](https://github.com/magento/magento2/issues/3890)

<!--- 59514 -->* The `tax_region_id` value is no longer hard-coded in the `\Magento\Tax\Setup\InstallData` file. 

<!--- 69964 -->* PHPCS can now correctly parse the syntax of PHP 7.x return types. 

<!--- 67619 -->* The Customer Segment page no longer shows non-matching customers when a customer logs in and you refresh the Customer Segment page. 

<!--- 59801 -->* We’ve improved the performance of the Tax Rules form in installations containing many tax rates. 

<!--- 69750 -->* Magento now successfully completes checkout when a custom address attribute is added. Previously, an error occurred during checkout when the user added a required custom address attribute. 


<!--- 57753 -->* You can now successfully create product attributes using the REST API. Previously, although the product was created, the attribute was not. [GitHub-6213](https://github.com/magento/magento2/issues/6213) (RC1.5)


<!--- 70406 -->* We’ve improved the performance of the CatalogPermission indexer. Previously, Magento performance degraded significantly during the indexing of large numbers of customer groups.(RC1.5)

<!--- 69521 -->* Magento now shows customer attributes in the Admin panel (as expected)  when the **Show on Storefront** option is set to **No**. Previously, when this setting was set to **No**, the attribute value would not appear in the customer account  section of the Admin panel customer account, but did appear in the orders section. (RC1.5)


<!--- 67048 -->* You can now add a `translate` attribute to any String argument in the `di.xml` file for any class. This attribute provides an ability on the level of dependency injection configuration to specify that an argument can be translated. The actual translation of strings is handled by another Magento component. (RC1.6)



<!--- 70642 -->* You can upload a new logo (or change other display features) when editing a transactional email. Previously, Magento crashed after you tried to save changes you may have made to this feature. (RC1.6)


<!--- 70628 -->* The Forgot Your Password? email now includes an active link to reset your password. (RC1.6)

<!--- 62405 -->* Magento no longer discounts items that belong to an excluded category. Previously, you were unable to exclude products assigned to a specific category due to the cart price rule. (RC1.6)


<!--- 64901 -->* Magento now supports new top level domains for email addresses. [GitHub-4547](https://github.com/magento/magento2/issues/4547) (RC1.6)




<!--- 67296 -->* String localizations now works as expected when  phrases include text wrapped with single quotation marks. (RC1.6)






### Search


<!--- 63249 -->* ElasticSearch now includes data about composite products in its search index. Previously, search results did not include data about composite products. 

<!--- 59477 -->* Attribute weighting now works correctly for the MySQL adapter. [GitHub-9020](https://github.com/magento/magento2/issues/9020) (RC1.5)

<!--- 65245 -->* Magento now sends the `parent_id` of a deleted configurable product variation to ElasticSearch. Previously, Magento didn’t send this information  to the ElasticSearch server  if  the simple product associated with a configurable product were changed. (RC1.5)


### URL rewrites

<!--- 70663 -->* You can now assign products to a category when  **Match Products by rule** is enabled. (RC1.6)


<!--- 70651 -->* URL rewrites now occur as expected when category or products are saved. Previously, URLs rewrites did not occur for all categories. (RC1.6)



## System requirements

Our technology stack is built on PHP and MySQL. For more information, see [System Requirements]({{ page.baseurl }}install-gde/system-requirements-tech.html).

## Installation

Installation instructions for all versions of this Release Candidate are documented [here]({{ page.baseurl }}release-notes/release-candidate/install.html).


## Credits
Dear community members, thank you for your suggestions and bug reports.