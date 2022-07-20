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
