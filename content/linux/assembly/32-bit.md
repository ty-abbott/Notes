### Instructions

mov <dest>, <source> ; Copy data from the <source> to the <dest>
xor <dest>, <source> ; XOR <source> with <dest> and store the answer in <dest>
cmp <dest>, <source> ; Compare <dest> with <source> by subtracting <source> from <dest> and checking if the answer is 0, if it is then it sets the Zero Flag in the Eflags register to 1
jz <dest>  ; Branch off to <dest> if the Zero Flag has been set
db <bytes>  ; Define bytes: This is an instruction to nasm to reserve bytes inside the section it is referenced
int <number>  ; This sends a software interrupt and <number> is an index in the interrupt table to determine the Kernel functionality that is called. For example, int 80h(h means hex number) is the system call functionality which we will be using a lot

### Registers
The data registers are EAX, EBX, ECX, and EDX:

EAX is normally used in any arithmetic operation
EBX is normally used as a base register to start referring to memory addresses
ECX is normally the counter register for looping
EDX is normally the register used for storing data for operations
The pointer registers are EIP, EBP, and ESP:

EIP is the instruction pointer which holds the memory address of the next instruction to be run
EBP is the base pointer which holds the memory address of the base of the current stack frame
ESP is the stack pointer which holds the memory address of the top of the current stack frame
The index registers are ESI and EDI:

ESI is the source index where the memory location for the start of a string is stored for string operations
EDI is the destination index where the memory location to store the string after it has been operated on is stored
Control registers

Lots of assembly instructions involve comparing or making mathematical calculations. The eflags register sets either a 0 or a 1 depending on the results of these comparisons or calculations. Once these results are evaluated, the program may need to jump to other branches of code (think if statements for higher level programming languages). There are 32 bits in the eflags register and each bit represents a different evaluation of the previous instruction. This series will cover many of them as they occur, but the below are particularly important for the moment:

Interrupt flag (IF) − If this is set to 1 then external interrupts like keyboard entry are to be processed. 0 means they are ignored.

Zero flag (ZF) − This shows the result of a comparison or mathematical operation. If a CMP returns a result of nonzero, it will clear the zero flag to 0. A result of 0 sets it to 1.

add <register>, <register>
cmp <register>, <memory>
mov <register>, <immediate>
xor <memory>, <register>
add <memory>, <immediate>

### File
The file command is critical for reversing. It will show if a binary is stripped or not (whether the binary has had all of its strings, function names, debugging information, and other such important information taken away during assembling and linking)
It can state whether the file is dynamically or statically linked (if the resources it needs are found in the executable folder or if they need to be present on the disk somewhere

### Readelf 
Readelf provides information on ELF executables. Using readelf -a <executable> will display:

File headers
Program headers
Section headers
Symbols
Relocations (if present)
Dynamic sections (if present)
Version sections (if present)
Architecture-specific information

### File structure 

All of the information above is important, yet you'll notice that some of the data returned may or may not be present in the binary. There are certain pieces of data that will always be present in an executable, as referred to the Application Binary Interface (ABI) in Linux. This is a set of ‘rules’ that executables need to follow for them to be ELF executables.

One of the important parts of the readelf analysis is Section headers. In the image below you can see a number of different sections shown from the readelf output. If you refer to the code above the assembly program, it only declares two sections: .text and .data. The assembler actually creates a few more sections automatically with the headers which hold the information about each of the following sections:

.text – Stores the executable code (defined by the program above)
.data – Stores the initialized variables (defined by the program above)
.symtab – An object file's symbol table which holds information needed to locate and relocate a program's symbolic definitions and symbolic references
.strtab – String table sections hold null-terminated character sequences, commonly called strings
.shstrtab – Holds section names
