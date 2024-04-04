# LAB REPORT ONE
Aidan Fuller <br>
4/2/2024

---
# Command `cd`
---

## **1. No Arguments**
```
aidan@DESKTOP-V7LTJCQ MINGW64 ~
$ cd
```
**Absolute Path:** /c/Users/aidan/ <br>
**Explanation:** Nothing happens, as there was no directory specified for `cd` to change the working directory to. <br>
**Error:** N/A

## **2. Directory as Argument**
```
aidan@DESKTOP-V7LTJCQ MINGW64 ~
$ cd lecture1

aidan@DESKTOP-V7LTJCQ MINGW64 ~/lecture1 (main)
```
**Absolute Path:** /c/Users/aidan/ <br>
**Explanation:** The directory is changed to `lecture1` as it was specified in the command line. <br>
**Error:** N/A

## **3. File as Argument**
```
aidan@DESKTOP-V7LTJCQ MINGW64 ~/lecture1 (main)
$ cd Hello.java
bash: cd: Hello.java: Not a directory
```
**Absolute Path:** /c/Users/aidan/lecture1 <br>
**Explanation:** An error occurs when a specific file is listed after the `cd` command. <br>
**Error:** `cd` cannot be used to change the current working directory to a specific file, as a file is not meant to be a directory. 

---
# Command `ls`
---

## **1. No Arguments**
```
aidan@DESKTOP-V7LTJCQ MINGW64 ~/lecture1 (main)
$ ls
Hello.class  Hello.java  messages/  README
```
**Absolute Path:** /c/Users/aidan/lecture1 <br>
**Explanation:** All of the files in the `lecture1` working directory are listed. The files are `Hello.class` , `Hello.java` , `messages` , and `README` <br>
**Error:** N/A

## **2. Directory as Argument**
```
aidan@DESKTOP-V7LTJCQ MINGW64 ~/lecture1 (main)
$ ls lecture1
ls: cannot access 'lecture1': No such file or directory
```
**Absolute Path:** /c/Users/aidan/lecture1 <br>
**Explanation:** An error occurs when the name of the current directory is specified within the `ls` command line <br>
**Error:** Because we are already in the `lecture1` directory, specifying "lecture1" again after `ls` attempts to find a second directory named `lecture1` which does not exist and results in an error. 

## **3. File as Argument**
```
aidan@DESKTOP-V7LTJCQ MINGW64 ~/lecture1 (main)
$ ls Hello.java
Hello.java
```
**Absolute Path:** /c/Users/aidan/lecture1 <br>
**Explanation:** `Hello.java` is a specific file within the `lecture1` directory, so typing `ls Hello.java` while in `lecture1` returns the files within `Hello.java`, which is simply itself. <br>
**Error:** N/A

---
# Command `cat`
---

## **1. No Arguments**
```
aidan@DESKTOP-V7LTJCQ MINGW64 ~/lecture1 (main)
$ cat
```
**Absolute Path:** /c/Users/aidan/lecture1 <br>
**Explanation:** Nothing happens, as `cat` is used to concatenate two files, however there are no files specified in the command line so the function is not provided with anything to concatenate. <br> 
**Error:** N/A

## **2. Directory as Argument**
```
aidan@DESKTOP-V7LTJCQ MINGW64 ~/lecture1 (main)
$ ls lecture1
ls: cannot access 'lecture1': No such file or directory
```

## **3. File as Argument**
```

