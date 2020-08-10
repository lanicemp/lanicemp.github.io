---
layout: post
title:      "How I Overcame My PostgreSQL Connection and Role Error "
date:       2020-08-09 15:22:20 -0400
permalink:  how_i_overcame_my_postgresql_connection_and_role_error
---



  When I started my JavaScript project I decided that I wanted to use PostgreSQL for my database instead of MySQL so that I would be successful when deploying my project onto Heroku.   It is necessary to have a PostgreSQL database in order to have Heroku host your application. To avoid the headache later of converting my database from MySQL to PostgreSQL, I started with PostgreSQL.   I started building of my project and encountered and error…. 


```
	psql: error: could not connect to server: could not connect to server: No such file or directory
        Is the server running locally and accepting
       connections on Unix domain socket "/var/run/postgresql/.s.PGSQL.5432"
```


This was alarming, so I started my research on how to resolve this error.  This began with downloading PostgreSQL  onto my windows laptop.  I thought that would have better results but I still encountered the same error.  After days of trying to trouble shoot I ended up uninstalling the PostgreSQL that I downloaded from their site. 

I found a website that showed much more promise.  [https://medium.com/@harshityadav95/postgresql-in-windows-subsystem-for-linux-wsl-6dc751ac1ff3](http://) by Hardhit Yadav, and followed his instructions on how to remove the error.   These commands were very helpful and easy to follow. Furthermore by following his directions  I was able to successfully overcome my connection error.  I began another project. 

```
rails new <app_name> --api --database=postgresql
rails g scaffold <your_tables> 
rails db:create
```

	
BAM!!!! Another error 

```
FATAL:  role "<role_name>" does not exist
Couldn't create '<app_name>_development' database. Please check your configuration.
rails aborted!
PG::ConnectionBad: FATAL:  role "<role_name>" does not exist
```

	
ARGGGG!!!

Okay, but guess what! I have connection! No more connection error.   One step in the right direction.  I preceded to  research about how to overcome this role error.  And what is a role??? 

```
"A role is a collection of privileges that can be granted to one or more users or other roles. Roles help you grant and manage sets of privileges for various categories of users, rather than grant those privileges to each user individually."
```


The error states that my role does not exist, so,  I have to exist to overcome this error.  I head to google and ask "How to create a role in PostgreSQL?"  I found another helpful site with commands[ https://www.postgresql.org/docs/8.1/sql-createrole.html](http://)

Yayyy!!

So in order for me to implement these commands I have to start back up my PostgreSQL server, and create the role. 

```
sudo service postgresql start (if its not started) 
sudo -u postgres psql
postgres=# CREATE ROLE <role_name> with CREATEDB CREATEROLE
```

It went through no error!! .I ` \q` out of there and tried again. 
 
`rails db:create`

	
BAM Another error!

```
FATAL:  role "<role_name>" is not permitted to log in
Couldn't create '<app_name>_development' database. Please check your configuration.
rails aborted!
PG::ConnectionBad: FATAL:  role "<role_name>" is not permitted to log in
```


Do you see that my role_name exist!!!! I still have an error but the role exist now. :) Trouble shoot some more.  Back to Google….  "how to permit login for a role in PostgreSQL?" I found a new command on how to alter the role.  Let's get back into postgres

```
sudo -u postgres psql
postgres=# ALTER ROLE <role_name> with LOGIN CREATEDB CREATEROLE
```
No error in altering the role then.` /q` out of postgres and try again. 

 ```
rails db:create
WARNING:  could not flush dirty data: Function not implemented
Created database '<app_name>_development'
WARNING:  could not flush dirty data: Function not implemented
Created database '<app_name>_test'
```

	
Great that worked! But in retrospect I think I could of avoided the login error if I would have created a login when I initially created the role using the code below 

	`CREATE ROLE <role_name> WITH LOGIN CREATEDB CREATEROLE`
	
	
I'm glad that is resolved, and the data base was created!! I can now move on with my application and it is running on PostgreSQL. 

Resources:
*  [<https://www.google.com/search?q=what+is+a+role+in+database&oq=What+is+a+role+in+da&aqs=chrome.1.69i57j0l7.5991j1j7&sourceid=chrome&ie=UTF-8> ](http://)

* [https://medium.com/@harshityadav95/postgresql-in-windows-subsystem-for-linux-wsl-6dc751ac1ff3 ](http://)
* [https://www.postgresql.org/docs/8.1/sql-createrole.html
](http://)
