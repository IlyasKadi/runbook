# cmd cheatsheet

| Linux                            | Windows (cmd)                       | Windows (psh)                                                      |
|----------------------------------|-------------------------------------|--------------------------------------------------------------------|
| ls                               | dir                                 | ls                                                                 |
| ip -h                            | help ipconfig ipconfig /?           | Get-Help ls                                                        |
| find / -name hi.txt 2> /dev/null | where /R C:\ hi.txt                 | ls -Recurse -Path C:\ -Filter hi.txt -ErrorAction SilentlyContinue |
| ls \| wc -l                      |                                     | ls \| Measure-Object                                               |
| pwd                              | cd                                  | pwd                                                                |
| chown a3cipher:a3cipher hi.txt   | takeown /F hi.txt                   |                                                                    |
| chmod 777 hi.txt                 | icacls hi.txt /grant "a3cipher:(F)" |                                                                    |
| nc ip 4444                       |                                     | Test-NetConnection -ComputerName ip -Port 4444                     |
