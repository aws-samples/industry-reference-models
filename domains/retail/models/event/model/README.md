# Event Service API

## Overview

The Event Service API provides a robust interface for managing and processing events, as well as creating subscriptions for event notifications. This service acts as an abstraction layer over an underlying event backbone (such as Event Bridge), allowing other microservices like Cart, Fulfillment, Payments, etc., to raise events and subscribe to events in a decoupled, API-driven manner.

## Version

1.0.0

## API Endpoints

### Events

#### POST /events

Receive and process events.

- **Request Body**: JSON object conforming to the `EventType` schema
- **Responses**:
  - `200`: Event received successfully
  - `400`: Invalid event payload

### Subscriptions

#### GET /subscriptions

Retrieve all subscriptions.

- **Responses**:
  - `200`: A list of all event subscriptions
  - `404`: No subscriptions found

#### POST /subscriptions

Create a new event subscription.

- **Request Body**: JSON object conforming to the `Subscription` schema
- **Responses**:
  - `201`: Subscription created successfully
  - `400`: Invalid request data

#### DELETE /subscriptions/{subscriptionId}

Remove a specific event subscription.

- **Parameters**:
  - `subscriptionId` (path, required): String
- **Responses**:
  - `204`: Subscription deleted successfully
  - `404`: Subscription not found

## Schemas

### EventType

- `eventId` (string, required): Unique ID for the event
- `eventType` (string, required): The type of event (e.g., CartItemAdded, OrderCompleted)
- `timestamp` (string, date-time format, required): Timestamp of when the event occurred
- `data` (object): The event payload, varying based on the eventType
- `source` (string): Source service or system that raised the event

### Subscription

- `eventType` (string, required): The type of event to subscribe to
- `conditions` (object): Optional conditions for filtering events
- `callbackUrl` (string, required): The webhook URL where event notifications will be sent
- `retryPolicy` (object):
  - `retryCount` (integer, default: 3)
  - `retryInterval` (string): Time interval between retries

### SubscriptionResponse

- `subscriptionId` (string): Unique ID of the created subscription
- `eventType` (string): Event type the subscription listens to
- `callbackUrl` (string): The webhook URL for event notifications
- `conditions` (object): Any conditions specified in the subscription
- `status` (string): Status of the subscription (e.g., active, paused)

### ProcessingResponse

- `status` (string): Status of event processing (e.g., success, failure)
- `message` (string): Any additional details about the event processing
