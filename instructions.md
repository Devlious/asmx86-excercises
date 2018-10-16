# General-Purpose Registers

## The 64-bit versions of the x86 registers

- **rax** - register a extended
- **rbx** - register b extended
- **rcx** - register c extended
- **rdx** - regisster d extended
- **rbp** - register base pointer ( start of stack )
- **rsp** - register stack pointer ( current location in stack, growing downwards )
- **rsi** - register source index ( source for data copies )
- **rdi** - register destination index ( destination for data copies ) 

### Registers 64-bit mode

- **r8** - register 8

- **r9** - register 9

- **r10** - register 10

- **r11** - register 11

- **r12** - register 12

- **r13** - register 13

- **r14** - register 14

- **r15** - register 15


### These may be accessed as

- **64-bit** registers using the **'r'** prefix: 

- ```assembly
  mov rax
  mov rdi
  mov r10
  mov r11
  ```

- **32-bit** registers using the **'e'** prefix or **'d'** suffix:

- ```assembly
  mov eax
  mov edi
  mov r10d
  mov r11d
  ```

- **16-bit** registers using **no** prefix ( original ) or **'w'** suffix:

- ```assembly
  mov ax
  mov di
  mov r10w
  mov r11w
  ```

- **8-bit** registers using **'h'** ( high-byte of 16 bits ) suffix:

- ```assembly
  mov ah
  mov dh
  ```

- **8-bit** registers using **'l'** ( low-byte of 16 bits ) or **'b'** suffix:

- ```assembly
  mov al
  mov dl
  mov r10b
  mov r11b
  ```



### Usage during syscall/function call

- First six arguments are in **rdi, rsi, rcx, r8d, r9d**; remaining arguments are on the stack.
- For syscalls, the syscall number is in **rax**.
- Return value is in **rax**.
- The called routine is expected to preserve **rsp, rbp, rbx, r12, r13, r14 and r15** but may trample any other registers.



#### Stack Pointer Register (RSP)

**rsp** is used to point to the current top of the stack. The **rsp** register should not be used for data or other uses.

#### Base Pointer Register (RBP)

**rbp** is used as a base pointer during function calls. The **rbp** register should not be used for data or other uses.

#### Instruction Pointer Register (RIP)

In addition to the GPRs, there is a special register, **rip**, that is used by the CPU to point to the **next instruction to be executed**. Specifically, since the **rip** points to the next instruction, that means the instruction being pointed to by **rip**, and shown in the debugger, has not yet been executed. _This is an important distinction which can be confusing when reviewing code in a debugger_



# Instructions - Starter kit

```assembly
add %r10, %r11 ; add r10 and r11, put result in r11
cmp %r10, %r11 ; compare register r10 with register r11. The comparison sets flags in the processor status register which affect conditional jumps.
cmp $99, %r11 ; compare the number 99 with register r11. The comparison set flags in the processor status register which affect conditional jumps.
div %r10 ; divide rax by the given register (r10), place quotient into rax and remainder into rdx (rdx must be zero before this instruction)
inc %r10 ; increment r10
jmp label ; jump to label
je label ; jump to label if equal
jne label ; jump to label if not equal
jl label ; jump to label if less
jg label ; jump to label if greater
mov %ro10, %r11 ; move data from r10 to r11
mov $99, %r10 ; put the immediate value 99 into r10
mov %r10, (%r11) ; move data from r10 to address pointed to by r11
mov (%r10), %r11 ; move data from address to by r10 to r10
mul %r10 ; multiplies rax by r10, places result in rax and overflow in rdx
push %r10 ; push r10 into the stack
pop %r10 ; pop r10 off the stack
syscall ; invoke a syscall (in 32-bit mode, use "int 0x80" instead)

```

