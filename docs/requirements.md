 GameStop Inventory Database Requirements

 Purpose of the Project

This database is for the purpose of assisting GameStop in the management of products, inventory, stores, customers, orders, employees and suppliers. This database would help GameStop manage their products, their locations and how their products are being sold.

 Entities

The following entities will be used in this database:

1. STORE
2. PRODUCT
3. INVENTORY
4. CUSTOMER
5. ORDER
6. ORDER_ITEM
7. EMPLOYEE
8. SUPPLIER

## Entity Attributes

### STORE
- store_id - Primary Key
- store_name
- address
- city
- state
- zip_code

### PRODUCT
- product_id - Primary Key
- product_name
- category
- price
- supplier_id

### INVENTORY
- inventory_id - Primary Key
- store_id
- product_id
- quantity

### CUSTOMER
- customer_id - Primary Key
- first_name
- last_name
- email
- phone

### ORDER
- order_id - Primary Key
- customer_id
- store_id
- order_date
- total_amount

### ORDER\_ITEM
- order_item_id - Primary Key
- order_id
- product_id
- quantity
- price

### EMPLOYEE
- employee_id - Primary Key
- store_id
- first_name
- last_name
- position

### SUPPLIER
- supplier_id - Primary Key
- supplier_name
- contact_email
- phone
