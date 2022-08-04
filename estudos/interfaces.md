# C# - Interfaces

- Uma interface é um tipo de classe que contém apenas as assinaturas de métodos, propriedades, eventos e indexadores.
- Usar interface é uma forma de criar e definir um contrato que ajuda na organização do código.
- "Programe para uma interface e não para uma implementação." (Erich Gamma).
- Permitem criar sistemas fracamente acoplados e mais flexível a mudanças.
- Uma interface não pode ser instanciada.
- Uma interface não pode conter um construtor.
- Uma interface pode herdar de um ou mais interfaces.
- Ao criar uma classe usando uma interface devem ser implementados todos os métodos da interface, caso contrario deverá ser criada uma classe abstrata.
- A implementação dos membros é feita por uma classe concreta ou struct que implementa a interface.
- Em C# por convenção iniciamos o nome de interfaces com a letra 'I', ex.: IProductService.
- Em C# uma classe pode implementar várias interfaces.
- Em C# um método criado na interface é por padrão público e abstrato e não possui corpo.

## Utilizando Interfaces

- Arquivo: ICalculadora.cs

~~~csharp
namespace MyApplication
{
    public interface ICalculadora
    {
        public int Soma(int x, int y);
        public int Subtracao(int x, int y);
    }
}
~~~

- Arquivo: ICalculadoraCientifica.cs

~~~csharp
namespace MyApplication
{
    public interface ICalculadoraCientifica
    {
        public double Potencia(int x, int y);
    }
}
~~~

- Arquivo: Calculadora.cs

~~~csharp
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

- Arquivo: CalculadoraCientifica.cs

~~~csharp
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

- Arquivo: Program.cs

~~~csharp
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
