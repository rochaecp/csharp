# C# - For e Foreach

## Exemplo 

~~~csharp
using System;

namespace For
{
    class Program
    {
        static void Main(string[] args)
        {
            for (int i = 0; i < 5; i++)
            {
                Console.WriteLine(i);
            }
        }
    }
}
~~~

## Exemplo 

~~~csharp
using System;

namespace Foreach
{
    class Program
    {
        static void Main(string[] args)
        {
            // foreach
            string[] cars = { "Volvo", "BMW", "Ford", "Mazda" };
            foreach (string i in cars)
            {
                Console.WriteLine(i);
            }
        }
    }
}
~~~
