# Simple Shell project

## Table of Contents
*[Description](#description)
*[File Structure](#file-structure)
*[File Structure](#Directories)
*[Requirements](#requirements)
*[Installation](#installation)
*[Usage](#usage)
*[Exampe of Use](#example-of-use)

* [Bugs](#bugs)
* [Authors](#authors)
* [License](#license)

## Description
Simple_shell is a command line interpreter, or shell, made by us in the tradition of the first Unix shell written by Ken Thompson in 1971. This shell is
intentionally minimalistic
Standard functions and system calls employed in simple_shell include:
	 `access, execve, exit, fork, free, fstat, getline, malloc, perror, signal, stat, wait, write.`

## File Structure
* [holberton.h](holberton.h) -Program header file


* [builtins.c](builtins.c) - Major builtin functions
	* `check_for_builtins` - Checks if the command is a builtin
	* `new_exit` - Exits the shell with the option of a specified status
	* `_env` - Prints the current shell's environment variables to the standard output
	* `new_setenv` -  Create a new environment variable, or edit an existing variable
	* `new_unsetenv` - Removes an environment variable

* [builtins2.c](builtins2.c) - Builtin functions that involves 'cd' builtin command.
	* `_new_cd` - Changes the current working directory .

* [enviroment](enviroment) - More builtin functions
	* `make_enviroment` - Make the shell environment from the environment.
	* `free_env` - Free the shell's environment

* [history.c](history.c) - History builting and funcions related to it.
	* `add_nodeint` - Add node in the beginning
	* `free_listint` - Free pointers related with malloc
	* `new_history` - Print the list of a single list
	* `_puts3` - Writes a string to standard output
	* `print_message` - Print a string to standart output

* [add_functions.c](add_functions.c) - Helpers functions for forking process
	* `_strcmp` - Compares two strings
	* `error_printing` - Prints a message error when a comand is not found.
	* `exec_error` - Prints exec errors.

* [helper_functions.c](helper_functions.c) - Functions to manage error messages     	and utils
	* `_puts_error` - Print a string to sdandart error
	* `prints_error_msg` - Prints error messages to standard error
	* `integer_converter` - Converts an unsigned int to a string
	* `atoi` - Converts a string into an integer

* [setenv_functions.c](setenv_functions.c) - helper functions for setenv builting
	* `add_value` - Creates a new environment variable string
	* `find_key` - Finds an environment variable
	* `add_key` - Create a new environment variable

* [memory_allocation.c](memory_allocation.c) - memory allocation functions
	* `_realloc` - A custom realloc function for arrays of pointers

* [new_strtok.c](new_strtok.c) - Custom strtok and helper functions
	* `check_match` - Checks if a character matches any in a string
	* `new_strtok` - A custom strtok for the shell
	* `build_path` - Combines two strings one representing the path directory and another representing the command file.

* [fork_child.c](fork_child.c) - functions related to executing commands
	* `fork_child` - Creates a child in  order to execute another program.
	* `path_finder` - Acts as an interface for functions that will be able
	*  to find the full path of a program.
	* `find_env_index` - Finds the index of an environmental variable.
	* `tokenize_path` - Separates a string of path as an array of
	*  strings containing the path directories.
	* `search_directories` - Looks through directories stored in path_tokens
	*  for a specific file aka command.

* [simple_shell.c](simple_shell.c) - essential functions to the shell
	* `main` - The main function of the program
	* `sig_handler` - Handles SIGINT

* [strfunctions.c](strfunctions.c) - functions related to string manipulation
	* `_puts` - Writes a string to standart output
	* `_strdup` - Duplicates a string
	* `_strcmpr` - Compares two strings
	* `_strcat` - Concatenates two strings with a `/` in the middle
	* `_strlen` - Calculates the length of a string

* [tokenizer.c](tokenizer.c) - tokenizing function
	* `tokenizer` - creates an array of tokens from a buffer with a specified delimiter
	* `tokenize` -tokenizes a buffer with a delimiter just use for for_child
	* `token_interface` - token interface
	* `count_token` - token's count

* [new_help.c](new_help.c) - Help builting and functions
	* `new_help` - Help builtin command
	* `new_help_help` -  Help builtin command help
	* `new_help_exit` - Help builtin command exit
	* `new_help_cd` - Help builtin command cd
	* `new_help_env` -  Help builtin command env

* [more_help_functions.c](more_help_functions.c) - More help functions
	* `new_help_history` - Help builtin command history
	* `new_help_unalias` - Help builtin command unalias
	* `new_help_unset` - Help builtin command unset
	* `new_help_unsetenv` - Help builtin command unsetenv
	* `new_help_setenv` -  Help builtin command setenv

* [more_help_functions2.c](more_help_functions2.c) -  More help functions
	* `new_help_alias` - Help builtin command alias
	* `new_help_else` - Error message if not command found

* [print_functions.c](print_functions.c) -  More utils
	* `print_str` - Prints a string character by character.
	* `_write_char` - Writes a character to stdout
	* `print_number` - Prints an unsigned number

* [man_1_simple_shell](man_1_simple_shell) -  Shell Man page

## Directories
* [helpfiles](helpfiles) - arguments files for help building.
* [Mishell](Mishell) - testing shell apart.
* [shell2](shell2) - backup to test shell, outdated version.

## Requirements

simple_shell is designed to run in the `Unix environment` linux environment and to be compiled using the GNU compiler collection v. `gcc 4.8.4` with flags`-Wall, -Werror, -Wextra, and -pedantic.`

## Installation

	 - Clone this repository: `https://github.com/yoyogold-a11/shelltestenviroment.git`.
	 - Change directories into the repository: `cd simple_shell`
	 - Compile: `gcc -Wall -Werror -Wextra -pedantic *.c -o hsh`
	 - Run the shell in interactive mode: `./hsh`
	 - Or run the shell in non-interactive mode: example `echo "pwd" | ./hsh`

## Usage

The simple_shell is designed to execute commands in a similar manner to sh, however with more limited functionality. The development of this shell is ongoing. The below features will be checked as they become available (see man page for complete information on usage):

### Features
- [x] uses the PATH
- [x] implements builtins
- [x] handles command line arguments
- [x] custom strtok function
- [x] uses exit status
- [x] shell continues upon Crtl+C (**^C**)
- [x] handles comments (#)
- [x] handles **;**
- [ ] custom getline type function
- [ ] handles **&&** and **||**
- [ ] aliases
- [ ] variable replacement


### Builtins

- [x] exit
- [x] env
- [x] setenv
- [x] unsetenv
- [x] cd
- [x] help
- [x] history

## Example of Use
Run the executable in your terminal after compiling:
```
$ ls
add_functions.c           helpfiles            more_help_functions2.c  shell2
builtings.c               holberton.h          more_help_functions.c   strfunctions.c
enviroment.c              hsh                  new_help.c              tokenizer.c
env_unsetenv_functions.c  main.c               new_strtok.c
fork_child.c              memory_allocation.c  print_functions.c
helper_functions.c        Mishell              README.md
$ help 2
./hsh: 5: help: no help topics match: `2'.  Try `help help' or `man -k 2' or `info 2'.
$ help cd
cd: cd
	Change the shell working directory.

	Change the current directory to DIR.  The default DIR is the value of the
	HOME shell variable.

	The variable CDPATH defines the search path for the directory containing
	DIR.  Alternative directory names in CDPATH are separated by a colo
n (:).
	A null directory name is the same as the current directory.  If DIR begins
	with a slash (/), then CDPATH is not used.

	Exit Status:
	Returns 0 if the directory is changed, and if $PWD is set successfully when
	-P is used; non-zero otherwise.
$ pwd
/home/shell_test/shelltestenviroment
$
```
## Bugs
At this time, there are no known bugs.

## Authors
Rytone Odhiambo | [GitHub](https://github.com/rai8)

Daisy | [GitHub](https://github.com/deeysi)

## License
simple_shell is open source and therefore free to download and use without permission.
