# C# - Beecrowd

- Lendo uma entrada a partir de um arquivo
    - Arquivo **Program.cs**:
    ~~~csharp
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

    - Para ler a partir de um arquivo **entrada.txt**:
    ~~~bash
    cat .\entrada.txt | dotnet run
    ~~~

- Lendo uma entrada até encontrar o EOF