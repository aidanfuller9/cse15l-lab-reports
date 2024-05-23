# LAB REPORT FOUR
Aidan Fuller <br> 5/22/2024

---

# Step 4

`ssh<space>aifuller@ieng6.ucsd.edu><enter>` 

To log into my `ieng6` server, I simply typed in `ssh` followed by my `ieng6` login email which put me in the remote machine environment. 

---

# Step 5
### In Browser
`<ctrlc>` 
### In Terminal
`git<space>clone<space><ctrlv><enter>`

To clone the repository into the remote environment, I copied the forked `lab7` repository from the Github browser page and typed in `git clone` to clone its contents into my terminal so I could access them. 

---

# Step 6

`cd<space>lab7<enter>` <br>
`ls<enter>` <br>
`bash<space>grade.sh`

To test the `grade.sh` bash script, first I changed the working directory I was in to `lab7` and then used `ls` to ensure all of the expected files were there. Next, I ran the script which resulted in one test passing while the other failed.

---

# Step 7
`vim<space>ListsExamples.java` <br>
`<esc>:44<right><right><right><right><right><x>2<esc>:wq<enter>`

In order to ensure both tests pass, I needed to make minor edits to the `ListExamples.java` file in the `lab7` directory, so I used `vim` to open it and display its contents. To save time and keystrokes, I used `:44` in order to skip directly to line 44 and from there I simply moved the cursor over to the right a few times and then replaced the incorrect `index1` variable with `index2`. I then entered normal mode again and typed `:wq: to exit the vim environment while saving my changes.

---

# Step 8
`bash<space>grade.sh`

Now that I had fixed the `ListExamples.java` file, I ran the tests again using the same command as I had done previously, and both tests passed without error.

---

# Step 9
`git<space>add<space>.<enter>`
`git<space>commit<space>-m<space>"Lab Report Done"<enter>`

After successfully fixing the tests, I used the `git add` command to save all of the edits I had made and then used the `git commit` command to commit my newly updated files into my forked repository back on Github. 
