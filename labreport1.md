# LAB REPORT ONE

---
## Command `cd`
---

**1. No Arguments**
```
aidan@DESKTOP-V7LTJCQ MINGW64 ~
$ cd
```

**2. Directory as Argument**
```
aidan@DESKTOP-V7LTJCQ MINGW64 ~
$ cd lecture1

aidan@DESKTOP-V7LTJCQ MINGW64 ~/lecture1 (main)
```

**3. File as Argument**
```
aidan@DESKTOP-V7LTJCQ MINGW64 ~/lecture1 (main)
$ cd Hello.java
bash: cd: Hello.java: Not a directory
```
Error: `cd` cannot be used to change the current working directory to a specific file, as a file is not meant to be a directory

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

