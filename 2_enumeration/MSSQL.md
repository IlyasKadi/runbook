# MSSQL

## nmap

```shell
nmap -oN nmap/scan_mssql.logs -p 1433 -sV --script=ms-sql-info
```

Other scripts are

```shell
ms-sql-empty-password
```