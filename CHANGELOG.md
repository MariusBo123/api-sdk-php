# Changelog

All Notable changes to `Kaufland.de API SDK for PHP` will be documented in this file.

## 1.50.0 - 2021-08-18
- Added the following carriers:
  - `Amazon Logistics DE (Swiship)`
  - `GLS Italy`
  - `Jersey Post`
  - `Raben Group`

## 1.49.0 - 2021-08-02
- Added the following carriers:
  - `Cargo International`
  - `Redur Spain`

## 1.48.0 - 2021-06-29

### Added
- Added the following carriers:
  - `Austrian Post`
  - `Geis`
  - `PPL`

## 1.47.0 - 2021-05-17

### Added
Added the field `is_marketplace_deemed_supplier` to the following endpoints:
  - `/orders/seller/`
  - `/orders/{id_order}/`
  - `/order-units/seller/`
  - `/order-units/{id_order_unit}/`

## 1.46.0 - 2021-04-03

### Added
- Added the following carriers:
    - `Czech Post`
    - `DPD Romania`
    - `DSV`
    - `Slovakia Post`
    - `WnDirect`
    
## 1.45.0 - 2021-02-12

### Added
- Added the following carriers:
    - `DHL Ecommerce`
    - `DPD UK`
    - `Hua Han Logistics`
    - `UBI Smart Parcel`
    - `YDH`
    - `PostNL 3S`

## 1.44.0 - 2021-01-29

### Added
- Added the following fields:
  - `order_received_timestamp` to the `/order-units/seller` endpoint 
  - `delivery_attempt_timestamp` to the `/order-units/{id_order_unit}`
  
## 1.43.0 - 2021-01-27

### Added
- Allow the request to follow redirects

## 1.42.0 - 2020-12-21

### Fixed
- variable usage in Client.php

### Added
- assertions to the ClientTest.php

## 1.41.0 - 2020-10-27

### Fixed
- Fixed EAN parameter with leading zeros to be accepted in the following endpoints
    - PUT `product-data/%s/`
    - PATCH `product-data/%s/`
    - GET `product-data/%s/`
    - DELETE `product-data/%s/`
    - GET `product-data-status/%s/`

## 1.40.0 - 2020-07-06

### Added
- Added the following carriers:
    - `CNE Express`
    - `PostNL`
    - `Winit`

## 1.39.0 -2020-06-30

### Added
- new method `findByIdOffer` to find units by id offer

## 1.38.0 - 2020-05-27

### Added
- new fields `dangerous_goods_li_shipping` and `danger_label_9A` in `items`-endpoint

## 1.37.0 - 2020-04-30

### Added
- new endpoint to create new `AccountListing` report

### Fixed
- compatability with >=PHP 5.4


## 1.36.0 - 2020-03-12

### Added
- Added the following carriers:
    - `4PX`
    - `China Post`
    - `Chukou1 Logistics`
    - `DHL Hong Kong`
    - `Flyt Express`
    - `Hong Kong Post`
    - `SFC Service`
    - `Wanb Express`
    - `Yanwen`
    - `Yun Express`

## 1.35.1 - 2020-02-13

### Fixed
- Property `shipment_information` of `OrderUnitShipmentTransfer` should not be empty

## 1.35.0 - 2019-11-11

### Added
- Property `additional_attributes` to `ProductDataTransfer` transfer


## 1.34.1 2019-09-26

### Fixed

- Adjust `hm-collection-range` header in `GET /orders/seller/

## 1.34.0 - 2019-09-26

### Added

- Added the following endpoints:
    - UPSERT `/returns/{id_return}/`    

## 1.33.4 - 2019-09-10

### Added

- Changed `defaultListLimit` from 20 to 30 for `GET /units/seller/` as described in
  	    documentation.
  	    
## 1.33.3 - 2019-09-10

### Added

- Increased `maximim` value from 1000 to 65535 for `claim_message_text` to enable writing longer
  	    messages.

## 1.33.2 - 2019-09-05

### Added

- Added `minimum value` and `maximum value` to every identifier in query.

## 1.33.1 - 2019-08-26

### Added

- Added `delivery_time_min` and `delivery_time_max` fields to order-units entity.

## 1.33.0 - 2019-08-26

### Added

- New Query Parameter `ts_units_updated:from` added to the `orders/seller/` endpoint.

## 1.32.0 - 2019-08-19

### Added

- Added the following endpoints:
    - GET `/order-invoices/seller`
    - GET `/order-invoices/{id_order_invoice}/`
    - POST `/order-invoices/`
    - DELETE `/order-invoices/{id_order_invoice}/`
- Added embedded Field `order_invoices` to `/orders/{id_order}` endpoint

    
## 1.31.1 - 2019-08-15

### Changed

- Allow adding shipment information (tracking numbers) for already marked as send order units via `POST /shipments/`.

## 1.30.1 - 2019-07-19

### Changed

- The endpoint `/returns/` now responds with a location header containing `/returns/{id_return}/`.


## 1.30.0 - 2019-05-28

### Added

- Added `delivery_time_min` and `delivery_time_max` fields to units endpoint.


## 1.29.0 - 2019-05-23

### Changed

- Modified `/tickets/seller/` and `/tickets/{id_ticket}/` Endpoints to now deliver a more differentiated set of claim reasons, named claim topics.


## 1.28.0 - 2019-05-17

### Added

- Open a new claim via `POST /tickets/`
- Attach Base 64 encoded files to Ticket messages via `POST /ticket-messages/`

## 1.26.1 - 2018-11-21

### Changed

- SDK forces HTTP/1.1 connection to be back compatible with older versions of curl

## 1.26.0 - 2018-09-17

### Added

- A new endpoint `/returns/` with a possibility to [initialize returns manually](https://www.kaufland.de/api/v1/?page=returns#returning-order-units).

## 1.25.0 - 2018-09-03

### Added

- Report on not found EANs
- Report on product data changes

## 1.24.0 - 2018-08-15

### Fixed

- Changed a pattern for `/product-data/{ean}/` endpoint, [PR #46](https://github.com/hitmeister/api-sdk-php/pull/46/)

### Added

- New fields `age_rating` and `is_valid` in `Item`
- New field `vat` in `OrderUnit`

## 1.23.0 - 2018-07-12

### Added

- New endpoints for reports `/reports/bookings-new/` and `/reports/sales-new/`

## 1.22.0 - 2018-04-28

### Updated

- New format for field `uri` when requesting ticket files via `/tickets/getTicket{id_ticket}`. Now the
  absolute uri for the given file is returned alongside with a key, so file downloading is possible without being
  logged in.

## 1.21.0 - 2018-04-23

### Added

- `/return-units/{id_return_unit}/clarify` endpoint
- `/return-units/{id_return_unit}/repair` endpoint
- `/order_units/{id_order_unit}/fulfil` endpoint


## 1.19.2 - 2018-04-20

### Added

- Tests are executed using PHP 7.2 as well
- More precise annotations to the thrown exceptions


## 1.19.1 - 2018-03-13

### Added

- New return-unit endpoint `repair`, which will set the returnUnit-status to `return_in_repair`

## 1.19.0 - 2018-03-12

### Added

- New return status `return_in_repair`
- New events for subscriptions (`return_new`, `return_status_changed`, `return_unit_status_changed`)
- New cancellation reasons (`DelayedInventory`, `NoReactionBuyer`)

### Deprecated

- Requests sent to `www.hitmeister.de` will stop working on March 26th

### Changed

- Switch the default hostname from `www.hitmeister.de` to `www.real.de`

## 1.17.3 - 2018-02-05

### Fixed

- Method `ItemsNamespace::findByEan()` returns either `ItemWithEmbeddedTransfer` or `null` instead of `ItemWithEmbeddedTransfer[]`

## 1.17.2 - 2017-11-15

### Fixed

- Use correct separator to generate signatures under Windows

## 1.17.1 - 2017-10-27

### Fixed

- Possibility to used embedded transfers for `GET order-units/{id}` endpoint

## 1.17.0 - 2017-10-26

### Added

- Embedded field `product_feed_async_done` to the `ImportFileTransfer`

## 1.16.0 - 2017-10-26

### Added

- Embedded field `return_unit` to the `OrderUnitWithEmbeddedTransfer`

## 1.15.0 - 2017-10-12

### Removed

- endpoint `/claims`
- endpoint `/claims/{id_claim}/refund`

## 1.13.4 - 2017-08-03

### Added

- Field `real_main_category_id` to `CategoryTransfer`
- Field `real_mgb_article_number` to `ItemTransfer`

### Fixed

- Typo in carrier name `Bursped`

## 1.11.0 - 2017-04-03

### Added

- New field `cancel_reason`

## 1.7.0 - 2016-07-06

### Added
- New endpoints `product-data`
- New endpoint `product-data-status`
- New endpoint `shipping-groups`
- New endpoint `warehouses`
- Support of `PUT` methods

### Fixed
- Missing constants have been added

### Deprecated
- Field `location` in `POST /units/` endpoint will be overwritten by `warehouse.country`



## 1.6.1 - 2016-07-01

### Fixed
- Fix client version number

## 1.6.0 - 2016-07-01

### Added
- Change a major and a minor versions in order to match version of API itself

## 0.1.3 - 2016-04-05

### Added
- Property `is_seller_responsible` to `ClaimTransfer` and `ClaimWithEmbeddedTransfer`
- Property `interim_notice` to `ClaimMessageAddTransfer`

## 0.1.2 - 2016-03-15

### Added
- Property `shipping_group` and `warehouse` to all transfer objects used in `/units/` endpoint

## 0.1.1 - 2016-01-26

### Fixed
- Embedded fields may have `null` value
