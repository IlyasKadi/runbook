# MSSQL

## nmap

```shell
nmap -oN nmap/1433.logs -p 1433 -sV --script vuln,ms-sql-info
```

Other scripts are

```shell
ms-sql-empty-password
```