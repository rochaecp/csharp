# C# - Interfaces

- Uma interface é um tipo de classe que contém apenas assinaturas de métodos, propriedades, eventos e indexadores.
- A interface define operações obrigatórias (contrato).
- Por padrão todos os membros de uma interface são ``` public ``` e ``` abstract ```.
- Por convenção iniciamos o nome de interfaces com a letra 'I'.
- Em C# uma classe pode implementar várias interfaces.
- É obrigatório implementar todos os métodos da interface.
- Interfaces não podem:
    - Ser instanciadas.
    - Conter implementações dos seus métodos (corpo dos métodos).
    - Conter constantes, construtores, variáveis de instância, destrutores, membros estáticos ou interfaces aninhada.
- Interfaces podem:
    - Herdar de um ou mais interfaces.
    - Ter constantes ``` static ```
- "Programe para uma interface e não para uma implementação." (Erich Gamma).

## Utilizando Interfaces

~~~csharp
// Arquivo: ICalculadora.cs
namespace MyApplication
{
    public interface ICalculadora
    {
        int Soma(int x, int y);
        int Subtracao(int x, int y);
    }
}
~~~

~~~csharp
// Arquivo: ICalculadoraCientifica.cs
namespace MyApplication
{
    public interface ICalculadoraCientifica
    {
        double Potencia(int x, int y);
    }
}
~~~

~~~csharp
// Arquivo: Calculadora.cs
namespace MyApplication
{
    public class Calculadora : ICalculadora // implementa a interface ICalculadora
    {
        public int Soma(int x, int y)
        {
            return x + y;
        }

        public int Subtracao(int x, int y)
        {
            return x - y;
        }
    }
}
~~~

~~~csharp
// Arquivo: CalculadoraCientifica.cs
using System;

namespace MyApplication
{
    public class CalculadoraCientifica : ICalculadora, ICalculadoraCientifica // implementa 2 interfaces
    {
        public int Soma(int x, int y)
        {
            return x + y;
        }

        public int Subtracao(int x, int y)
        {
            return x - y;
        }

        public double Potencia(int x, int y)
        {
            return Math.Pow(x, y);
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
            ICalculadora calc = new Calculadora();
            Console.WriteLine(calc.Soma(90, 10));

            calc = new CalculadoraCientifica();
            Console.WriteLine(calc.Soma(90, 10));
        }
    }
}
~~~
