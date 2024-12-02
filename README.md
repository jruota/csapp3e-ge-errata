# csapp3e-ge-errata
Errata in the 3rd edition of "Computer Systems: A Programmer's Perspective", Global Edition

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

### **New to C?**	Pointer creation and dereferencing, p. 84
> The type of this pointer depends on the type of `x`, and hence these three
> pointers are of type `int *`, `float *`, and **`void **`**, respectively.

This should say:

> The type of this pointer depends on the type of `x`, and hence these three
> pointers are of type `int *`, `float *`, and **`void *`**, respectively.

### Solution to Problem 2.6, p. 181
The alignment of the hexadecimal float `4A1F23E0` to its binary representation
is off.
The asterisks marking matching bits is wrong. It makes it look like the first
22 bits are matching, which is not the case. Instead, the last 21 bits of the
integer match with bits 10 to 30 (inclusive) of the floating point.
```
0   0   2   7   C   8   F   8
00000000001001111100100011111000
           *********************
  4   A   1   F   2   3   E   0
  01001010000111110010001111100000
```

### Practice Problem 2.16, p. 94 / p. 184
Two answers for the arithmetic right shift by 3 bits are wrong.

They are given as

Arithmetic a >> 3
| Binary            | Hex        |
| :---------------: | :--------: |
| `[1111 1010]`     | `0xFA`     |
| **`[1110 1100]`** | **`0xEC`** |
| `[0000 1110]`     | `0x0E`     |
| **`[1110 1000]`** | **`0xE9`** |


They should be

Arithmetic a >> 3
| Binary            | Hex        |
| :---------------: | :--------: |
| `[1111 1010]`     | `0xFA`     |
| **`[0000 1100]`** | **`0x0C`** |
| `[0000 1110]`     | `0x0E`     |
| **`[0000 1000]`** | **`0x08`** |

### **Aside**	Shifting by *k*, for large values of *k*, p. 95
`unsigned uval = 0xFEDCBA98u >> 40;`

should be

`unsigned uval = 0xFEDCBA98 >> 40;`

### Solution to Problem 2.17 (page 101), p. 184
The solution for the first problem has a wrong power in the last column for
the $B2T_4 \left( \vec{x} \right)$ function.

It is given as

| Hexadecimal $\vec{x}$ | Binary $\vec{x}$ | $B2U_4 \left( \vec{x} \right)$ | $B2T_4 \left( \vec{x} \right)$ |
| :-------------------: | :--------------: | :----------------------------- | :----------------------------- |
| 0xA                   | [1010]           | $2^3 + 2^1 = 10$               | **$-2^3 + 2^2 = -6$**          |

It should be

| Hexadecimal $\vec{x}$ | Binary $\vec{x}$ | $B2U_4 \left( \vec{x} \right)$ | $B2T_4 \left( \vec{x} \right)$ |
| :-------------------: | :--------------: | :----------------------------- | :----------------------------- |
| 0xA                   | [1010]           | $2^3 + 2^1 = 10$               | **$-2^3 + 2^1 = -6$**          |

### Practice Problem 2.18, p. 105 / p. 185
The problem states

> Being able to recognize these numbers and understand their significance (for
> example, whether they are negative or positive) is an important skill.

> [...] convert the hexadecimal values (in 32-bit two's-complement form) [...]

but the numbers given in hexadecimal are unsigned with a minus sign (-)
signifying a negative value. This renders the exercise mostly useless and
demotes it to being an exercise in converting unsigned hexadecimal values to
unsigned decimal values.

### 2.2.4 Conversion between Signed and Unsigned
The code at the bottom of the page is

```C
unsigned u = 4294967295**u**;	/* UMax */
int		tu = (int) u;
```

It should be

```C
unsigned u = 4294967295;	/* UMax */
int		tu = (int) u;
```