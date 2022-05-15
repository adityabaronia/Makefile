# Make file basics

Make file is kind of a script where all the commands related to compilation of source code is present. Instead of giving names of all the 
source file while compiling
we can mention names of those source files in a script and use it again and again.

# Points to remember while writing make files.
- Name of the file should be "Makefile".
- Make file should be present in same folder where the project is.
- Comments i make file can be given using "#".
- A single make file can run for multiple target.
- Make file can take input target. If no target is given to file then it automatically executes first target.
- There are some commands under every target. Commands are written from next line onwards and each command is given in new line. Make sure to 
give a "tab space" before every command. 
- Make file is executed using "make" command.
- We can declare variables in make file.

# How to declare variables in make file
- variable are declared without any space before delaration
- syntax:
-- $(CC) = "what ever we want to replace $(CC) with"
-- example: $(CC) = gcc

# How to write different targets
- example
 ```bash
 final: main.o add.o hello.o
  "tab space"$(CC) main.o add.o hello.o -o final
 
 clean: 
  "tab space"rm *.o final
 # clean will remove all .o extention files and final executable also
 ```



