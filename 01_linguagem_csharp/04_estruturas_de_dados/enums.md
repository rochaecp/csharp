# C# - Enums

- Uma enum é uma classe especial que representa um grupo de constantes (variáveis unchangeable/read-only).  
- Por padrão o primeiro elemento da enum tem valor 0, o segundo tem valor 1 e etc.  
- Para obter o valor inteiro da enum é necessário realizar uma conversão explícita para int.  

## Enum em arquivo

~~~csharp
// Arquivo Level.cs
namespace MyProject
{
    public enum Level: sbyte 
    {
        Low = 10,
        Medium = 20, 
        High = 30 
    }
}
~~~

~~~csharp
// Arquivo Program.cs
using System;

namespace MyProject
{
    public class Program
    {
        static void Main(string[] args)
        {
            Level myVar = Level.Medium;
            Console.WriteLine(myVar);
        }
    }
}
~~~

## Printando o valor int da enum

~~~csharp
// Arquivo Program.cs
namespace ConsoleApp
{
    public class Program
    {
        public static void Main(string[] args)
        {
            TesteEnum e = TesteEnum.TRES;
            Console.WriteLine((int) e);
        }
    }

    public enum TesteEnum : int
    {
        UM = 1,
        DOIS = 2,
        TRES = 3
    }
}
~~~
