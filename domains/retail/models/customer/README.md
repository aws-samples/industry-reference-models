# Customer Service API
Customer Service API for managing customer records and operations.

## Version: 2024-01-01

### /customers

#### POST
##### Summary:

Creates a new customer record.

##### Responses

| Code | Description |
| ---- | ----------- |
| 201 | The created customer record. |

### /customers/{customerId}

#### GET
##### Summary:

Retrieves details for a specific customer.

##### Parameters

| Name | Located in | Description | Required | Schema |
| ---- | ---------- | ----------- | -------- | ---- |
| customerId | path | The unique identifier for the customer. | Yes | string |

##### Responses

| Code | Description |
| ---- | ----------- |
| 200 | The customer details. |

#### PATCH
##### Summary:

Updates an existing customer record.

##### Parameters

| Name | Located in | Description | Required | Schema |
| ---- | ---------- | ----------- | -------- | ---- |
| customerId | path | The unique identifier for the customer. | Yes | string |

##### Responses

| Code | Description |
| ---- | ----------- |
| 200 | The updated customer record. |

#### DELETE
##### Summary:

Deletes a customer record.

##### Parameters

| Name | Located in | Description | Required | Schema |
| ---- | ---------- | ----------- | -------- | ---- |
| customerId | path | The unique identifier for the customer. | Yes | string |

##### Responses

| Code | Description |
| ---- | ----------- |
| 204 | The customer record was deleted. |
