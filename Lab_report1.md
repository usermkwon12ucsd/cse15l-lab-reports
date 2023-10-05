# 1.Command with no arguments

## ls:

1) [user@sahara ~]$ ls
   
   lecture1
2) Working under directory: /home
3) ls command list the files and directories directory under working directory which is just lecture directory in this case.
4) No output error

## cd:

1) [user@sahara ~]$ cd
2) Working under directory: /home
3) cd command enables user to move into directory same as the given argument. Here, no argument is given so there is no change.
4) No output error

## cat:
1) [user@sahara ~]$ cat
2) working under directory:/home
3) cat command show the content of the file given by the argument. Here, nothing is given and the terminal wait the user to type anything.
4) I would not say it gives an error. It waits until the user to type any argument.


# 2.Command with a path to directory as an argument

## ls:
1) [user@sahara ~]$ ls lecture1/
Hello.class  Hello.java  messages  README


2) Working under directory: /home
3) It shows the files and a folder directly under the directory lecture1.
4) No output error

## cd:
1) [user@sahara ~]$ cd lecture1
   
 [user@sahara ~/lecture1]$ 
 
2) Working under directory: /home -> /home/lecture1
3) Move into lecture1 directory
4) No output error

## cat:
1) [user@sahara ~/lecture1]$ cat messages

   cat: messages: Is a directory

2) Working under directory: /home/lecture1
3) Cat shows the content of an file but messages is an directory so it gives an error message.
4) It's an error, messages is a directory not a file.

# 3.command with a path to file as an argument

## ls:
1) [user@sahara ~/lecture1]$ ls Hello.java
   
   Hello.java
   
2) working under directory: /home/lecture1
3) Only Hello.java file is under Hello.java
4) No output error

## cd:
1) [user@sahara ~/lecture1]$ cd README

   bash: cd: README: Not a directory

2) working under directory: /home/lecture1
3) cd changes to directory but README is a file
4) Yes there's an error. cd requires directory name or some particular symbol like .. or ~ as an argument but the file name was given

## cat:
1) [user@sahara ~/lecture1]$ cat README

   To use this program:

   javac Hello.java
   java Hello messages/en-us.txt


2) working under directory: /home/lecture1
3) Content of README was printed
4) No output error
