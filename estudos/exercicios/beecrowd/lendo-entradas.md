# C# - Beecrowd

## Lendo uma entrada a partir de um arquivo

~~~csharp
// Arquivo Program.cs
using System;

namespace ConsoleApp
{
    public class Program
    {
        static void Main(string[] args)
        {
            string? x = Console.ReadLine();
            Console.WriteLine("Bom dia " + x);
        }
    }
}
~~~

~~~bash
# No cmd: Para ler a partir de um arquivo **entrada.txt**:
cat .\entrada.txt | dotnet run
~~~

## Lendo uma entrada até encontrar o EOF

~~~csharp

~~~
