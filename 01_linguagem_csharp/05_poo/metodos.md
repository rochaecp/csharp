# C# - Métodos

- Métodos são blocos de códigos que só são executados quando chamados.   
- Métodos Get e Set:
    - São utilizados para obtermos e modificarmos atributos privados.  
    - São sempre public.    
    - Pode-se utilizar um ou outro ou ambos.  

## Métodos Get e Set

~~~csharp
// Arquivo: Pessoa.cs
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

~~~csharp
// Arquivo: Program.cs
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

## Argumentos Nomeados      

~~~csharp
// Arquivo: Program.cs
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
// Arquivo: Program.cs
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
// Arquivo: Program.cs
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
// Arquivo: Program.cs
using System;

namespace MyApplication
{
    class Program
    {
        static void Soma(ref int x)
        {
            x += 10;
        }

        static void Main(string[] args)
        {
            int x = 0;
            Soma(ref x);
        }
    }
}
~~~

## Parâmetros out

~~~csharp
// Arquivo: Program.cs
using System;

namespace MyApplication
{
    class Program
    {
        static void Soma(int x, int y, out int result)
        {
            result = x + y;
        }

        static void Main(string[] args)
        {
            int resultado;
            Soma(1, 2, out resultado);

        }
    }
}
~~~
