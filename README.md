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
                     
