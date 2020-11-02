# Integration with the Points of Sale (Smart Fridge & Kiosks)

## Status
_PROPOSED_

## Context
The meals provided by Farmacy foods can be sold from multiple Points of Sale:
1. Smart Fridges
2. Kiosks or Manual Points of Sale

We need to integrate with all the different points of sale for the following functionalities:
- Updating the changes in the Menu (Prices, New Meals)
- Updating the Promotional Coupons
- Fetching the Active status of POS
- Fetching the Inventory Available at a POS
- Fetching the purchases made at a POS

As there are multiple types of systems involved, we need to come with the design to easily integrate with all the currently active POS and also provide the capability to easily add new POS types.

For example, there are multiple softwares used for the Points of Sale like: Square POS, Shopify, Lightspeed, Quickbooks, Oracle micros and more.

## Decision

As we are partnering with Byte Technology for the Smart Fridges, We can assume that we will be majorly using this Smart Fridge as one of our Points of Sale. So, it is important that we make sure **this integration is done as an independent component** so that it can be scaled and maintained easily.

So, we can split into the following components:
1. Smart Fridge Integrator: To integrate with all the Smart Fridges of Byte Technology.
2. Kiosk Integrator: To integrate with all the Kiosks / Manual Points of Sale.
