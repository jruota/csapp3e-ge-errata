# csapp3e-ge-errata
Errata in the global, third edition of "Computer Systems: A Programmer's Perspective"

## Chapter 2: Representing and Manipulating Information

### Practice Problem 2.1 A, p. 73 / p. 179
The solution is given as:
```
0010 0101 1101 1001 1101 0010
```
It should be:
```
0010 0101 1011 1001 1101 0010
```

### Practice Problem 2.1 B, p. 73 / p. 179
The problem asks to convert:
```
1010 1110 0100 1001 [0xAE49]
```
The solution is for a different number:
```
1100 1001 0111 1011 [0xC97B]
```

### New to C?	Pointer creation and dereferencing, p. 84
> The type of this pointer depends on the type of `x`, and hence these three
> pointers are of type `int *`, `float *`, and **`void **`**, respectively.
This should say:
> The type of this pointer depends on the type of `x`, and hence these three
> pointers are of type `int *`, `float *`, and **`void *`**, respectively.