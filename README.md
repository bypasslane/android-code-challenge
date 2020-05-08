# Android Point of Sale App Challenge
Design and build an application that displays a restaurant menu for a point-of-sale. Use the defined schemas and payloads provided below to meet the requirements of this challenge.

## Fetching the Menu
Retrieve by sending a `GET` request to the `GET /menus/:uuid` endpoint.  
Use the uuid `5ced2fea-9155-11ea-bb37-0242ac130002` to fetch the menu for the challenge.  
A sample response follows:
```
{
  uuid: '5ced2fea-9155-11ea-bb37-0242ac130002',
  items: [
    {
      uuid: '7cd7f0ef-8265-4593-95ea-dd7c2bb6396d',
      name: 'Hamburger',
      price: 875,
      tax_rate: 0.0625
    },
    {
      uuid: '6d419f88-b53f-49e2-af0a-832444d6ed41',
      name: 'Water',
      price: 235,
      tax_rate: 0.0625
    },
    {
      uuid: '47dfb3e6-b892-40b8-9ce6-f769c6e15537',
      name: 'Beer',
      price: 1025,
      tax_rate: 0.0825
    }
  ]
}
```

## Displaying the Menu
Display the fetched menu in a RecyclerView.  **No extra points for pretty UI**.  Each item in the RecyclerView must display the item `name` and `price`.  The Activity which displays the menu should respond to the `<intent-filter>`:
```
<intent-filter>
    <action android:name="android.intent.action.MAIN" />

    <category android:name="android.intent.category.LAUNCHER" />
</intent-filter>
```

## Clicking on a Menu Item
Clicking on a menu item in the RecyclerView should `display a detail view` for the selected item.  **No extra points for pretty UI**.  
The detail view should display the following information:
- `item name`
- `item price`
- `subtotal` - calculated subtotal (excluding taxes) for an order containing `1` of this item
- `taxes` - calculated taxes for an order containing `1` of this item
- `total` - calculated total (including taxes) for an order containing `1` of this item

#### Calculating the Subtotal for an order
The above step requires you to correctly calculate the subtotal for an order that contains one item.
The subtotal for an order can be calculated by calculating `item price x item quantity` for each item on the order and summing the results.

#### Calculating the Taxes for an order
The above step requires you to correctly calculate the taxes for an order that contains one item.
The taxes for an order can be calculated by calculating `item price x item quantity x item tax_rate` for each item on the order and summing the results.

#### Calculating the Total for an order
The above step requires you to correctly calculate the total (including taxes) for an order that contains one item.
The total for an order can be calculated as `order subtotal + taxes`.

## Returning to the Menu
The user should have the ability to `dismiss the item detail view` and return to the Menu

## Assumptions
* You can assume that you will transact in USD.
* You can assume that we'd prefer you to spend as little time as possible on layouts, animations, etc. as possible.
* You can assume that we will pay close attention to whether your calculations are correct.
* For item prices, assume `100 is equivalent to $1 USD`.
* For item tax rates, assume `0.0825 is equivalent to 8.25%`.
* You can assume that we're only expecting a couple hours of your time
* You can assume that we'd prefer you to spend as little time as possible focusing on how your Application builds.
* You can assume that you are free to make any choices that you want so long as the written requirements of this document are satisfied.

## Technical Requirements
* Your Application should compile on Android Studio 3.6.3 or newer.
* Your application should run on Android 7.1.2 and newer.

## Questions
Contact the proctor of your test if you have any questions or feedback about this challenge.


