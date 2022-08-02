# C# - Métodos

> Métodos são blocos de códigos que só são executados quando chamados.   
> Métodos Static pertencem à classe.

## Métodos Getters e Setters

> São utilizados para obtermos e modificarmos atributos privados, são sempre public e pode-se utilizar um ou outro ou ambos.

- Arquivo: Pessoa.cs

~~~csharp
namespace MyApplication
{
    class Pessoa
    {
        private string nome;

        // propriedade
        public string Nome
        {
            get { return nome; }
            set { nome = value; }
        }
    }
}
~~~

- Arquivo: Program.cs

~~~csharp
using System;

namespace MyApplication
{
    class Program
    {
        static void Main(string[] args)
        {
            Pessoa p = new Pessoa();
            p.Nome = "Maurício";            // p.Nome usando set
            Console.WriteLine(p.Nome);      // p.Nome usando get
        }
    }
}
~~~

## Sobrecarga de Métodos

~~~csharp
using System;

namespace MyApplication
{
    class Program
    {
        static int Soma(int x, int y)
        {
            return x + y;
        }

        static double Soma(double x, double y)
        {
            return x + y;
        }

        static void Main(string[] args)
        {
            int myInt = Soma(1, 2);
            double myFloat = Soma(1.3, 2.4);
        }
    }
}
~~~

## Sobrescrita de Métodos

> Em C# para um método poder ser sobrescrito ele precisa da palavra reservada *virtual*.   
> Em C# para um método poder sobrescrever outro precisamos adicionar a palavra reservada *override*.    

## Argumentos Nomeados        

~~~csharp
using System;

namespace MyApplication
{
    class Program
    {
        static void MyMethod2(string pessoa1, string pessoa2, string pessoa3)
        {
            Console.WriteLine(pessoa1);
        }

        static void Main(string[] args)
        {
            MyMethod2(pessoa3: "Maurício", pessoa2: "Maria", pessoa1: "Joana"); // argumentos nomeados
        }
    }
}
~~~

## Parâmetros Opcionais

~~~csharp
using System;

namespace MyApplication
{
    class Program
    {
        static void MeuMetodo(string meuParametro = "Maurício") // parametro opcional
        {
            Console.WriteLine(meuParametro);
        }

        static void Main(string[] args)
        {
            MeuMetodo();
        }
    }
}
~~~
        
## Arrays como Argumento

~~~csharp
using System;
namespace MyApplication
{
    class Program
    {

        static void printArgsLen(string[] myArgs)
        {
            if (myArgs.Length == 0)
                Console.WriteLine("no argument");
            else
            {
                Console.WriteLine(myArgs.Length);
                foreach(string s in myArgs)    
                    Console.WriteLine(s);
            }
        }

        static void Main(string[] args)
        {
            string[] names = new string[] { "Maurício", "Maria", "Joana" };
            printArgsLen(names);
        }
    }
}
~~~

## Parâmetros ref

~~~csharp
using System;

namespace MyApplication
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

## Parâmetros out

~~~csharp
using System;

namespace MyApplication
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
    

