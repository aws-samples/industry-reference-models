# Pricing Service API
API for managing pricing rules, item prices, and real-time data feeds.

## Version: 2024-01-01

### /pricing-rules

#### GET
##### Summary:

Retrieves a list of pricing rules.

##### Description:

Supports filtering based on start and end timestamps.

##### Parameters

| Name | Located in | Description | Required | Schema |
| ---- | ---------- | ----------- | -------- | ---- |
| limit | query | Maximum number of pricing rules to retrieve. | No | integer |
| endsAtMax | query | Retrieve rules that end before this timestamp. | No | dateTime |
| endsAtMin | query | Retrieve rules that end after this timestamp. | No | dateTime |
| startsAtMax | query | Retrieve rules that start before this timestamp. | No | dateTime |
| startsAtMin | query | Retrieve rules that start after this timestamp. | No | dateTime |

##### Responses

| Code | Description |
| ---- | ----------- |
| 200 | A list of pricing rules. |
| 400 |  |
| 500 |  |

### /pricing-rules/{pricingRuleId}

#### GET
##### Summary:

Retrieves a specific pricing rule by its ID.

##### Parameters

| Name | Located in | Description | Required | Schema |
| ---- | ---------- | ----------- | -------- | ---- |
| pricingRuleId | path |  | Yes | [PricingRuleId](#PricingRuleId) |

##### Responses

| Code | Description |
| ---- | ----------- |
| 200 | A specific pricing rule. |
| 400 |  |
| 404 |  |
| 500 |  |

#### POST
##### Summary:

Creates a new pricing rule.

##### Responses

| Code | Description |
| ---- | ----------- |
| 201 | The created pricing rule. |
| 400 |  |
| 500 |  |

#### PUT
##### Summary:

Updates an existing pricing rule.

##### Parameters

| Name | Located in | Description | Required | Schema |
| ---- | ---------- | ----------- | -------- | ---- |
| pricingRuleId | path |  | Yes | [PricingRuleId](#PricingRuleId) |

##### Responses

| Code | Description |
| ---- | ----------- |
| 200 | The updated pricing rule. |
| 400 |  |
| 404 |  |
| 500 |  |

#### DELETE
##### Summary:

Deletes a pricing rule by its ID.

##### Parameters

| Name | Located in | Description | Required | Schema |
| ---- | ---------- | ----------- | -------- | ---- |
| pricingRuleId | path |  | Yes | [PricingRuleId](#PricingRuleId) |

##### Responses

| Code | Description |
| ---- | ----------- |
| 204 | Pricing rule deleted. |
| 400 |  |
| 404 |  |
| 500 |  |

### /prices/{priceId}

#### GET
##### Summary:

Retrieves price details by ID.

##### Parameters

| Name | Located in | Description | Required | Schema |
| ---- | ---------- | ----------- | -------- | ---- |
| priceId | path |  | Yes | [PriceId](#PriceId) |

##### Responses

| Code | Description |
| ---- | ----------- |
| 200 | Price details for the specified ID. |
| 400 |  |
| 404 |  |
| 500 |  |

#### PUT
##### Summary:

Updates the price details for an item by SKU.

##### Parameters

| Name | Located in | Description | Required | Schema |
| ---- | ---------- | ----------- | -------- | ---- |
| priceId | path |  | Yes | [PriceId](#PriceId) |

##### Responses

| Code | Description |
| ---- | ----------- |
| 200 | The updated price. |
| 400 |  |
| 500 |  |

#### DELETE
##### Summary:

Deletes a price by its ID.

##### Parameters

| Name | Located in | Description | Required | Schema |
| ---- | ---------- | ----------- | -------- | ---- |
| priceId | path |  | Yes | [PriceId](#PriceId) |

##### Responses

| Code | Description |
| ---- | ----------- |
| 204 | Price deleted. |
| 400 |  |
| 404 |  |
| 500 |  |
