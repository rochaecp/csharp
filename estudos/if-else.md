# C# - IF .. Else

## Exemplo

~~~csharp
using System;

namespace If_Else
{
    class Program
    {
        static void Main(string[] args)
        {
            int time = 22;
            int myInt = 1;

            // if 1
            if (time < 10)
            {
                Console.WriteLine("Good morning.");
            }
            else if (time < 20)
            {
                Console.WriteLine("Good day.");
            }
            else
            {
                Console.WriteLine("Good evening.");
            }

            // if 2
            // comando if..else
            if (myInt == 1)
                Console.WriteLine("Um");
            else if (myInt == 2)
                Console.WriteLine("Dois");
            else
                Console.WriteLine("Nenhum");
        }
    }
}
~~~
