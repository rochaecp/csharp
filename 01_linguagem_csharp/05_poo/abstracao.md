# C# - Abstração

- Classes abstratas:
    - Uma classe abstrata é uma classe que não pode ser instanciada. 
    - Uma classe abstrata define um comportamento básico mas não auto-suficiente.
    - Uma classe abstrata pode ser herdada e geralmente serve como classe base para outras classes.
    - Uma classe abstrata pode conter métodos abstratos e métodos comuns. 
    - Uma classe abastrata também pode possuir construtores, propriedades, indexadores e eventos.
    - Uma classe abstrata não pode ser ``` static ``` nem ``` sealed ```.
    - Uma classe abstrata pode herdar de outra classe abstrata.
    - Cada classe pode herdar apenas de uma classe abstrata.
- Métodos abstratos:
    - Um método abstrato é um método que não possui implementação na classe abstrata.
    - Um método abstrato é um método ``` virtual ``` e deve ser implementado usando o modificador ``` override ```.
    - Um método abstrato somente pode existir em uma classe abstrata.
    - Um método abstrato não pode usar os modificadores ``` static ``` nem ``` virtual ```.

## Classes Abstratas

~~~csharp
// Arquivo: Forma.cs
namespace MyApplication
{
    public abstract class Forma
    {
        // propriedades

        public string Cor { get; set; }
        public double Perimetro { get; set; }
        public double Area { get; set; }

        // metodos abstratos

        public abstract void CalcularPerimetro();
        public abstract void CalcularArea();

        // metodo publico
        public string Descricao()
        {
            return "Sou a classe abstrata Forma";
        }
    }
}
~~~

~~~csharp
// Arquivo: Quadrado.cs
using System;

namespace MyApplication
{
    public class Quadrado : Forma
    {
        public double Lado { get; set; }
        
        public override void CalcularPerimetro()
        {
            this.Perimetro = 4 * Lado;
        }

        public override void CalcularArea()
        {
            this.Area = Lado * Lado;
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
            Quadrado q = new Quadrado();
            q.Lado = 10;
            q.CalcularPerimetro();
            q.CalcularArea();

            Console.WriteLine(q.Descricao());

            Console.WriteLine($"{q.Perimetro} - {q.Area}");
        }
    }
}
~~~
