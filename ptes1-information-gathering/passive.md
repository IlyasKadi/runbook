# passive

## Passive information gathering

- Get domain registrar information
```shell
whois example.com
```

- Disover hosts related to a domain using [https://dnsdumpster.com/](https://dnsdumpster.com/).

- Perform a DNS zone transfer using

```shell
dig -t AXFR example.com @$ip
```

- Enumerate DNS zone (such as cached records) using the `dnsrecon` tool

```shell
dnsrecon --domain example.com
```

- Identify the Web Application Firewall (WAF) solution that is being used with [wafw00f](https://github.com/EnableSecurity/wafw00f).

```shell
wafw00f example.com
```
