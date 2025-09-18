```HTML
<a href="https://www.codecademy.com/article/command-line-commands"> Command Line Prompts Complete List</a>
```

# File System Navigation

* ls - "list" lists all the files inside the current directory

* pwd - "print working directory" and outputs the name of the directory and the path.

* cd - "change directory" switches the directory
        example: cd home
    - If we want to move up one directory we can do cd ..
    - Moving several directories down can be done by typing the path to the directory we want.
        example: cd home/Documents/Cats
    - Moving up several directories is also possible
        example: cd ../../..
    - Also moving to an adjacent directory can be done by combining the two commands.
        example: cd ../Dogs

* mkdir - "make directory" makes a new directory (lol).
    example: mkdir basics

* touch - makes new files.
    example: touch text_file.txt

We can make multiple directories and files with 1 command by separating the names.
Example: touch file1.txt file2.txt

*Personal Note (not in the lesson):*
We can also "pipe" commands together with |
Example: mkdir RandomFolder | touch text_file.txt 

*Another note:*
Renamed and moved the file into the OS folder as this had absolutely nothing to do with web dev. Idk why Codecademy decided to name the module "CLI for deploying sites"...