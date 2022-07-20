# C# - Enums

- Uma enum é uma classe especial que representa um grupo de constantes (variáveis unchangeable/read-only).
- Por padrão o primeiro elemento da enum tem valor 0, o segundo tem valor 1 e etc.
- Para obter o valor inteiro da enum é necessário realizar uma conversão explícita para int.

## Exemplo

~~~csharp
enum Level: sbyte { // type == sbyte
  Low = 10,
  Medium = 20, 
  High = 30 
}
~~~

## Exemplo

~~~csharp
using System;

namespace Enums
{
    enum Level
    {
        Low, // 0
        Medium, // 1
        High // 2
    }
    class Program
    {
        static void Main(string[] args)
        {
            Level myVar = Level.Medium;
            Console.WriteLine(myVar);
        }
    }
}
~~~

## Exemplo

~~~csharp
using System;

namespace Enums
{
    class Program
    {
        enum Level
        {
            Low, // 0
            Medium, // 1
            High // 2
        }
        static void Main(string[] args)
        {
            Level myVar = Level.Medium;
            Console.WriteLine(myVar);
        }
    }
}
~~~
