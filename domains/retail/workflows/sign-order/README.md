

## Workflow Overview
Order signing happens after a shopper has added all the items to the cart, chose a delivery date, provided delivery address, and pament mechansim. 

## Workflow Steps

1. The first step is to get the existing Order from the Order Service.
2. Next we pass the Order to the Fulfillment Service to create a fulfillment plan.
3. Next we raise an event that the order has been signed, if there are no validation errors.
