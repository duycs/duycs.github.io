---
layout: post
title: SSO Server Identity
description: Create a Single sign on authentication server, support development many applications with only once sign on.
date: 2019-12-04 10:59:00 +0700
categories: demo
thumbnail: https://drive.google.com/file/d/1rfcOXlrsO4MXlYGYKkHIdAQcwZsJZkAA/view?usp=sharing
---

![](https://drive.google.com/file/d/1rfcOXlrsO4MXlYGYKkHIdAQcwZsJZkAA/view?usp=sharing)

## Criteria
Create a Single sign on authentication server, support development many applications with only once sign on

## Sources
- Server: [https://github.com/duycs/sso-server](https://github.com/duycs/sso-server){:.text-link}
- Client: [https://github.com/duycs/sso-oauth-client](https://github.com/duycs/sso-oauth-client){:.text-link}

## Development environment
- Visual Studio Code
- IdentityServer4
- MySQL

## Setup

### To run the demo

**1.** Clone/Fork this repository
[https://github.com/duycs/sso-server](https://github.com/duycs/sso-server){:.text-link}

**2.** Create the database on MySQL server by using the dotnet cli to run the migrations from within the command

### Create EFMigrateHistory table at each database
```
CREATE TABLE `__EFMigrationsHistory` ( `MigrationId` nvarchar(150) NOT NULL, 
`ProductVersion` nvarchar(32) NOT NULL, 
PRIMARY KEY (`MigrationId`) );
```

### Migrate database

<pre><code>dotnet ef database update --context AppIdentityDbContext</code></pre>
<pre><code>dotnet ef database update --context PersistedGrantDbContext</code></pre>

### TODO
- Fix bugs
- 

---
### References
- https://en.wikipedia.org/wiki/Single_sign-on
- https://github.com/mmacneil/AngularASPNETCoreOAuth
- https://github.com/echuck66/ASPNETMVCCoreTest
