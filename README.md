# Architecture Katas

## Step 1
### Identifying the Users/Clients
1. Customers
2. Vendors
3. Kitchens
4. Smart Fridges
5. Kiosk / POS Systems
6. Admin

### Identifying Use Cases and deriving components
![Use-Case Analysis](image/FarmacyFoods_UseCase_Analysis.png)

## Step 2
### Overall High-level Architecture

![High Level Architecture Diagram](image/OverallArchitectureDiagram.png)

Architecture Approach - Decision Records
1. [Monolithic Design](adrs/monolithic-approach.md)
2. [Serverless Design](adrs/serverless-approach.md)

Moving ahead with the **Serverless design** for the Farmacy Food Service.

## Step 3
### Architecture of POS integration

Decision Record: [POS Integration Design](adrs/pos-integration.md)

![POS Integration Architecture Diagram](image/POSIntegrationArchitecture.png)

## Step 4
### Component & Sequence Diagrams

![Component Diagram](image/component-arch-diagram.png)

Vendor Registration

![Vendor Sequence Diagram](sequence-diagrams/vendor.png)

Kitchen Registration

![Kitchen Sequence Diagram](sequence-diagrams/kitchen.png)

Adding Menu Items

![Menu Sequence Diagram](sequence-diagrams/menu.png)

Kitchen Order Placement

![Kitchen Order Placement Diagram](sequence-diagrams/kitchen-order.png)

Expiry Tracker 

![Expiry Tracker Diagram](sequence-diagrams/expiry-tracker.png)

Online Order Reservations

![Order Resevation Diagram](sequence-diagrams/reserve-meal.png)

Purchasing Meal offline

![Purchase Meal Diagram](sequence-diagrams/purchase-items-and-send-survey.png)

Create Surveys

![Create Surveys Diagram](sequence-diagrams/surveys.png)

Create Coupons

![Create Coupons Diagram](sequence-diagrams/coupons-create.png)
