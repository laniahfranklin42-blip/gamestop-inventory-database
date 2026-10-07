business_rules.md
# GameStop Inventory Database Business Rules

## Store and Employee
- A STORE can be associated with 0 or more EMPLOYEE(s).
- An EMPLOYEE can be associated with exactly one STORE.
- Degree of association: Binary
- Cardinality: One-to-Many
- Participation: EMPLOYEE is associated; STORE is optionally associated.

## Store and Inventory
- A STORE can be associated with 0 or more INVENTORY(s).
- An INVENTORY can be associated with exactly one STORE.
- Degree of association: Binary
- Cardinality: One-to-Many
- Participation: INVENTORY is associated; STORE is optionally associated.

## Product and Inventory
- A PRODUCT is present in 0 or more INVENTORY(s).
- An INVENTORY can be associated with exactly one PRODUCT.
- Degree of association: Binary
- Cardinality: One-to-Many
- Participation: INVENTORY is associated; PRODUCT is optionally associated.

## Supplier and Product
- A SUPPLIER supplies 0 or more PRODUCTS.
- A PRODUCT can be associated with exactly one SUPPLIER.
- Degree of association: Binary
- Cardinality: One-to-Many
- Participation: PRODUCT is associated; SUPPLIER is optionally associated.

## Customer and Order
- A CUSTOMER can be associated with 0 or more ORDERS.
- An ORDER can be associated with exactly one CUSTOMER.
- Degree of association: Binary
- Cardinality: One-to-Many
- Participation: ORDER is associated; CUSTOMER is optionally associated.

## STORE and ORDER
- Zero or many ORDER may exist within a single STORE.
- Each ORDER should belong to one STORE.
- Degree of Relationship: Binary
- Cardinality: One to Many
- Participation: Mandatory for ORDER and Optional for STORE.

## ORDER and ORDER_ITEM
- At least one or many ORDER_ITEMS may exist within an ORDER.
- Each ORDER_ITEM should belong to one ORDER.
- Degree of Relationship: Binary
- Cardinality: One to Many
- Participation: Mandatory for ORDER and ORDER_ITEM.

## Product and ORDER_ITEM
- Zero or many ORDER_ITEMS may exist for one PRODUCT.
- Each ORDER_ITEM should belong to one PRODUCT.
- Degree of Relationship: Binary
- Cardinality: One to Many
- Participation: Mandatory for ORDER_ITEM and Optional for PRODUCT.
