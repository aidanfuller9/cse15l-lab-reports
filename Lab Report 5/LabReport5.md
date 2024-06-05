## LAB REPORT FIVE
Aidan Fuller <br> 6/4/2024





> **private question @5**
---

Hello, I am having trouble with my autograder `grade.sh` script for Lab 6. I have designed it to display the number of tests that are passing in my program and everything seems to work except the score part, where it keeps saying `Total Score Is: 0 out of 1`. I've looked over the bash script and I can't find any reason as to why it keeps displaying zero, but there must be some issue. The autograder must be broken!!! 

Here is an image of my autograder: <br>
![BashScript](BashScript.png) <br>


---
> **the instructors' answer**
---
While it is still possible that your bash script contains an error as I cannot see the entire command in the screenshot, there don't appear to be any errors in the declaration or calculation of the `result` variable. <br>

Please provide more information to help debug, such as screenshots of the method and test case that your bash script is currently running. 

---
> **students' response**
---
Here is an image of the test case: <br>
![TestCase](TestCase.png) <br>

Here is an image of the filter method: <br>
![FilterMethod](FilterMethod.png) <br>

---
> **instructors' response**
---
Ah, I see where the error is. Your bash script seems to be calculating the amount of tests passed without problem, the issue lies within your test case! If you look to the line in your `filter` method that states `result.add(0, s);`, be mindful of the fact that you are adding each new item to the **front** of your new filtered list, not the back. Therefore, your `grade.sh` autograder works fine, but you need to fix your test case. 


---
> **students' response**
---
I get it now, thank you! My test case was capturing the words `cereal`, `baseball`, and `phone` as words that contained `E`, but I had set up my expected list in a random order. It should have been in the reverse order as to how they appeared in the original list because each new word added pushes the first word an index back. I fixed that in the test case, but I am still receiving an issue, now within my bash script. If all of the test cases are correct, instead of showing `1 out of 1` it just shows ` out of ` and I can't figure out why. Here is a screenshot of the `result.txt` file that my `grade.sh` bash script is using to calculate the values of failures and tests run. 



---
> **instructors' response**
---
I see where the issue is here as well. When you get all of the tests correct, there is no indication of `Failures:` or `Tests Run:` within `Results.txt`, because the displayed message is different and just contains `OK (X Tests`. This means that if **all** of your tests properly pass, there is no way for the `failures` or `testsRun` variables to be selected using the `grep` command. I would recommend using an `if else` statement in order to add a case depending on whether or not all the tests pass or fail, and then accessing the amount differently based on the condition. 

---
> **students' response**
---
That makes so much sense, thank you for your help! I added an `if else` statement to determine whether or not 100% of the tests passed, and then I determined the `testsRun` value a different way. Now when I run it, the output properly lists `Total Score Is: 1 out of 1`. Thank you so much for all of your help!
![FixedScript](FixedScript.png) <br>


