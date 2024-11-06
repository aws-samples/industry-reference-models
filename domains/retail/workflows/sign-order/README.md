

## Workflow Overview
Order signing happens after a shopper has added all the items to the cart, chose a delivery date, provided delivery address, and pament mechansim. 

## Workflow Steps

1. The first step is to get the existing Order from the Order Service.
2. Next we pass the Order to the Fulfillment Service to create a fulfillment plan.
3. Next we raise an event that the order has been signed, if there are no validation errors.

## API Gateway Used for Web Service Calls

API Gateway will be Invoked from the Step Function for each action the process needs to call.

### Example API Gateway Invoke Request
```json
"Customer.GetCustomer": {
                    "Type": "Task",
                    "Resource": "arn:aws:states:::apigateway:invoke",
                    "Parameters": {
                      "ApiEndpoint": "MyApiId.execute-api.us-east-1.amazonaws.com",
                      "Method": "GET",
                      "Path": "/customers/${$.customerId}"
                    },
                    "End": true
                  }
```
