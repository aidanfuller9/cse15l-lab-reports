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
![TestSymptom](Screenshot_LocalKey) <br>



