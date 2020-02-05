```Bash
cd /tmp
mkdir missing
cd missing
touch semester
```

Writing following script to semester file
#!/bin/sh
curl --head --silent https://missing.csail.mit.edu

```Bash
ls -l
chmod u+x semester
./semester | grep -i last-modified > last-modified.txt
```

