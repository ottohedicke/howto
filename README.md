![OTTO.market Logo](https://github.com/ottohedicke/howto/blob/main/img/otto_market_logo_white_bg.PNG)

*Read this document in other languages: [deutsch](https://github.com/Uncrout/TestFuerOttoDL_Leitfaden/blob/main/README.md), [english](https://github.com/Uncrout/TestFuerOttoDL_Leitfaden/blob/main/EN/README_EN.md)*

# Service Provider Integration guide

**Präambel
- Was kann in diesem Repo gefunden werden?
- Hinweis auf Testfälle und Postman Collection**

### Contact
Partner Connector Management: partnerintegration@otto.market

## Table of content
### 1. Things to know
* Introduction
* Process
* Contact
* Environments
### 2. Integration
* Must-Haves
* Test phase
* Pilot phase
* ~~Project conclusion~~
### 3. Operation
* Marketing und Sales
* ~~Development~~

# 1. Things to know
## Introduction

Afteryouhave learned  more  about  the Partner  Connector  Management  (PCM), we  can start withthe technical  connection. In this document  you will  find all  the information about the integrationprocess. The PCM is the partner at your side and supports you in developing a stable and scalable interface so that the first partner can  already  count  on  a  reliable  service.  In  this  way,  we  create  the  basis  for  a sustainable exploitation of potential on both sides. 

This document is the central source of information for your integrationto OTTO. In order to ultimately create a valid interface, it is essential to read this document and to always consult the information as an aid. 

In addition to an overview of the entire integrationprocess and information about contact  persons  and  the  system  landscape,  the  document  contains  detailed information about the individual process steps. Finally, you will find information on marketing and the development process.  

Before  you  start  working  through  the  document,  you  will  find  explanations  of OTTO language usage here:

**Partner**: Merchants selling on otto.de

**PCM**: Partner Connector Management

We  look  forward  to  working  with  you  as  partners  and  are  happy  to  answer  any questions  you  may  have.  If  you  have  any  suggestions  or  feedback,  please do  not hesitate to contact us. 

## Process

![Prozesschart Anbindung OTTO.market](https://github.com/Uncrout/TestFuerOttoDL_Leitfaden/blob/main/img/Prozesschart_eng.PNG)

This process chart gives you a general overview of the mandatory process of the integration. The shown process ensures a smooth connection, so it should be followed exactly.

At the start of the project, it is important to get to know the behavior of the interfaces and to start with the development. For this purpose, you will receive test cases from us as part of the kickoff package, which you will process in the test environments provided by us. You have received the access to the test environments from us together with this document. During the development you have time to develop your software independently and to test it internally. After completion of the internal tests you have to run through the test cases once and submit your results to us. 

If these are successfully accepted, we will work together in the pilot phase to find a suitable pilot partner and you can start setting up and sending data for the pilot partner to the OTTO Market. After a period of being live, the PCM will have a deeper look into the data of the pilot partner and give feedback. After the last points are discussed and the partner is running smoothly, the project can be completed successfully. 

## Contact

During and after the integration, the Partner Connector Management (PCM) is available to you. The PCM is the central point of contact for all service providers who want to connect to OTTO. 

```
You can always reach out to our Partner Connector Management at:  partnerintegration@otto.market
```

Please refer potential partners to the official website [OTTO.market](https://www.otto.market/).
  
## Environments

During the integration process, you will first work in the test environment before switching to the live environment during operation. You can access the environments, which differ in terms of their scope of services, via the PCM. 

```
Please note that the credentials are different for all environments.
Nonlive data does not work in the live environment.
```

Please include the following key and value in the request header of the API requests for all data transmissions to OTTO:

```
Key: user-agent
Value: <your company name>
```

This will help us bundle your data submissions and assist you with any potential issues.

To avoid misunderstandings, we would like to ask you to familiarize yourself with the individual environments. For more details please use the following links.

**Sandbox**

For your technical integration we are providing a Sandbox for test purposes. There you can test the OTTO Market API Endpoints and generate test orders. All further information you can find here: [API Dokumentation](https://public-docs.nonlive.api.otto.market/02_Sandbox/index.html).

At the moment the sandbox does not have all interfaces ready which are available in the live environment. Due to the lack of the interfaces products and quantites in the sandbox, we are offering you an API-User for our Nonlive environment as well.

**Nonlive**

The Products and Quantities interfaces can be tested in the Nonlive environment. The PCM will send you the user separately.

**Live**

The live environment will be used for the first time during the pilot phase.
You as a service provider do not get your own access and have to fall back on the accesses of a first active partner. With this so-called pilot partner, you test in the live environment for the first time. The partners get the access within their onboarding.

```
The log in data for the sandbox does not work in the live environment.

The user for the Sandbox- and the nonlive-environment are only for the OTTO Market API.
You will not receive a user for the partner portal.
```

# Integration

In this section, you will find a detailed overview of the integration steps. First, in the must-haves chapter, we show you an insight into the categorization of endpoints in terms of their necessity. This is followed by a more detailed look at the test and pilot phase. In the Project Completion chapter, we will show you the shift to operation.

## Must-Haves

Below you will find an overview with all our endpoints and a categorization by musts, shoulds and coulds. In addition, you will find further important special features for individual endpoints. Please note that the categorization is of course only valid for your respective scope of services. If, for example, you only want to cover the order processing process in your service, then only the musts from Orders, Shipments and Returns apply. We will be happy to advise you and answer any further questions you may have about individual musts, shoulds and coulds.

**Must´s**: Endpoints that are mandatory order to use the respective interface  
**Should´s**: Endpoints that are recommended but not mandatory 
**Could´s**: Optional endpoints

### Products
|**Version**|**Interface**|**Endpoint**|**Request**|**Must / Should / Could**|
|-|-|-|-|-|
|/v1|/products|/|GET|Could|
|||/{sku}|GET|Could|
|||/|POST|Must|
|||/brands|GET|Must|
|||/categories|GET|Must|
|||/marketplace-status|GET|Must|
|||{sku}/marketplace-status|GET|Should|
|||/active-status|GET|Should|
|||{sku}/active-status|GET|Could|
|||/active-status|POST|Must|

```
In order to always have the latest brands and categories it is important to download the lists
/v1/ products/ brands (GET) and /v1/ products/ categories (GET)
several times a week.
```

```
To form different variants, it is important that via
/v1/ products/ (POST)
all related SKUs are sent with the same productName.
This controls the merging of the SKUs into one product.
```

```
Please note that the processing of the product data (POST /v1/products) is asynchronous 
and you will receive further links (self, succeeded, failed, unchanged) in the response to retrieve the errors. 
```

### Quantities
|**Version**|**Interface**|**Endpoint**|**Request**|**Must / Should / Could**|
|-|-|-|-|-|
|/v2|/quantities|/|POST|Must|


### Orders
|**Version**|**Interface**|**Endpoint**|**Request**|**Must / Should / Could**|
|-|-|-|-|-|
|/v3|/|/|GET|Must|
|||/{salesOrderId}|GET|Could|
|||/{salesOrderId}/cancellation|POST|Must|

### Shipments
|**Version**|**Interface**|**Endpoint**|**Request**|**Must / Should / Could**|
|-|-|-|-|-|
|/v1|/shipments|/|GET|Could|
|||/|POST|Must|
|||/{shipmentId}|POST|Should|
|||/carries/{carrier}/trackingnumbers/{trackingnumber}|GET|Must|
|||/carries/{carrier}/trackingnumbers/{trackingnumber}/positionitems|GET|Should|

```
For /v1/shipments/ (POST) a return tracking key must always be transmitted if it is a parcel shipment.
This is optional for forwarding shipments. The validation is based on the deliveryType when creating the product.
```

### Returns
|**Version**|**Interface**|**Endpoint**|**Request**|**Must / Should / Could**|
|-|-|-|-|-|
|/v2|/returns|/|GET|Should|
|||/acceptance|POST|Must|
|||/rejection|POST|Must|

### Receipts
|**Version**|**Interface**|**Endpoint**|**Request**|**Must / Should / Could**|
|-|-|-|-|-|
|/v2|/receipts|/|GET|Should|
|||/{receiptNumber}|GET|Could|
|||/{receiptNumber}.pdf|GET|Could|

## Test phase

As soon as you have finished implementing the interfaces, you can start testing the best practice test cases.

We want to give you a better understanding which are important processes on our side and with the results of the test cases, we want to get first insights into your systems. With the screenshots we can enable our support to help our partners in a better way. 

The test cases can be found in the corresponding document, which you received from us with this guide. As soon as all test cases have been accepted by us, you can continue with the pilot phase.  

## Pilot phase

After successful completion of the test phase, a pilot partner will be selected and will operate in the live environment for the first time. If no pilot partner is available, please contact the PCM, which will support you in your search.

Once a pilot partner has been determined, it must be specified at the PCM. The role of the PCM in the pilot phase is to support you as a service provider and an approval of a scalable and stable interface. The support of the partner in the regular process will be provided by our partner support and the partner helpdesk. 

All partners who start importing products initially have a display restriction. This means that products are not directly visible to the end customer on otto.de. Only after the display restriction has been removed, customers can find the products. This enables the partner to test and adjust products and processes under live conditions. Before OTTO makes the products visible to end customers on otto.de, the partner must independently confirm the removal of the display restriction. A partner can do this independently in the Partner Portal. On the start page and the interface and the product creation interface, a yellow banner is provided for this purpose. There the partner must agree to the following: 

1. The procedure for a test order
2. 2.	The understanding of the order process (Shipment Request)

PCM checks two weeks after going live to see if there are any anomalies or problems along the interface.

During the pilot integration, particular attention is paid to the following criteria:

*	Is the variant formation of the products correct? 
*	Error messages - are they apparent and understood?
*	Can the orders be fetched correctly? 
*	Do the shipping requests work - Is the returnTrackingkey also included correctly?
*	Are there any noticeable http errors in the API requests? Error rate per interface
*	Is the user agent also being send by every Request?

After the PCM checked all these points and give the go, you can now start to connect additional partners.

# Operations
## Marketing und Sales

After completion of the integration and the pilot phase is done, you have the opportunity show you as a service provider on our homepage otto.market. All we need from you is a logo and a landing page. For any marketing actions on your part, we ask for constant coordination with us.
