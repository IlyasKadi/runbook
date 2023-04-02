# MSSQL

## nmap

```shell
nmap -oN nmap/scan_1433.logs -p 1433 -sV --script ms-sql-info
```

Other scripts are

```shell
ms-sql-empty-password
```