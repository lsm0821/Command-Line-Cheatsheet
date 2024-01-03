# Command Line Cheatsheet

Reference: Learn the Command Line course from Codecademy

## Navigation
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

## Manipulation

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
- Example:

    ``` bash
    mv Train.txt directory2/
    ```

- To move multiple files:
- Example:

    ``` bash
    mv my_file_1.txt my_file_2.txt my_directory/
    ```

- can be used to rename a file
- Example: ```mv file_original.txt file_renamed.txt```

rm

- Delete files and directories
- Removing a file:
  - ```rm unwanted_file.txt```
- Removing a directory and all of its child directories:
  - ```rm -r unwanted_directory```

## Redirection

echo

- Accepts the string as **standard input**
- Echoes the string back to the terminal as **standard output**
- Example: ```echo "Hello"```
- standard input ```stdin``` - information inputted into the terminal through the keyboard or input device
- standard output ```stdout``` - information outputted after a process is run
- standard error ```stderr``` - an error message outputted by a failed process

```>``` command

- redirects the standard output to a file
- takes the standard output of the command on the left, and redirects it to the file on the right
- Example 1:
  - ```echo "Hello" > hello.txt```
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

- Takes the standard input from the file on right and input it into the command on the left
- Example:
  - ```cat < deserts.txt```
  - ```deserts.txt``` is the standard input for the ```cat``` command.
  - Accomplishes the same thing as ```cat deserts.txt```

```|``` Pipe command

- Takes the standard output of the command on the left, and **pipes** it as standard input to the command on the right.
- "Command to command" redirection
- Example 1:
  - count words in ```volcanoes.txt``` using the word count command ```wc```
  - ```cat volcanoes.txt | wc```

``` sort ``` command

- Takes the standard input and orders it alphabetically for the standard output
- Example:

    ```bash
    Apple.txt
    Banana.txt
    Cat.txt
    ```

```uniq``` command

- Stands for unique
- Filters out **adjacent**, **duplicated** lines in a file.
- Example:

    ``` bash
    $ cat fruits.txt
    banana
    apple
    pear

    $ uniq fruits.txt
    apple
    banana
    pear
    ```
