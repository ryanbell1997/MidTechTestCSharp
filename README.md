# MidTechTestCSharp
Welcome to the pair programming exercise 👋

This test comprises of a simple boilerplate Minimal API that will be used to create, fetch and update customer orders.

This is a short challenge, where you will have around 30 minutes to work through as many tickets as possible. Don’t worry if you do not finish them all in the time.

If you get stuck, feel free to use Google or ask your interviewers for help.

❌ Whilst AI is a common tool in an engineering environment, **generative AI is off limits for this challenge**. ❌

## Challenge 1 - Persistence
The API requires a mechanism for persisting customer order data.

For the purpose of this initial implementation and given the time constraint, an in-memory data store should be implemented to manage order data during the application's runtime.

Below is the structure for a typical order we'll store:
``` json
{
  "id": "th1sIsS0me0rderId",
  "customerId": 129348,
  "containsAllergens": true,
  "items": [
    {
      "name": "Cheese burger",
      "cost": 10.0
    },
    {
      "name": "Fries",
      "cost": 5.99
    }
  ]
}
```

## Challenge 2 - Create an endpoint to store an order
When a user places an order, we need a way to store that order.

Implement an API endpoint to store order data into the persistence store.

Order ids should always be 17 characters long.

Customer ids should always be 6 numbers in length.

The order should be persisted to the database with a timestamp denoting its creation date.

## Challenge 3 - Create an endpoint to get an order
Now that users orders are being persisted to the database, we need to be able to fetch customer orders using our API.

Create an API endpoint where we can fetch the details for a particular `orderId`.

The item costs should be totalled and returned in the response.

## Challenge 4 - Create an endpoint to update an order
Implement an endpoint that allows for updating an existing order.

Any update to an order should not change the `createdAt` property, but it should introduce a new `updatedAt` property.

## Challenge 5 - Create an endpoint to fetch a customers order history
Customers place more than one order, and so we need an endpoint to get their order history.

We should be able to provide a customer id and get multiple orders for that customer.

The orders should be returned in createdAt order, with the most recent orders being returned first.

Below is some sample data for seeding into the database:
``` json
{
  "id": "thisIsAOrderIdNo1",
  "customerId": 111111,
  "containsAllergens": true,
  "items": [
    {
      "name": "Cheese burger",
      "cost": 10.0
    },
    {
      "name": "Fries",
      "cost": 5.99
    }
  ]
},
{
  "id": "thisIsAOrderIdNo2",
  "customerId": 111111,
  "containsAllergens": false,
  "items": [
    {
      "name": "Hot Dog",
      "cost": 7.0
    },
    {
      "name": "Fries",
      "cost": 5.99
    }
  ]
},
{
  "id": "thisIsAOrderIdNo3",
  "customerId": 111111,
  "containsAllergens": true,
  "items": [
    {
      "name": "Cheese burger",
      "cost": 10.0
    },
    {
      "name": "Mixed Salad",
      "cost": 3.99
    }
  ]
},
{
  "id": "thisIsAOrderIdNo4",
  "customerId": 111111,
  "containsAllergens": false,
  "items": [
    {
      "name": "Hamburger",
      "cost": 8.0
    },
    {
      "name": "Fries",
      "cost": 5.99
    }
  ]
}
```