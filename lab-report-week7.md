# Week 7 Lab Report
This lab report is a tutorial on how to complete the following steps most efficiently:
1. Log into ieng6
2. Clone your fork of the repository from your Github account
3. Run the tests, demonstrating that they fail
4. Edit the code file to fix the failing test
5. Run the tests, demonstrating that they now succeed
6. Commit and push the resulting change to your Github account

## Step 1
Keys pressed: `<Ctrl + c> <Ctrl + v> <enter>`
* I used these two commands to copy my login command `ssh cs15lwi23aqq@ieng6.ucsd.edu` from another document to save time. 

<img width="599" alt="1" src="https://user-images.githubusercontent.com/122562552/221046927-4753a247-8929-4513-820d-d39f2f80191d.PNG">


## Step 2
Keys pressed: `git clone <Ctrl + c> <Ctrl + v> <enter>`, `cd l `<tab> <enter>`
* I typed `git clone` and used the copy and paste command again to copy this url: git@github.com:kevinsun0904/lab7.git, which clones the lab7 repository I forked previously.
* Then I typed `cd l` and pressed `<tab>` to allow bash to autocomplete the directory and changed my working directory to ~/lab7

<img width="459" alt="2" src="https://user-images.githubusercontent.com/122562552/221048198-fcf06218-95f8-4ab2-91d2-1b7fbbd3b451.PNG">


## Step 3
Keys pressed: `<Ctrl + c> <Ctrl + v> <enter>`, `<Ctrl + c> <Ctrl + v> T <tab> <delete> <enter>`
* I used the first set of copy and paste to copy this line: `javac -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar *.java` to compile the code.
* Then I used copy and paste again to copy this line: `java -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar org.junit.runner.JUnitCore` and typed ` T` (with a space in front of T) and pressed `<tab>` to allow bash to autocomplete the directory to `TestListExamples.`.
* Then I deleted the extra `.` at the end of the directory to run the test file. 

<img width="770" alt="3" src="https://user-images.githubusercontent.com/122562552/221049639-840fa7c9-a1c8-4a9e-b06d-27f1568ed561.PNG">


## Step 4
Keys pressed: `nano L <tab> j <tab> <enter>`, `<Ctrl + w> while(index2 <enter>`, `<down>` * 2, `<right>` * 8, `<delete> 2`, `<Ctrl + o> <enter> <Ctrl + x>`
* First, I typed `nano L` and pressed `<tab>` and then typed `j` and then pressed `<tab>` again to allow bash to autocomplete this line to `nano ListExamples.java`.
* Then i used `<Ctrl w>` to search for `while(index2` and used the arrow keys to navigate to the line that I am going to edit. 
* After that I changed the `1` on that line to `2`.
* Lastly, I used `<Ctrl + o>` to save and `<Ctrl + x>` to exit. 
  
<img width="680" alt="4" src="https://user-images.githubusercontent.com/122562552/221052841-6981f803-8efc-40ef-9d7e-dd8300be7c0d.PNG">
  

## Step 5
Keys pressed: `<up>` * 3, `<enter>`, `<up>` * 3, `<enter>`
* I pressed `<up>` 3 times to find `javac -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar *.java` in history and ran it to compile the code again.
* I pressed `<up>` 3 times again to find `java -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar org.junit.runner.JUnitCore TestListExamples` to run the tester. 
 
<img width="768" alt="5" src="https://user-images.githubusercontent.com/122562552/221053241-063150fb-3580-4769-a534-a0c8cd1ed0f0.PNG">

  
## Step 6
Keys pressed: `git add L <tab> j <tab>`, `git commit -m "message"`
* I typed `git add L` and used `<tab>` to allow bash to autocomplete it into `git add ListExample.`, and typed `j` and pressed `<tab>` again to complete the whole line into `git add ListExample.java` to add the changes. 
* Then I typed `git commit -m "message"` to commit these changes to github with a message of "message".
  
<img width="436" alt="6" src="https://user-images.githubusercontent.com/122562552/221054684-82442850-c331-46e7-be5c-96ad86ec3836.PNG">
