# C# - Tipos

## Tipos por Valor

### Inteiros

| Tipo           | Característica   | Tamanho (bytes) | Tamanho (bits)  | Intervalo                 | Exemplo   |
| :---:          | :---:            | :---:           | :---:           | :---:                     | :---:     |
| ``` byte ```   | unsigned         | 1               | 8               | 0 a 255                   |           |
| ``` sbyte ```  | signed           | 1               | 8               | -127 a 128                |           |
| ``` short ```  | signed           | 2               | 16              | -32768 a 32767            |           |
| ``` ushort ``` | unsigned         | 2               | 16              | 0 a 65535                 |           |
| ``` int ```    | signed           | 4               | 32              | -2147483648 a 2147483647  |           |
| ``` uint ```   | unsigned         | 4               | 32              | 0 a 4294967295            |           |
| ``` long ```   | signed           | 8               | 64              |                           |           |
| ``` ulong ```  | unsigned         | 8               | 64              |                           | 10L       |

### Reais

| Tipo           | Característica   | Tamanho (bytes) | Tamanho (bits) | Intervalo  | Exemplo        |
| :---:          | :---:            | :---:           | :---:          | :---:      | :---:          |
| ``` float ```  | 7 digits         | 4               | 32             |            | 10F ou 35e3F   |
| ``` double ``` | 15 digits        | 8               | 64             |            | 10D ou 12E4D   |
| ``` decimal ```| 28 digits        | 16              | 128            |            |                |

### Outros

| Tipo              | Tamanho                   |
| ---               | ---                       |
| ``` char ```      | 2 bytes - unicode         |
| ``` bool ```      | 1 bit ex.: true, false    |
| ``` enum ```      |                           |
| ``` struct ```    |                           |
| ``` nullable ```  |                           |

## Tipos por Referência

| Tipo              |
| ---               |  
| ``` Class ```     |
| ``` Object ```    |
| ``` Array ```     |
| ``` Interface ``` |
| ``` Delegate ```  |

## Constantes

| Tipo          | Exemplo                   |
| ---           | ---                       |
| ``` const```  | const int myConst = 10;   |


## Operadores

sizeof()

~~~csharp
int tamanho = sizeof(byte)
~~~

