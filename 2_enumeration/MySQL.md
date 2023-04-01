# MySQL

## nmap

```shell
nmap -oN nmap/scan_mysql.logs -p 3306 -sV --script mysql-empty-password $ip
```

Other scripts are

```shell
mysql-info
```

## clients

Log in to MySQL server using the cli

```shell
mysql --user username --host $ip -p
```
