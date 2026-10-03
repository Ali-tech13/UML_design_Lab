# Problem Analysis

## Main Entities

- User
- Restaurant
- Item
- Order
- OrderItem

## Key Relationships

- A User can have multiple Orders.
- Each Order belongs to one User.
- A Restaurant can provide multiple Items.
- Each Item belongs to one Restaurant.
- Each Order is associated with one Restaurant.
- An Order contains multiple OrderItems.
- Each OrderItem references one Item.
- All items in an Order must belong to the same Restaurant.

## Main Use Cases

### 1. Place an Order
The user finalizes the current order and confirms it.

### 2. Add an Item to an Order
The user adds an item and quantity to the current order.

### 3. Update Order Status
The order status changes through the following lifecycle:

CREATED -> CONFIRMED -> PREPARED -> DELIVERED

## Design Decisions

- No separate Menu class is used because the Restaurant can directly provide its Items.
- No Cart class is used because an Order in the CREATED state represents the order while it is being built.
- OrderItem is used to store the selected Item, quantity, and unit price.
- OrderStatus is represented as an enumeration to restrict the order to valid states.
- Payment and delivery routing are not modeled because they are outside the project scope.