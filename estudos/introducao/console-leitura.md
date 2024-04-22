# C# - Leitura no Console  

## Console.Read()

- Ler o próximo caractere

~~~csharp
int myInt = Console.Read(); // le o cvalor ASCII do primeiro caracatere
char myChar = (char)Console.Read();
~~~

## Console.ReadLine()

- Ler a próxima linha

~~~csharp
string myStr = Console.ReadLine();
int myInt = Convert.ToInt32(Console.ReadLine());
int numero = Int32.Parse(Console.ReadLine()); // evitar: nem toda entrada poderá ser convertida
~~~