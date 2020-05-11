# Android Point of Sale App Challenge
Design and build an application that displays a restaurant menu for a point-of-sale. Use the defined schemas and payloads provided below to meet the requirements of this challenge.

## Note from the Team
We're excited that you're considering working with us.  We hope that you choose to dedicate a few hours of your time to completing this challenge.  We want to be transparent about what we're looking for at this stage of the interview process in hopes that we can be efficient with your time.

**In this challenge, we want to see how you think about architecting applications.**
- What classes do you choose to build and what are their responsibilities?
- What tools and techniques do you use and why?
- How do you ensure that your application meets the requirements of the challenge?
- Have you set the project up in a way that others could easily jump in and add additional functionality?

We `will not` be evaluating your layouts, animations, nor anything else related to aesthetics of the app on-screen as part of this challenge.

We `will not` be evaluating your gradle build skillset as part of this challenge.

## Fetching the Menu
Retrieve a menu by sending a `GET` request to the `GET https://challenge.fiserv.com/menus/:uuid` endpoint.  
Use the uuid `5ced2fea-9155-11ea-bb37-0242ac130002` to fetch the menu for the challenge.  
A sample response follows:
```
{
  uuid: '5ced2fea-9155-11ea-bb37-0242ac130002',
  items: [
    {
      uuid: '7cd7f0ef-8265-4593-95ea-dd7c2bb6396d',
      name: 'Hamburger',
      price: 875
    },
    {
      uuid: '6d419f88-b53f-49e2-af0a-832444d6ed41',
      name: 'Water',
      price: 235
    },
    {
      uuid: '47dfb3e6-b892-40b8-9ce6-f769c6e15537',
      name: 'Beer',
      price: 1025
    }
  ]
}
```

## Displaying the Menu
Display the fetched menu in a RecyclerView.  Each item in the RecyclerView must display the item `name` and `price`.  The Activity which displays the menu should respond to the `<intent-filter>`:
```
<intent-filter>
    <action android:name="android.intent.action.MAIN" />

    <category android:name="android.intent.category.LAUNCHER" />
</intent-filter>
```

## Clicking on a Menu Item
Clicking on a menu item in the RecyclerView should **display a new view** for the selected item.  The new view should display the following:
- `item name` - pulled from the fetched menu
- `item price` - pulled from the fetched menu
- `total price` - calculated total price for the item, accounting for quantity.  Details below.
- `quantity` - the quantity for calculating total price.  Starts at **1** every time the new view is loaded.  Never goes below **0**.  Does not need to be remembered after the view is closed.
- `+1 quantity button` - increases the quantity by **1**.  `quantity` view updates.  `total price` view updates.
- `-1 quantity button` - decrements the quantity by **1**.  `quantity` view updates.  `total price` view updates.
- `cancel button` - returns the user to the Menu.

#### Disabling the `-1 quantity button`
The `-1 quantity button` button should be disabled if `quantity` is **0**.  It should be enabled otherwise.  

#### Calculating the Total Price for an item
The above step requires you to correctly calculate total price for an item.
The total price for an item can be calculated by calculating `item price x quantity`.
The resulting value should be rounded to the nearest penny for display.

## Assumptions
* You can assume that all all prices should be displayed USD, rounded to the nearest penny.
* For item prices, assume `100 is equivalent to $1 USD`.

## Technical Requirements
* Your Application should compile on Android Studio 3.6.3 or newer.
* Your application should run on Android 7.1.2 and newer.

## Questions
Contact the proctor of your test if you have any questions or feedback about this challenge.


