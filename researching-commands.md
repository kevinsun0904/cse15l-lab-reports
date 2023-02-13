# Week 5 Lab Report
This lab report contains results from researching 4 different interesting command-line options when using the `grep` command, and two examples for each option would be given.

## The grep command
`grep` is a command that is mainly used to search for a string within a text file and outputing the line that contains the string. The format of running grep is: `grep [option] [file]`. Below is an example of running grep:

<img width="505" alt="捕获" src="https://user-images.githubusercontent.com/122562552/218348244-90696f48-daf3-45b4-8d16-9052f1a06488.PNG">

* In the above example, `grep` is used to search for the string "hi" inside the file under the directory of `written_2/travel_guides/berlitz1/HandRHawaii.txt`.
* The lines that contain "hi" is outputted in the terminal.

## Interesting options
### grep -l:
This command-line option is one of the most basic but most important option for grep, because the `-l` means it will only output the file name of the grep search instead of the matching line. This is very useful because it displaying all of the lines that contain a certain string may be too overwhelming, and only displaying a file be easier to determine which file contains a certain string. The following are two examples:

<img width="472" alt="2" src="https://user-images.githubusercontent.com/122562552/218351152-db28bb90-56e4-494a-bb92-987943189bf0.PNG">

* In this example, only the filename is outputed when searching for "hi" in the file. 
* This shows the that file contains "hi" without flooding the command-line.

---

<img width="485" alt="3" src="https://user-images.githubusercontent.com/122562552/218351829-c21f39ba-fac2-44d5-a007-765bdcf60b64.PNG">

* In this example, the grep command searches for any file under the directory of `*/*/*/*.txt` for the string "hi".
* But because multiple files contain "hi", using grep without the `-l` option may result in hundreds of outputs.
* Therefore using the `-l` option would only show the files that contain "hi" and reduce the outputs. 

Found on: [https://man7.org/linux/man-pages/man1/grep.1.html](https://man7.org/linux/man-pages/man1/grep.1.html)

### grep -r:
This command-line option means recursive, and it is similar to the find command as it recursively goes through all of the files in the given directory to finds the lines that contain the string given. This is very useful because it automatically searches all of the files in the directory and saves time by preventing file by file search. The following are two examples:

<img width="689" alt="4" src="https://user-images.githubusercontent.com/122562552/218357659-d767bbf1-174a-4376-b2e3-b161053db5f9.PNG">

* This example recursively searches all of the files in the directory, and outputs all of the lines that contain "Lucayans".
* If -r wasn't used, you would have to search each file one by one or directory by directory with *. 

---

<img width="500" alt="5" src="https://user-images.githubusercontent.com/122562552/218357780-32369ea3-5e10-43e1-86d9-67373e1b6a4a.PNG">

* This example combines -l with -r to only out put the name of the file that contains "Lucayans".
* This is extremely useful, as it can recursively search though all of the files for a string in one command. 

Found on: [https://man7.org/linux/man-pages/man1/grep.1.html](https://man7.org/linux/man-pages/man1/grep.1.html)

### grep -v
This option reverts the command of grep, and finds all of the lines that doesnt contain the given string. This option can be somewhat useful because it can essentially filter out any lines that contain the given string. The following are two examples:

<img width="705" alt="6" src="https://user-images.githubusercontent.com/122562552/218366302-bee97ee5-70fa-470e-b160-ccee6bd75180.PNG">

* This example searches the file under the directory `written_2/travel_guides/berlitz2/Bahamas-History.txt` for all the lines that does not contain any instances of the string "hi"

---

<img width="652" alt="7" src="https://user-images.githubusercontent.com/122562552/218366474-1d674588-c86b-45d9-9b7d-111400da22bd.PNG">

* This example is similar to the previous example, with the only difference being the `-i`.
* `-i` means that this grep is not case sensitive, so as you can see the line of "A Brief History" is not included in the inverted grep search due to containing the string "Hi".

### grep -c
