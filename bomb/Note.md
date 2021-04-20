## How resolve the bomb lab

disassemble the executable file:

```bash
objdump -d bomb > bomb.asm
```

then, you could read the disassembled code in bomb.asm!

### Find the first phase

first of all, you should find the phase_1 section in bomb.asm. Next, we can get it that the code just compare our input with the string that was stored in `$0x402400`, therefore we just have to get that string!

```bash
yum install gdb
gdb bomb
x/s 0x402400
```

then we can see the correct string displayed on the terminal:

```bash
Border relations with Canada have never been better.
```