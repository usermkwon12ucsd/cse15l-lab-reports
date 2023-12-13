## Step1
Direction: mkdir  
  - source/
    - Main.java
  - lib/
    - Library.java
  - data/
    - 2022/
      - data.csv
    - 2023/
      - data.csv

`mkdir source lib data`
`touch source/Main.java`
`touch lib/Library.java`
`cd data`
`mkdir 2022 2023`
`touch 2022/data.csv`
`touch 2023/data.csv`

- `ls -R` to check

## Step2
`vim README`<br>
`git add README`<br>
`git commit -m "skill demo"`
## Step3
`bash test.sh > /home/student/test-fail-output.txt`<br>
## Step4
`vim ListExamples.java`<br>
fix bugs ( there are 2bugs results.add  & index1 -> index2)<br>
`bash test.sh > /home/student/test-fail-output.txt`
## Step5
`git add *`<br>
`git commit -m "fix bugs"
## Step6
`vim BCrypt.java`<br>
and setting break point
`:684` to jump set breakpoint at 685<br>
`javac -g *.java`<br>
`jdb Main password1`<br>
`stop at BCrypt:685`<br>
`run`<br>
`print hashed.length`<br>
`echo 24 > /home/student/hashed.txt` 
## Step 7
`print hashed[3]` <br>
`echo 100 > /home/student/hashed_index.txt`
