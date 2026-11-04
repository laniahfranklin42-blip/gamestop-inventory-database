All tables contain primary keys which allows every record to be identified.

STORE.store_id
PRODUCT.product_id
INVENTORY.inventory_id
CUSTOMER.customer_id
CUSTOMER_ORDER.order_id
ORDER_ITEM.order_item_id
EMPLOYEE.employee_id
SUPPLIER.supplier_id
This would mean that there will not be duplicate id’s.

Foreign Keys
Foreign keys are used to connect tables together and ensure that no records can be referenced that do not exist.

INVENTORY.store_id REFERENCES STORE.store_id
INVENTORY.product_id REFERENCES PRODUCT.product_id
PRODUCT.supplier_id REFERENCES SUPPLIER.supplier_id
CUSTOMER_ORDER.customer_id REFERENCES CUSTOMER.customer_id
CUSTOMER_ORDER.store_id REFERENCES STORE.store_id
ORDER_ITEM.order_id REFERENCES CUSTOMER_ORDER.order_id
ORDER_ITEM.product_id REFERENCES PRODUCT.product_id

NOT NULL
These fields cannot be blank.

STORE.store_name
PRODUCT.product_name
PRODUCT.price
INVENTORY.quantity
CUSTOMER.first_name
CUSTOMER.last_name

This ensures that the fields are filled in correctly.

Unique

Some fields must be unique. CUSTOMER.email must be unique and for INVENTORY there is UNIQUE on store_id and product_id to stop duplicate inventory records.
Check
Check constraints are used to prevent invalid data being added.

CHECK (quantity >= 0)
CHECK (price >= 0)
CHECK (total_amount >= 0)
This ensures that the quantity, price and total amount will not be negative.
Default Values
Some fields will have default values.
INVENTORY.quantity DEFAULT 0
CUSTOMER_ORDER.order_date DEFAULT CURRENT_DATE
CUSTOMER_ORDER.total_amount DEFAULT 0
This ensures the data is accurate.

Referential Actions
This ensures that updates/deletes are done correctly.

ON DELETE RESTRICT – This means that no customers can be deleted if they have records in orders.
ON DELETE RESTRICT – This means that no products can be deleted if they have order items referencing it.
ON UPDATE CASCADE – This means that when the primary key is updated so will the foreign keys.

Conclusion
The GameStop Inventory Database has primary keys, foreign keys, NOT NULL, UNIQUE, Check, default values and referential actions. These ensure the data is correct.

Some of the above should be recommended and added into the SQL schema.
