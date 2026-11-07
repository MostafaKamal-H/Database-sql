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

[ERD diagram](https://github.com/user-attachments/files/34516645/erd.drawio)
<mxfile host="Electron">
  <diagram name="Page-1" id="72zJpq0JiTk41Ku353fI">
    <mxGraphModel dx="1709" dy="723" grid="1" gridSize="10" guides="1" tooltips="1" connect="1" arrows="1" fold="1" page="1" pageScale="1" pageWidth="827" pageHeight="1169" math="0" shadow="0">
      <root>
        <mxCell id="0" />
        <mxCell id="1" parent="0" />
        <mxCell id="bIaEX7cATKtcx6IZL7tZ-5" edge="1" parent="1" source="bIaEX7cATKtcx6IZL7tZ-1" style="edgeStyle=orthogonalEdgeStyle;rounded=0;orthogonalLoop=1;jettySize=auto;html=1;entryX=0.5;entryY=1;entryDx=0;entryDy=0;" target="bIaEX7cATKtcx6IZL7tZ-4">
          <mxGeometry relative="1" as="geometry" />
        </mxCell>
        <mxCell id="bIaEX7cATKtcx6IZL7tZ-6" edge="1" parent="1" source="bIaEX7cATKtcx6IZL7tZ-1" style="edgeStyle=orthogonalEdgeStyle;rounded=0;orthogonalLoop=1;jettySize=auto;html=1;exitX=1;exitY=0.5;exitDx=0;exitDy=0;entryX=0.5;entryY=1;entryDx=0;entryDy=0;" target="bIaEX7cATKtcx6IZL7tZ-3">
          <mxGeometry relative="1" as="geometry" />
        </mxCell>
        <mxCell id="bIaEX7cATKtcx6IZL7tZ-7" edge="1" parent="1" source="bIaEX7cATKtcx6IZL7tZ-1" style="edgeStyle=orthogonalEdgeStyle;rounded=0;orthogonalLoop=1;jettySize=auto;html=1;" target="bIaEX7cATKtcx6IZL7tZ-2" value="">
          <mxGeometry relative="1" as="geometry" />
        </mxCell>
        <mxCell id="bIaEX7cATKtcx6IZL7tZ-43" edge="1" parent="1" source="bIaEX7cATKtcx6IZL7tZ-1" style="edgeStyle=orthogonalEdgeStyle;rounded=0;orthogonalLoop=1;jettySize=auto;html=1;" target="bIaEX7cATKtcx6IZL7tZ-41">
          <mxGeometry relative="1" as="geometry">
            <Array as="points">
              <mxPoint x="400" y="320" />
            </Array>
          </mxGeometry>
        </mxCell>
        <mxCell id="bIaEX7cATKtcx6IZL7tZ-1" parent="1" style="rounded=0;whiteSpace=wrap;html=1;" value="Customer" vertex="1">
          <mxGeometry height="60" width="120" x="350" y="200" as="geometry" />
        </mxCell>
        <mxCell id="bIaEX7cATKtcx6IZL7tZ-2" parent="1" style="ellipse;whiteSpace=wrap;html=1;shapeInside=1;fontStyle=4" value="Id" vertex="1">
          <mxGeometry height="60" width="90" x="345" y="100" as="geometry" />
        </mxCell>
        <mxCell id="bIaEX7cATKtcx6IZL7tZ-3" parent="1" style="ellipse;whiteSpace=wrap;html=1;shapeInside=1;" value="Mail" vertex="1">
          <mxGeometry height="60" width="90" x="470" y="100" as="geometry" />
        </mxCell>
        <mxCell id="bIaEX7cATKtcx6IZL7tZ-4" parent="1" style="ellipse;whiteSpace=wrap;html=1;shapeInside=1;" value="name" vertex="1">
          <mxGeometry height="60" width="90" x="230" y="100" as="geometry" />
        </mxCell>
        <mxCell id="bIaEX7cATKtcx6IZL7tZ-58" edge="1" parent="1" source="bIaEX7cATKtcx6IZL7tZ-12" style="edgeStyle=orthogonalEdgeStyle;rounded=0;orthogonalLoop=1;jettySize=auto;html=1;entryX=0.5;entryY=1;entryDx=0;entryDy=0;" target="bIaEX7cATKtcx6IZL7tZ-13">
          <mxGeometry relative="1" as="geometry">
            <Array as="points">
              <mxPoint x="1410" y="210" />
              <mxPoint x="1410" y="185" />
              <mxPoint x="1435" y="185" />
            </Array>
          </mxGeometry>
        </mxCell>
        <mxCell id="bIaEX7cATKtcx6IZL7tZ-62" edge="1" parent="1" source="bIaEX7cATKtcx6IZL7tZ-12" style="edgeStyle=orthogonalEdgeStyle;rounded=0;orthogonalLoop=1;jettySize=auto;html=1;entryX=1;entryY=0.5;entryDx=0;entryDy=0;" target="bIaEX7cATKtcx6IZL7tZ-60">
          <mxGeometry relative="1" as="geometry" />
        </mxCell>
        <mxCell id="bIaEX7cATKtcx6IZL7tZ-12" parent="1" style="rounded=0;whiteSpace=wrap;html=1;" value="Products" vertex="1">
          <mxGeometry height="60" width="120" x="1270" y="200" as="geometry" />
        </mxCell>
        <mxCell id="bIaEX7cATKtcx6IZL7tZ-13" parent="1" style="ellipse;whiteSpace=wrap;html=1;shapeInside=1;" value="price" vertex="1">
          <mxGeometry height="60" width="90" x="1390" y="105" as="geometry" />
        </mxCell>
        <mxCell id="bIaEX7cATKtcx6IZL7tZ-33" edge="1" parent="1" source="bIaEX7cATKtcx6IZL7tZ-15" style="edgeStyle=orthogonalEdgeStyle;rounded=0;orthogonalLoop=1;jettySize=auto;html=1;exitX=0.5;exitY=1;exitDx=0;exitDy=0;entryX=0.5;entryY=0;entryDx=0;entryDy=0;" target="bIaEX7cATKtcx6IZL7tZ-12">
          <mxGeometry relative="1" as="geometry" />
        </mxCell>
        <mxCell id="bIaEX7cATKtcx6IZL7tZ-15" parent="1" style="ellipse;whiteSpace=wrap;html=1;shapeInside=1;fontStyle=4" value="Id" vertex="1">
          <mxGeometry height="50" width="105" x="1277.5" y="95" as="geometry" />
        </mxCell>
        <mxCell id="bIaEX7cATKtcx6IZL7tZ-57" edge="1" parent="1" source="bIaEX7cATKtcx6IZL7tZ-16" style="edgeStyle=orthogonalEdgeStyle;rounded=0;orthogonalLoop=1;jettySize=auto;html=1;entryX=0;entryY=0;entryDx=0;entryDy=0;" target="bIaEX7cATKtcx6IZL7tZ-12">
          <mxGeometry relative="1" as="geometry" />
        </mxCell>
        <mxCell id="bIaEX7cATKtcx6IZL7tZ-16" parent="1" style="ellipse;whiteSpace=wrap;html=1;shapeInside=1;rotation=0;" value="name" vertex="1">
          <mxGeometry height="50" width="80" x="1170" y="90" as="geometry" />
        </mxCell>
        <mxCell id="bIaEX7cATKtcx6IZL7tZ-39" edge="1" parent="1" source="bIaEX7cATKtcx6IZL7tZ-36" style="edgeStyle=orthogonalEdgeStyle;rounded=0;orthogonalLoop=1;jettySize=auto;html=1;" target="bIaEX7cATKtcx6IZL7tZ-38" value="">
          <mxGeometry relative="1" as="geometry" />
        </mxCell>
        <mxCell id="K24DuPq0Bi-DtG7BQWcg-4" edge="1" parent="1" source="bIaEX7cATKtcx6IZL7tZ-36" style="edgeStyle=orthogonalEdgeStyle;shape=link;rounded=0;orthogonalLoop=1;jettySize=auto;html=1;exitX=1;exitY=0.5;exitDx=0;exitDy=0;entryX=0;entryY=0.5;entryDx=0;entryDy=0;" target="bIaEX7cATKtcx6IZL7tZ-49">
          <mxGeometry relative="1" as="geometry" />
        </mxCell>
        <mxCell id="bIaEX7cATKtcx6IZL7tZ-36" parent="1" style="rounded=0;whiteSpace=wrap;html=1;" value="Order" vertex="1">
          <mxGeometry height="60" width="120" x="640.5" y="200" as="geometry" />
        </mxCell>
        <mxCell id="bIaEX7cATKtcx6IZL7tZ-38" parent="1" style="ellipse;whiteSpace=wrap;html=1;shapeInside=1;rounded=0;" value="order-date" vertex="1">
          <mxGeometry height="40" width="105" x="648" y="110" as="geometry" />
        </mxCell>
        <mxCell id="K24DuPq0Bi-DtG7BQWcg-2" edge="1" parent="1" source="bIaEX7cATKtcx6IZL7tZ-41" style="edgeStyle=orthogonalEdgeStyle;shape=link;rounded=0;orthogonalLoop=1;jettySize=auto;html=1;exitX=1;exitY=0.5;exitDx=0;exitDy=0;entryX=0.5;entryY=1;entryDx=0;entryDy=0;" target="bIaEX7cATKtcx6IZL7tZ-36">
          <mxGeometry relative="1" as="geometry" />
        </mxCell>
        <mxCell id="bIaEX7cATKtcx6IZL7tZ-41" parent="1" style="rhombus;whiteSpace=wrap;html=1;shapeInside=1;" value="places" vertex="1">
          <mxGeometry height="80" width="80" x="520" y="280" as="geometry" />
        </mxCell>
        <mxCell id="bIaEX7cATKtcx6IZL7tZ-44" parent="1" style="text;html=1;whiteSpace=wrap;strokeColor=none;fillColor=none;align=center;verticalAlign=middle;rounded=0;" value="1" vertex="1">
          <mxGeometry height="30" width="60" x="390" y="290" as="geometry" />
        </mxCell>
        <mxCell id="bIaEX7cATKtcx6IZL7tZ-46" parent="1" style="text;html=1;whiteSpace=wrap;strokeColor=none;fillColor=none;align=center;verticalAlign=middle;rounded=0;" value="M" vertex="1">
          <mxGeometry height="30" width="60" x="648" y="290" as="geometry" />
        </mxCell>
        <mxCell id="K24DuPq0Bi-DtG7BQWcg-3" edge="1" parent="1" source="bIaEX7cATKtcx6IZL7tZ-49" style="edgeStyle=orthogonalEdgeStyle;shape=link;rounded=0;orthogonalLoop=1;jettySize=auto;html=1;exitX=1;exitY=0.5;exitDx=0;exitDy=0;" target="bIaEX7cATKtcx6IZL7tZ-51">
          <mxGeometry relative="1" as="geometry" />
        </mxCell>
        <mxCell id="bIaEX7cATKtcx6IZL7tZ-49" parent="1" style="rhombus;whiteSpace=wrap;html=1;shapeInside=1;rounded=0;" value="Contains" vertex="1">
          <mxGeometry height="60" width="80" x="825" y="200" as="geometry" />
        </mxCell>
        <mxCell id="bIaEX7cATKtcx6IZL7tZ-56" edge="1" parent="1" source="bIaEX7cATKtcx6IZL7tZ-51" style="edgeStyle=orthogonalEdgeStyle;rounded=0;orthogonalLoop=1;jettySize=auto;html=1;" target="bIaEX7cATKtcx6IZL7tZ-55" value="">
          <mxGeometry relative="1" as="geometry" />
        </mxCell>
        <mxCell id="K24DuPq0Bi-DtG7BQWcg-5" edge="1" parent="1" source="bIaEX7cATKtcx6IZL7tZ-51" style="edgeStyle=orthogonalEdgeStyle;shape=link;rounded=0;orthogonalLoop=1;jettySize=auto;html=1;exitX=0.5;exitY=1;exitDx=0;exitDy=0;entryX=0;entryY=0.5;entryDx=0;entryDy=0;" target="bIaEX7cATKtcx6IZL7tZ-60">
          <mxGeometry relative="1" as="geometry" />
        </mxCell>
        <mxCell id="bIaEX7cATKtcx6IZL7tZ-51" parent="1" style="whiteSpace=wrap;html=1;rounded=0;" value="Order-item" vertex="1">
          <mxGeometry height="60" width="105" x="980" y="200" as="geometry" />
        </mxCell>
        <mxCell id="bIaEX7cATKtcx6IZL7tZ-53" parent="1" style="text;html=1;whiteSpace=wrap;strokeColor=none;fillColor=none;align=center;verticalAlign=middle;rounded=0;" value="1" vertex="1">
          <mxGeometry height="30" width="60" x="750" y="200" as="geometry" />
        </mxCell>
        <mxCell id="bIaEX7cATKtcx6IZL7tZ-54" parent="1" style="text;html=1;whiteSpace=wrap;strokeColor=none;fillColor=none;align=center;verticalAlign=middle;rounded=0;" value="M" vertex="1">
          <mxGeometry height="30" width="60" x="920" y="200" as="geometry" />
        </mxCell>
        <mxCell id="bIaEX7cATKtcx6IZL7tZ-55" parent="1" style="ellipse;whiteSpace=wrap;html=1;shapeInside=1;rounded=0;" value="Quantity" vertex="1">
          <mxGeometry height="40" width="80" x="992.5" y="100" as="geometry" />
        </mxCell>
        <mxCell id="bIaEX7cATKtcx6IZL7tZ-60" parent="1" style="rhombus;whiteSpace=wrap;html=1;shapeInside=1;" value="Represent" vertex="1">
          <mxGeometry height="70" width="70" x="1140" y="250" as="geometry" />
        </mxCell>
        <mxCell id="bIaEX7cATKtcx6IZL7tZ-63" parent="1" style="text;html=1;whiteSpace=wrap;strokeColor=none;fillColor=none;align=center;verticalAlign=middle;rounded=0;" value="M" vertex="1">
          <mxGeometry height="30" width="60" x="1072.5" y="200" as="geometry" />
        </mxCell>
        <mxCell id="bIaEX7cATKtcx6IZL7tZ-64" parent="1" style="text;html=1;whiteSpace=wrap;strokeColor=none;fillColor=none;align=center;verticalAlign=middle;rounded=0;" value="1" vertex="1">
          <mxGeometry height="30" width="60" x="1220" y="200" as="geometry" />
        </mxCell>
      </root>
    </mxGraphModel>
  </diagram>
</mxfile>

