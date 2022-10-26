# C# - Tipos

## Tipos por Valor

### Inteiros

| Tipo | Tamanho |
| --- | --- |
| ``` byte ```  | 8-bit - 1 byte unsigned 0 to 255 |
| ``` sbyte ``` | 8-bit - 1 byte signed -127 to 128|
| ``` short ``` | 16-bit - 2 bytes signed -32768 to 32767|
| ``` ushort ```| 16-bit - 2 bytes unsigned 0 to 65535|
| ``` int ```	| 32-bit - 4 bytes signed -2147483648 to 147483647|
| ``` uint ```  | 32-bit - 4 bytes unsigned 0 to 4294967295|
| ``` long ```  | 64-bit - 8 bytes signed|
| ``` ulong ``` | 64-bit - 8 bytes unsigned - ex.: 10L|

### Reais

| Tipo | Tamanho |
| --- | --- |
| ``` float ```		| 4 bytes 7 digits - ex.: 10F ou 35e3F|
| ``` double ```	| 8 bytes 15 digits - ex.: 10D ou 12E4D|
| ``` decimal ```	| 16 bytes 28 digits|

### Outros

| Tipo | Tamanho |
| --- | --- |
| ``` char ``` | 2 bytes - unicode|
| ``` bool ``` | 1 bit ex.: true, false|
| ``` enum ```| |
| ``` struct ```| |
| ``` nullable ```| |

## Tipos por Referência

| Tipo |
| --- | 
| ``` Class ```			|
| ``` Object ```		|
| ``` Array ```			|
| ``` Interface ```		|
| ``` Delegate ```		|

## Constantes

| Tipo | Exemplo |
| --- | --- |
| ``` const``` | const int myConst = 10; |


## Operadores

sizeof()

~~~csharp
int tamanho = sizeof(byte)
~~~

