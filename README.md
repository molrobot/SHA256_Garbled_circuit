# **Garbled Circuit**

## Basic Function
> Reading circuit from a file. Only support combinational circuit and it must be hierarchy.

### Circuit File Description Format
```
> The first line contains all of the circuit input name tag, separate with space.  
> The second line contains all of the circuit output name tag, separate with space.  
> The next ***n*** lines are the two-input logic gates description, each line contains the logic type, first input name, second input name, and output name.
```

### Sameple Circuit Description
> circuit_file.txt
```
i1 i2 i3 i4
o1 o2 o3 o4 o5
XOR i1 i2 o1
AND i2 i3 o2
OR i3 i4 o3
NAND o1 i1 o4
NOR o2 o3 o5
```

### Input Format
The input only have one line string ***s*** with 0 or 1. 

### Output Format
Output ***lo*** lines, which indicates the number of circuit output wire and each line has a name tag and a number either 0 or 1.

### Technical Specification
The input string length ***l<sub>s</sub>*** must same as the number of circuit input wire.

### Execute
```
> python garbled_circuit.py circuit_file.txt
```

### Sample Input:
```
1010
```

### Sample Output:
```
o1 1
o2 0
o3 1
o4 0
o5 0
```

## SHA256 with Garbled Circuit
> As same as the basic function, I also wrote it in another "class", and easily call the `garbled_circuit` function to calculate.

### Execute
> Using `python sha256_gc.py` to generate the input string randomly or `python sha256_gc.py <arg1>` to indicate the string.

### Example
```
> python sha256_gc.py

RANDOM STRING: A5V6S8M8qoIgte16PPls1Qq7LAtinDSO
Generate garbled circuit:  1.0856802463531494
Drcrypt garbled circuit:  0.11695456504821777
0x2b0fea56f3f4bd0305c0e9c1f69f9b1815563e9699f43ad73c2deab62d213412
```
```
> python sha256_gc.py AAAAAAAAA

Generate garbled circuit:  1.080643653869629
Drcrypt garbled circuit:  0.10996103286743164
0xe5f9176ecd90317cf2d4673926c9db65475b0b58e7f468586ddaef280a98cdbd
```