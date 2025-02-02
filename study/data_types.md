# FUNDAMENTAL DATA TYPES

A fundamental data type is an elementary unit of data that is manipulated by the processor 
during program execution. The x86 platform supports a comprehensive set of fundamental 
data types ranging in length from 8 bits (1 byte) to 256 bits (32 bytes). Table 1-1 shows 
these types along with typical uses.

## X86 Fundamental Data Types

```
DATA TYPE           Length in Bits  Typical Use

Byte                8               Character, integers, Binary Coded Decimal (BCD) values
Word                16              Character, integers
Doubleword          32              Integers, single-precision floating-point
Quadword            64              Integers, double-precision floating-point, packed integers
QuintWord           80              Double extended-precision floating-point, packed BCD
Double Quarword     128             Packed integers, packed floating-point
Quad Quadword       256             Packed integers, packed floating-point
```

## NUMERICAL DATA TYPES

A numerical data type is an elementary value such as an integer or floating-point 
number. All numerical data types recognized by the CPU are represented using one of the 
fundamental data types discussed in the previous section. Numerical data types can be 
divided into two subtypes: scalar and packed.

### SCALAR

Scalar data types are used to perform calculations with discrete values. The x86 
platform supports a set of scalar data types that resemble the basic data types available 
in C/C++

```
TYPE                    Size in Bits    Equivalent C/C++ Type

Signed integers         8/16/32/64      Char/short/int and long/long long
Unsigned integers       8/16/32/64      unsigned char/unsigned short/unsgined int and unsgined long/unsigned long long                                 
Floating-point          32/64/80        float/double/long double
```
### PACKED

The x86 platform supports a variety of packed data types, which are employed to perform 
SIMD calculations using either integers or floating-point values.

```
Packed Size (Bits)      Data Element Type                                                       Number of Items

64                      bit integers: 8,16,32,64                                                8,4,2
128                     bit integers: 8,16,32,64, Single-precision FP, Double-precision FP      16,8,4,2,4,2
256                     bit integers: 8,16,32,64, Single-precision FP, Double-precision FP      32,16,8,4,8,4
```

