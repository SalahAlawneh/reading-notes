# DB Normalization
- normalizing database in organising the database in tables and columns every one of them will be for just one category
- There  three main reasons to normalize a database:
1. minimize duplicate data
1. avoid data modication issues
1. simplify queries.
- problems that come with duplicated information:
  - It increases storage and decrease performance.
  - It becomes more difcult to maintain data changes.
- we cannot insert until we know the entire row
- thre is three types of normalization databases:
1. First Normal Form – The information is stored in a relational table with each
column containing atomic values. There are no repeating groups of columns.
1. Second Normal Form – The table is in first normal form and all the columns
depend on the table’s primary key.
1. Third Normal Form – the table is in second normal form and all of its columns
are not transitively dependent on the primary key
