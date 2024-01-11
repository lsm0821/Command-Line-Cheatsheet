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
- Move up one directory:

    ``` bash
    cd ..
    ```

- Move up multiple directories:

    ``` bash
    cd ../..
    ```

mkdir

- Make Directory
- Create a new directory named **Train** :

    ``` bash
    mkdir Train
    ```

touch

- Creates a new file inside the **working directory**.
- Create a new file named Train.txt:

    ``` bash
    touch Train.txt
    ```

## Manipulation

ls options

- Options: modify the behavior of commands
- ```-a```: lists all contents, including hidden files and directories.
- ```l``` : lists all contents of a directory in long format, as well as the file permissions.
- ```t``` : orders files and directories by the time they were last modified.

cat

- outputs the contents of a specified file
- Example:

    ``` bash
    cat Train.txt
    ```

Wildcards

- A special characters like ``` * ``` can select group of files

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
- Example:

    ``` bash
    mv file_original.txt file_renamed.txt
    ```

rm

- Delete files and directories
- Removing a file:

    ``` bash
    rm unwanted_file.txt
    ```

- Removing a directory and all of its child directories:

    ``` bash
    rm -r unwanted_directory
    ```

## Redirection

echo

- Accepts the string as **standard input**
- Echoes the string back to the terminal as **standard output**
- Example:

    ```bash
    echo "Hello"
    ```

- standard input ```stdin``` - information inputted into the terminal through the keyboard or input device
- standard output ```stdout``` - information outputted after a process is run
- standard error ```stderr``` - an error message outputted by a failed process

```>``` command

- redirects the standard output to a file
- takes the standard output of the command on the left, and redirects it to the file on the right
- Example 1:

  ``` bash
  echo "Hello" > hello.txt
  ```
  
  - ```"Hello"``` is entered as the standard input --> redirected to the file ```hello.txt``` by ```>```
- Example 2:

  ``` bash
  cat deserts.txt > hello.txt
  ```
  
  - output of ```cat deserts.txt``` redirected to ```hello.txt```
  - ```>``` overwrites all original content in ```hello.txt```

```>>``` command

- Takes the standard output of the command on the left and appends (adds) it to the file on the right.
- Example:

  ``` bash
  cat forests.txt >> hello.txt
  ```
  
  - output data of ```hello.txt``` will contain the original content of ```hello.txt``` with the content of ```forests.txt``` appended to it.

```<``` command

- Takes the standard input from the file on right and input it into the command on the left
- Example:

  ``` bash
  cat < deserts.txt
  ```

  - ```deserts.txt``` is the standard input for the ```cat``` command.
  - Accomplishes the same thing as ```cat deserts.txt```

```|``` Pipe command

- Takes the standard output of the command on the left, and **pipes** it as standard input to the command on the right.
- "Command to command" redirection
- Example 1:

  ``` bash
  cat volcanoes.txt | wc
  ```

  - count words in ```volcanoes.txt``` using the word count command ```wc```

``` sort ``` command

- Takes the standard input and orders it alphabetically for the standard output
- Example:

    ```bash
    sort fruits.txt

    Apple
    Banana
    Pear
    ```

```uniq``` command

- Stands for unique
- Filters out **adjacent**, **duplicated** lines in a file.
- Example:

    ``` bash
    $ cat fruits.txt
    banana
    banana
    apple
    pear

    $ uniq fruits.txt
    banana
    apple
    pear
    ```

- Using ```sort``` and ```uniq```:

    ``` bash
    sort fruits.txt | uniq
    ```

- To send filtered contents:

    ``` bash
    sort fruits.txt | uniq > new-fruits.txt
    ```

```grep``` command

- Stands for "global regular expression print"
- Searches files for lines that match a pattern and then returns the results
- **Case Sensitive**
- Example:

    ```bash
    grep America continents.txt
    ```

  - Searched for anything that matched "America" in continents.txt

```grep -i``` command

- Enables the command to be **case insensitive**
- Example:

    ``` bash
    grep -i America continents.txt
    ```

  - In this command, grep will search for capital or lowercase strings that match "America" in continents.txt.

```grep -R``` command

- Searches all files in a directory and outputs filenames and lines containing matched results
- ```-R``` stands for "recrusive"

```grep -Rl``` command

- Searches all files in a directory and outputs only filenames with matched results (No lines)
- ```l``` stands for "files with matches"

```sed``` command

- Stands for "stream editor"
- Accepts standard input and modifies it based on an expression before displaying it as output data.
- Similar to "Find and Replace"
- Example:

    ``` bash
    sed 's/snow/rain/' forests.txt
    ```

  - ```s```: stands for "substitution." Always used when using ```sed``` command.
  - ```snow```: the searching string, or the text to find.
  - ```rain```: the replacement string, or the text to add in place.
  - This command will only rewrite the command line output --> the actual file **won't be** changed.

```sed -i``` command

- This command will rewrite the actual file
- Example:

    ``` bash
    sed -i 's/snow/rain/g' forests.txt
    ```

```nano``` command

- A command line text editor.
- ```Ctrl``` + ```O```: saves a file.
- ```Ctrl``` + ```X```: exits the nano program.
- ```Ctrl``` + ```G```: opens a help menu.

```.bash_profile```

- ```.``` indicates a hidden file.
- To open and edit the bash profile:

    ```bash
    nano .bash_profile
    ```
 
- To activate the changes made in ```.bash_profile```:

    ``` bash
    source .bash_profile
    ``` 