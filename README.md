# Architecture Katas - Farmacy Food

## Presentation
[View Presentation](https://drive.google.com/drive/folders/1iaBb1ZlPgxhvYSS1HB35YBBvyU9GvBhq?usp=sharing)

## Overview
![Overview](image/FarmacyFoods_Overview.png)

Farmacy Food is a tech-enabled healthy food startup that creates tasty meals around people's dietary needs and active lifestyles to support their overall well-being.

Their mission is to make health and wellness radically affordable and accessible.

Let me explain the basic concept of Farmacy Food:
1. Farmacy Food is a “Ghost Kitchen” which will prepare the meals.
2. We use Smart Fridges and Sub-let spaces in other businesses as our Points of Sale. So, the meals are delivered to these POS from the Kitchen.
3. Customers will check availability of meals using Mobile/Web App in the nearby Points of Sale.
4. Customers go to the nearest available POS and purchase or pick-up the meals.
5. The system has to maintain the inventory levels in the Smart Fridge and other POS.

Some Long Term goals are: 
1. Allowing multiple vendors or kitchens to provide meals using our system.
2. Provide personalized recommendation based on user profile & purchase history.

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
| User Profile | User Profile will provide users' data and authentication services | 1- Availability<br>2- Performance<br>3- Reliability<br> 4- Scalability
| Coupons | Coupons service will be used mainly to create promotional coupons and validate them. | 1- Availability<br>2- Reliability<br>3- Customizable
| Menu Catalog | Menu Catalog will hold the menu for all enabled items and it will manage adding/removing/disabiling menu items as well as listing menu items for customers. | 1- Availability<br>2- Performance<br>3- Customizable<br>4- Scalability<br>5- Reliability
