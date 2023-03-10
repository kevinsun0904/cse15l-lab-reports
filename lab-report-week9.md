# Week 9 Lab Report
This lab report is on Lab 6 and explains how my grader.sh bash scrip works.

## The code
```
rm -rf student-submission
git clone $1 student-submission
echo 'Finished cloning'

cd student-submission
if [[ -f ListExamples.java ]]
then
  echo "student submission found"
else
  echo "wrong file submitted"
  echo "You're grade is 0%, try again!"
  exit 1
fi

cp ../TestListExamples.java ./
javac -cp ".;../lib/hamcrest-core-1.3.jar;../lib/junit-4.13.2.jar" *.java 2>compiler-error.txt

if [[ $? == 0 ]]
then
  echo "successfully compiled"
else
  echo "compiler error"
  echo "You're grade is 0%, try again!"
  exit 1
fi

java -cp ".;../lib/hamcrest-core-1.3.jar;../lib/junit-4.13.2.jar" org.junit.runner.JUnitCore TestListExamples>results.txt 2>&1
if [[ $? == 0 ]]
then
  echo "tests passed"
  cat results.txt
  echo "You're grade is 100%, congratulations!"
else
  echo "tests failed"
  cat results.txt
  num_tests=$(grep 'Tests run:' results.txt | sed 's/^.*: //')
  failures=$(grep 'Failures:' results.txt | sed 's/^.*: //')
  num_tests=$(($num_tests))
  failures=$(($failures))
  successes=$(($num_tests-$failures))
  echo "You're grade is:" $(($successes / $num_tests))"% Try again!"
  exit 1
fi
```

## Step by Step Breakdown
### Clone repository
* This part first removes any files from the previous student.
* Then clones the repository to `student-submission` and outputs "Finished cloning".
```
rm -rf student-submission
git clone $1 student-submission
echo 'Finished cloning'
```

### Check if File is Found
* This part first changes the working directory to `student-submission`.
* Then checks recursively if the file `ListExamples.java` is found and outputs accordingly.
```
cd student-submission
if [[ -f ListExamples.java ]]
then
  echo "student submission found"
else
  echo "wrong file submitted"
  echo "You're grade is 0%, try again!"
  exit 1
fi
```

### Check if Compiled Successfully
* This part first copies the tester file into the current directory.
* Then copiles the code and checks for whether an error is outputed.
* Lastly outputs a message accordingly.
```
cp ../TestListExamples.java ./
javac -cp ".;../lib/hamcrest-core-1.3.jar;../lib/junit-4.13.2.jar" *.java 2>compiler-error.txt

if [[ $? == 0 ]]
then
  echo "successfully compiled"
else
  echo "compiler error"
  echo "You're grade is 0%, try again!"
  exit 1
fi
```

### Run Tester and Output Results
* This part first runs the tester and stores the error message in a file called `results.txt`.
* Then if there is no error from running the tester, the grade script outputs a grade of 100%.
* If there is an error, the grade scrip then outputs the error messages in `results.txt` and then checks for the total tests an failures by finding the integar after "Tests run:" and "Failures:".
* Lastly, a grade is calculated from these numbers and outputed. 
```
java -cp ".;../lib/hamcrest-core-1.3.jar;../lib/junit-4.13.2.jar" org.junit.runner.JUnitCore TestListExamples>results.txt 2>&1
if [[ $? == 0 ]]
then
  echo "tests passed"
  cat results.txt
  echo "You're grade is 100%, congratulations!"
else
  echo "tests failed"
  cat results.txt
  num_tests=$(grep 'Tests run:' results.txt | sed 's/^.*: //')
  failures=$(grep 'Failures:' results.txt | sed 's/^.*: //')
  num_tests=$(($num_tests))
  failures=$(($failures))
  successes=$(($num_tests-$failures))
  echo "You're grade is:" $(($successes / $num_tests))"% Try again!"
  exit 1
fi
```

## Trying the Grade Script
### Failed Tester
<img width="554" alt="1" src="https://user-images.githubusercontent.com/122562552/224128837-79032581-dcf5-45c0-b9d3-3d30fa96f52b.PNG">

### Passed Tester
<img width="572" alt="2" src="https://user-images.githubusercontent.com/122562552/224128869-7e1d4bde-8fa9-417c-abad-e7e4ace35087.PNG">

### Compiler Error
<img width="537" alt="3" src="https://user-images.githubusercontent.com/122562552/224128891-e7bbeb91-9228-4ceb-a8c5-cd1d6cf6b0c4.PNG">

### Wrong File Name
<img width="532" alt="4" src="https://user-images.githubusercontent.com/122562552/224128913-b7364db0-d54b-410d-ba7d-318571f2d3bd.PNG">
