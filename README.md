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

![Component Diagram](image/ComponentDiagram.png)
