# Week 3 Lab Report
For this lab report, I wrote a java program which starts a localhost server that can take in queries to add to a string list with the URL and display the elements in the list. 
## Part One: Implementing StringServer
### The following is the code for my StringServer:
- In my code, the StringServer class is mainly used to take in the port number when running the server, and starting the server properly.
- The Handler class is used to handle any requests or queries typed in the URL, and outputs "404 not found" if the path or query is not specified.

<img width="652" alt="stringServerCode" src="https://user-images.githubusercontent.com/122562552/215205003-e50eb0ac-5af4-4abc-8f8e-fd031ba0e9f4.PNG">



### The following are two screenshots of using `/add-message`:

<img width="345" alt="addApple" src="https://user-images.githubusercontent.com/122562552/215206197-d7c0782e-0b3e-41b3-a661-6694ef6b45d4.PNG">

* In this first screenshot, the handleRequest method is called. In this method, the query is split at the "=", which separates the messages that was added. It then adds the message to a list, and displays the list as a string output with a for loop. 
* The relevant argument is **url** that was inputted by me when using the server and the relevant class field is the instance variable **list** which stores all of the string messages inputted. There are also local variables such as **parameters** which is used to stored the splitted URL, and **output** which is used to return **list** as a String. 
* In this specific request, the URL inputted is `http://localhost:4000/add-message?s=apple`, and **list** got changed such that "apple" is added to the list. 

---
<img width="339" alt="addOrange" src="https://user-images.githubusercontent.com/122562552/215206205-0a0a18f1-4a81-49b5-8852-5442b1c8c50b.PNG">

* In this second screenshot, the handleRequest method is called again, which does the same operations as it did in the first screenshot.
* The relevant argument is still **url** and **list**, but this time lists starts with an element of "apple" inside it. Local variables such as **parameters** and **output** are still used to split the URL and return **list**
* In this specific request, the URL inputted is `http://localhost:4000/add-message?s=orange`, and **list** got changed such that "orange" is added to the list. 



## Part Two: Debugging from Lab 3
### The following is a buggy method from Lab 3:
```
static void reverseInPlace(int[] arr) {
    for(int i = 0; i < arr.length; i += 1) {
        arr[i] = arr[arr.length - i - 1];
    }
}
```
### This is a JUnit test for the previous method that fails:
```
@Test
public void testReverseInPlace1() {
    int[] input1 = {1, 2, 3};
    ArrayExamples.reverseInPlace(input1);
    assertArrayEquals(new int[]{3, 2, 1}, input1);
}
```
### This is a JUnit test for the previous method that passes:
```
@Test
public void testReverseInPlace2() {
    int[] input1 = {2, 1, 3};
    ArrayExamples.reverseInPlace(input1);
    assertArrayEquals(new int[]{3, 1, 3}, input1);
}
```
### The following screenshot is the symptom after running the two testers:

<img width="1034" alt="testReverseFail" src="https://user-images.githubusercontent.com/122562552/215219716-e80b1bdb-a66b-4c9e-a6af-6aab281c31ad.PNG">


### The following is a comparason between the code before and after fixing the bug:
**Before:**
```
static void reverseInPlace(int[] arr) {
    for(int i = 0; i < arr.length; i += 1) {
        arr[i] = arr[arr.length - i - 1];
    }
}
```

**After:**
```
static void reverseInPlace(int[] arr) {
    int[] temp = new int[arr.length];
    for(int i = 0; i < arr.length; i += 1) {
        temp[i] = arr[arr.length - i - 1];
    }
    for(int i = 0; i < arr.length; i++){
        arr[i] = temp[i];
    }
}
```
**How does this fix the issue?**
The bug of this method is mainly that when the array **arr** is reversed in place, the original array is overrided when the reveresed element is copied to the front of the array. Therefore, to fix this bug, I stored the reversed elements in a temporary array called **temp**, and deep copied the elements of **temp** into **arr**. Deep copy is required in this case because shallow copy would just change the reference of the local varaible **arr**, which means the original array outside of this method used as the argument would not be changed. 


## Part Three: Reflection
In lab 2 and lab 3, I mainly learnt how to start a local server on my computer or run it on a remote computer. I can now start a server that takes in different paths or queries and run simple algroithms from the queries. I also learnt how to write testers and debug programs according to the symptom outputted form the tester, and got many practices during lab time. 
