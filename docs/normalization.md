There are 8 tables in our database. The tables are: Store, Product, Inventory, Customer, Customer_Order, Order_Item, Employee and Supplier.

1st Normal Form
Each table has single values in each column. Each record has a unique identifier.

Our database is in 1 st Normal form as:
Each table has a primary key. Each column has single values. Any repeated values have been put into separate records.
For example each piece of information regarding the customer has been put into separate columns (first_name, last_name, email, phone).
2nd Normal Form
Database must be in 1st Normal form. All non-key attributes are fully functionally dependent on the primary key.
Our database is in 2nd Normal form as:
All tables have a primary key. Product information has been put into its own table. Order information has been split into its own table.
For example Inventory Table has store_id, product_id and quantity. Product Table has product_name, category and price.
3rd Normal Form
Database must be in 2nd Normal form. Non-key attributes cannot be functionally dependent on other non-key attributes.
Our database is in 3 rd Normal form.

Customer information has been put into the Customer table. Supplier information has been put into the Supplier table. Product information has been put into the Product table. Customer information has been referenced in the Order Table.
For example Customer Order Table references customer_id.
Modifications to the Database

The database was designed to split the information into different tables. We did the following:
Split customer information into a Customer Table. Split product information into a Product Table. Split order information into a Customer Order Table. Created an Order Item table to link orders and products. Split supplier information into a Supplier Table. Used an Inventory Table to show how many products are in each store.
Conclusion
The GameStop Inventory Database has been designed to be in 1st, 2nd and 3rd Normal form. By splitting the data into the correct tables there is less duplication, it is more accurate and easier to maintain.
