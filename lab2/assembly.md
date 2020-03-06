# Assembly

- Register: small memory storage areas built into tthe processors. There are 8 general purpose registers + the instruction pointer which points at the next instruction to execute
  - a register can be 32 or 64 bits long
## Registers
- EAX: stores the function return values
- ECX: counter for string and loop operations
- ESI: source pointer for string operations
- EDI: destination pointer for string operations
- ESP: stack pointer
- EBP: stack frame base pointer
- EIP: pointer to next instruction to execute

### Caller-save registers
eax, edx, ecx

If the caller has anything in the registers that it cares about, the calller is in charge of saving the value before a call to a subroutine, and restoring the value after the call returns. The callee can modify values in the caller-save registers

### Callee-save registers
ebp, ebx, esi, edi

If the callee needs to use more registers than are saved by the caller, the callee is responsible for making sure the values are stored

## EFLAGS

This register holds many single bit flags.
- ZF: zero flag, set if the result of an instruction is zero
- SF: sign flag, set equal to the most significant bit of the result (negative or positive value indicator)

## x86 Operations

- NOP: no operation, used by bad guys and for padding, or delay time

### The stack

The stack is a conceptual area of main memory (RAM) which is designated by OS when a program is started.

A stack is a Last in First Out data structure where data is pushed on the top of the stack and popped off the top

By convention, the stack grows toward lower memory addresses. Adding something to the stack means the top of the stack is now at a lower memory address.

ESP points to the top of the stack, the lowes address which is being used.

The stack keeps track of which functons were called before the current one, it holds local variables and is frequently used to pass arguments to the next function to be called.

- PUSH: push word, double word or quad word onto stack. The push instruction automatically decrements the stack pointer, ESP, by 4.
- POP: pop a value from the stack. Take a DWORD off the stack, put it in a register, and increment ESP by 4.

**Calling conventions**
1.  cdecl: C declaration. Function parameters pushed onto stack right to left, saves the old frame pointer and sets up a new stack frame. Caller is responsible for cleaning up the stack.
2. stdcall: microsoft C++ code. The callee is responsible for cleaning up any stack parameters it takes

- CALL: call procedure. It transfer the control to a different function, in away that control can be later be resumed where it left off. First it pushes the address of the next instruction onto the stack, then it changes EIP to the address given in the instruction
- RET: return from procedure. There are two forms: one pop the top of the stack into EIP, while the other pop the top of the stack into EIP and add a constant number of bytes to ESP.
- MOV: move. It never moves memory to memory:
  - register to register
  - memory to register
  - register to memory
  - immediate to register
  - immediate to memory
- 

## Control Flow

Two forms of control flow:
- Conditional: if
- Unconditional: go somewhere no matter what

- JMP: change the EIP to the given address. It can be absolute, absolute indirect, near relative and short relative.

- JCC: jump if condition is met
  - JNZ/JNE: if ZF is 0
  - JLE/JNG: if ZF is 1 or SF!=OF
  - 

- CMP compare two operands. It is obtain by subtractin the second operand from the first operand and then setting the status flags in the same manner as the SUB instruction
- TEST logical compare. computes the bitwise logical AND of first operand and the second operand and sets the SF, ZF and PF status flags
  - NOT: one complement operand

- SHL: logical shift left. It puts a number of bits to zero. E.g.: shl cl,2 multiply the value by $2^2$
- SHR: dshift logical right. Division of the value
- IMUL: signed multiply
- DIV: unsigned divide.
- REP STOS: repeat store string.
  - REP is used to repeat an operation multiple times. All REP operations use ECX register as a counter
### Example 3

- line 3 allocate space for the two local varibles, initialized afterward.
- then it compares the two number
- jne jumps if the two variables are not equal (the opposite what is written in the code).

