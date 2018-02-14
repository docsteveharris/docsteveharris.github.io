---
title: My SQL setup
Slug: my-sql-setup
category: blog
tags: [howto, tips, methods, sweetsetup]
status: published
comments: true
image:
  feature:
excerpt:

---

Install MySQL via homebrew

    brew install mysql

Data will be stored by default at `/usr/local/var/mysql`. You can confirm this as follows:

    $>mysql.server start
    $>mysql -u root
    mysql> select @@datadir;
    +-----------------------+
    | @@datadir             |
    +-----------------------+
    | /usr/local/var/mysql/ |
    +-----------------------+
    1 row in set (0.00 sec)
    $>mysql.server stop

Moving the data directory means editing the `my.cnf` file at `my.cnf` which can exist in multiple locations. See below ...

    $>my_print_defaults --help
    ...
    Default options are read from the following files in the given order:
    /etc/my.cnf /etc/mysql/my.cnf /usr/local/etc/my.cnf ~/.my.cnf
    ...

I edited `/usr/local/etc/my.cnf`. This worked and didn't require root privileges. Make sure the server has been stopped before you do this.

My data directory is at `/volumes/safe/sql' and my file currently looks like:

    [mysqld]
    # Default Homebrew MySQL server config
    # Only allow connections from localhost
    bind-address = 127.0.0.1

    datadir=/volumes/safe/sql

    [client]
    port=3306


## Useful links

- [How to Change a MySQL Data Directory to a New Location on CentOS 7](https://www.digitalocean.com/community/tutorials/how-to-change-a-mysql-data-directory-to-a-new-location-on-centos-7)
- [For homebrew mysql installs, where's my.cnf?](https://stackoverflow.com/questions/7973927/for-homebrew-mysql-installs-wheres-my-cnf)
