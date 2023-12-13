## Step1
git clone https://github.com/ucsd-cse15l-f23/skill_demo3_data
## Step2
Direction: Find the path to the .java file with the most lines among all files in the submissions/ directory. 
          Store the path to that file (either absolute or relative from the skill_demo3_data directory) in the file biggest.txt.


cd skill_demo3_data/ 
after finding all java files using ls submissions/*/*.java or ls submissions/*/*/*.java
`wc -l submissions/*/*.java submissions/*/*/*.java`

## Step3
Direction: Find all the lines in all the .java files that contain the string Collections.sort. Store the content of these lines in a file called sorts.txt.
`grep -h "Collections.sort" submissions/*/*.java submissions/*/*/*.java` > ~sorts.txt

## Step4
Put the total number of files called "Sorter.java" that appear anywhere recursively when the submissions directory into a file called all_javas.txt
`ls submissions/*/*.java submissions/*/*/*.java|wc -l > "all_javas.txt"`

## Step5
Save and grade`
## Step 6
in bash: `if [[ $? -ne 0 ]]` 
## Step 7
in bash: `grep "Test results" $all_results > run-results.txt`
## Step 8
Direction: redirect error output from java to error-feedback.txt
in bash `javac Sorter.java 2> error-feedback.txt` add `2> error-feedback.txt` this part
