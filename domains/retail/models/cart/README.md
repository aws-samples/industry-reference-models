# Cart Service API
Cart Service API for managing shopping carts and cart items.

## Version: 2024-01-01

### /carts

#### POST
##### Summary:

Creates a new cart with an optional list of items.

##### Responses

| Code | Description |
| ---- | ----------- |
| 201 | The created cart. |

#### GET
##### Summary:

Retrieves a paginated list of all carts.

##### Parameters

| Name | Located in | Description | Required | Schema |
| ---- | ---------- | ----------- | -------- | ---- |
| nextToken | query |  | No | integer |
| pageSize | query |  | No | integer |

##### Responses

| Code | Description |
| ---- | ----------- |
| 200 | A list of cart summaries. |

### /carts/{cartId}

#### GET
##### Summary:

Retrieves a cart by cartId.

##### Parameters

| Name | Located in | Description | Required | Schema |
| ---- | ---------- | ----------- | -------- | ---- |
| cartId | path | The ID of the cart. | Yes | string |

##### Responses

| Code | Description |
| ---- | ----------- |
| 200 | The cart details. |

#### PATCH
##### Summary:

Updates an existing cart.

##### Parameters

| Name | Located in | Description | Required | Schema |
| ---- | ---------- | ----------- | -------- | ---- |
| cartId | path | The ID of the cart. | Yes | string |

##### Responses

| Code | Description |
| ---- | ----------- |
| 200 | The updated cart. |

#### DELETE
##### Summary:

Deletes a cart by cartId.

##### Parameters

| Name | Located in | Description | Required | Schema |
| ---- | ---------- | ----------- | -------- | ---- |
| cartId | path | The ID of the cart. | Yes | string |

##### Responses

| Code | Description |
| ---- | ----------- |
| 204 | The cart was deleted. |

### /carts/{cartId}/items

#### POST
##### Summary:

Creates a new cart item in the specified cart.

##### Parameters

| Name | Located in | Description | Required | Schema |
| ---- | ---------- | ----------- | -------- | ---- |
| cartId | path |  | Yes | string |

##### Responses

| Code | Description |
| ---- | ----------- |
| 201 | The cart item was created. |

#### GET
##### Summary:

Retrieves all items in the specified cart.

##### Parameters

| Name | Located in | Description | Required | Schema |
| ---- | ---------- | ----------- | -------- | ---- |
| cartId | path |  | Yes | string |

##### Responses

| Code | Description |
| ---- | ----------- |
| 200 | A list of cart items. |

### /carts/{cartId}/items/{cartItemId}

#### GET
##### Summary:

Retrieves details for a specific cart item.

##### Parameters

| Name | Located in | Description | Required | Schema |
| ---- | ---------- | ----------- | -------- | ---- |
| cartId | path |  | Yes | string |
| cartItemId | path |  | Yes | string |

##### Responses

| Code | Description |
| ---- | ----------- |
| 200 | The cart item details. |

#### PATCH
##### Summary:

Updates a specific cart item.

##### Parameters

| Name | Located in | Description | Required | Schema |
| ---- | ---------- | ----------- | -------- | ---- |
| cartId | path |  | Yes | string |
| cartItemId | path |  | Yes | string |

##### Responses

| Code | Description |
| ---- | ----------- |
| 200 | The cart item was updated. |

#### DELETE
##### Summary:

Deletes a cart item by cartItemId.

##### Parameters

| Name | Located in | Description | Required | Schema |
| ---- | ---------- | ----------- | -------- | ---- |
| cartId | path |  | Yes | string |
| cartItemId | path |  | Yes | string |

##### Responses

| Code | Description |
| ---- | ----------- |
| 204 | The cart item was deleted. |
