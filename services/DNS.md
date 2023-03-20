# DNS

Use [https://dnsdumpster.com/](https://dnsdumpster.com/) to do both passive and active information gathering on the DNS configuration of the target.

Or, from terminal, perform a DNS zone transfer using

```shell
dig -t AXFR domain.com @$ip
```
