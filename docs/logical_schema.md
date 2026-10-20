# GameStop Inventory Database - Logical Schema

## Tables and Columns

### STORE
- store_id INT PRIMARY KEY
- store_name VARCHAR(100) NOT NULL
- address VARCHAR(255) NOT NULL
- city VARCHAR(100) NOT NULL
- state VARCHAR(50) NOT NULL
- zip_code VARCHAR(10) NOT NULL

### PRODUCT
- product_id INT PRIMARY KEY
- product_name VARCHAR(150) NOT NULL
- category VARCHAR(100) NOT NULL
- price DECIMAL(10,2) NOT NULL
- supplier_id INT NOT NULL FOREIGN KEY

### INVENTORY
- inventory_id INT PRIMARY KEY
- store_id INT NOT NULL FOREIGN KEY
- product_id INT NOT NULL FOREIGN KEY
- quantity INT NOT NULL
- UNIQUE(store_id, product_id)

### CUSTOMER
- customer_id INT PRIMARY KEY
- first_name VARCHAR(100) NOT NULL
- last_name VARCHAR(100) NOT NULL
- email VARCHAR(255) NOT NULL UNIQUE
- phone VARCHAR(20)

### CUSTOMER_ORDER
- order_id INT PRIMARY KEY
- customer_id INT NOT NULL FOREIGN KEY
- store_id INT NOT NULL FOREIGN KEY
- order_date DATETIME NOT NULL
- total_amount DECIMAL(10,2) NOT NULL

### ORDER_ITEM
- order_item_id INT PRIMARY KEY
- order_id INT NOT NULL FOREIGN KEY
- product_id INT NOT NULL FOREIGN KEY
- quantity INT NOT NULL
- price DECIMAL(10,2) NOT NULL

### EMPLOYEE
- employee_id INT PRIMARY KEY
- store_id INT NOT NULL FOREIGN KEY
- first_name VARCHAR(100) NOT NULL
- last_name VARCHAR(100) NOT NULL
- position VARCHAR(100) NOT NULL

### SUPPLIER
- supplier_id INT PRIMARY KEY
- supplier_name VARCHAR(100) NOT NULL
- contact_email VARCHAR(255)
- phone VARCHAR(20)

## Foreign Keys

- PRODUCT.supplier_id references SUPPLIER.supplier_id
- INVENTORY.store_id references STORE.store_id
- INVENTORY.product_id references PRODUCT.product_id
- CUSTOMER_ORDER.customer_id references CUSTOMER.customer_id
- CUSTOMER_ORDER.store_id references STORE.store_id
- ORDER_ITEM.order_id references CUSTOMER_ORDER.order_id
- ORDER_ITEM.product_id references PRODUCT.product_id
- EMPLOYEE.store_id references STORE.store_id

## Relationships

1. STORE to EMPLOYEE: One-to-Many
2. STORE to INVENTORY: One-to-Many
3. PRODUCT to INVENTORY: One-to-Many
4. SUPPLIER to PRODUCT: One-to-Many
5. CUSTOMER to CUSTOMER_ORDER: One-to-Many
6. STORE to CUSTOMER_ORDER: One-to-Many
7. CUSTOMER_ORDER to ORDER_ITEM: One-to-Many
8. PRODUCT to ORDER_ITEM: One-to-Many

## Associative Tables

There are two associative tables in the database.

INVENTORY is an associative table that links STORE and PRODUCT.

ORDER_ITEM is an associative table that links CUSTOMER_ORDER and PRODUCT.

## Keys

Each table has its own primary key.

Additionally, the INVENTORY table uses a composite unique constraint on store_id and product_id. This prevents a store from having multiple inventory records for the same product. The inventory_id remains the primary key.

Moreover, foreign keys are used to link tables and enforce referential integrity.

CUSTOMER_ORDER is used instead of ORDER because ORDER is a reserved word in MySQL.

## MySQL Data Types

- INT is used for identifiers and quantities.
- VARCHAR is used for names, addresses, and other text.
- DECIMAL(10,2) is used for prices and monetary amounts.
- DATETIME is used to store order dates and times.
- NOT NULL indicates that a column requires a value.
- UNIQUE prevents duplicate values where specified.

## Design Notes

The database contains eight tables based on the conceptual model from Milestone 2. The relationships between these tables are maintained using primary and foreign keys.

The logical schema defines the database structure before implementation in MySQL. Foreign key references are listed separately; actual MySQL CREATE TABLE statements will require FOREIGN KEY constraints with REFERENCES clauses.
