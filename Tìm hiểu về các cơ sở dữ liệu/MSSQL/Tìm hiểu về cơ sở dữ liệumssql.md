# Hệ cơ sở dữ liệu MSSQL 
## Tổng quan 

1. What is the microsoft SQL ?

- Microsoft SQL server í a relational database management system that support a wide variety of transaction processing , business intelligence and anlytics application in corporate IT enviromants . Microsoft SQL Server is one of the three market-leading database technologies , along with Oracle Database and IBM's (DB2)
- Inside SQL Server's architecture -- How SQL Server works
  - Like other RDBMS technologies , SQL Server is primarily built around a row-based table structure that connects related data elemants in different tables , The relational madel also provides refertial integrity and other integrity constraints to maintain data accuracy , isolation and durabillity, coolectively known as the ACID properties , and are designed to guuaratee

  - the core component of Microsoft SQL Server is the SQL Server Database Enginbe , which controls data storage , processing and security . Includes a relational engine that processes commands and queres and a storage engine that manages database file , tables , page, indexes , databuffers and transations . Stored procedures , triggers , views and other database objects are also created and executed by the Database Engine .

  - Setting beneath the Database Engine is the SQL Operating SYStem or SQLOS . SQLOS handles lower-level funtions , such as memory and I/O management, job scheduling and locking of data to avoid conflicting update , A network interface layer sits above the Database Engine and uses MS Tabular Data Stream protocol to facciliate requestand response interactions with database servers . aaaaand at the user level , SQL server DBAs and developers write T- SQL statements to built and modify database structures , manipulate data , implement security protection and back up database , among other tasks. 