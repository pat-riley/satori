#System Architecture

##Filesystem Hierarchy Standard (FHS)
Defines the directory structure and directory contents in Unix and Unix-like operating systems.

In the FHS all files and directories appear under the root directory `/`

* need to put a full description here http://en.wikipedia.org/wiki/Filesystem_Hierarchy_Standard

http://hivelogic.com/articles/using_usr_local




##Shell

In computing, a shell is a user interface for access to a computers operating system services. In general, operating systems use either a command-line interface (CLI) of a graphical user interface (GUI).

A shell is the generic name for any program that gives you a text-interface to interact with the computer.
You type a command and the output is shown on screen.

Many shells have scripting abilities: Put multiple commands in a script and the shell executes them as if they were typed from the keyboard. Most shells offer additional programming constructs that extend the scripting feature into a programming language.

On most Unix/Linux systems multiple shells are available: bash, csh, ksh, sh, tcsh, zsh just to name a few. They differ in the various options they give the user to manipulate the commands and in the complexity and capabilities of the scripting language.

##Bash 

Bash is a specific UNIX shell. It is a command processor, Which means that you type commands into it cause actions. It can also read command from a file, called a script. 

The name itself is an acronym, a pun, and a description. As an Acronym, it strands for *Bourne-agin shell* referring to its objective as a free replacement for the Bourne shell. As a pun, it is expressed that objective in a phrase that sounds similiar to borne again, a term for spiritual rebirth. The term is also descriptive of what it did, bashing together the features of sh, csh, and ksh.


Both the `~/.bashrc` and `~/.bash_profile` are scripts that might be executed when bash is invoked (started up). 


####Login Shell & Nonlogin
A **Login** shell is run as part of the login of the user to the system. Typically used to do any configuration that a user needs/wants to establish his work-environment.

A **Non-login** shell is run by the user after logging on, or which is run by any automated process which is not coupled to a logged in user.

A login Shell is a bash shell that is started with - or --login. The following examples invoke a login shell.

```
sudo su -
bash --login
ssh user@host
```
When BASH Is invoked as a login shell, the following files are executed in the displayed order.
1. `/etc/profile`
2. `~/.bash_profile`
3. `~/.bash_login`
4. `~/.profile`




####Interactive Shell

**Interactive:** As the term implies: Interactive means that the commands are run with user-interaction from keyboard. E.g. the shell can prompt the user to enter input.

**Non-interactive:** the shell is probably run from an automated process so it can't assume if can request input or that someone will see the output. E.g Maybe it is best to write output to a log-file.

`~/.bashrc` gets executed when you run bash on an interactive shell that is **not** a login shell.

```
sudo su
bash
ssh user@host /path/to/command
```


##Path
`$PATH` is nothing but an environment variable on Linux and OS X like systems.

It is where the keywords are stored, or the commands that are then turned into actions.

You can specify a set of directories where executable programs are located using $PATH

The Path variable is specified as a list of directory names seperated by colon (:)

When you run a command from a UNIX or UNIX-like shell, the shell looks for the executable file using the directories listed in your PATH variable as a map. For convenience, adding directories to this environment variable means you don’t have to go hunting for a file each time you run it. Following these directions will allow you to add a directory to the search PATH.

To change your path, you must edit the `.profile` file in your home directory.


##Binary Files

A file that is not a text file; it may comtain any type of date encoded in binary form for computer storage and processing purposes. 

In Linux you'll often hear the term binaries when referring to "binary executable files" or programs. This is because whiles sources of most programs (written in high-level languages) are plain text, complied exectuables are binary. 

####Where are Binaries located

`/bin` Essential command binaries that need to be availible for all users

`/usr/bin` Non-essential command binaries for all users

`/usr/local/bin` Binaries of personal apps



##Terminal Commands
`echo` is a command that places a string on the terminal. It is a built in command typically used in shell scripts and batch files to output text to a screen or file.



