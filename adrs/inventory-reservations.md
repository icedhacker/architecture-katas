# Inventory Reservations Communication

## Status
_PROPOSED_

## Context
Farmacy food inventory service will be a critical component for all the operations in the entire system.
- Inventory numbers should be consitent for all the clients in the system.
- When an Online Order is placed, the inventory should be immiediatly reserved and should not be available for other users.
- Tolerations:
        - As Edge customer location (ie. POS or Smart Fridge) contains very limited number of serving of a perticuler type(<25) the system should not report over amounts that leads to reservation of items that are not available.
        - Quantity updates that result in increasing the inventory can be delayed as it does not result in reservation of unavailable item.

## Decision

The reservation of items from the invenotry system will be a synchronus communication process.

Process :
1. In the online order proces before payment the order service will call the Inventory Service for resevation.
2. Inventory service will check the availability reserve the products and respond with availability.
3. Order Service will return the order confirmation to the customer.

## Consequences
1. Inventory Service availabilty will be critcal for the Order Services tasks.
2. There will be stale reservations if the customer did not pick up the meal within a reasonable time(1 day). Expirations of these items needs to be handled.
3. In case of order service failure in the middle of a transaction there could be stale reservations.
