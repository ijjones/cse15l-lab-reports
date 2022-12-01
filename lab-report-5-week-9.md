```
# Create your grading script here
set -e
echo "To earn max points, the file must be found, compile, and the test should pass!"
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
echo "Ssore: $grade/3 Points"

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
echo "Score: $grade/3 Points"

echo "Running Test:"
java -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar org.junit.runner.JUnitCore TestListExamples > output.txt

if grep -q "fail" output.txt 
then
    echo "Tests Failed! (No Points Gained)"
else
    echo "All Test Passed! (1 Point Gained)"
    ((grade+=1))
fi
echo "Score: $grade/3 Points"

echo "Testing Finished!"

echo "Overall Grade: $grade/3 Points"

exit
```
