# Loyalty Service API
The Loyalty Service API provides operations to manage loyalty members, transactions, and promotions.

## Version: 2024-01-01

### /loyalty/members

#### POST
##### Summary:

Enroll a new member.

##### Responses

| Code | Description |
| ---- | ----------- |
| 201 | The created member. |

#### GET
##### Summary:

List loyalty members.

##### Parameters

| Name | Located in | Description | Required | Schema |
| ---- | ---------- | ----------- | -------- | ---- |
| nextToken | query |  | No | string |
| pageSize | query |  | No | integer |
| tier | query |  | No | [LoyaltyTier](#LoyaltyTier) |
| status | query |  | No | [LoyaltyMemberStatus](#LoyaltyMemberStatus) |

##### Responses

| Code | Description |
| ---- | ----------- |
| 200 | A list of loyalty members. |

### /loyalty/members/{memberId}

#### GET
##### Summary:

Retrieve member details.

##### Parameters

| Name | Located in | Description | Required | Schema |
| ---- | ---------- | ----------- | -------- | ---- |
| memberId | path |  | Yes | string |

##### Responses

| Code | Description |
| ---- | ----------- |
| 200 | The member details. |

#### PUT
##### Summary:

Update member information.

##### Parameters

| Name | Located in | Description | Required | Schema |
| ---- | ---------- | ----------- | -------- | ---- |
| memberId | path |  | Yes | string |

##### Responses

| Code | Description |
| ---- | ----------- |
| 200 | The updated member. |

#### DELETE
##### Summary:

Delete a member.

##### Parameters

| Name | Located in | Description | Required | Schema |
| ---- | ---------- | ----------- | -------- | ---- |
| memberId | path |  | Yes | string |

##### Responses

| Code | Description |
| ---- | ----------- |
| 204 | The member was deleted. |

### /loyalty/transactions

#### POST
##### Summary:

Create a new transaction.

##### Responses

| Code | Description |
| ---- | ----------- |
| 201 | The created transaction. |

#### GET
##### Summary:

List loyalty transactions.

##### Parameters

| Name | Located in | Description | Required | Schema |
| ---- | ---------- | ----------- | -------- | ---- |
| nextToken | query |  | No | string |
| pageSize | query |  | No | integer |
| memberId | query |  | No | [MemberId](#MemberId) |
| type | query |  | No | [TransactionType](#TransactionType) |

##### Responses

| Code | Description |
| ---- | ----------- |
| 200 | A list of loyalty transactions. |

### /loyalty/transactions/{transactionId}

#### GET
##### Summary:

Retrieve transaction details.

##### Parameters

| Name | Located in | Description | Required | Schema |
| ---- | ---------- | ----------- | -------- | ---- |
| transactionId | path |  | Yes | string |

##### Responses

| Code | Description |
| ---- | ----------- |
| 200 | The transaction details. |

### /loyalty/promotions

#### POST
##### Summary:

Create a new promotion.

##### Responses

| Code | Description |
| ---- | ----------- |
| 201 | The created promotion. |

#### GET
##### Summary:

List promotions.

##### Parameters

| Name | Located in | Description | Required | Schema |
| ---- | ---------- | ----------- | -------- | ---- |
| nextToken | query |  | No | string |
| pageSize | query |  | No | integer |
| status | query |  | No | [PromotionStatus](#PromotionStatus) |

##### Responses

| Code | Description |
| ---- | ----------- |
| 200 | A list of promotions. |

### /loyalty/promotions/{promotionId}

#### GET
##### Summary:

Retrieve promotion details.

##### Parameters

| Name | Located in | Description | Required | Schema |
| ---- | ---------- | ----------- | -------- | ---- |
| promotionId | path |  | Yes | string |

##### Responses

| Code | Description |
| ---- | ----------- |
| 200 | The promotion details. |

#### PUT
##### Summary:

Update promotion details.

##### Parameters

| Name | Located in | Description | Required | Schema |
| ---- | ---------- | ----------- | -------- | ---- |
| promotionId | path |  | Yes | string |

##### Responses

| Code | Description |
| ---- | ----------- |
| 200 | The updated promotion. |

#### DELETE
##### Summary:

Delete a promotion.

##### Parameters

| Name | Located in | Description | Required | Schema |
| ---- | ---------- | ----------- | -------- | ---- |
| promotionId | path |  | Yes | string |

##### Responses

| Code | Description |
| ---- | ----------- |
| 204 | The promotion was deleted. |
