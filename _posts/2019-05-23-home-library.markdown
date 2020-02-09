---
layout: post
title: Home Library
description: a book library management system. Because I have many ebooks and paper books so I develop this site to hope that I can share books with everyone, I base on ideas like as Goodreads social and Zlibrary share ebooks online.
date: 2019-03-25 10:59:00 +0700
categories: netcore
thumbnail: https://lh3.googleusercontent.com/FgeypeEi9nYjbCVuAcmTNfSqwAxEmNhB8pJ5rWfQooWsPRtCwq4fDBObDZ_VKoMOJO91fbAPoRNAsn7HZC6NlPXFQQfsHKDrmEEJJ_E8Y2fi6aMQEPDQDHSFNp73EQDtnAA57HO08wh5aoS2sdw7On7G6j1RHQkybv4uQUxQe7haUbepb7JMln0sE4Bdxo2LHmfA3kOPPeR5Pq_gOFt4hPjXZHqeR7MrvkobB0RRCDvtQoslIuVA-5xJbgoX74xg2O9uwGrCkI5x3v9ccBbAI5vxTmiRhDjoWH5-RO_Bnr9uQy1K-NTFWJgpf95_XkAK70AK8qqUSYb5DV2rx97-FobjnZQanqeok7z4tduYo09QbPotr9S-LFjz1WDh4rTsR32-tPiWhSsth9LIc1bU8gmEOULQhpHQtBpdODN3hWKZeS2zhgt5WOFCLOolNy7HUsH-Ejv7n5p783tFqHkCtyAeN79zFJTUEhmEns9eNZVC2z4ZYFBAMU4mVKJiFlyT9jHzuWQWDgo8hG9u9YI_COKiFIDrhzUKyKs78zxtCRKivwH2qtSzEqtJjulGXCupHlfhnXHe2suf0VPQVQLGwvGCf4oj02wpq5KqU41ZTSqR3X2gJFRwjTVjA2oTF4tH-QuaGO2CLOXrD9MSFvylWl0rrWAKVDndqO8S4boGUCUEbN2S665PYKs=w999-h634-no
---

# Demo at
- API docs: https://poststudy-library.azurewebsites.net/index.html
- Client: http://library.poststudy.s3-website-ap-southeast-1.amazonaws.com/

### Business
- Library System Management

### Design
- UML: https://www.educative.io/collection/page/5668639101419520/5692201761767424/5636470266134528
- Domain Driven Design
- CQRS

### Technical
- Backend: Dotnet Core 2.2
- The Web API is a collection of HTTP RPC-style methods
- FrontEnd: Angular 8, SPA, MVVM
- Database: MySQL 8

### Migration
- Create database: 
```
CREATE DATABASE HomeLibrary;
CREATE DATABASE DomainEventRecord;
```

- If your development have .net-core > 2.2, please force to .net-core 2.2 by create *global.json* file at root folder:

```
{
    "sdk": {
        "version": "2.2.100"
    }
}
```

- Create EFMigrateHistory table at each databases:
```
CREATE TABLE `__EFMigrationsHistory` ( `MigrationId` nvarchar(150) NOT NULL, 
`ProductVersion` nvarchar(32) NOT NULL, 
PRIMARY KEY (`MigrationId`) );
```

- If host still in use kill all prot:
```
dotnet build-server shutdown 
lsof -i:5000
```

### Index searching
- Full text index for search: 
```
ALTER TABLE Books ADD FULLTEXT (Title);
ALTER TABLE Books ADD FULLTEXT (Authors);
ALTER TABLE Books ADD FULLTEXT (Subjects);
```

- Show full text index:
```
SHOW CREATE TABLE Books;
```

- Drop full text index:
```
ALTER TABLE Books DROP INDEX Subjects;
```

### Drop if need
- Drop all table if need:
```
SET FOREIGN_KEY_CHECKS = 0; 
SET @tables = NULL;
SELECT GROUP_CONCAT(table_schema, '.', table_name) INTO @tables
  FROM information_schema.tables 
  WHERE table_schema = 'HomeLibrary'; -- specify DB name here.
SET @tables = CONCAT('DROP TABLE ', @tables);
PREPARE stmt FROM @tables;
EXECUTE stmt;
DEALLOCATE PREPARE stmt;
SET FOREIGN_KEY_CHECKS = 1; 
```

### Need TODO
- Share domain models problem
- Searching use search engine like as Elastic-search
- Event
- Deploy
- Public domain

## Reference
### Library Management System
- https://www.educative.io/collection/page/5668639101419520/5692201761767424/5636470266134528

### Keywords
- Book: book is the main object
- Rack: a rack inside a library and have many books
- Library: a library have racks and books
- Librarian: the user who mamange library, books, member,...
- Author: authors of book
- Member: the user who want to use books
- Tag: use for searching related to book
- Subject: use for classified book, like as fiction, story, technology,...
- Catalog: use for searching book with title, author, subject, tag...
- Comment: users comment for book
- Domain Driven Design
- CQRS