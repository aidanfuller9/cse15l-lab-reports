# LAB REPORT ONE

---
## Command `cd`
---

**1. No Arguments**
```
aidan@DESKTOP-V7LTJCQ MINGW64 ~
$ cd
```
**Absolute Path:** 
**Explanation:** Nothing happens, as there was no directory specified for `cd` to change the working directory to. 
**Error:** N/A

**2. Directory as Argument**
```
aidan@DESKTOP-V7LTJCQ MINGW64 ~
$ cd lecture1

aidan@DESKTOP-V7LTJCQ MINGW64 ~/lecture1 (main)
```
**Absolute Path:**
**Explanation:** The directory is changed to `lecture1` as it was specified in the command line. 
**Error:** N/A

**3. File as Argument**
```
aidan@DESKTOP-V7LTJCQ MINGW64 ~/lecture1 (main)
$ cd Hello.java
bash: cd: Hello.java: Not a directory
```
**Absolute Path:**
**Explanation:** An error occurs when a specific file is listed after the `cd` command. 
**Error:** `cd` cannot be used to change the current working directory to a specific file, as a file is not meant to be a directory. 

---
## Command `ls`
---

**1. No Arguments**
```
aidan@DESKTOP-V7LTJCQ MINGW64 ~/lecture1 (main)
$ ls
Hello.class  Hello.java  messages/  README
```

**2. Directory as Argument**
```
aidan@DESKTOP-V7LTJCQ MINGW64 ~/lecture1 (main)
$ ls lecture1
ls: cannot access 'lecture1': No such file or directory
```

**3. File as Argument**
```
aidan@DESKTOP-V7LTJCQ MINGW64 ~/lecture1 (main)
$ ls Hello.java
Hello.java
```

---
## Command `cat`
---

**1. No Arguments**
```

```

**2. Directory as Argument**
```
aidan@DESKTOP-V7LTJCQ MINGW64 ~/lecture1 (main)
$ ls lecture1
ls: cannot access 'lecture1': No such file or directory
```

**3. File as Argument**
```

