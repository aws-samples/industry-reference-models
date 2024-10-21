# Event Service API

## Overview

The Event Service API provides a interface for receiving events. This service acts as an abstraction layer over an underlying event backbone (such as Event Bridge), allowing other microservices like Cart, Fulfillment, Payments, etc., to raise events in a decoupled, API-driven manner.

## Version

1.0.0

## API Endpoints

### Events

#### POST /events

Receive and process events.

- **Request Body**: JSON object conforming to the `EventType` schema
- **Responses**:
  - `202`: Event received successfully
  - `400`: Invalid event payload

## Schemas

### EventType

- `eventId` (string, required): Unique ID for the event
- `eventType` (string, required): The type of event (e.g., CartItemAdded, OrderCompleted)
- `timestamp` (string, date-time format, required): Timestamp of when the event occurred
- `data` (object): The event payload, varying based on the eventType
- `source` (string): Source service or system that raised the event

### ProcessingResponse

- `message` (string): Any additional details about the event processing
