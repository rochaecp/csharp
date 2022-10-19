# C# - Atributos e Métodos Static

- Membros declarados como static são membros da classe e não membros de instância.

## Classes Estáticas

- Não podem ser instanciadas.
- Só podem ter membros static.
- São sealed (não podem ser herdadas).
- Contém apenas construtores static.
- Possuem somente construtores privados.

Arquivo Program.cs:

~~~csharp
using System;

namespace MyApplication
{
    class Program
    {
        static void Main(string[] args)
        {
            Console.WriteLine(Calculadora.Somar(2, 4)) ;
        }
    }
}
~~~

Arquivo Calculadora.cs:

~~~csharp
using System;

namespace MyApplication
{
    static class Calculadora
    {
        public static int Somar(int num1, int num2)
        {
            return num1 + num2;
        }

        public static int Multiplicar(int num1, int num2)
        {
            return num1 * num2;
        }
    }
}
~~~

## Atributos Estáticos:

- Podemos ter acesso a atributos Static sem a necessidade de instanciar um objeto a partir de uma classe.

## Métodos Estáticos:

- Podemos ter acesso a métodos estáticos sem a necessidade de instanciar um objeto a partir de uma classe.
  
