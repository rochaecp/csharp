# C# - Atributos e Métodos Static

- Membros declarados como static são membros da classe e não membros de instância.
- Classes Estáticas:
    - Não podem ser instanciadas.
    - Só podem ter membros static.
    - São sealed (não podem ser herdadas).
    - Contém apenas construtores static.
    - Possuem somente construtores privados.
- Atributos Estáticos:
    - Podemos ter acesso a atributos Static sem a necessidade de instanciar um objeto a partir de uma classe.
- Métodos Estáticos:
    - Podemos ter acesso a métodos estáticos sem a necessidade de instanciar um objeto a partir de uma classe.        

## Classes Estáticas

~~~csharp
// Arquivo Calculadora.cs
using System;

namespace MyApplication
{
    public static class Calculadora
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

~~~csharp
// Arquivo Program.cs
// Utilizando a classe estática criada anteriormente
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

