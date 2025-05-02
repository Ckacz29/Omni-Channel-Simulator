
# Fulfillment Logic for Retail Order Routing System

This logic determines how an order should be fulfilled based on customer location and inventory availability.

## Fulfillment Methods

1. **BOPIS (Buy Online, Pick Up In Store)**
   - Customer ZIP is within 5 miles of a store.
   - The store has the product in stock.

2. **Same Day Delivery (SDD)**
   - Customer ZIP is within 15 miles of a store.
   - The store has the product in stock.
   - Customer requests delivery (future enhancement).

3. **Ship-to-Store**
   - No nearby stores have inventory.
   - Product is shipped from central warehouse to a chosen store.

## Distance Simulation

We simulate distances using ZIP code approximations or latitude/longitude coordinates using the `geopy` library.

## Decision Tree Example

```
IF nearby_store WITH product_in_stock:
    IF distance <= 5 miles:
        fulfillment_method = "BOPIS"
    ELSE IF distance <= 15 miles:
        fulfillment_method = "Same Day Delivery"
ELSE:
    fulfillment_method = "Ship-to-Store"
```
