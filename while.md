# C# - While e Do .. While

## Exemplo

~~~csharp
using System;

namespace While_e_Do_While
{
    class Program
    {
        static void Main(string[] args)
        {
            int i;

            // while
            i = 0;
            while (i < 5)
            {
                Console.WriteLine(i);
                i++;
            }

            Console.WriteLine();

            // do .. while
            i = 0;
            do
            {
                Console.WriteLine(i);
                i++;
            } while (i < 5);
        }
    }
}
~~~
