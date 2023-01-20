# Linux

Linux is a family of free and open-source operating systems based on the Linux kernel. Operating systems based on Linux are known as Linux distributions or distros. Examples include Debian, Ubuntu, Fedora, CentOS, Gentoo, Arch Linux, and many others.

The Linux kernel has been under active development since 1991, and has proven to be extremely versatile and adaptable. You can find computers that run Linux in a wide variety of contexts all over the world, from web servers to cell phones. Today, 90% of all cloud infrastructure and 74% of the world’s smartphones are powered by Linux.

However, newcomers to Linux may find it somewhat difficult to approach, as Linux filesystems have a different structure than those found on Windows or MacOS. Additionally, Linux-based operating systems depend heavily on working with the command line interface, while most personal computers rely on graphical interfaces.

This guide serves as an introduction to important command line concepts and skills and equips newcomers to learn more about Linux.



## The Terminal

The terms “terminal,” “shell,” and “command line interface” are often used interchangeably, but there are subtle differences between them:

A terminal is an input and output environment that presents a text-only window running a shell.
A shell is a program that exposes the computer’s operating system to a user or program. In Linux systems, the shell presented in a terminal is a command line interpreter.
A command line interface is a user interface (managed by a command line interpreter program) which processes commands to a computer program and outputs the results.
When someone refers to one of these three terms in the context of Linux, they generally mean a terminal environment where you can run commands and see the results printed out to the terminal

## Basics Commands
### Navigation

Linux filesystems are based on a directory tree. This means that you can create directories (which are functionally identical to folders found in other operating systems) inside other directories, and files can exist in any directory.

### pwd
To see what directory you are currently active in you can run the pwd command, which stands for “print working directory”:
```bash
  pwd
```

### ls
To see a list of files and directories that exist in your current working directory, run the ls command:
```bash
  ls
```

### mkdir
You can create one or more new directories within your current working directory with the mkdir command, which stands for “make directory”. For example, to create two new directories named test1 and test2, you might run the following command:
```bash
   mkdir test1 test2
```

### cd
To navigate into one of these new directories, run the cd command (which stands for “change directory”) and specify the directory’s name:
```bash
cd /home/sam/test2
```

Note: In Linux, a tilde (~) is shorthand for the home directory of the user you’re logged in as. Knowing this, you could alternatively write the previous command like this and it would achieve the same result:
```bash
cd ~/test2
```

Additionally, you can specify .. to change to the directory one level up in your path. To get back to your original directory:
```bash
cd ..
```

### File Manipulation
You cannot use cd to interact with files; cd stands for “change directory”, and only allows you to navigate directories. You can, however, create, edit, and view the contents of files.

### touch
One way to create a file is with the touch command. To create a new file called file.txt:
```bash
touch file.txt
```
This creates an empty file with the name file.txt in your current working directory. The contents of this file are empty.

### mv
If you decide to rename file.txt later on, you can do so with the mv command:
```bash
mv file.txt newfile.txt
```
mv stands for “move” and it can move a file or directory from one place to another. By specifying the original file, file.txt, you can “move” it to a new location in the current working directory, thereby renaming it.
### cp
It is also possible to copy a file to a new location with the cp command. If we want to bring back file.txt but keep newfile.txt, you can make a copy of newfile.txt named file.txt like this:
```bash
cp newfile.txt file.txt
```
As you may have guessed, cp is short for “copy”. By copying newfile.txt to a new file called file.txt, you have replicated the original file in a new file with a different name.

### cat 
The cat command prints the contents of a specified file to your system’s output. Try running cat and pass the file.txt file you just edited as an argument:
```bash
cat file.txt
```
This will print out the entire contents of file.txt to the terminal.
Using cat to view file contents can be unwieldy and difficult to read if the file is particularly long. As an alternative, you can use the less command which will allow you to paginate the output.

### less
Use less to view the contents of the file.txt file, like this:
```bash
less file.txt
```
This will also print the contents of file.txt, but one terminal page at a time beginning at the start of the file. You can use the spacebar to advance a page, or the arrow keys to go up and down one line at a time.

Press q to quit out of less.

### rm 
Finally, to delete the file.txt file, pass the name of the file as an argument to rm:
```bash
rm file.txt
```
Note: Without other options, the rm command (which stands for “remove”) cannot be used to delete directories. However, it does include the -d flag which allows you to delete empty directories:

```bash
rm -d directory
```
You can also remove empty directories with the rmdir command:

```bash
rmdir directory
```
If you want to delete a directory that isn’t empty, you can run rm with the -r flag. This will delete the specified directory along with of its contents, including any files and subdirectories:

```bash
rm -r directory
```
However, because deleting content is a permanent action, you should only run rm with the -r option if you’re certain that you want to delete the specified directory.



### man 
If your question has to do with a specific Linux command, the manual pages offer detailed and insightful documentation for nearly every command. To see the man page for any command, pass the command’s name as an argument to the man command:
```bash
man command
```
