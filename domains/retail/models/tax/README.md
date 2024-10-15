# Tax Calculation API

## Overview

The Tax Calculation API is a RESTful service designed to provide accurate tax calculations for e-commerce transactions across multiple countries. This API is particularly useful for businesses operating in Japan and other international markets, offering a streamlined solution for tax computation during the checkout process of online shopping sessions.

## Features

- Real-time tax calculation for shopping carts
- Support for multiple tax types (VAT, GST, Sales Tax, Consumption Tax)
- International address support
- Currency flexibility
- Product categorization for different tax treatments
- Detailed tax breakdown in responses
- Tax rate lookup by location

## Endpoints

### 1. Calculate Tax

Calculate tax for a given shopping cart.

- **URL**: `/calculate-tax`
- **Method**: POST
- **Request Body**: JSON object containing cart items, shipping address, billing address, and other relevant information.
- **Response**: Detailed tax calculation including total tax and breakdown by tax type.

### 2. Get Tax Rates

Retrieve applicable tax rates for a specific location.

- **URL**: `/tax-rates`
- **Method**: GET
- **Query Parameters**: 
  - `country` (required)
  - `state`
  - `city`
  - `postalCode`
- **Response**: List of applicable tax rates for the specified location.

## Request/Response Examples

### Calculate Tax

**Request:**

```json
POST /calculate-tax
{
  "items": [
    {
      "productId": "PROD123",
      "quantity": 2,
      "unitPrice": 100.00,
      "productType": "physical"
    }
  ],
  "shippingAddress": {
    "country": "JP",
    "postalCode": "100-0005",
    "city": "Tokyo"
  },
  "billingAddress": {
    "country": "JP",
    "postalCode": "100-0005",
    "city": "Tokyo"
  },
  "currencyCode": "JPY"
}
```

**Response:**

```json
{
  "totalTax": 20.00,
  "taxBreakdown": [
    {
      "taxType": "ConsumptionTax",
      "taxRate": 0.10,
      "taxableAmount": 200.00,
      "taxAmount": 20.00
    }
  ],
  "currencyCode": "JPY"
}
```

### Get Tax Rates

**Request:**

```
GET /tax-rates?country=JP&postalCode=100-0005
```

**Response:**

```json
{
  "country": "JP",
  "postalCode": "100-0005",
  "taxRates": [
    {
      "taxType": "ConsumptionTax",
      "rate": 0.10,
      "name": "Japan Consumption Tax",
      "description": "Standard rate for most goods and services in Japan"
    }
  ]
}
```

## Error Handling

The API uses standard HTTP response codes to indicate the success or failure of requests. Detailed error messages are provided in the response body for failed requests.
