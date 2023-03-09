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
* This part clones the repository and outputs "Finished cloning".
```
rm -rf student-submission
git clone $1 student-submission
echo 'Finished cloning'
```
