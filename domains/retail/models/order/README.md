# Order Service API

## Overview

The Order Service API provides a set of endpoints for managing orders and related operations. This API allows you to create, retrieve, update, and delete orders, as well as perform various order-related actions.

## Base URL

The base URL for all API endpoints is: `https://api.example.com/v1`

## Authentication

Authentication details are not specified in the provided OpenAPI specification. Please contact the API provider for information on how to authenticate your requests.

## Endpoints

### 1. List Orders

Retrieves a list of orders.

- **HTTP Method:** GET
- **Endpoint:** `/orders`
- **Query Parameters:**
  - `nextToken` (string): Specifies the beginning of the next page of results.
  - `pageSize` (integer): The maximum number of results to return at once.
  - `customerFilter` (string): Filters orders by customer ID.
  - `keywordFilter` (string): Filter orders by keyword.
  - `timeFilter` (string): Filter orders by time period. Valid values are 'last30', 'last90', or a year value, such as 'year-2022'.
  - `orderStatusFilter` (string): Filters orders by order status.

### 2. Create Order

Creates a new order.

- **HTTP Method:** POST
- **Endpoint:** `/orders`
- **Request Body:** JSON object containing order details (see `CreateOrderRequest` schema)

### 3. Get Order Details

Retrieves details for a specific order.

- **HTTP Method:** GET
- **Endpoint:** `/orders/{orderNumber}`
- **Path Parameters:**
  - `orderNumber` (string): The unique identifier for the order.

### 4. Update Order

Updates an existing order.

- **HTTP Method:** PUT
- **Endpoint:** `/orders/{orderNumber}`
- **Path Parameters:**
  - `orderNumber` (string): The unique identifier for the order.
- **Request Body:** JSON object containing updated order details (see `UpdateOrderRequest` schema)

### 5. Delete Order

Deletes an order.

- **HTTP Method:** DELETE
- **Endpoint:** `/orders/{orderNumber}`
- **Path Parameters:**
  - `orderNumber` (string): The unique identifier for the order.

## Data Models

The API uses various data models to represent order-related information. Some key models include:

- `OrderStatus`: Enum representing the status of an order.
- `PaymentStatus`: Enum representing the status of a payment.
- `FulfillmentStatus`: Enum representing the status of order fulfillment.
- `RefundStatus`: Enum representing the status of a refund.
- `ReturnStatus`: Enum representing the status of a return.
- `OrderSummary`: Object containing a summary of order information.
- `ItemSummary`: Object representing an item in an order.
- `CustomerSummary`: Object containing customer information.
- `FulfillmentSummary`: Object containing fulfillment information.
- `PaymentSummary`: Object containing payment information.
- `BillingSummary`: Object containing billing information.

For detailed information on the structure of these models and their properties, please refer to the full API specification.

## Error Handling

The API uses standard HTTP status codes to indicate the success or failure of requests. Specific error responses are not detailed in the provided specification.
