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
Identify Entity   

Identify Attributes 

Identify Relationship:  belong to , study    مثال   entities تحديد الافعال الي بتربط بين ال

Identify Cardinality  :   like 1:m M:n 1:1 

Identify Participation :   like Total Participation or partial



# Business Requirements Document (BRD)
## Project: Order Management System

### 1. Project Overview

The company requires a database system to manage customers, products, and customer orders.

The system must allow customers to place orders containing different products. The company needs to maintain order information and track the quantities of products included in each order.

### 2. Customer Management

The system must maintain customer records containing:
- Customer ID.
- Customer Name.
- Customer Email.

Each registered customer must have a unique identifier.

Customers must be registered in the system before placing orders.

A customer may register without placing any orders.

### 3. Product Management

The system must maintain a catalog of available products.

Each product record must contain:
- Product ID.
- Product Name.
- Product Price.

Each product must have a unique identifier.

Products can exist in the system even if they have never been included in an order.

### 4. Order Management

Whenever a customer makes a purchase, the system must create an order.

Each order must maintain its creation date.

Every order must be associated with the customer who placed it.

An order must contain at least one order item.

A customer can place multiple orders over time.

### 5. Order Items Management

An order can contain multiple products.

For every product included in an order, the system must record the purchased quantity.

The same product can be included in different orders.

Each order item must refer to an existing order and an existing product.

### 6. Business Constraints

- Customers can exist without placing orders.
- Orders cannot exist without a registered customer.
- Orders must contain at least one order item.
- Products can exist without being included in orders.
- Every order item must belong to an order and refer to a product.
- Product prices must be greater than zero.
- Purchased quantities must be greater than zero.

**End of Business Requirements Document.**

[TASK 2.drawio](https://github.com/user-attachments/files/34516587/TASK.2.drawio)

