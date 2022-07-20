# C# - Switch

## Exemplo

~~~csharp
using System;

namespace Switch
{
    class Program
    {
        static void Main(string[] args)
        {
            // Exemplo 1
            int day = 6;
            switch (day)
            {
                case 6:
                    Console.WriteLine("Today is Saturday.");
                    break;
                case 7:
                    Console.WriteLine("Today is Sunday.");
                    break;
                default:
                    Console.WriteLine("Looking forward to the Weekend.");
                    break;
            }

            // Exemplo 2
            int myInt = 1;
            switch (myInt)
            {
                case 1:
                    Console.WriteLine("Um");
                    break;
                case 2:
                    Console.WriteLine("Dois");
                    break;
                default:
                    Console.WriteLine("Nenhum");
                    break;
            }
        }
    }
}
~~~
