# Database Concept 
Database: collection of related data 

DBMS : Database Management System,It is the software that stores, organizes, and controls a database.
Examples: MySQL, PostgreSQL, SQL Server

Database System : The DBMS Software together with the Data Itself 


# Main Concepts
                 Database System
                         |
                       users
                         |
                Application Program
                        |
      DBMS  .1 Software to proccess queries
            .2 Software to stored data 
                         |
             Stored DB Meta Data : Metadata means “data about data”. It describes the data
                            Table names
                            Column names
                            Data types 
                            Constraints 
                            Relationships between tables
                            Indexes.
            Stored Data 



            
# Database Advantages 
- Less data redundancy
- Better data consistency
- Data integrity
- Backup and recovery
- Data independence .
# Database Architecture 
                         External schema : ده  الي المستخدم بيشوفه  بمعني المستخدم محتاج يشوف اي
                                 |
                        conceptual schema :   (المستوى المنطقي) relations , Tables, constrains ,   
                                              ده هو الـ ERD اللي بتحوّله لجداول (Logical Design
                                 |
                        physical schema : Internal Schema    ( Indexes, طريقه ضغط البيانلت ,ترتيب البيانات)
                     


# Database Design 

Entity Relationship Modeling : Identifies information required by the business by displaying the relevant entities and relationships between them

# How to Analyzed the Requirements
Identify Entity : هو اي شئ اي فكره اي شخص او فكره محتاج اخزن معلومات او سمات 
Identify Attributes :  COLUMN صفه او خاصيه بتوصف الكيان و بتظهر ك
Identify Relationship:  belong to , study    مثال   entities تحديد الافعال الي بتربط بين ال
Identify Cardinality  :   like 1:m M:n 1:1 
Identify Participation :   like Total Participation or partial



# Business Requirements
# System Requirements Specification (SRS)
## Project: Retail Store Management System

**Client:** Retail Store  
**Department:** Sales & Operations  
**Prepared By:** System Analysis Team  
**Document Version:** 1.0

---

## 1. Project Overview

The client operates a retail store that sells different types of products to registered customers.

The company requires a centralized transactional database to manage its customers, employees, products, and daily sales operations.

The system must maintain accurate records of every sales transaction and provide management with reliable business information.

The first release will focus on the core sales operations of a single physical store.

## 2. Data Requirements

The following entities and attributes have been identified by the System Analysis Team.

### 2.1 Customer

| Attribute | Description |
|---|---|
| Customer_ID | Unique customer identification number |
| First_Name | Customer's first name |
| Last_Name | Customer's last name |
| Phone_Number | Customer's contact number |
| Email | Customer's email address |
| Registration_Date | Date the customer registered |

**Constraints:**
- Customer_ID is unique.
- Phone_Number must be unique.
- Email is optional but must be unique when provided.
- First_Name, Last_Name, and Phone_Number are required.

### 2.2 Employee

| Attribute | Description |
|---|---|
| Employee_ID | Unique employee identification number |
| First_Name | Employee's first name |
| Last_Name | Employee's last name |
| Email | Employee's work email |
| Phone_Number | Employee's contact number |
| Job_Title | Employee's job position |
| Hire_Date | Employee's hiring date |

**Constraints:**
- Employee_ID is unique.
- Email must be unique.
- All attributes are required.

### 2.3 Category

| Attribute | Description |
|---|---|
| Category_ID | Unique category identification number |
| Category_Name | Name of the product category |
| Description | Category description |

**Constraints:**
- Category_ID is unique.
- Category_Name must be unique.
- Description is optional.

### 2.4 Product

| Attribute | Description |
|---|---|
| Product_ID | Unique product identification number |
| SKU | Product stock keeping unit |
| Product_Name | Product name |
| Description | Product description |
| Unit_Price | Current selling price |
| Stock_Quantity | Available quantity |
| Product_Status | Product availability status |
| Created_Date | Date the product was added |

**Constraints:**
- Product_ID is unique.
- SKU must be unique.
- Unit_Price must be greater than zero.
- Stock_Quantity cannot be negative.
- Product_Status accepts Active or Inactive.
- Description is optional.

### 2.5 Sales_Order

| Attribute | Description |
|---|---|
| Order_ID | Unique sales order identification number |
| Order_Date | Date and time the order was created |
| Order_Status | Current order status |
| Total_Amount | Total value of the order |

**Constraints:**
- Order_ID is unique.
- Order_Date is required.
- Order_Status accepts Draft, Completed, or Cancelled.
- Total_Amount is calculated from the order details.
- A completed order cannot be modified through normal operations.

### 2.6 Order_Item

| Attribute | Description |
|---|---|
| Order_Item_ID | Unique order item identification number |
| Quantity | Number of units purchased |
| Unit_Price | Selling price per unit at the time of sale |
| Subtotal | Total value of this order item |

**Constraints:**
- Order_Item_ID is unique.
- Quantity must be greater than zero.
- Unit_Price must be greater than zero.
- Subtotal = Quantity × Unit_Price.
- Historical Unit_Price must not change when the current product price changes.

---

## 3. Business Requirements and Operational Rules

### BR-01: Customer Registration
The system must allow employees to register new customers and maintain their information.

Customers can be registered even if they have never made a purchase.

A registered customer may return to the store and make purchases on different occasions.

### BR-02: Employee Management
The system must maintain employee records.

Employees are responsible for processing customer sales.

An employee may process several sales transactions during their employment.

Employees may exist in the system before processing their first transaction.

### BR-03: Product Categorization
The store organizes its product catalog into categories.

Every product must be assigned to a category before it becomes available for sale.

A category can be registered before any products are assigned to it.

### BR-04: Product Management
The system must allow employees to add and update product information.

A product must belong to one category.

Products can be maintained in the catalog even if they have never been sold.

Only active products can be added to new sales transactions.

### BR-05: Sales Order Creation
When a customer makes a purchase, an employee creates a sales order.

Each sales order must identify:
- The customer making the purchase.
- The employee processing the transaction.
- The date and time of the transaction.
- The current order status.
- The total order amount.

An order cannot be created without identifying the customer and the responsible employee.

A customer may make multiple sales transactions.

An employee may process multiple sales transactions.

### BR-06: Sales Order Details
A sales order may contain multiple products.

For every product added to an order, the system must record its quantity and selling price at the time of purchase.

A product may appear in sales transactions belonging to different customers.

The same product must not appear as two separate lines within the same order. Its quantity must be updated on the existing line.

A draft order may exist before any products are added.

However, an order cannot be completed unless it contains at least one product.

### BR-07: Order Calculation
The system must calculate the subtotal of every order item.

The total order amount must equal the sum of all order item subtotals.

Product prices recorded in completed sales transactions must remain unchanged for historical reporting purposes.

### BR-08: Inventory Management
The store must maintain the available stock quantity for every product.

When an order is completed, the system must deduct the quantities sold from the corresponding product stock.

Before completing an order, the system must verify that sufficient stock is available for all included products.

An order must not be completed if any product has insufficient stock.

Draft and cancelled orders must not reduce available stock.

The completion process and stock deductions must be executed consistently, so that a failed operation does not leave inventory partially updated.

### BR-09: Historical Records
Completed and cancelled orders must remain available for historical reporting.

Deleting a customer, employee, product, or category must not cause the loss of historical sales information.

---

## 4. Sales Process Scenario

The following scenario describes a typical business operation:

1. A customer registers with the store.
2. A sales employee logs into the system.
3. The customer selects three different products.
4. The employee creates a sales order under the customer's record.
5. The employee adds the selected products and their quantities.
6. The system calculates individual subtotals.
7. The system calculates the final order amount.
8. The system checks available inventory.
9. The order is completed.
10. The system updates the stock quantities.

---

## 5. Project Scope

**Included:**
- Customer Management.
- Employee Management.
- Product Management.
- Category Management.
- Sales Order Management.
- Order Items Management.
- Basic Inventory Tracking.

**Excluded from the first release:**
- Multiple branches.
- Supplier Management.
- Purchasing Management.
- Payment Processing.
- Returns and Refunds.
- Discounts and Coupons.
- Delivery Management.

---

## 6. Expected Deliverables

The Database Designer is responsible for:

1. Conceptual ERD.
2. Logical ERD.
3. Relational Mapping.
4. Database Creation Scripts (DDL).
5. Data Manipulation Scripts (DML).
6. Business SQL Queries.
7. Database Testing.

**End of Document.**



