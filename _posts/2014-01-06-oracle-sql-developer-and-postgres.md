---
layout: post
title: "Oracle SQL Developer and PostgreSQL"
description: ""
category: 
tags: [oracle postgresql database jdbc sql gui]
---
[Oracle SQL Developer](http://www.thatjeffsmith.com/sql-developer) isn't the sexiest choice of SQL GUIs, but it works and I use it anyway to connect to Oracle databases at work. Besides, PostgreSQL GUI app choices are [pretty underwhelming](http://wiki.postgresql.org/wiki/Community_Guide_to_PostgreSQL_GUI_Tools); the best ones are all JDBC clients anyway, and I already have one of those. So here's how you use SQL Developer as a PostgreSQL database GUI.

* Download [PostgreSQL JDBC 4.1 driver](http://jdbc.postgresql.org/download/postgresql-9.3-1100.jdbc41.jar) and put it somewhere.
* In the SQL Developer Preferences Menu, navigate to *Database* » *Third Party JDBC Drivers*. Click **Add Entry** and select postgresql-9.3-1100.jdbc41.jar. Click **OK**.
* When you add a new connection, the bottom half of the dialog should now have Oracle and PostgreSQL tabs. You can connect, but only to your user database. **Choose Database** looks like it should work, but clicking it gives this helpful error:

![Failure -Select the Connection Name / User Name / Password](https://s3.amazonaws.com/substars_github_io_images/sqldeveloper_1.png "Failure -Select the Connection Name / User Name / Password")

* Put something--anything!--in the *Connection Name* field, and your username in the *Username* field. Click **Choose Database** again:

![oraclicious](https://s3.amazonaws.com/substars_github_io_images/sqldeveloper_2.png "oraclicious")

Now you can connect and query away as usual, even **Migrate to Oracle** with a simple right click in the connection browser if you dare.


