# ALX Simple Shell Team Project

> 

Write a simple UNIX command interpreter.


## Requirements
- Allowed editors: vi, vim, emacs
- All files will be compiled on Ubuntu 20.04 LTS using gcc, using the options -Wall -Werror -Wextra -pedantic -std=gnu89
- All files should end with a new line
- A README.md file, at the root of the folder of the project is mandatory
- Your code should use the Betty style. It will be checked using betty-style.pl and betty-doc.pl
- Your shell should not have any memory leaks
- No more than 5 functions per file
- All header files should be include guarded
- Use system calls only when you need to 
- Write a README with the description of the project
- You should have an AUTHORS file at the root of your repository, listing all individuals having contributed content to the repository. 


## Description ##

**hsh** is a simple UNIX command language interpreter that reads commands from either a file or standard input and executes them.

### How **hsh** works
* Prints a prompt and waits for a command from the user
* Creates a child process in which the command is checked
* Checks for built-ins, aliases in the PATH, and local executable programs
* The child process is replaced by the command, which accepts arguments
* When the command is done, the program returns to the parent process and prints the prompt
* The program is ready to receive a new command
* To exit: press Ctrl-D or enter "exit" (with or without a status)
* Works also in non interactive mode


### Invocation

Usage: **hsh** [filename]

To invoke **hsh**, compile all `.c` files in the repository and run the resulting executable.

##List of allowed functions and system calls##

    access (man 2 access)
    chdir (man 2 chdir)
    close (man 2 close)
    closedir (man 3 closedir)
    execve (man 2 execve)
    exit (man 3 exit)
    _exit (man 2 _exit)
    fflush (man 3 fflush)
    fork (man 2 fork)
    free (man 3 free)
    getcwd (man 3 getcwd)
    getline (man 3 getline)
    getpid (man 2 getpid)
    isatty (man 3 isatty)
    kill (man 2 kill)
    malloc (man 3 malloc)
    open (man 2 open)
    opendir (man 3 opendir)
    perror (man 3 perror)
    read (man 2 read)
    readdir (man 3 readdir)
    signal (man 2 signal)
    stat (__xstat) (man 2 stat)
    lstat (__lxstat) (man 2 lstat)
    fstat (__fxstat) (man 2 fstat)
    strtok (man 3 strtok)
    wait (man 2 wait)
    waitpid (man 2 waitpid)
    wait3 (man 2 wait3)
    wait4 (man 2 wait4)
    write (man 2 write)

###Compilation

Your shell will be compiled this way:

gcc -Wall -Werror -Wextra -pedantic -std=gnu89 *.c -o hsh

Testing

Your shell should work like this in interactive mode:

$ ./hsh
($) /bin/ls
hsh main.c shell.c
($)
($) exit
$

But also in non-interactive mode:

$ echo "/bin/ls" | ./hsh
hsh main.c shell.c test_ls_2
$
$ cat test_ls_2
/bin/ls
/bin/ls
$
$ cat test_ls_2 | ./hsh
hsh main.c shell.c test_ls_2
hsh main.c shell.c test_ls_2
$

##Checks##

The Checker will be released at the end of the project (1-2 days before the deadline). We strongly encourage the entire class to work together to create a suite of checks covering both regular tests and edge cases for each task. See task 8. Test suite.

