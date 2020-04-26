---
layout: post
title: Security for Web
description: Some secure for Web Application
date: 2020-04-26 10:59:00 +0700
categories: demo
thumbnail: https://lh3.googleusercontent.com/mzg-ak3wXzexOEzSC3A9bpEItvrFlMJRpbRw5Kca5XJQOYkK9D711Yk_yoAN-gAbNRgqp8V2Umq6Oqgb5OsgwW7FGSGB-mWAF_CIEiFbeve4IjN_7QUlntPyQVlyI9rKpKb_hPrR1oaR0Ja7g6sdUX6Pq0ow3tnax2-qQ7w-lxcRf0R5HrAR8WlK0owO1z9wPZvWckrRnMKPG1gHOgVe1JtSLHnqJax-Cz9CWQ3iI6td6mfD0UZSWGsxMgBvnvoXTkVutmeJlaHA8Hv_mBJupEA21On3TpOXGB7QTcDda5nYcm5Vnh407FU0BtsyLoNe74ZU8Lg94sjYbXYA93-XkGIwwlZArLSZqppj2M_1ssBM2bmfbsP73tsDyZcxc0gvt79MlzvGOkhbh-zChtKRtVETi1q27YNxnYcBL7rDXY8Z2kfElTiJkmOmHv2xpC9i7lSPfBI3t4OlIFDlXcZqVZTI1Z4i6XfpIbSBJh7jfEKDYfimYJQu0n0GtE12HCw4B32TmwH0jt9GXRZJOAmexwdfr1GpQAE-UryKzqqnetOJ57yslr37jJE5b5YPSzb-PVRKoPQld133IQtI9ldLLUf0hEue3QYg-f23Tq15-eZZ3moBsaxncnpc48hk6PT4sGCho3tJd2jN_RbV7C-ejZLbDnIlFE6Hd-okWk8h3MjpSqqofzTAj-Oa4UJekJmEiT4CFwUpm46IQ6okWcdpEZnHxDfnL8znC1zGfzQ4b98IoGF8-ftIA-o=w828-h358-no
---

![](https://lh3.googleusercontent.com/mzg-ak3wXzexOEzSC3A9bpEItvrFlMJRpbRw5Kca5XJQOYkK9D711Yk_yoAN-gAbNRgqp8V2Umq6Oqgb5OsgwW7FGSGB-mWAF_CIEiFbeve4IjN_7QUlntPyQVlyI9rKpKb_hPrR1oaR0Ja7g6sdUX6Pq0ow3tnax2-qQ7w-lxcRf0R5HrAR8WlK0owO1z9wPZvWckrRnMKPG1gHOgVe1JtSLHnqJax-Cz9CWQ3iI6td6mfD0UZSWGsxMgBvnvoXTkVutmeJlaHA8Hv_mBJupEA21On3TpOXGB7QTcDda5nYcm5Vnh407FU0BtsyLoNe74ZU8Lg94sjYbXYA93-XkGIwwlZArLSZqppj2M_1ssBM2bmfbsP73tsDyZcxc0gvt79MlzvGOkhbh-zChtKRtVETi1q27YNxnYcBL7rDXY8Z2kfElTiJkmOmHv2xpC9i7lSPfBI3t4OlIFDlXcZqVZTI1Z4i6XfpIbSBJh7jfEKDYfimYJQu0n0GtE12HCw4B32TmwH0jt9GXRZJOAmexwdfr1GpQAE-UryKzqqnetOJ57yslr37jJE5b5YPSzb-PVRKoPQld133IQtI9ldLLUf0hEue3QYg-f23Tq15-eZZ3moBsaxncnpc48hk6PT4sGCho3tJd2jN_RbV7C-ejZLbDnIlFE6Hd-okWk8h3MjpSqqofzTAj-Oa4UJekJmEiT4CFwUpm46IQ6okWcdpEZnHxDfnL8znC1zGfzQ4b98IoGF8-ftIA-o=w828-h358-no)

### Criteria
Some secure for Web Application

### Keyword
- OWASP
- Injection
- Broken Authentication and Session Management
- Cross Site Scripting (XSS)
- Insecure Direct Object References
- Security Misconfiguration
- Sensitive Data Exposure
- Missing Function Level Access Control
- Cross Site Request Forgrey (CSRF)
- Using Known Vulnerable Components
- Unvalidated Redirects and Forwards

### 1. OWASP
- The Open Web Application Security Project (OWASP) is a nonprofit foundation that works to improve the security of software. Through community-led open source software projects, hundreds of local chapters worldwide, tens of thousands of members, and leading educational and training conferences, the OWASP Foundation is the source for developers and technologists to secure the web.

- You can see top 10 web application security risks at https://owasp.org/www-project-top-ten/

### 2. Injection
#### 2.1 SQL Injection
##### Secenario
- Current system: Query without checking
```
FindUser(username, password){
    String sql = "select * from users where user_name = '" + username + "' and password = '" + encrypt(password) "'";
    contextDatabase.executeQuery(sql);
}
```
- Hacker action: Input ```username = test' or '1'='1```, the sql have been executed alway true:
```
.... user_name = 'test' or '1'='1' and ...
```
- Result: Get all users of the database

##### Prevent
- Verify input data
- Don't use concatenated params with string query, use Prepared Statements (Parameterized queries).
Django use (Prepared query: https://django-prepared-query.readthedocs.io/en/latest/)
- White list input validation

#### 2.2 OS Command Injection
###### Secenario
- Current system: A method action with command
```
ExecuteFile(String fileName){
    String file = 'fileName';
    String command = "/usr/bin/find . -name " + fileName;
    process = Runtime.getRuntime();
    process.exec(command);
}
```
- Hacker action: Input fileName = "abc.txt; rm -rf *"
- Result: All fields will be deleted

##### Prevent
- Verify data input
- Use white list, regular expression to verify the character allowed to use..

### 3. Broken Authentication and Session Management
##### Secenario
- Current system:
Password is not strong (default, week password...)\
Leaked Session IDs show in the URL\
Doesn't properly invalidate Session IDs\
Doesn't roate Session IDs after login sucessful\

- Hacker action: check to detect and steal passwords, session to fake users

##### Prevent
- Storage password need to encryption, strong password, multi-factor authentication,...
- Limit or increasingly delay failed login attempts
- Server alway check logging in with an avalible session ID
- Server always create new Session ID when user log in
- Server remove the Session ID when user log out
- Server set expiration time for the session
- Client set HTTPOnly cookies

### 4. Cross Site Scripting (XSS)
##### Secenario
- Current system: A resource of Patient with body data ``` name: Joker``` need to save to the database via method POST /api/patient 
- Hacker action: Change value of field name to a script ``` name: http:evil-script.io``` then submit to save to the database
- Result: method get this resource GET /api/patient/x will load the script on client then execute them

Hacker injection HTLM or malicius scripts into client web site. There are 3 type of XSS attract:
- XSS Reflected: Send link directly to the user to trick the user into cliking on the link then stealing cookies or session
- Dom base XSS: Change the website structure, tricking users into entering information to stals it
- Stored XSS: Directly insert malicious code the database

##### Prevent
- Verify data input with white list characters allowed to use
- Encode HTML characters by htmlspecialchars()
- Use Content Security Policy to execute Javascript from whitelist domain

### 5. Insecure Direct Object References
##### Secenario
- Current system: A Ecommerce system don't authorization correct user, every user is the same permission
- Hacker action: Change parameters between 2 users 
- Result: Will be leaked users information

##### Prevent
- Server check permissions to execute on each request function
- Check permissions to manipulate function on the data in the request

### 6. Security Misconfiguration
##### Secenario
- Current system: A config file in web application easy to see config admin account like as ```...username = "admin" password = "admin"...```
- Hacker action: Steal configuration file then use admin account infomation to attract the system.
- Result: System be attracted 

##### Prevent 
- Use a check list to check configuration be careful and safe
- Don't store production configuration at source code, this information should be configured at deployment environment

### 7. Sensitive Data Exposure
##### Secenario 1
- Current system: A system when user input wrong login, the system show sensitive infomation such as wrong password, wrong username. 
- Hacker action: Hacker can easy known to focus attract this field
- Result: System be attracted

##### Secenario 2
- Current system: A banking system be attracted, then database and log file can be expose, 
- Hacker action: After have data, many sensitive data can be exploited such as user information
- Result: Causing harm to users

##### Prevent
- System doesn't show sensitive data
- Should encrypt all sensitive data at rest by MD5, SHA2...

### 8. Missing Function Level Access Control
##### Secenario
- Current system: System have url ```https:bank.com/user/getAccounts``` for normal user login then get information, but allow this user change url to have higer permissions ```https:bank.com/admin/getAccount``` 
- Hacker action: Change url to hack information of admin
- Result: System be attracted

##### Prevent
- Use role-base access control (RBAC) to check permission for each request

### 9. Cross Site Request Forgrey (CSRF)
##### Secenario
- Current system: Web site don't have any token or session to check user for submit request, example a Change-password page don't check token
- Hacker action: Create a fake Change-password to deceive users to change passwords as the hacker wanted
- Result: System be attracted

##### Prevent
- Use token check authentication

### 10. Using Known Vulnerable Components
##### Secenario
- Current system: Plugin, library, feature, files components which are not enough security
- Hacker action: Find security holes of components then attract
- Result: System be attracted

##### Prevent
- Remove unused dependences, feature, component, files...
- Only obtain components from offical source over secure links
- Update, enhance security for components

### 11. Unvalidated Redirects and Forwards
##### Secenario
- Current system: Allow easy to redirect to another website, this reditect website can not safe enough
- Hacker: Create fake links to deceive users into clicking
- Result: Steal user information

##### Prevent
- Check redirect and show up for user confirm

---
### References
- https://owasp.org/
- https://owasp.org/www-project-top-ten/
- https://django-prepared-query.readthedocs.io/en/latest/
- https://developer.mozilla.org/en-US/docs/Web/HTTP/Cookies
