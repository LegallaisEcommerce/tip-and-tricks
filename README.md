tip-and-tricks
==============

# MySQL on MacOS

## Load big dump "MySQL has gone away"

edit:
```sh
sudo vim /usr/local/mysql/my.cnf
```

add line:

```sh
max_allowed_packet = 512M
```

restart MySQL:

```sh
sudo /usr/local/mysql/support-files/mysql.server restart
```

