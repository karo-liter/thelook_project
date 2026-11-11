# TheLook eCommerce Dataset

## Overview

**TheLook** is a fictitious eCommerce clothing site developed by the Looker team. The dataset contains comprehensive information about customers, products, orders, logistics, web events, and digital marketing campaigns.

* **Data Source:** [BigQuery Public Dataset](https://console.cloud.google.com/bigquery?p=bigquery-public-data&d=thelook_ecommerce&page=dataset&project=%3F&ws=!1m5!1m4!3m2!1sbigquery-public-data!2sthelook_ecommerce!23sWS_URL_PARAM)

---

## Tables Summary

### 1. `distribution_centers`
Contains geographical location details for each fulfillment center.

* **`id`**: Unique identifier for each distribution center.
* **`name`**: Name of the distribution center.
* **`latitude`**: Latitude coordinate of the distribution center.
* **`longitude`**: Longitude coordinate of the distribution center.

---

### 2. `events`
Tracks raw web traffic and interaction events across sessions.

* **`id`**: Unique identifier for each event.
* **`user_id`**: Identifier for the user associated with the event (can be null for anonymous sessions).
* **`sequence_number`**: Order sequence of the event within the session.
* **`session_id`**: Identifier for the browsing session.
* **`created_at`**: Timestamp indicating when the event took place.
* **`ip_address`**: IP address from which the event originated.
* **`city`**: City location of the event.
* **`state`**: State location of the event.
* **`postal_code`**: Postal code of the event location.
* **`browser`**: Web browser used during the event.
* **`traffic_source`**: Marketing or acquisition channel leading to the event.
* **`uri`**: Uniform Resource Identifier (page URL) visited.
* **`event_type`**: Type of event recorded (e.g., product, cart, purchase).

---

### 3. `inventory_items`
Tracks physical inventory stock and unit-level sale lifecycle.

* **`id`**: Unique identifier for each inventory item.
* **`product_id`**: Identifier for the associated catalog product.
* **`created_at`**: Timestamp indicating when the inventory item was stocked.
* **`sold_at`**: Timestamp indicating when the item was sold (null if unsold).
* **`cost`**: Unit cost of the inventory item.
* **`product_category`**: Category of the associated product.
* **`product_name`**: Name of the associated product.
* **`product_brand`**: Brand of the associated product.
* **`product_retail_price`**: Retail price of the associated product.
* **`product_department`**: Department (e.g., Men, Women) of the product.
* **`product_sku`**: Stock Keeping Unit (SKU) identifier.
* **`product_distribution_center_id`**: Identifier for the originating distribution center.

---

### 4. `order_items`
Line-item detail for individual products purchased within an order.

* **`id`**: Unique identifier for each order line item.
* **`order_id`**: Identifier for the parent order.
* **`user_id`**: Identifier for the user who placed the order.
* **`product_id`**: Identifier for the purchased product.
* **`inventory_item_id`**: Identifier for the matched inventory unit.
* **`status`**: Current fulfillment status of the line item.
* **`created_at`**: Timestamp indicating when the order item was created.
* **`shipped_at`**: Timestamp indicating when the order item was shipped.
* **`delivered_at`**: Timestamp indicating when the order item was delivered.
* **`returned_at`**: Timestamp indicating when the order item was returned.

---

### 5. `orders`
High-level order header details.

* **`order_id`**: Unique identifier for each order.
* **`user_id`**: Identifier for the purchasing customer.
* **`status`**: Overall status of the order (e.g., Complete, Cancelled, Shipped).
* **`gender`**: Gender attribute associated with the customer profile.
* **`created_at`**: Timestamp indicating when the order was placed.
* **`returned_at`**: Timestamp of order return, if applicable.
* **`shipped_at`**: Timestamp of order shipment, if applicable.
* **`delivered_at`**: Timestamp of order delivery, if applicable.
* **`num_of_item`**: Total number of items in the order.

---

### 6. `products`
Master catalog of available merchandise.

* **`id`**: Unique identifier for each product.
* **`cost`**: Production/acquisition cost of the product.
* **`category`**: Merchandise category.
* **`name`**: Product name.
* **`brand`**: Product brand.
* **`retail_price`**: Listed retail price.
* **`department`**: Target demographic/department (e.g., Men, Women).
* **`sku`**: Stock Keeping Unit code.
* **`distribution_center_id`**: Default distribution center for the product.

---

### 7. `users`
Customer profile information and demographic data.

* **`id`**: Unique identifier for each user.
* **`first_name`**: First name of the user.
* **`last_name`**: Last name of the user.
* **`email`**: Email address of the user.
* **`age`**: Age of the user.
* **`gender`**: Gender identity of the user.
* **`state`**: State of residence.
* **`street_address`**: Street address of the user.
* **`postal_code`**: Postal code.
* **`city`**: City of residence.
* **`country`**: Country of residence.
* **`latitude`**: Latitude coordinate of the user address.
* **`longitude`**: Longitude coordinate of the user address.
* **`traffic_source`**: Channel through which the user was acquired.
* **`created_at`**: Timestamp of customer account creation.