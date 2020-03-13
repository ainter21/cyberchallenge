# Programs and their analysis

Compiling a C program is a multi stage process.
- Pre processing: in this phase preprocessor commands are interpreted (# commands in C). 
  `gcc -E hello.c`
- compilation phase: proprocessed code is translated in assembly instructions. 
  `gcc -s hello.c`
- assembly: in the assembly phase instructions are translated in machine or object code.
  `gcc -c hello.c`
- In the last phase object code are combined in a single executable. references to the used libraries are added.
  `gcc -o hello hello.o`

In static link all binaries files are contained, while in dinamic link binaries rely on system libraries, dynamic relocation.

The executable and linkable format (ELF) is a common file format for object files. there are three types of object files:
- relocatable files contain code and data that can be linked with other object files to create an executable
- executable files hold a probram suitable for execution 
- shared object files that can be linked with other relocatable and shared object files or can be use by a dynamic linker together with other executable files and object files to creat a process image.

An hel file is composed:
- ELF header
- Program header table
-  a sequence of sections
   -  .text
   -  .bss: unitialized data
   -  .data, .data1
   -  .rodata read only data
   -  .symtab
   -  .dynamic
-  a section header table

objdump and readelf are tools used to extract information from and ELF file. They are tools for static analysis.

Given a binary we can find:
- if it is executable
- discoveer the architecture
- collect symbols and strings used in the program
- check if running process are associated with the binary
- read the sha of the file and check if it is  associated with some malicious software.
- find used libraries.

We can perform disassembler actions or decompiler actions.

## Dynamic analysis

At runtime

We use a debugger in order to run the program and track the process, and change the content of memory location.

- `gcc -o helloo -g hello.c`

- `readelf --debug-dump hello`

### GDB debugger 

main gdb commands:
- file filename: loads a file
- break function: set abreakpoint at a given function
- layout asm display dissasembly and command info
- layout regs: display registers info
- run start debugged program
- stepi execute next instruction
- x/s $rax inspects the registry content

ltrace allows to execute a program and see when system libraries are used.