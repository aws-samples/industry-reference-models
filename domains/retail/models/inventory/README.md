# Inventory Service API
The Inventory Service provides operations to manage inventories, items, product variants, and locations.

## Version: 2024-07-17

### /inventories

#### POST
##### Summary:

Creates a new inventory record.

##### Responses

| Code | Description |
| ---- | ----------- |
| 201 | The created inventory. |

#### GET
##### Summary:

Retrieves a paginated list of inventory records.

##### Parameters

| Name | Located in | Description | Required | Schema |
| ---- | ---------- | ----------- | -------- | ---- |
| nextToken | query |  | No | string |
| pageSize | query |  | No | integer |

##### Responses

| Code | Description |
| ---- | ----------- |
| 200 | A list of inventory summaries. |

### /inventories/{inventoryId}

#### GET
##### Summary:

Retrieves a specific inventory record by its ID.

##### Parameters

| Name | Located in | Description | Required | Schema |
| ---- | ---------- | ----------- | -------- | ---- |
| inventoryId | path |  | Yes | string |

##### Responses

| Code | Description |
| ---- | ----------- |
| 200 | The inventory details. |

#### PATCH
##### Summary:

Updates an existing inventory record.

##### Parameters

| Name | Located in | Description | Required | Schema |
| ---- | ---------- | ----------- | -------- | ---- |
| inventoryId | path |  | Yes | string |

##### Responses

| Code | Description |
| ---- | ----------- |
| 200 | The updated inventory. |

#### DELETE
##### Summary:

Deletes a specific inventory record by its ID.

##### Parameters

| Name | Located in | Description | Required | Schema |
| ---- | ---------- | ----------- | -------- | ---- |
| inventoryId | path |  | Yes | string |

##### Responses

| Code | Description |
| ---- | ----------- |
| 204 | The inventory record was deleted. |

### /items

#### POST
##### Summary:

Creates a new item.

##### Responses

| Code | Description |
| ---- | ----------- |
| 201 | The created item. |

#### GET
##### Summary:

Retrieves a paginated list of items.

##### Parameters

| Name | Located in | Description | Required | Schema |
| ---- | ---------- | ----------- | -------- | ---- |
| nextToken | query |  | No | string |
| pageSize | query |  | No | integer |

##### Responses

| Code | Description |
| ---- | ----------- |
| 200 | A list of item summaries. |

### /items/{itemId}

#### GET
##### Summary:

Retrieves a specific item by its ID.

##### Parameters

| Name | Located in | Description | Required | Schema |
| ---- | ---------- | ----------- | -------- | ---- |
| itemId | path |  | Yes | string |

##### Responses

| Code | Description |
| ---- | ----------- |
| 200 | The item details. |

#### PATCH
##### Summary:

Updates an existing item.

##### Parameters

| Name | Located in | Description | Required | Schema |
| ---- | ---------- | ----------- | -------- | ---- |
| itemId | path |  | Yes | string |

##### Responses

| Code | Description |
| ---- | ----------- |
| 200 | The updated item. |

#### DELETE
##### Summary:

Deletes a specific item by its ID.

##### Parameters

| Name | Located in | Description | Required | Schema |
| ---- | ---------- | ----------- | -------- | ---- |
| itemId | path |  | Yes | string |

##### Responses

| Code | Description |
| ---- | ----------- |
| 204 | The item was deleted. |
