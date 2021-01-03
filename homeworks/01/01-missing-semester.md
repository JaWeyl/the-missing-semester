# Exercises

*1. Create a new directory called missing under /tmp.*

**Answer:**
```bash
mkdir /tmp/missing
```

*2. Use ```touch``` to create a new file called semester in missing*

**Answer:**
```bash
touch /tmp/missing/semester
```

*3. Write the following into that file, one line at a time:*
```bash
#!/bin/sh
curl --head --silent https://missing.csail.mit.edu
```

**Answer:**
```bash
echo "#\!/bin/sh\ncurl --head --silent https://missing.csail.mit.edu" > /tmp/missing/semester
```
*4. Use chmod to make it possible to run the command ./semester rather than having to type sh semester. How does your shell know that the file is supposed to be interpreted using sh? See this page on the shebang line for more information.*

**Answer:**
```bash
chmod +x /tmp/missing/semester
```

*5. Use | and > to write the “last modified” date output by semester into a file called last-modified.txt in your home directory.*

**Answer:**
```bash
/tmp/missing/semester | grep last-modified | cut -f2 -d ":" > last-modified.txt
```