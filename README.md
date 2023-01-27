# Makefile basics

makefile is kind of a script where all the commands related to compilation of source code is present. Instead of giving names of all the 
source file while compiling we can mention names of those source files in a script and use it again and again.

Example:
```bash
ASSEMBLER=nasm -f win64
LINKER=x86_64-w64-mingw32-ld

basic:
    $(ASSEMBLER) basic.asm -o basic.o
    $(LINKER) basic.o -o basic.exe
    rm basic.o

clean:
	rm -rf basic.exe
```


# Points to remember while writing makefile.
- Name of the file should be "Makefile".
- makefile should be present in same folder where the project is and if not, then, while mentioning the file names in makefile make sure to mention file path relative to makefile.
- Comments in makefile can be given using "#".
- A single makefile can run for multiple target.
- makefile can take input target. If no target is given to file then it automatically executes first target.
- There are some commands under every target. Commands are written from next line onwards and each command is given in new line.
Example:
```bash
#here "basic" is target and line below is command to be executed
basic:
    $(ASSEMBLER) basic.asm -o basic.o
    $(LINKER) basic.o -o basic.exe
    rm basic.o

# here clean is target and line below is command to be executed
clean:
	rm -rf basic.exe
```
- Make sure to give a "tab space" before every command. 
- makefile is executed using "make" command.

Example usage:
```bash
make basic
```
- We can declare variables in makefile.

Example:
```bash
ASSEMBLER=nasm -f win64
LINKER=x86_64-w64-mingw32-ld
```

# How to declare variables in makefile
- variable are declared without any space before delaration
- syntax:
```$(CC) = "what ever we want to replace $(CC) with"```

Example: 
```bash
$(CC) = gcc
```

# How to write different targets
- example
 ```bash
LINKER=x86_64-w64-mingw32-ld
final: 
    $(LINKER) main.o add.o hello.o -o final.exe
 
clean: 
    rm *.o final.exe
# clean will remove all .o extention files and final executable also
 ```



