# POP3

## nmap

```shell
nmap -oN nmap/110.logs -p 110 -sV --script pop3-capabilities $ip
```

## clients 
Below we provide basic commands to interact with a POP3 server.

```
telnet $ip 110
```

```
USER username
```

```
PASS password
```

```
STAT
```

```
LIST
```

```
RETR nr
```

