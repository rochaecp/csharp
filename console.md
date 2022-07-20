# C#

## Entrada pelo Console

### Console.Read()

- Le próximo caractere

### Console.ReadLine()

- Lê próxima linha

## Saída pelo Console

## Exemplo

~~~csharp
using System;

namespace Entrada_pelo_Console
{
    class Program
    {
        static void Main(string[] args)
        {
            string nome = "";

            Console.WriteLine("Digite o seu nome: ");
            nome = Console.ReadLine();
            Console.WriteLine("Seu nome é: " + nome);

            Console.WriteLine("\nDigite a sua idade: ");
            int age = Convert.ToInt32(Console.ReadLine());
            Console.WriteLine("Sua idade é: " + age);
        }
    }
}
~~~

## Exemplo

~~~csharp
using System;

namespace Saida_pelo_Console
{
    class Program
    {
        static void Main(string[] args)
        {
            string nome = "Mauricio";
            int idade = 30;
            double salario = 6500.00D;

            Console.WriteLine("on a new line.");
            Console.Write("on the same line. ");

            Console.WriteLine($"Olá {nome}");
            Console.WriteLine("Olá: " + nome);
            Console.WriteLine("Sua idade é: " + idade); // int
            Console.WriteLine($"Sua idade é: {salario:F2}"); // double
            Console.WriteLine("nome: {0} salario: {1:F2}", nome, salario); // double

        }
    }
}
~~~
