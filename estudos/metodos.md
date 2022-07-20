# C# - Métodos

- **Métodos**:
    - Métodos são blocos de códigos que só são executados quando chamados.

## Exemplo

- Arquivo: Pessoa.cs

~~~csharp
using System;

namespace MeuProjeto
{
    public class Pessoa
    {
        // metodo 1
        public void apresentar()
        {
            Console.WriteLine("Olá");
        }
        // metodo 2
        public void apresentar(string nome)
        {
            Console.WriteLine("Olá " + nome);
        }
        // metodo 3
        public void apresentar(string nome, int idade)
        {
            Console.WriteLine("Olá " + nome + " Idade é " + idade);
        }
    }
}
~~~

- Arquivo: Program.cs

~~~csharp
using System;

namespace MeuProjeto
{
    class Program
    {
        static void Main(string[] args)
        {
            Pessoa obj = new Pessoa();
            obj.apresentar();
            obj.apresentar("Mauricio");
            obj.apresentar("Mauricio", 29);
        }
    }
}
~~~

## Exemplo

~~~csharp
using System;
namespace Treinos
{
    class Program
    {
        /* name is a parameter, static means that the method belongs 
        to the Program class and not an object of the Program class. */
        static string sayHello(string name)
        { 
            return $"Hello {name}";
        }

        static void Main(string[] args)
        {
            Console.WriteLine(sayHello("Mauricio")); // "Mauricio" is an argument
        }
    }
}
~~~

## Exemplo - Parâmetro opcional e argumentos nomeados

~~~csharp
using System;
namespace Treinos
{
    class Program
    {
        // country é um parâmetro opcional
        static void MyMethod(string country = "Brasil")
        {
            Console.WriteLine(country);
        }

        static void MyMethod2(string child1, string child2, string child3)
        {
            Console.WriteLine("The youngest child is: " + child3);
        }

        static void MyMethod3(string child1 = "Liam", string child2 = "Jenny", string child3 = "John")
        {
            Console.WriteLine(child3);
        }

        static void Main(string[] args)
        {
            MyMethod();
            MyMethod("Uruguai");

            // argumentos nomeados
            MyMethod2(child3: "John", child1: "Liam", child2: "Liam"); // call

            MyMethod3();
        }
    }
}
~~~

## Exemplo - Sobrecarga de métodos

~~~csharp
using System;
namespace Treinos
{
    class Program
    {
        static int PlusMethod(int x, int y)
        {
            return x + y;
        }
        static double PlusMethod(double x, double y)
        {
            return x + y;
        }
        static void Main(string[] args)
        {
            Console.WriteLine(PlusMethod(2, 3));
            Console.WriteLine(PlusMethod(2.3, 3.2));
        }
    }
}
~~~

## Exemplo - Strings e Arrays como argumentos

~~~csharp
using System;
namespace Treinos
{
    class Program
    {
        static void printArgs(string[] myArgs)
        {
            if (myArgs.Length == 0)
                Console.WriteLine("no argument");
            else
                Console.WriteLine($"{myArgs.Length} arguments");
        }

        static void Main(string[] args)
        {
            string[] names = new string[3] { "Mauricio", "Maria", "Jose" };
            printArgs(names);
        }
    }
}
~~~

## Exemplo - Parâmetros ref

~~~csharp
using System;
namespace Treinos
{
    class Program
    {
        static void swapInt(ref int x, ref int y)
        {
            int temp = x;
            x = y;
            y = temp;
        }

        static void Main(string[] args)
        {
            int x = 10, y = 20;

            Console.WriteLine($"x = {x}, y = {y}");
            swapInt(ref x, ref y);
            Console.WriteLine($"x = {x}, y = {y}");
        }
    }
}
~~~

## Exemplo - Parâmetros out

~~~csharp
using System;
namespace Treinos
{
    class Program
    {
        static void divide(int x, int y, out int result, out int rest)
        {
            result = x / y;
            rest = x % y;
        }
        static void Main(string[] args)
        {
            int result, rest;
            divide(10, 3, out result, out rest);
            Console.WriteLine($"result = {result}, rest = {rest}");
        }
    }
}
~~~
