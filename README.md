# MySQL Dump Backup

This is a short snippet of code to dump a logical backup of a MySQL database
and upload it to a WebDAV server.

## Installation

You can install the script simply issuing the command `sudo install dbbackup
/path/to/install/location` from the command line.

## Setup

Once you have installed it remember to configure the MySQL client and the
remote WebDAV server credentials. Specifically prepare two files such as:

  - **~/.my.cnf**:
```shell
[client]
user = username
password = the_password
```
  - **~/.dbdumpbackup/config** (create with `mkdir ~/.dbdumpbackup`):
```shell
USR="username"
PSW="the password"
DBNAME="database name"
REMOTE="WebDAV location"
```

Remember to issue `chmod 600 ~/.my.cnf ~/.dbdumpbackup/config` for security
reasons.

## Crontab

You can have the script run as a cron job issuing `crontab -e` as your user and
add something like `00 12 * * * /path/to/install/location/dbbackup` to run
`dbbackup` every day at noon.

## License

This is free software available freely under the **MIT License**.
