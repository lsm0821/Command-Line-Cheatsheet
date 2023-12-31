<h1>Command Line Cheatsheet</h1>

Reference: Learn the Command Line course from Codecademy

<h2>Navigation </h2>
ls
- list
- Lists all the files and directories

pwd
- Print Working Directory
- Outputs the name of directory you are currently in

cd
- Change Directory
- Switches you into the directory you specify
- Move up one directory: ```cd ..``` 
- Move up multiple directories: ```cd ../..```

mkdir 
- Make Directory
- Create a new directory named **Train** : ```mkdir Train```

touch 
- Creates a new file inside the **working directory**.
- Create a new file named Train.txt: ```touch Train.txt```

<h2>Manipulation </h2>

ls options
- Options: modify the behavior of commands
- ```-a```: lists all contents, including hidden files and directories.
- ```l``` : lists all contents of a directory in long format, as well as the file permissions.
- ```t``` : orders files and directories by the time they were last modified. 

cat
- outputs the contents of a specified file
- Example: ```cat Train.txt```

Wildcards
- A special characters like ```*``` can select group of files

mv
- command move files without making a copy
- Example: ```mv Train.txt directory2/```
- To move multiple files:
- Example: ```mv my_file_1.txt my_file_2.txt my_directory/```
- can be used to rename a file
- Example: ```mv file_original.txt file_renamed.txt```

rm
- Delete files and directories
- Removing a file: 
    - ```rm unwanted_file.txt```
- Removing a directory and all of its child directories: 
    - ```rm -r unwanted_directory```

<h2>Redirection</h2>

echo
- Accepts the string as **standard input**
- Echoes the string back to the terminal as **standard output**
- Example: ```echo "Hello" ```
- standard input ```stdin``` - information inputted into the terminal through the keyboard or input device
- standard output ```stdout``` - information outputted after a process is run
- standard error ```stderr``` - an error message outputted by a failed process

```>``` command
- redirects the standard output to a file
- takes the standard output of the command on the left, and redirects it to the file on the right
- Example 1:
    -  ```echo "Hello" > hello.txt```
    - ```"Hello"``` is entered as the standard input --> redirected to the file ```hello.txt``` by ```>```
- Example 2:
    - ```cat deserts.txt > hello.txt```
    - output of ```cat deserts.txt``` redirected to ```hello.txt```
    - ```>``` overwrites all original content in ```hello.txt```

```>>``` command
- Takes the standard output of the command on the left and appends (adds) it to the file on the right. 
- Example:
    - ```cat forests.txt >> hello.txt```
    - output data of ```hello.txt``` will contain the original content of ```hello.txt``` with the content of ```forests.txt``` appended to it. 

```<``` command
- 