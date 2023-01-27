# Week 3 Lab Report
For this lab report, I wrote a java program which starts a localhost server that can take in queries to add to a string list with the URL and display the elements in the list. 
## Part 1
**The following is the code for my StringServer:**
- In my code, the StringServer class is mainly used to take in the port number when running the server, and starting the server properly.
- The Handler class is used to handle any requests or queries typed in the URL, and outputs "404 not found" if the path or query is not specified.

<img width="652" alt="stringServerCode" src="https://user-images.githubusercontent.com/122562552/215205003-e50eb0ac-5af4-4abc-8f8e-fd031ba0e9f4.PNG">

---
**The following are two screenshots of using `/add-message`:**

<img width="345" alt="addApple" src="https://user-images.githubusercontent.com/122562552/215206197-d7c0782e-0b3e-41b3-a661-6694ef6b45d4.PNG">

* In this first screenshot, the handleRequest method is called. In this method, the query is split at the "=", which separates the messages that was added. It then adds the message to a list, and displays the list as a string output with a for loop. 
* The relevant argument is the **URL** that was inputted by me when using the server and the relevant class field is the instance variable **list** which stores all of the string messages inputted. There are also local variables such as **parameters** which is used to stored the splitted URL, and **output** which is used to return **list** as a String. 
* In this specific request, the URL inputted is `http://localhost:4000/add-message?s=apple`, and **list** got changed such that "apple" is added to the list. 

---
<img width="339" alt="addOrange" src="https://user-images.githubusercontent.com/122562552/215206205-0a0a18f1-4a81-49b5-8852-5442b1c8c50b.PNG">

