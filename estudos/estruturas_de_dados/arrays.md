# C# - Arrays Unidimensionais

## Tamanho

~~~csharp
myInt = myStrArr.Length;
~~~

## Criar

~~~csharp
int[] myIntArr = new int[3];
int[] myIntArr2 = new int[3] { 10, 20, 30 };
int[] myIntArr3 = new int[] { 10, 20, 30 };
int[] myIntArr4 = { 10, 20, 30 };

int[] myIntArr5;
myIntArr5 = new int[3] { 10, 20, 30 };
~~~

~~~csharp
string[] myStrArr = new string[3];
string[] myStrArr2 = new string[3] { "aaa", "bbb", "ccc" };
string[] myStrArr3 = new string[] { "aaa", "bbb", "ccc" };
string[] myStrArr4 = { "aaa", "bbb", "ccc" };

string[] myStrArr5;
myStrArr5 = new string[3] { "aaa", "bbb", "ccc" };
~~~

## Indexar

#### Um elemento

~~~csharp
myItemStr = myStrArr[0]; 
~~~

#### Todos elementos

~~~csharp
for (int i = 0; i < myArrayString2.Length; i++) 
    Console.WriteLine(myStrArr[i]);        
~~~

~~~csharp
foreach (string i in myArrayString2)
    Console.WriteLine(i);   
~~~

## Alterar

~~~csharp
myStrArr[0] = "Mauricio";
~~~

## Ordenar

#### Ordenar de modo crescente

~~~csharp
Array.Sort(myStrArr);
~~~

#### Ordenar de modo decrescente

~~~csharp
int[] array = {5, 3, 8, 1, 4};
Array.Sort(array);
Array.Reverse(array);
~~~

## Exibir

#### Utilizando linq com foreach (converte em lista)

~~~csharp
using System.Linq;
// ...
int[] meuArray = { 5, 3, 8, 4, 1 };
meuArray.ToList().ForEach(e => Console.WriteLine(e));
~~~

## Max()

~~~csharp
using System.Linq;
// ...
myInt = myIntArr.Max();
~~~        

## Min()

~~~csharp
using System.Linq;
// ...
myInt = myIntArr.Min();
~~~        

## Sum()

~~~csharp
using System.Linq;
// ...
myInt = myIntArr.Sum();
~~~ 

## Coverter String em Array de Char

~~~csharp
string myStr = "This is String example";
char[] myCharArr = myStr.ToCharArray();        
~~~

## Converter Array de Char em String

~~~csharp
myStr = string.Join("", myCharArr);    
~~~

# C# - Arrays Bidimensionais

## Criar

~~~csharp
int [,] myIntArr = new int [3, 2];
int [,] myIntArr2 = new int[3, 2] { { 1, 2 }, { 3, 4 }, { 5, 6 } };
~~~

## Indexar

~~~csharp
myItemStr = myStrArr[0, 0];
~~~        

# C# - Arrays Tridimensionais

## Criar

~~~csharp
int [, ,] myIntArr = new int [3, 2, 4];
~~~
