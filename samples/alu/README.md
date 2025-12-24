### C based 4bit ALU

Using godbolt to show compilation and execution of RISC-V: https://godbolt.org/z/a9dv6Mrnf

-- compile to risc-v
```
riscv64-unknown-elf-gcc -o alu alu.c
```
-- execute using spike
```
spike pk alu
```
-- command line C program run
![image](../../images/c_alu.png)

### Verilog 4bit ALU
-- compiler verilog with test bench

Note that the alu_tb.v test bench sets up the test operations and defines the name of the .vcd file for gtkwave
```
iverilog -o alu_v alu_tb.v alu.v
```
-- execute verilog
```
vvp alu_v
```
![image](../../images/alu_verilog_run.png)

-- display gtkwave for ALU (needs X windows, do it in a VNC window)
```
gtkwave.vcd
```
![image](../../images/gtkwave_alu.png)
