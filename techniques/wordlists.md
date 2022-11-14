# wordlists

Below contains Python code to generate wordlists from `rockyou.txt`.

```python
file = open('/usr/share/wordlists/rockyou.txt', 'r', encoding='latin-1')

for line in file.read().splitlines():
  if len(line) == 4:
    potential = True
    for char in line:
      if not char.isalpha() or not char.islower():
        potential = False
        break
    if potential:
      print(line)
```
