---
tags:
  - algo
---



To print

```java
Integer.toString(100, 2);
Integer.toBinaryString(100, 2);
```

Is integer even?

```java
(x & 1) ? odd: even; //LSB is 1 for odd
```

Is n-th bit is set?

```java
(x & (1 << n) ) ? true: false;
```

Set the n-th bit
```java
y = x | (1 << n);
```

Unset the n-th bit
```java
y = x & ~(1 << n);
```

Toggle the n-th bit
```java
y = x ^ (1 << n);
```

Turn off the rightmost bit that is set to 1
```java
y = x & (x - 1); // 01011000 => 01010000
```

Turn on the rightmost 0-bit
```java
y = x | (x + 1); // 10100111 => 10101111
```

Isolate the rightmost 1-bit, producing 0 if none
```java
y = x & (~x + 1); // 01011000 => 00001000
```

Isolate the rightmost 0-bit
// Create word with single 1-bit at rightmost 0-bit

```java
y = ~x & (x + 1);
```

Right propogate the rightmost 1-bit
```java
y = x | (x - 1);
```

Turn off trailing 1's
```java
y = x & (x + 1); // 10100111 => 10100000
```

Turn on trailing 0's
```java
y = x | (x - 1); // 10101000 => 10101111
y = ~x & (x + 1); // 10100111 => 00001000
```

Create a word with single 0-bit at rightmost 1-bit
```java
y = ~x | (x - 1); // 10101000 => 11110111
```

Create a word with 1's at the position of trailing 0's and 0's elsewhere
```java
y = ~x & (x - 1); // 01011000 => 00000111
y = ~(x | -x);
y = (x & -x) - 1;
```

Create a word with 0's at the position of trailing 1's and 1's elsewhere
```java
y = ~x | (x +1); // 10100111 => 11111000
```

Create a word with 1’s at the positions of the rightmost 1-bit and the trailing 0’s in x, producing all 1’s if no 1-bit, and the integer 1 if no trailing 0’s 
```java
y = x ^ (x - 1); // 01011000 => 00001111
```

Create a word with 1's at the position of the rightmost 0-bit and the trailing 1's in x, producing all 1's if no 0-bit, and the integer 1 if no trailing 1's
```java
y = x ^ (x + 1); // 01010111 => 00001111
```

Turn off the rightmost contiguous string of 1's
```java
y = ((x & -x) + x) & x; // 01011100 => 01000000
y = (((x | (x - 1)) + 1) & x);
```



