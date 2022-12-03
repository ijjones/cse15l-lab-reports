## Script for Autograder
```
# Create your grading script here
set -e
rm -rf student-submission
git clone $1 student-submission

cp TestListExamples.java student-submission
cp -R lib student-submission
cd student-submission
grade=0

if [ -f ListExamples.java ]
then 
    echo "File was found! (1 Point Gained)"
    ((grade+=1))
else
    echo "File not found! (No Points Gained)"
    exit 1
fi

set +e
javac -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar *.java 2> error.txt

if [ $? -ne 0 ]
then
    echo "Compile Error! Fix Error Below and Retry! (No Points Gained)"
    cat error.txt
    exit 1
else
    echo "File Compiled Successfully! (1 Point Gained)"
    ((grade+=1))
fi

echo "Running Test:"
java -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar org.junit.runner.JUnitCore TestListExamples > output.txt

if grep -q "fail" output.txt 
then
    echo "One or More Tests Failed! Please Refer to output.txt! (No Points Gained)"
else
    echo "All Test Passed! (1 Point Gained)"
    ((grade+=1))
fi

echo "Testing Finished!"

echo "Overall Grade: $grade/3 Points"

exit
```
#### Test Submission 1
![screenshot](images/lab5-s1.png)

#### Test Submission 2
![screenshot](images/lab5-s2.png)

#### Test Submission 3
![screenshot](images/lab5-s3.png)

## Test Submission 1 Trace
```
set -e
rm -rf student-submission
git clone $1 student-submission
```
* This block of code will exit the code if a command returns a non-zero status then remove the previous student-submission then clone the students directory. The standard output would be (Cloning into 'student-submission') and its return code would be 0 because in test submission 1, the previous directory was removed and students directory was cloned successfully.
```
cp TestListExamples.java student-submission
cp -R lib student-submission
cd student-submission
grade=0
```
* This block of code will copy the java file into student-submission, recusrivleey copy lib into student-submission, change into the student-submission directory, and create a variable to hold the grade in. 
```
if [ -f ListExamples.java ]
then 
    echo "File was found! (1 Point Gained)"
    ((grade+=1))
else
    echo "File not found! (No Points Gained)"
    exit 1
fi
```
*
```
set +e
javac -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar *.java 2> error.txt

if [ $? -ne 0 ]
then
    echo "Compile Error! Fix Error Below and Retry! (No Points Gained)"
    cat error.txt
    exit 1
else
    echo "File Compiled Successfully! (1 Point Gained)"
    ((grade+=1))
fi
```
*
```
echo "Running Test:"
java -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar org.junit.runner.JUnitCore TestListExamples > output.txt

if grep -q "fail" output.txt 
then
    echo "One or More Tests Failed! Please Refer to output.txt! (No Points Gained)"
else
    echo "All Test Passed! (1 Point Gained)"
    ((grade+=1))
fi

echo "Testing Finished!"

echo "Overall Grade: $grade/3 Points"

exit
```
*
