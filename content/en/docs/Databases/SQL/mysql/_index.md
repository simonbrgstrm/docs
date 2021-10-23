
---
title: "Mysql/Mariadb"
linkTitle: "Mysql/Mariadb"
date: 2017-01-05
description: >
  A short lead description about this section page. Text here can also be **bold** or _italic_ and can even be split over multiple paragraphs.
---

{{% pageinfo %}}
This is a placeholder page. Replace it with your own content.
{{% /pageinfo %}}


This is the section landing page.

### Create user

Create new localhost user.
```mysql
mysql> CREATE USER 'newuser'@'localhost' IDENTIFIED BY 'password';
```
Or global user.
```mysql
mysql> CREATE USER 'newuser'@'%' IDENTIFIED BY 'password';
```

Grant all privileges.
```mysql
mysql> GRANT ALL PRIVILEGES ON * . * TO 'newuser'@'localhost';
```

Flush.
```mysql
mysql> FLUSH PRIVILEGES;
```

### How To Grant Different User Permissions

Here is a short list of other common possible permissions that users can enjoy.

- ALL PRIVILEGES- as we saw previously, this would allow a MySQL user full access to a designated database (or if no database is selected, global access across the system)
- CREATE- allows them to create new tables or databases
- DROP- allows them to them to delete tables or databases
- DELETE- allows them to delete rows from tables
- INSERT- allows them to insert rows into tables
- SELECT- allows them to use the SELECT command to read through databases
- UPDATE- allow them to update table rows
- GRANT OPTION- allows them to grant or remove other users’ privileges

To provide a specific user with a permission, you can use this framework:

```mysql
mysql> GRANT type_of_permission ON database_name.table_name TO 'username'@'localhost';
```

If you want to give them access to any database or to any table, make sure to put an asterisk (*) in the place of the database name or table name.

Each time you update or change a permission be sure to use the Flush Privileges command.

If you need to revoke a permission, the structure is almost identical to granting it:

```mysql
mysql> REVOKE type_of_permission ON database_name.table_name FROM 'username'@'localhost';
```

You can review a user’s current permissions by running the following:

```mysql
mysql> SHOW GRANTS FOR 'username'@'localhost';
```

Just as you can delete databases with DROP, you can use DROP to delete a user altogether:

```mysql
mysql> DROP USER 'username'@'localhost';
```

