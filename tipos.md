# C#

## Tipos de dados

- Tipos por Valor

~~~csharp
byte myByte = 10;       // 1 byte unsigned 0 to 255
sbyte mySbyte = 10;     // 8 byte signed -127 to 128
short myShort = 10;     // 2 bytes signed -32768 to 32767
ushort myUshort = 10;   // 2 bytes unsigned 0 to 65535
int myInt = 10;         // 4 bytes signed -2147483648 to 147483647
uint myUint = 10;       // 4 bytes unsigned 0 to 4294967295
long myLong = 10L;      // 8 bytes signed
ulong myUlong = 10L;    // 8 bytes unsigned
float myFloat1 = 10F;   // 4 bytes 7 digits
float myFloat2 = 35e3F; // 4 bytes 7 digits
double myDoub1 = 10D;   // 8 bytes 15 digits
double myDoub2 = 12E4D; // 8 bytes 15 digits
decimal myDecimal = 10; // 16 bytes 28 digits
char myChar = 'A';      // 2 bytes - unicode
bool myBoolean = true;  // 1 bit

// enum
// struct
// nullable
~~~

- Tipos por Referência

~~~csharp
string myString = "abc";

// Class 
// Object
// Array
// Interface
// Delegate
~~~

- Constantes

~~~csharp
const int myConst = 10; // myConst = 9; // erro
~~~
