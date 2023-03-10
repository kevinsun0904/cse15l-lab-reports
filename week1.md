# **Week 1 Lab Report**
This lab report will be a tutorial for myself and future CSE 15L students who are trying to log onto our course-specific accounts on ieng6.

Step 1: Installing VScode
---
* For this step, I first went onto the [VScode website](https://code.visualstudio.com/) to download and install visual studio code.
* Then I went to the [Git website](https://gitforwindows.org/) to download Git for windows.
* VScode should looke something like this after setting it up properly:
<img width="1440" alt="screenshot2" src="https://user-images.githubusercontent.com/122562552/212164377-aa666499-8a88-4605-a887-6a7f79cf4057.PNG">

Step 2: Remotely Connecting 
---
* After setting up VScode, I starting setting up the remote connection on VScode.
* FIrst, I pressed `` Ctrl+Shift+` `` to open the terminal on VScode. This should look like this:
<img width="1214" alt="screenshot4" src="https://user-images.githubusercontent.com/122562552/212165373-c59403e1-b477-43c1-aa09-6365d080930c.PNG">

* Then I typed `ssh cs15lwi23aqq@ifeng6.ucsd.edu` in the terminal. (If you are logging into your own account, replace the `aqq` part with letters from **your own** username)
* After that, the terminal asked me if I wanted to connect to my host, and I simply answered **yes**.
* Then I typed my CSE 15L specific password into the terminal in the password section. (Note that it is normal that the password you typed doesnt show due to privacy reasons) 
* Finally, I pressed enter and this is what it should look like:

![screenshot](https://user-images.githubusercontent.com/122562552/212191613-c385f59c-3032-42b7-a587-569a4a796e60.png)

Step 3: Trying Some Commands
---
* Now the terminal should be connected to a remote computer in the CSE department.
* I then tested out a few lines of codes including:
  * `cd ~` - This command changes the current working directory to the home directory. 
  * `cd ..` - This changes the directory to the previous directory.
  * `ls -lat` - `l` means a long list of files, `a` means all files and `t` means in time of last accessed order, so this gives a long list of all the files in directory in terms of when it was last accessed. 
  * `ls -a` - This lists all files in the current working directory. 
  * `ls <directory>` where `<directory>` is `/home/linux/ieng6/cs15lwi23/cs15lwi23abc`, where the abc is one of the **other** group members??? username - This shows the files in a certain directory of another user. 
  * `cp /home/linux/ieng6/cs15lwi23/public/hello.txt ~/` - This copies a file called `hello.txt` to the current directory. 
  * `cat /home/linux/ieng6/cs15lwi23/public/hello.txt` - This outputs the text within `hello.txt` to the terminal.
* This is what my terminal looks like after testing a few of these codes:

![screenshot 3](https://user-images.githubusercontent.com/122562552/212193463-d7e8dbed-1306-4ed8-81d0-d5807d8bd635.png)

