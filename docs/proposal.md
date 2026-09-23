# GameStop Inventory and Store Availability Database

## Project Domain
The project domain is retail inventory management. This database will focus on managing products and inventory across GameStop store locations.

## Problem Description
GameStop sells video games, consoles, accessories, collectibles, and other products at different store locations. A problem in retail is keeping track of which products are available at each location. A product may be sold out at one GameStop while another store has it available. Customers and employees need accurate inventory information so they can know where a product is available.

## Purpose of the Database
The purpose of this database it to keep the inventory of GameStop more  organized.This will help to make it easier for employees to keep track of products, store locations, product quantities, customers and orders 

## Mini-World
The mini-world of this database focuses on the inventory of GameStop and the access to products. The database will actively update in order to show accurate information for every location.

## Intended Users
The intended users are employees (those who work at Gamestop) and customers. Each location and  its workers should have quick and accurate information about each product.

## Major Data That Must Be Stored
The database will store:
- Product IDs and product names
- Product categories
- Product prices
- Store IDs and locations
- Inventory quantities
- Customer information
- Orders
- Product reservations
- Purchase dates

## Questions the Database Should Answer
1. Which products are currently available at a specific GameStop location?
2. How many units of a product are currently in stock?
3. Which products are currently out of stock?
4. Which store locations have a specific product available?
5. Which products have been reserved by customers?
6. Which products need to be restocked?
7. When will a specific product restock?

## Initial Business Rules
1. Every product should have an unique ID.
2. Every store should have an unique ID.
3. Stores can have multiple products in its inventory.
4. A product can be at multiple locations.
5. Each purchase should be associated with an employee and store location.


## Initial Functional Requirements
1. The system should allow employees to search for products
2. The system should allow employees to see whats in stock at other locations.
3. The system should show the quantity of every product
4. The system should allow employees to update the inventory.
5. The system should show incoming products,the date and the quantity.
6. The sustem should show shipment dates
7. The system should allow managers to identify products that need to be restocked.
