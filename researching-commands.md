# Week 5 Lab Report
This lab report contains results from researching 4 different interesting command-line options when using the `grep` command, and two examples for each option would be given.

## The grep command
`grep` is a command that is mainly used to search for a string within a text file and outputing the line that contains the string. The format of running grep is: `grep [option] [file]`. Below is an example of running grep:

<img width="505" alt="捕获" src="https://user-images.githubusercontent.com/122562552/218348244-90696f48-daf3-45b4-8d16-9052f1a06488.PNG">

* In the above example, `grep` is used to search for the string "hi" inside the file under the directory of `written_2/travel_guides/berlitz1/HandRHawaii.txt`.
* The lines that contain "hi" is outputted in the terminal.

## Interesting options
### grep -l
This command-line option is one of the most basic but most important option for grep, because the `-l` means it will only out put the file name of the grep search instead of the matching line. This is very useful because it displaying all of the lines that contain a certain string may be too overwhelming, and only displaying a file be easier to determine which file contains a certain string. The following are two examples of that:

<img width="472" alt="2" src="https://user-images.githubusercontent.com/122562552/218351152-db28bb90-56e4-494a-bb92-987943189bf0.PNG">

* In this example, only the filename is outputed when searching for "hi" in the file. 
* This shows that the file contains "hi" without flooding the command-line.

---

<img width="485" alt="3" src="https://user-images.githubusercontent.com/122562552/218351829-c21f39ba-fac2-44d5-a007-765bdcf60b64.PNG">

* In this example, the grep command searches for any file under the directory of `*/*/*/*.txt` for the string "hi".
* But because multiple files contain "hi", using grep without the `-l` option may result in hundreds of outputs.
* Therefore using the `-l` option would only show the files that contain "hi" and reduce the outputs. 

### grep -r


### grep -v


### grep -c
