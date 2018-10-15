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

