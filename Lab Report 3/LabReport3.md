# LAB REPORT THREE
Aidan Fuller <br>
5/8/2024

---
# Bugs - Part 1 
---
## Buggy Method: reverseInPlace

### Failure Inducing Input: 
```
@Test 
public void testReverseInPlaceLengthThree() {
    int[] input1 = { 1, 2, 3 };
    ArrayExamples.reverseInPlace(input1);
    assertArrayEquals(new int[]{ 3, 2, 1 }, input1);
}
```

### Non-Failure Inducing Input: 
```
@Test 
public void testReverseInPlaceLengthOne() {
    int[] input1 = { 1 };
    ArrayExamples.reverseInPlace(input1);
    assertArrayEquals(new int[]{ 1 }, input1);
}
```
This only passes because there is only one element in the array, so even though the method is faulty it still returns the 'correct' order. 

## Test Symptom
![TestSymptom](Screenshot_TestSymptom) <br>

## Before-and-After Bug Fix
### Buggy reverseInPlace
```
static void reverseInPlace(int[] arr) {
    for(int i = 0; i < arr.length; i += 1) {
      arr[i] = arr[arr.length - i - 1];
    }
  }
```
### Fixed reverseInPlace
```
static void reverseInPlace(int[] arr) {
    for(int i = 0; i < arr.length / 2; i += 1) {
      int temp = arr[i];
      arr[i] = arr[arr.length - i - 1];
      arr[arr.length - i - 1] = temp;
    }
  }
```
The problem with the original method is that it will essentially replace every element in the array with the last element, because the each iteration of `i` changes the index `arr[i]` to `arr[arr.length - i - 1]` which is just the last element in the array and is never altered throughout the loop. The fixed version only iterates through half of the array as determined by `arr.length / 2` and creates a `temp` variable inside the loop that is set to the current value at `arr[i]` before it is overwritten. Then, the index at the of the array is set to the value stored in temp so that no numbers are overwritten and lost.  

---
# Researching Commands - Part 2
---
## grep -c 
---
### File
```
$ grep -c "pairs" biomed-lines.txt
133
```
### Directory
```
$ grep -c "pairs" technical/biomed/*.txt
technical/biomed/1468-6708-3-1.txt:0
technical/biomed/1468-6708-3-10.txt:0
technical/biomed/1468-6708-3-3.txt:0
technical/biomed/1468-6708-3-4.txt:0
**continues on to list more files**
```
-c lists the amount of lines that a specified search term appears in as an integer when used on a file. On a directory however, it lists out each individual file in said directory with a number next to it with how many lines in that exact file contain the search term. The command format is <br> `grep -c "[Search Term]" [File Name(s)]`

<br>

Source: `grep --help` 

## grep -a
---
### File
```
$ grep -a "pairs" biomed-lines.txt
technical/biomed/1471-2091-3-4.txt:        AES, atomic emission spectroscopy; bp, base pairs; CD,
technical/biomed/1471-2105-2-8.txt:          base pairs. This involves making an independence
technical/biomed/1471-2105-2-8.txt:          the aligned base pairs as the average of these two
**continues on to list more lines**
```
### Directory
```
$ grep -a "pairs" technical/biomed/*.txt
technical/biomed/1471-2091-3-13.txt:        acids separating the pairs of cysteines (Cys-X 
technical/biomed/1471-2091-3-18.txt:        of its β7-β8 loop impairs the catalytic function of the
technical/biomed/1471-2091-3-30.txt:          (Chroma). Fura2 image pairs illuminated at 340 and 380 nm
**continues on to list many many more lines**
```
-a lists all of the lines after the first occurence of a specified search term that also contain said term. The command works essentially the same when used on both a file and a directory. The command format is `grep -b "[Search Term]" [File Name(s)]`

<br>

Source: `grep --help` 

## grep -b
---
### File
```
$ grep -b "pairs" biomed-lines.txt
0:technical/biomed/1471-2091-3-4.txt:        AES, atomic emission spectroscopy; bp, base pairs; CD,
177:technical/biomed/1471-2105-2-8.txt:          base pairs. This involves making an independence
271:technical/biomed/1471-2105-2-8.txt:          the aligned base pairs as the average of these two
**continues on to list more lines**
```
### Directory
```
$ grep -b "pairs" technical/biomed/*.txt
technical/biomed/1471-2091-3-13.txt:20014:        acids separating the pairs of cysteines (Cys-X 
technical/biomed/1471-2091-3-18.txt:24035:        of its β7-β8 loop impairs the catalytic function of the
technical/biomed/1471-2091-3-30.txt:32840:          (Chroma). Fura2 image pairs illuminated at 340 and 380 nm
**continues on to list more lines**
```
-b lists the byte offset of each occurence of a search term. On the very left, the offset for each of the occurences of the term `pairs` in the `biomed-lines.txt` file. The command works essentially the same regardless of whether or not a file or directory is specified. The format is `grep -b "[Search Term]" [File Name(s)]`

<br>

Source: `grep --help` 

## grep -H
---
### File
```
$ grep -H "base pair" plos-lines.txt biomed-lines.txt
plos-lines.txt:technical/plos/journal.pbio.0020190.txt:        sequence, which is a specific series of eight base pairs in the DNA of the bacterial
plos-lines.txt:technical/plos/journal.pbio.0020190.txt:        chromosomes, on the order of one or two thousand base pairs of DNA (or less—their length is
plos-lines.txt:technical/plos/journal.pbio.0020223.txt:        Watson-Crick base pairing, the proximity of the synthetic reactive groups elevates their
biomed-lines.txt:technical/biomed/1471-2091-3-4.txt:        AES, atomic emission spectroscopy; bp, base pairs; CD,
biomed-lines.txt:technical/biomed/1471-2105-2-8.txt:           ) for all base paired positions
biomed-lines.txt:technical/biomed/1471-2105-2-8.txt:          base pairs. This involves making an independence
**continues on to list more lines**
```
### Directory
```
$ grep -H "base pair" technical/plos/*.txt
technical/plos/journal.pbio.0020190.txt:        sequence, which is a specific series of eight base pairs in the DNA of the bacterial
technical/plos/journal.pbio.0020190.txt:        chromosomes, on the order of one or two thousand base pairs of DNA (or less—their length is
technical/plos/journal.pbio.0020223.txt:        Watson-Crick base pairing, the proximity of the synthetic reactive groups elevates their
**continues on to list more lines**
```
-H lists all of the lines that match the given text and can be used to find all the correct lines within multiple files. The format is <br> `grep -H "[Search Term]"[File Name(s)]` . If you search a directory with it, it will find also all of the instances of the specific term. 

<br>

Source: `grep --help` 




