# Class 12 Notes

## SQL vs NoSQL

### Differences explained

- ***SQL***
  - called Relational Databases (RDBMS)
  - table based 
  - rows of data
  - predefined scheme
  - vertically scalable
  - uses SQL databases by increasing power of hardware

- ***NoSQL***
  - non relational
  - document base
  - key value pairs
  - dynamic
  - horizontally scalable
  - queries focused on collection of docs

## SQL Database Examples

### MySQL Community Ed

- ![MySQLdatabase](https://www.thegeekstuff.com/2008/07/howto-install-mysql-on-linux/)

### MS-SQL Server Express Edition

- powerful, user friendly database which has good stability and support from MSFT

- disaster recovery

- cloud backup

### Oracle

- limited edition of Oracle Enterprise Edition server

- easy upgrade

- wide support

## NoSQL Database Examples

### MongoDB

- one of most popular

- stores data in JSON

- speed

- scale

- manageable

- dynamic scheme

### CouchDB

- Scheme-less

- HTTP query - can cross DB docs using web browser

- conflict resolution

- easy replication

### Redis

- open source

- very fast!

## NoSQL modeling Techniques

- often compared by various non functional critera, like scalability 

### General Notes

- NoSQL data modeling often starts from the application-specific queries as opposed to relational modeling

- requires a deeper understanding of data structure

- data duplication and denormalization are first-class citizens

### Conceptual Techniques

- Denormalization
  - defined as the copying of the same data into multiple documents or tables in order to simplify query processing
  - helpful for the following tradeoffs
    - query data volume or IO per query vs total data volume

- Aggregates
  - key value stores and graph database
  - big table models
  - doc database are inherently schema-less

- Application Side Joins
  - Many to many relationships are often modeled by links and require joins
  - often inapplicable when entry internals are the subject of frequent modifications

- Atomic Aggregates
  - not all NoSQL solutions have limited transaction support
  - one can achieve transac behavior using destributed locks
  - Key-Value Stores, Document Databases, BigTable-style Databases

- Enumerable Keys
  - Key-Value Stores

- Dimensionality Reduction
  - Key-Value Stores, Document Databases, BigTable-style Databases

- Index Table
  - BigTable-style Databases

- Composite key Index
  - BigTable-style Databases

- Aggregation with Composite Keys
  - Ordered Key-Value Stores, BigTable-style Databases

- Inverted Search - DIrect Aggregation
  - Key-Value Stores, BigTable-style Databases, Document Databases

- Tree Aggregation
  - Key-Value Stores, Document Databases

- Adjacency Lists
  - Key-Value Stores, Document Databases

- Materialized Paths
  - Key-Value Stores, Document Databases, Search Engines

- Nested Sets
  - Key-Value Stores, Document Databases

- Nested Documents Flattening: Numbered Field Names
  - Search Engines

- Nested Documents Flattening: Proximity Queries
  - Search Engines

- Batch Graph Processing
  - Key-Value Stores, Document Databases, BigTable-style Databases