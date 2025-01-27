# C# - Encapsulamento

Encapsulamento:
    É o processo de ocultar membros de uma classe do acesso exterior utilizando modificadores de acesso.
Propriedades:
    Uma propriedade permite um acesso controlado a um campo.  
    Se não definirmos o método set a propriedade será somente de leitura.

## Criando uma classe com campos privados e propriedades públicas

~~~csharp
// Arquivo: Retangulo.cs
using System;

namespace MyApplication
{
    public class Retangulo
    {
        // campos privados
        private double largura;
        private double comprimento;

        // propriedade pública
        public double Largura
        {
            get { return largura; }
            set
            {
                if (value < 0)
                    throw new ArgumentException("Largura não pode ser menor do que zero");
                else
                    largura = value;
            }
        }

        // propriedade pública
        public double Comprimento
        {
            get { return comprimento; }
            set
            {
                if (value < 0)
                    throw new ArgumentException("Comprimento não pode ser menor do que zero");
                else
                    comprimento = value;
            }
        }

        public double GetArea()
        {
            return largura * comprimento;
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
            var r = new Retangulo();

            try
            {
                r.Comprimento = Convert.ToDouble(Console.ReadLine());
                r.Largura = Convert.ToDouble(Console.ReadLine());

                Console.WriteLine($"Area = {r.GetArea()}");
            }
            catch (ArgumentException ex)
            {
                Console.WriteLine(ex.Message);
            }
        }
    }
}
~~~
