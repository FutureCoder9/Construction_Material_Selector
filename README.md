
# Construction Material Selector Database

### Overview 

This project sets up a database for a construction company's e-commerce platform, allowing clients to choose finishing materials for their orders. The database schema includes tables for customers, suppliers, materials, orders, invoices, and order details. A trigger ensures data integrity by verifying that the total area specified in the orders matches the sum of areas in the order finishes.

The project helps manage a construction company's e-commerce operations by keeping track of customers, suppliers, materials, orders, invoices, and order details, while ensuring data integrity through the use of a trigger. Clients can pick their finishing materials from the website, and the system calculates the total surface area and other related metrics for the orders.

So, picture this: a client clicks through the website, selects their favorite marble slab, and voilà! Our system calculates the total surface area, crunches the numbers, and delivers a seamless order experience. It’s like magic, but with SQL.

### Detailed Explanation

1. **Customer Table**: Stores information about customers including their ID, name, surname, address, and email. The `Customer_ID` is the primary key.

2. **Supplier Table**: Stores information about suppliers including their ID, name, postal code, and email. The `Supplier_ID` is the primary key.

3. **Material Table**: Stores information about materials including their ID, name, and the supplier ID. The `Material_ID` is the primary key, and `Supplier_ID` is a foreign key referencing the `Supplier` table.

4. **Product Table**: Stores details about products available for orders. The `Product_ID` is the primary key, and `Material_ID` and `Subcontractor_ID` are foreign keys referencing the `Material` and `Subcontractor` tables, respectively.

5. **Finish_Type Table**: Stores information about different types of finishes. The `Finish_Type_ID` is the primary key.

6. **Orders Table**: Stores information about orders including order ID, customer ID, order type, product type, product location, product ID, and total area. The `Order_ID` is the primary key, and `Customer_ID` is a foreign key referencing the `Customer` table.

7. **Invoice Table**: Stores invoice information including invoice ID, customer ID, order ID, price, tax, dates, due date, and total. The `Invoice_ID` is the primary key, and `Order_ID` is a foreign key referencing the `Orders` table.

8. **Order_Detail Table**: Stores details of the orders including order detail ID, order ID, material ID, quantity, and unit price. The `Order_Detail_ID` is the primary key, and `Order_ID` and `Material_ID` are foreign keys referencing the `Orders` and `Material` tables, respectively.

9. **Order_Finish Table**: Stores information about the finishes applied to orders including order finish ID, order ID, finish type ID, area, and percentage. The `Order_Finish_ID` is the primary key, and `Order_ID` and `Finish_Type_ID` are foreign keys referencing the `Orders` and `Finish_Type` tables, respectively.

10. **Trigger to Ensure Data Integrity**: Ensures that the sum of all areas in the `Order_Finish` table for each order matches the `Total_Area` in the `Orders` table.

### Trigger Explanation

The trigger ensures that the sum of all areas in the `Order_Finish` table for each order matches the `Total_Area` in the `Orders` table, thereby maintaining data integrity.
