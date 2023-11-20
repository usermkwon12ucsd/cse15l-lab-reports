# Part 1 - Bugs
## ArrayExamples.reversed method has bug in its code 



1. Failure input
```
  @Test
  public void testReversed2(){
    int[] input1 = {1,2,3};
    assertArrayEquals(new int[] {3,2,1}, ArrayExamples.reversed(input1));
  }
```
2. Passing input
```
  @Test
  public void testReversed() {
    int[] input1 = { };
    assertArrayEquals(new int[]{ }, ArrayExamples.reversed(input1));
  }
```
3. Symptom
   Test Code
   ![Code](Code.png)
   &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
   
   Results
   ![Result](Failure.png)
   
5. Bug and the Fix
- Bug
```
  static int[] reversed(int[] arr) {
    int[] newArray = new int[arr.length];
    for(int i = 0; i < arr.length; i += 1) {
      arr[i] = newArray[arr.length - i - 1];
    }
    return arr;
  }
```

  - Fix
    
```
    static int[] reversed(int[] arr) {
    int[] newArray = new int[arr.length];
    for(int i = 0; i < arr.length; i += 1) {
      newArray[i] = arr[arr.length - i - 1];
    }
    return newArray;
  }
```
In original code, newArray is initiated with all 0. Respectively, as we  all loop over the arr all elements in arr become 0.
For the fix, we copy from arr to newArray in reverse and return newArray.




# Part 2 - Researching Commands
## I choosed find command

1. name flag: find files based on their name, source:lecture
   
- Find all text files under technical and its subdirectories.
- In this way, we search for files using its extension. For example the extension that is used here is txt.
  
```
minseok@minseoks-MacBook-Pro technical % find . -name "*.txt"
./government/About_LSC/LegalServCorp_v_VelazquezSyllabus.txt
./government/About_LSC/Progress_report.txt
./government/About_LSC/Strategic_report.txt
./government/About_LSC/Comments_on_semiannual.txt
./government/About_LSC/Special_report_to_congress.txt
./government/About_LSC/CONFIG_STANDARDS.txt
./government/About_LSC/commission_report.txt
./government/About_LSC/LegalServCorp_v_VelazquezDissent.txt
./government/About_LSC/ONTARIO_LEGAL_AID_SERIES.txt
./government/About_LSC/LegalServCorp_v_VelazquezOpinion.txt
./government/About_LSC/diversity_priorities.txt
./government/About_LSC/reporting_system.txt
./government/About_LSC/State_Planning_Report.txt
./government/About_LSC/Protocol_Regarding_Access.txt
./government/About_LSC/ODonnell_et_al_v_LSCdecision.txt
./government/About_LSC/conference_highlights.txt
./government/About_LSC/State_Planning_Special_Report.txt
./government/Env_Prot_Agen/multi102902.txt
./government/Env_Prot_Agen/section-by-section_summary.txt
./government/Env_Prot_Agen/jeffordslieberm.txt
./government/Env_Prot_Agen/final.txt
./government/Env_Prot_Agen/ctf7-10.txt
./government/Env_Prot_Agen/ctf1-6.txt
./government/Env_Prot_Agen/ro_clear_skies_book.txt
```
and many more lines
   

- Find all text files under biomed directory, having names starting with 1471.
- As we specify the directories and name of the files we can search for files we want more easily.


```
minseok@minseoks-MacBook-Pro technical % find ./biomed -name  "1471*.txt"
./biomed/1471-2350-4-3.txt
./biomed/1471-2156-2-3.txt
./biomed/1471-2156-3-11.txt
./biomed/1471-2121-3-10.txt
./biomed/1471-2172-3-4.txt
./biomed/1471-2466-1-1.txt
./biomed/1471-2199-2-10.txt
./biomed/1471-2202-2-9.txt
./biomed/1471-2369-3-9.txt
./biomed/1471-2164-2-9.txt
./biomed/1471-2091-2-10.txt
./biomed/1471-213X-2-1.txt
./biomed/1471-2407-2-3.txt
./biomed/1471-2156-4-5.txt
./biomed/1471-2431-2-1.txt
./biomed/1471-2180-2-22.txt
./biomed/1471-2334-3-9.txt
./biomed/1471-2091-2-11.txt
./biomed/1471-2202-4-12.txt
./biomed/1471-2164-2-8.txt
./biomed/1471-2148-2-12.txt
./biomed/1471-2202-2-8.txt
./biomed/1471-2121-3-11.txt
./biomed/1471-2156-3-10.txt
./biomed/1471-2458-3-20.txt
./biomed/1471-2350-4-2.txt
./biomed/1471-2121-3-13.txt
./biomed/1471-2407-3-18.txt
./biomed/1471-2229-2-3.txt

```
and many more lines


   
2. type flag: find files based on their type, source:lecture

   
- Find all subdirectories under technical directory.
- We can easily see the file structure in this way.
  
```
minseok@minseoks-MacBook-Pro technical % find . -type d
.
./government
./government/About_LSC
./government/Env_Prot_Agen
./government/Alcohol_Problems
./government/Gen_Account_Office
./government/Post_Rate_Comm
./government/Media
./plos
./biomed
./911report
minseok@minseoks-MacBook-Pro technical %
```

- Find all files under 911report directories and its sub directories.
- We can easily search for files we want if the number of files are small.
  
```
minseok@minseoks-MacBook-Pro technical % find ./911report -type f
./911report/chapter-13.4.txt
./911report/chapter-13.5.txt
./911report/chapter-13.1.txt
./911report/chapter-13.2.txt
./911report/chapter-13.3.txt
./911report/chapter-3.txt
./911report/chapter-2.txt
./911report/chapter-1.txt
./911report/chapter-5.txt
./911report/chapter-6.txt
./911report/chapter-7.txt
./911report/chapter-9.txt
./911report/chapter-8.txt
./911report/preface.txt
./911report/chapter-12.txt
./911report/chapter-10.txt
./911report/chapter-11.txt

```

  
3. size flag: search for files based on size we can use comparison operator such as +,-,=.
   &nbsp;  Source: https://www.makeuseof.com/find-command-linux/
- Find all files under current and sub directories with size less than 512byte.
- We can see files under certain size.
  

```
minseok@minseoks-MacBook-Pro technical % find . -size 512c
./government/Env_Prot_Agen
./government/Post_Rate_Comm

```
   

- Find all files under current and sub directories with size more than 100kb. In this way, we can see which files need lots of memories.
  
```
minseok@minseoks-MacBook-Pro technical % find . -size +100k
./government/About_LSC/commission_report.txt
./government/About_LSC/State_Planning_Report.txt
./government/Env_Prot_Agen/multi102902.txt
./government/Env_Prot_Agen/ctm4-10.txt
./government/Env_Prot_Agen/bill.txt
./government/Env_Prot_Agen/tech_adden.txt
./government/Gen_Account_Office/d0269g.txt
./government/Gen_Account_Office/GovernmentAuditingStandards_yb2002ed.txt
./government/Gen_Account_Office/Sept27-2002_d02966.txt
./government/Gen_Account_Office/d01376g.txt
./government/Gen_Account_Office/Statements_Feb28-1997_volume.txt
./government/Gen_Account_Office/pe1019.txt
./government/Gen_Account_Office/gg96118.txt
./government/Gen_Account_Office/d01591sp.txt
./government/Gen_Account_Office/im814.txt
./government/Gen_Account_Office/ai9868.txt
./government/Gen_Account_Office/May1998_ai98068.txt
./government/Gen_Account_Office/d02701.txt
./biomed/1471-2105-3-2.txt
./911report/chapter-13.4.txt
./911report/chapter-13.5.txt
./911report/chapter-13.2.txt
./911report/chapter-13.3.txt
./911report/chapter-3.txt
./911report/chapter-1.txt
./911report/chapter-6.txt
./911report/chapter-7.txt
./911report/chapter-9.txt
./911report/chapter-12.txt
```

4. empty flag: search for empty files. Source:https://www.freecodecamp.org/news/how-to-search-files-effectively-in-linux/#:~:text=You%20can%20use%20the%20%2Dempty,and%20directories%20that%20are%20empty.&text=This%20command%20will%20list%20all,the%20empty%20files%20and%20folders.
   
- Find all empty files in technical directory and its subdirectories.
- We can search for empty files and maybe delete it.
  
```
minseok@minseoks-MacBook-Pro technical % find . -empty
minseok@minseoks-MacBook-Pro technical % 
```

- Find empty files in government directory and its subdirectories.
- We can search for blank text files and maybe delete it.

  
```
minseok@minseoks-MacBook-Pro technical % find ./government -empty
minseok@minseoks-MacBook-Pro technical % 
```
  

