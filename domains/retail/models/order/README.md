# Order Service API
Order Service API for managing orders and related operations.

## Version: 2024-01-01

### /orders

#### GET
##### Summary:

Retrieves a list of orders.

##### Parameters

| Name | Located in | Description | Required | Schema |
| ---- | ---------- | ----------- | -------- | ---- |
| nextToken | query | Specifies the beginning of the next page of results. | No | string |
| pageSize | query | The maximum number of results to return at once. | No | integer |
| customerFilter | query | Filters orders by customer ID. | No | string |
| keywordFilter | query | Filter orders by keyword. | No | string |
| timeFilter | query | Filter orders by time period. Valid values are 'last30', 'last90', or a year value, such as 'year-2022'. | No | string |
| orderStatusFilter | query | Filters orders by order status. | No | string |

##### Responses

| Code | Description |
| ---- | ----------- |
| 200 | A list of order summaries. |

#### POST
##### Summary:

Creates a new order.

##### Responses

| Code | Description |
| ---- | ----------- |
| 201 | The created order. |

### /orders/{orderNumber}

#### GET
##### Summary:

Retrieves details for a specific order.

##### Parameters

| Name | Located in | Description | Required | Schema |
| ---- | ---------- | ----------- | -------- | ---- |
| orderNumber | path | The unique identifier for the order. | Yes | string |

##### Responses

| Code | Description |
| ---- | ----------- |
| 200 | The retrieved order details. |

#### PUT
##### Summary:

Updates an existing order.

##### Parameters

| Name | Located in | Description | Required | Schema |
| ---- | ---------- | ----------- | -------- | ---- |
| orderNumber | path | The unique identifier for the order. | Yes | string |

##### Responses

| Code | Description |
| ---- | ----------- |
| 200 | The updated order. |

#### DELETE
##### Summary:

Deletes an order.

##### Parameters

| Name | Located in | Description | Required | Schema |
| ---- | ---------- | ----------- | -------- | ---- |
| orderNumber | path | The unique identifier for the order. | Yes | string |

##### Responses

| Code | Description |
| ---- | ----------- |
| 204 | The order was deleted. |
