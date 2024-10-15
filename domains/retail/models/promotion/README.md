# Promotions API

## Overview

The Promotions API is designed for managing and retrieving promotions in an e-commerce context. It provides endpoints for creating, updating, and deleting promotions, as well as retrieving applicable promotions for users and shopping carts. This API is built with international commerce and localization in mind, making it suitable for e-commerce companies worldwide.

## Endpoints

### Promotions

1. **Create a new promotion**
   - Method: POST
   - Path: `/promotions`
   - Description: Creates a new promotion with the provided details.

2. **Update an existing promotion**
   - Method: PUT
   - Path: `/promotions/{promotionId}`
   - Description: Updates an existing promotion with the provided details.

3. **Delete a promotion**
   - Method: DELETE
   - Path: `/promotions/{promotionId}`
   - Description: Deletes a promotion or marks it as inactive.

4. **Get promotions for a user**
   - Method: GET
   - Path: `/promotions/user`
   - Query Parameters:
     - `userId` (required): The ID of the user
     - `lang` (optional): Language code (default: en)
     - `currency` (optional): Currency code (default: USD)
   - Description: Retrieves applicable promotions for a given user.

5. **Get promotions for a cart**
   - Method: GET
   - Path: `/promotions/cart`
   - Query Parameters:
     - `cartId` (required): The ID of the cart
     - `userId` (required): The ID of the user
     - `lang` (optional): Language code (default: en)
     - `currency` (optional): Currency code (default: USD)
   - Description: Retrieves applicable promotions for a given cart and user.

## Request/Response Formats

All request and response bodies are in JSON format.

### Promotion Object

```json
{
  "id": "string",
  "name": {
    "en": "string",
    "ja": "string"
  },
  "description": {
    "en": "string",
    "ja": "string"
  },
  "type": "percentage | fixed_amount | buy_x_get_y",
  "value": 0,
  "startDate": "2023-05-01T00:00:00Z",
  "endDate": "2023-05-31T23:59:59Z",
  "conditions": {
    "minPurchaseAmount": 0,
    "applicableProducts": ["string"],
    "applicableCategories": ["string"],
    "userGroups": ["string"]
  },
  "maxUsageCount": 0,
  "maxUsagePerUser": 0,
  "stackable": false,
  "createdAt": "2023-05-01T12:00:00Z",
  "updatedAt": "2023-05-01T12:00:00Z",
  "isActive": true
}
```

## Error Handling

The API uses standard HTTP status codes for error responses. In case of an error, the response body will contain a JSON object with `code` and `message` fields providing more details about the error.

Example error response:

```json
{
  "code": 400,
  "message": "Invalid input: missing required field 'name'"
}
```

## Localization

The API supports localization for promotion names and descriptions. Provide localized strings in the `name` and `description` fields of the promotion object, using language codes as keys (e.g., "en" for English, "ja" for Japanese).

## Currency

The API supports different currencies. Specify the desired currency using the `currency` query parameter in applicable endpoints.


## Support

For any questions or issues regarding the Promotions API, please contact our support team at support@example.com.
