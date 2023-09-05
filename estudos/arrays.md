# C# - Arrays

## Arrays Unidimensionais

#### Criar

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

#### Indexar

~~~csharp
myItemStr = myStrArr[0]; // Um elemento
~~~

~~~csharp
for (int i = 0; i < myArrayString2.Length; i++) Todos elementos
    Console.WriteLine(myStrArr[i]);        
~~~

~~~csharp
foreach (string i in myArrayString2) // Todos elementos
    Console.WriteLine(i);   
~~~

#### Alterar

~~~csharp
myStrArr[0] = "Mauricio";
~~~

#### Length

~~~csharp
myInt = myStrArr.Length;
~~~

#### Array.Sort()

~~~csharp
Array.Sort(myStrArr);
~~~

#### Max()

~~~csharp
myInt = myIntArr.Max(); // Namespace: System.Linq
~~~        

#### Min()

~~~csharp
myInt = myIntArr.Min(); // // Namespace: System.Linq
~~~        

#### Sum()

~~~csharp
myInt = myIntArr.Sum(); // // Namespace: System.Linq
~~~ 

#### Coverter String em Array de Char

~~~csharp
string myStr = "This is String example";
char[] myCharArr = myStr.ToCharArray();        
~~~

#### Converter Array de Char em String

~~~csharp
myStr = string.Join("", myCharArr);    
~~~

## Arrays Bidimensionais

#### Criar

~~~csharp
int [,] myIntArr = new int [3, 2];
int [,] myIntArr2 = new int[3, 2] { { 1, 2 }, { 3, 4 }, { 5, 6 } };
~~~

#### Indexar

~~~csharp
myItemStr = myStrArr[0, 0];
~~~        

## Arrays Tridimensionais

#### Criar

~~~csharp
int [, ,] myIntArr = new int [3, 2, 4];
~~~
