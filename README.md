# Architecture Katas - Farmacy Food

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

Architecture Approach for **Farmacy Food Service** - Decision Records
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

#### Vendor Registration

![Vendor Sequence Diagram](sequence-diagrams/vendor.png)

#### Kitchen Registration

![Kitchen Sequence Diagram](sequence-diagrams/kitchen.png)

#### Adding Menu Items

![Menu Sequence Diagram](sequence-diagrams/menu.png)

#### Kitchen Order Placement

![Kitchen Order Placement Diagram](sequence-diagrams/kitchen-order.png)

#### Expiry Tracker 

![Expiry Tracker Diagram](sequence-diagrams/expiry-tracker.png)

#### Online Order Reservations

Architecture Decisions:

[Inventory Updates Communicaiton](adrs/inventory-reservations.md)

[Payment Service Communication](adrs/payments-communication.md)

![Order Resevation Diagram](sequence-diagrams/reserve-meal.png)

#### Purchasing Meal offline

Architecture Decisions:

[POS Integration](adrs/pos-integration.md)

![Purchase Meal Diagram](sequence-diagrams/purchase-items-and-send-survey.png)

#### Create Surveys

![Create Surveys Diagram](sequence-diagrams/surveys.png)

#### Create Coupons

![Create Coupons Diagram](sequence-diagrams/coupons-create.png)

## Step 5
### Components Architecture Characteristics

| Component         | Description                                                                                                                                                    | Architecture Characteristics                                          |
|-------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------|
| Inventory         | As this is one of the system's core<br>components, it need to be highly available, <br>provide necessary responses to other system services <br>in short time. | 1- Scalability<br>2- Performance<br>3- Availability<br>4- Reliability |
| Expiry<br>Tracker | This job needs to run daily but should be <br>quick enough to analyze all items that are expired.                                                              | 1- Performance                                                        |
| Feedback          | This component is highly needed to render the menu,<br>and thus needs to be highly available and performant.                                                   | 1- Performance<br>2- Availability<br>3- Customizable                  |
