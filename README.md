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
## Project: Library Management System

**Project Type:** Transactional Database (OLTP)  
**Project Scope:** Single Library  
**Entities:** 4

---

## 1. Project Overview

A library requires a database system to manage its books, physical book copies, registered members, and borrowing operations.

The system must allow the library to register new members, maintain its book catalog, track individual book copies, and record borrowing and return operations.

The main objective is to maintain accurate records of library activities and track the availability of physical book copies.

## 2. Required Data

### 2.1 Members

The system must maintain the following information for each registered member:

| Attribute | Description |
|---|---|
| Member_ID | Unique member identification number |
| First_Name | Member's first name |
| Last_Name | Member's last name |
| Email | Member's email address |
| Phone | Member's phone number |
| Registration_Date | Date the member registered |

**Business Rules:**
- Every member must have a unique Member_ID.
- Email addresses must be unique.
- A member can be registered even if they have never borrowed a book.

### 2.2 Books

The library must maintain a catalog of all books available in its collection.

Each book record must contain:

| Attribute | Description |
|---|---|
| Book_ID | Unique book identification number |
| Title | Book title |
| ISBN | International Standard Book Number |
| Author | Book author |
| Publication_Year | Year of publication |
| Available_Copies | Number of currently available copies |

**Business Rules:**
- Every book must have a unique Book_ID.
- ISBN must be unique.
- Available_Copies cannot be negative.
- A book can be registered even if it has never been borrowed.

### 2.3 Borrowing

The system must record every borrowing operation performed by a library member.

Each borrowing record must contain:

| Attribute | Description |
|---|---|
| Borrowing_ID | Unique borrowing identification number |
| Borrowing_Date | Date the book was borrowed |
| Due_Date | Expected return date |
| Return_Date | Actual return date |

**Business Rules:**
- Every borrowing operation must have a unique Borrowing_ID.
- The system must identify the member who borrowed the book.
- The system must identify the specific physical copy being borrowed.
- A member may borrow books on multiple occasions.
- The actual return date must be recorded when the borrowed copy is returned.
- Return_Date cannot be earlier than Borrowing_Date.
- A physical copy cannot be borrowed again while it is already borrowed.

### 2.4 Book Copies

The library needs to track each physical copy of a book separately.

Each physical copy must contain the following information:

| Attribute | Description |
|---|---|
| Copy_ID | Unique identification number for the physical copy |
| Copy_Status | Current status of the copy |
| Acquisition_Date | Date the copy was acquired by the library |

**Business Rules:**
- Every physical copy must have a unique Copy_ID.
- Each physical copy must belong to a specific book.
- A book may have multiple physical copies.
- Copy_Status must support the following values:
  - Available
  - Borrowed
  - Damaged
- Damaged copies cannot be borrowed.
- A borrowed copy becomes available again after it is returned, provided it is not damaged.

## 3. General Business Rules

1. A member must be registered before borrowing a book.
2. Every borrowing operation must be associated with an existing member.
3. Every borrowing operation must identify one specific physical book copy.
4. The library must preserve historical borrowing records after books are returned.
5. The system must update the physical copy's status when it is borrowed or returned.
6. The library must maintain the distinction between a book title and its individual physical copies.

## 4. Project Scope

**Included:**
- Member Registration.
- Book Catalog Management.
- Physical Book Copy Management.
- Borrowing Management.
- Book Return Management.

**Excluded:**
- Financial Fines and Penalties.
- Book Reservations.
- Employee Management.
- Multiple Library Branches.

---

**End of Business Requirements Document.**

[DATABASE ERD.drawio](https://github.com/user-attachments/files/34517886/DATABASE.ERD.drawio)


<mxfile host="Electron">
  <diagram name="Page-1" id="GWGypTb2kf2xozXeal3F">
    <mxGraphModel dx="1514" dy="790" grid="1" gridSize="10" guides="1" tooltips="1" connect="1" arrows="1" fold="1" page="1" pageScale="1" pageWidth="827" pageHeight="1169" math="0" shadow="0">
      <root>
        <mxCell id="0" />
        <mxCell id="1" parent="0" />
        <mxCell id="23JTafLmVhfkPfJm8UxH-10" edge="1" parent="1" source="23JTafLmVhfkPfJm8UxH-2" style="edgeStyle=orthogonalEdgeStyle;rounded=0;orthogonalLoop=1;jettySize=auto;html=1;entryX=1;entryY=1;entryDx=0;entryDy=0;" target="23JTafLmVhfkPfJm8UxH-6">
          <mxGeometry relative="1" as="geometry" />
        </mxCell>
        <mxCell id="23JTafLmVhfkPfJm8UxH-14" edge="1" parent="1" source="23JTafLmVhfkPfJm8UxH-2" style="edgeStyle=orthogonalEdgeStyle;rounded=0;orthogonalLoop=1;jettySize=auto;html=1;exitX=1;exitY=0.5;exitDx=0;exitDy=0;entryX=0;entryY=0.5;entryDx=0;entryDy=0;" target="23JTafLmVhfkPfJm8UxH-8">
          <mxGeometry relative="1" as="geometry" />
        </mxCell>
        <mxCell id="23JTafLmVhfkPfJm8UxH-53" edge="1" parent="1" source="23JTafLmVhfkPfJm8UxH-2" style="edgeStyle=orthogonalEdgeStyle;rounded=0;orthogonalLoop=1;jettySize=auto;html=1;exitX=0.5;exitY=1;exitDx=0;exitDy=0;" target="23JTafLmVhfkPfJm8UxH-55">
          <mxGeometry relative="1" as="geometry">
            <mxPoint x="620" y="460" as="targetPoint" />
          </mxGeometry>
        </mxCell>
        <mxCell id="23JTafLmVhfkPfJm8UxH-2" parent="1" style="rounded=0;whiteSpace=wrap;html=1;" value="Members" vertex="1">
          <mxGeometry height="60" width="114" x="370" y="315" as="geometry" />
        </mxCell>
        <mxCell id="23JTafLmVhfkPfJm8UxH-3" parent="1" style="ellipse;whiteSpace=wrap;html=1;shapeInside=1;" value="&lt;br&gt;&lt;u&gt;Member_ID&lt;/u&gt;" vertex="1">
          <mxGeometry height="50" width="100" x="364" y="230" as="geometry" />
        </mxCell>
        <mxCell id="23JTafLmVhfkPfJm8UxH-4" parent="1" style="ellipse;whiteSpace=wrap;html=1;shapeInside=1;" value="Email" vertex="1">
          <mxGeometry height="50" width="90" x="250" y="230" as="geometry" />
        </mxCell>
        <mxCell id="23JTafLmVhfkPfJm8UxH-5" parent="1" style="ellipse;whiteSpace=wrap;html=1;shapeInside=1;" value="Phone_number" vertex="1">
          <mxGeometry height="50" width="90" x="480" y="230" as="geometry" />
        </mxCell>
        <mxCell id="23JTafLmVhfkPfJm8UxH-6" parent="1" style="ellipse;whiteSpace=wrap;html=1;shapeInside=1;" value="First_name" vertex="1">
          <mxGeometry height="50" width="90" x="250" y="310" as="geometry" />
        </mxCell>
        <mxCell id="23JTafLmVhfkPfJm8UxH-7" parent="1" style="ellipse;whiteSpace=wrap;html=1;shapeInside=1;" value="Last_name" vertex="1">
          <mxGeometry height="50" width="90" x="250" y="370" as="geometry" />
        </mxCell>
        <mxCell id="23JTafLmVhfkPfJm8UxH-8" parent="1" style="ellipse;whiteSpace=wrap;html=1;shapeInside=1;" value="&lt;div&gt;&lt;br&gt;&lt;/div&gt;&lt;div&gt;Registration_Date&lt;/div&gt;" vertex="1">
          <mxGeometry height="50" width="100" x="560" y="270" as="geometry" />
        </mxCell>
        <mxCell id="23JTafLmVhfkPfJm8UxH-9" edge="1" parent="1" source="23JTafLmVhfkPfJm8UxH-2" style="edgeStyle=orthogonalEdgeStyle;rounded=0;orthogonalLoop=1;jettySize=auto;html=1;exitX=0.5;exitY=0;exitDx=0;exitDy=0;entryX=0.604;entryY=1;entryDx=0;entryDy=0;entryPerimeter=0;" target="23JTafLmVhfkPfJm8UxH-3">
          <mxGeometry relative="1" as="geometry" />
        </mxCell>
        <mxCell id="23JTafLmVhfkPfJm8UxH-11" edge="1" parent="1" source="23JTafLmVhfkPfJm8UxH-2" style="edgeStyle=orthogonalEdgeStyle;rounded=0;orthogonalLoop=1;jettySize=auto;html=1;exitX=0;exitY=1;exitDx=0;exitDy=0;entryX=0.996;entryY=0.648;entryDx=0;entryDy=0;entryPerimeter=0;" target="23JTafLmVhfkPfJm8UxH-7">
          <mxGeometry relative="1" as="geometry" />
        </mxCell>
        <mxCell id="23JTafLmVhfkPfJm8UxH-12" edge="1" parent="1" source="23JTafLmVhfkPfJm8UxH-2" style="edgeStyle=orthogonalEdgeStyle;rounded=0;orthogonalLoop=1;jettySize=auto;html=1;exitX=0;exitY=0;exitDx=0;exitDy=0;entryX=0.684;entryY=0.936;entryDx=0;entryDy=0;entryPerimeter=0;" target="23JTafLmVhfkPfJm8UxH-4">
          <mxGeometry relative="1" as="geometry" />
        </mxCell>
        <mxCell id="23JTafLmVhfkPfJm8UxH-13" edge="1" parent="1" source="23JTafLmVhfkPfJm8UxH-2" style="edgeStyle=orthogonalEdgeStyle;rounded=0;orthogonalLoop=1;jettySize=auto;html=1;exitX=1;exitY=0;exitDx=0;exitDy=0;entryX=0.422;entryY=1.016;entryDx=0;entryDy=0;entryPerimeter=0;" target="23JTafLmVhfkPfJm8UxH-5">
          <mxGeometry relative="1" as="geometry" />
        </mxCell>
        <mxCell id="23JTafLmVhfkPfJm8UxH-15" edge="1" parent="1" source="23JTafLmVhfkPfJm8UxH-17" style="edgeStyle=orthogonalEdgeStyle;rounded=0;orthogonalLoop=1;jettySize=auto;html=1;entryX=1;entryY=1;entryDx=0;entryDy=0;" target="23JTafLmVhfkPfJm8UxH-21">
          <mxGeometry relative="1" as="geometry" />
        </mxCell>
        <mxCell id="23JTafLmVhfkPfJm8UxH-16" edge="1" parent="1" source="23JTafLmVhfkPfJm8UxH-17" style="edgeStyle=orthogonalEdgeStyle;rounded=0;orthogonalLoop=1;jettySize=auto;html=1;exitX=1;exitY=0.5;exitDx=0;exitDy=0;entryX=0;entryY=0.5;entryDx=0;entryDy=0;">
          <mxGeometry relative="1" as="geometry">
            <mxPoint x="1420" y="345.00000000000006" as="targetPoint" />
          </mxGeometry>
        </mxCell>
        <mxCell id="23JTafLmVhfkPfJm8UxH-58" edge="1" parent="1" source="23JTafLmVhfkPfJm8UxH-17" style="edgeStyle=orthogonalEdgeStyle;rounded=0;orthogonalLoop=1;jettySize=auto;html=1;exitX=0.5;exitY=1;exitDx=0;exitDy=0;" target="23JTafLmVhfkPfJm8UxH-59">
          <mxGeometry relative="1" as="geometry">
            <mxPoint x="1327.5789473684208" y="600.0000000000002" as="targetPoint" />
          </mxGeometry>
        </mxCell>
        <mxCell id="23JTafLmVhfkPfJm8UxH-17" parent="1" style="rounded=0;whiteSpace=wrap;html=1;" value="Books" vertex="1">
          <mxGeometry height="60" width="114" x="1270" y="315.00000000000006" as="geometry" />
        </mxCell>
        <mxCell id="23JTafLmVhfkPfJm8UxH-18" parent="1" style="ellipse;whiteSpace=wrap;html=1;shapeInside=1;" value="&lt;u&gt;Book_id&lt;/u&gt;" vertex="1">
          <mxGeometry height="50" width="100" x="1270" y="231.8" as="geometry" />
        </mxCell>
        <mxCell id="23JTafLmVhfkPfJm8UxH-19" parent="1" style="ellipse;whiteSpace=wrap;html=1;shapeInside=1;" value="Title" vertex="1">
          <mxGeometry height="50" width="90" x="1160" y="226.8" as="geometry" />
        </mxCell>
        <mxCell id="23JTafLmVhfkPfJm8UxH-20" parent="1" style="ellipse;whiteSpace=wrap;html=1;shapeInside=1;" value="&lt;br&gt;ISBN&lt;br&gt;&lt;div&gt;&lt;br/&gt;&lt;/div&gt;" vertex="1">
          <mxGeometry height="50" width="90" x="1370" y="231.8" as="geometry" />
        </mxCell>
        <mxCell id="23JTafLmVhfkPfJm8UxH-21" parent="1" style="ellipse;whiteSpace=wrap;html=1;shapeInside=1;" value="Author" vertex="1">
          <mxGeometry height="50" width="90" x="1150" y="310.00000000000006" as="geometry" />
        </mxCell>
        <mxCell id="23JTafLmVhfkPfJm8UxH-22" parent="1" style="ellipse;whiteSpace=wrap;html=1;shapeInside=1;" value="Publication_Year" vertex="1">
          <mxGeometry height="50" width="90" x="1150" y="370.00000000000006" as="geometry" />
        </mxCell>
        <mxCell id="23JTafLmVhfkPfJm8UxH-23" parent="1" style="ellipse;whiteSpace=wrap;html=1;shapeInside=1;" value="&lt;br&gt;Available_Copies&lt;br&gt;&lt;div&gt;&lt;br/&gt;&lt;/div&gt;" vertex="1">
          <mxGeometry height="50" width="100" x="1420" y="320.00000000000006" as="geometry" />
        </mxCell>
        <mxCell id="23JTafLmVhfkPfJm8UxH-24" edge="1" parent="1" source="23JTafLmVhfkPfJm8UxH-17" style="edgeStyle=orthogonalEdgeStyle;rounded=0;orthogonalLoop=1;jettySize=auto;html=1;exitX=0.5;exitY=0;exitDx=0;exitDy=0;entryX=0.604;entryY=1;entryDx=0;entryDy=0;entryPerimeter=0;">
          <mxGeometry relative="1" as="geometry">
            <mxPoint x="1324.4" y="280.00000000000006" as="targetPoint" />
          </mxGeometry>
        </mxCell>
        <mxCell id="23JTafLmVhfkPfJm8UxH-25" edge="1" parent="1" source="23JTafLmVhfkPfJm8UxH-17" style="edgeStyle=orthogonalEdgeStyle;rounded=0;orthogonalLoop=1;jettySize=auto;html=1;exitX=0;exitY=1;exitDx=0;exitDy=0;entryX=0.996;entryY=0.648;entryDx=0;entryDy=0;entryPerimeter=0;" target="23JTafLmVhfkPfJm8UxH-22">
          <mxGeometry relative="1" as="geometry" />
        </mxCell>
        <mxCell id="23JTafLmVhfkPfJm8UxH-26" edge="1" parent="1" source="23JTafLmVhfkPfJm8UxH-17" style="edgeStyle=orthogonalEdgeStyle;rounded=0;orthogonalLoop=1;jettySize=auto;html=1;exitX=0;exitY=0;exitDx=0;exitDy=0;entryX=0.684;entryY=0.936;entryDx=0;entryDy=0;entryPerimeter=0;">
          <mxGeometry relative="1" as="geometry">
            <mxPoint x="1211.5599999999997" y="276.80000000000024" as="targetPoint" />
          </mxGeometry>
        </mxCell>
        <mxCell id="23JTafLmVhfkPfJm8UxH-27" edge="1" parent="1" source="23JTafLmVhfkPfJm8UxH-17" style="edgeStyle=orthogonalEdgeStyle;rounded=0;orthogonalLoop=1;jettySize=auto;html=1;exitX=1;exitY=0;exitDx=0;exitDy=0;entryX=0.422;entryY=1.016;entryDx=0;entryDy=0;entryPerimeter=0;">
          <mxGeometry relative="1" as="geometry">
            <mxPoint x="1417.98" y="280.80000000000024" as="targetPoint" />
          </mxGeometry>
        </mxCell>
        <mxCell id="23JTafLmVhfkPfJm8UxH-28" edge="1" parent="1" source="23JTafLmVhfkPfJm8UxH-30" style="edgeStyle=orthogonalEdgeStyle;rounded=0;orthogonalLoop=1;jettySize=auto;html=1;entryX=1;entryY=1;entryDx=0;entryDy=0;" target="23JTafLmVhfkPfJm8UxH-34">
          <mxGeometry relative="1" as="geometry" />
        </mxCell>
        <mxCell id="23JTafLmVhfkPfJm8UxH-66" edge="1" parent="1" source="23JTafLmVhfkPfJm8UxH-30" style="edgeStyle=orthogonalEdgeStyle;shape=link;rounded=0;orthogonalLoop=1;jettySize=auto;html=1;exitX=0;exitY=1;exitDx=0;exitDy=0;entryX=1;entryY=0.5;entryDx=0;entryDy=0;" target="23JTafLmVhfkPfJm8UxH-55">
          <mxGeometry relative="1" as="geometry" />
        </mxCell>
        <mxCell id="23JTafLmVhfkPfJm8UxH-77" edge="1" parent="1" source="23JTafLmVhfkPfJm8UxH-30" style="edgeStyle=orthogonalEdgeStyle;shape=link;rounded=0;orthogonalLoop=1;jettySize=auto;html=1;exitX=0.5;exitY=1;exitDx=0;exitDy=0;entryX=0.5;entryY=0;entryDx=0;entryDy=0;" target="23JTafLmVhfkPfJm8UxH-62">
          <mxGeometry relative="1" as="geometry" />
        </mxCell>
        <mxCell id="23JTafLmVhfkPfJm8UxH-30" parent="1" style="rounded=0;whiteSpace=wrap;html=1;" value="&lt;h3&gt;Borrowing&lt;/h3&gt;" vertex="1">
          <mxGeometry height="60" width="114" x="820" y="318.20000000000005" as="geometry" />
        </mxCell>
        <mxCell id="23JTafLmVhfkPfJm8UxH-31" parent="1" style="ellipse;whiteSpace=wrap;html=1;shapeInside=1;" value="&lt;u&gt;Borrowing_ID&lt;/u&gt;" vertex="1">
          <mxGeometry height="50" width="100" x="820" y="235.00000000000003" as="geometry" />
        </mxCell>
        <mxCell id="23JTafLmVhfkPfJm8UxH-32" parent="1" style="ellipse;whiteSpace=wrap;html=1;shapeInside=1;" value="Due_Date" vertex="1">
          <mxGeometry height="50" width="90" x="710" y="230.00000000000003" as="geometry" />
        </mxCell>
        <mxCell id="23JTafLmVhfkPfJm8UxH-33" parent="1" style="ellipse;whiteSpace=wrap;html=1;shapeInside=1;" value="&lt;div&gt;Borrowing_Date&lt;/div&gt;" vertex="1">
          <mxGeometry height="50" width="90" x="920" y="235.00000000000003" as="geometry" />
        </mxCell>
        <mxCell id="23JTafLmVhfkPfJm8UxH-34" parent="1" style="ellipse;whiteSpace=wrap;html=1;shapeInside=1;" value="Return_Date" vertex="1">
          <mxGeometry height="50" width="90" x="700" y="313.20000000000005" as="geometry" />
        </mxCell>
        <mxCell id="23JTafLmVhfkPfJm8UxH-37" edge="1" parent="1" source="23JTafLmVhfkPfJm8UxH-30" style="edgeStyle=orthogonalEdgeStyle;rounded=0;orthogonalLoop=1;jettySize=auto;html=1;exitX=0.5;exitY=0;exitDx=0;exitDy=0;entryX=0.604;entryY=1;entryDx=0;entryDy=0;entryPerimeter=0;">
          <mxGeometry relative="1" as="geometry">
            <mxPoint x="874.4000000000001" y="283.20000000000005" as="targetPoint" />
          </mxGeometry>
        </mxCell>
        <mxCell id="23JTafLmVhfkPfJm8UxH-39" edge="1" parent="1" source="23JTafLmVhfkPfJm8UxH-30" style="edgeStyle=orthogonalEdgeStyle;rounded=0;orthogonalLoop=1;jettySize=auto;html=1;exitX=0;exitY=0;exitDx=0;exitDy=0;entryX=0.684;entryY=0.936;entryDx=0;entryDy=0;entryPerimeter=0;">
          <mxGeometry relative="1" as="geometry">
            <mxPoint x="761.5599999999997" y="280.0000000000002" as="targetPoint" />
          </mxGeometry>
        </mxCell>
        <mxCell id="23JTafLmVhfkPfJm8UxH-40" edge="1" parent="1" source="23JTafLmVhfkPfJm8UxH-30" style="edgeStyle=orthogonalEdgeStyle;rounded=0;orthogonalLoop=1;jettySize=auto;html=1;exitX=1;exitY=0;exitDx=0;exitDy=0;entryX=0.422;entryY=1.016;entryDx=0;entryDy=0;entryPerimeter=0;">
          <mxGeometry relative="1" as="geometry">
            <mxPoint x="967.98" y="284.0000000000002" as="targetPoint" />
          </mxGeometry>
        </mxCell>
        <mxCell id="23JTafLmVhfkPfJm8UxH-41" edge="1" parent="1" source="23JTafLmVhfkPfJm8UxH-42" style="edgeStyle=orthogonalEdgeStyle;rounded=0;orthogonalLoop=1;jettySize=auto;html=1;entryX=1;entryY=1;entryDx=0;entryDy=0;" target="23JTafLmVhfkPfJm8UxH-45">
          <mxGeometry relative="1" as="geometry" />
        </mxCell>
        <mxCell id="23JTafLmVhfkPfJm8UxH-61" edge="1" parent="1" source="23JTafLmVhfkPfJm8UxH-42" style="edgeStyle=orthogonalEdgeStyle;rounded=0;orthogonalLoop=1;jettySize=auto;html=1;exitX=0.5;exitY=1;exitDx=0;exitDy=0;" target="23JTafLmVhfkPfJm8UxH-62">
          <mxGeometry relative="1" as="geometry">
            <mxPoint x="870" y="618.578947368421" as="targetPoint" />
          </mxGeometry>
        </mxCell>
        <mxCell id="23JTafLmVhfkPfJm8UxH-73" edge="1" parent="1" source="23JTafLmVhfkPfJm8UxH-42" style="edgeStyle=orthogonalEdgeStyle;shape=link;rounded=0;orthogonalLoop=1;jettySize=auto;html=1;exitX=1;exitY=1;exitDx=0;exitDy=0;entryX=0;entryY=0.5;entryDx=0;entryDy=0;" target="23JTafLmVhfkPfJm8UxH-59">
          <mxGeometry relative="1" as="geometry" />
        </mxCell>
        <mxCell id="23JTafLmVhfkPfJm8UxH-42" parent="1" style="rounded=0;whiteSpace=wrap;html=1;" value="&lt;h3&gt;Book_Copies&lt;/h3&gt;" vertex="1">
          <mxGeometry height="60" width="114" x="1054" y="558.2" as="geometry" />
        </mxCell>
        <mxCell id="23JTafLmVhfkPfJm8UxH-43" parent="1" style="ellipse;whiteSpace=wrap;html=1;shapeInside=1;" value="Copy_id" vertex="1">
          <mxGeometry height="50" width="100" x="1054" y="475" as="geometry" />
        </mxCell>
        <mxCell id="23JTafLmVhfkPfJm8UxH-44" parent="1" style="ellipse;whiteSpace=wrap;html=1;shapeInside=1;" value="&lt;table&gt;&lt;tbody&gt;&lt;tr&gt;&lt;td&gt;&lt;br&gt;&lt;table&gt;&lt;tbody&gt;&lt;tr&gt;&lt;td&gt;Copy_Status&lt;/td&gt;&lt;/tr&gt;&lt;/tbody&gt;&lt;/table&gt;&lt;/td&gt;&lt;/tr&gt;&lt;/tbody&gt;&lt;/table&gt;" vertex="1">
          <mxGeometry height="50" width="90" x="944" y="470" as="geometry" />
        </mxCell>
        <mxCell id="23JTafLmVhfkPfJm8UxH-45" parent="1" style="ellipse;whiteSpace=wrap;html=1;shapeInside=1;" value="&lt;br&gt;&lt;table&gt;&lt;tbody&gt;&lt;tr&gt;&lt;td&gt;&lt;table&gt;&lt;tbody&gt;&lt;tr&gt;&lt;td&gt;Acquisition_Date&lt;/td&gt;&lt;/tr&gt;&lt;/tbody&gt;&lt;/table&gt;&lt;/td&gt;&lt;/tr&gt;&lt;/tbody&gt;&lt;/table&gt;&lt;br&gt;&lt;div&gt;&lt;br/&gt;&lt;/div&gt;" vertex="1">
          <mxGeometry height="50" width="90" x="920" y="540" as="geometry" />
        </mxCell>
        <mxCell id="23JTafLmVhfkPfJm8UxH-46" edge="1" parent="1" source="23JTafLmVhfkPfJm8UxH-42" style="edgeStyle=orthogonalEdgeStyle;rounded=0;orthogonalLoop=1;jettySize=auto;html=1;exitX=0.5;exitY=0;exitDx=0;exitDy=0;entryX=0.604;entryY=1;entryDx=0;entryDy=0;entryPerimeter=0;">
          <mxGeometry relative="1" as="geometry">
            <mxPoint x="1108.4" y="523.2" as="targetPoint" />
          </mxGeometry>
        </mxCell>
        <mxCell id="23JTafLmVhfkPfJm8UxH-47" edge="1" parent="1" source="23JTafLmVhfkPfJm8UxH-42" style="edgeStyle=orthogonalEdgeStyle;rounded=0;orthogonalLoop=1;jettySize=auto;html=1;exitX=0;exitY=0;exitDx=0;exitDy=0;entryX=0.684;entryY=0.936;entryDx=0;entryDy=0;entryPerimeter=0;">
          <mxGeometry relative="1" as="geometry">
            <mxPoint x="995.5599999999997" y="520.0000000000002" as="targetPoint" />
          </mxGeometry>
        </mxCell>
        <mxCell id="23JTafLmVhfkPfJm8UxH-55" parent="1" style="rhombus;whiteSpace=wrap;html=1;shapeInside=1;" value="Places" vertex="1">
          <mxGeometry height="80" width="80" x="600" y="410" as="geometry" />
        </mxCell>
        <mxCell id="23JTafLmVhfkPfJm8UxH-59" parent="1" style="rhombus;whiteSpace=wrap;html=1;shapeInside=1;" value="has&amp;nbsp;" vertex="1">
          <mxGeometry height="80" width="80" x="1286.9989473684209" y="558.2000000000003" as="geometry" />
        </mxCell>
        <mxCell id="23JTafLmVhfkPfJm8UxH-62" parent="1" style="rhombus;whiteSpace=wrap;html=1;shapeInside=1;" value="Borrowed" vertex="1">
          <mxGeometry height="80" width="80" x="830" y="578.578947368421" as="geometry" />
        </mxCell>
        <mxCell id="23JTafLmVhfkPfJm8UxH-67" parent="1" style="text;html=1;whiteSpace=wrap;strokeColor=none;fillColor=none;align=center;verticalAlign=middle;rounded=0;" value="1" vertex="1">
          <mxGeometry height="30" width="60" x="480" y="360" as="geometry" />
        </mxCell>
        <mxCell id="23JTafLmVhfkPfJm8UxH-68" parent="1" style="text;html=1;whiteSpace=wrap;strokeColor=none;fillColor=none;align=center;verticalAlign=middle;rounded=0;" value="M" vertex="1">
          <mxGeometry height="30" width="60" x="670" y="420" as="geometry" />
        </mxCell>
        <mxCell id="23JTafLmVhfkPfJm8UxH-69" parent="1" style="text;html=1;whiteSpace=wrap;strokeColor=none;fillColor=none;align=center;verticalAlign=middle;rounded=0;" value="1" vertex="1">
          <mxGeometry height="30" width="60" x="1280" y="370" as="geometry" />
        </mxCell>
        <mxCell id="23JTafLmVhfkPfJm8UxH-70" parent="1" style="text;html=1;whiteSpace=wrap;strokeColor=none;fillColor=none;align=center;verticalAlign=middle;rounded=0;" value="M" vertex="1">
          <mxGeometry height="30" width="60" x="1170" y="570" as="geometry" />
        </mxCell>
        <mxCell id="23JTafLmVhfkPfJm8UxH-74" parent="1" style="text;html=1;whiteSpace=wrap;strokeColor=none;fillColor=none;align=center;verticalAlign=middle;rounded=0;" value="1" vertex="1">
          <mxGeometry height="30" width="60" x="1010" y="600" as="geometry" />
        </mxCell>
        <mxCell id="23JTafLmVhfkPfJm8UxH-76" parent="1" style="text;html=1;whiteSpace=wrap;strokeColor=none;fillColor=none;align=center;verticalAlign=middle;rounded=0;" value="M" vertex="1">
          <mxGeometry height="30" width="60" x="880" y="390" as="geometry" />
        </mxCell>
      </root>
    </mxGraphModel>
  </diagram>
</mxfile>
