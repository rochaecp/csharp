# C# Polimorfismo

Permite que classes forneçam diferentes implementações para métodos que possuem o mesmo nome.
Tipos:
    Polimorfismo em tempo de execução (Overriding/Sobrescrita) usa herança e métodos virtuais
    Polimorfismo em tempo de compilação (Overloading/Sobrecarga) usa sobrecarga de métodos e de operadores
Sobrescrita de Métodos:
    Em C# para um método poder ser sobrescrito ele precisa da palavra reservada *virtual*. 
        O modificador de acesso virtual indica que o método pode ser sobrescrito na classe derivada.
    Em C# para um método poder sobrescrever outro precisamos adicionar a palavra reservada *override*.  
Sobrecarga de Métodos:
    Usamos o mesmo nome de método (mas com parâmetros diferenes) duas ou mais vezes numa mesma classe

## Polimorfismo com Herança e Métodos Virtuais

- Em uma implementação mais robusta teríamos a classe ```Veiculo``` como abstrata e os métodos ```Mover()``` e ```Parar()``` seriam abstratos.

~~~csharp
// Arquivo: Veiculo.cs
namespace MyApplication
{
    public class Veiculo
    {
        // atributo
        private string tipo;

        // propriedade
        public string Tipo
        {
            get { return tipo; }
            set { tipo = value; }
        }

        // construtor
        public Veiculo(string tipoVeiculo)
        {
            this.Tipo = tipoVeiculo;
        }

        // metodo a ser sobrescrito
        public virtual void Mover()
        { }

        // metodo a ser sobrescrito
        public virtual void Parar()
        { }
    }
}
~~~

~~~csharp
// Arquivo: Automovel.cs
using System;

namespace MyApplication
{
    public class Automovel : Veiculo // herda de veículo
    {
        public Automovel(string tipoVeiculo)
            : base(tipoVeiculo)
        { }

        // sobrescreve o metodo Mover()
        public override void Mover()
        {
            Console.WriteLine("Acelerando o carro");
        }

        // sobrescreve o metodo Parar()
        public override void Parar()
        {
            Console.WriteLine("Parando o carro");
        }
    }
}
~~~

~~~csharp
// Arquivo: Aeronave.cs
using System;

namespace MyApplication
{
    public class Aeronave : Veiculo // herda de veículo
    {
        public Aeronave(string tipoVeiculo)
            : base(tipoVeiculo)
        { }

        // sobrescreve o metodo Mover()
        public override void Mover()
        {
            Console.WriteLine("Acelerando a aeronave");
        }

        // sobrescreve o metodo Parar()
        public override void Parar()
        {
            Console.WriteLine("Parando a aeronave");
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
            Veiculo[] veiculos = new Veiculo[2];

            veiculos[0] = new Automovel("Ferrari");
            veiculos[1] = new Aeronave("A29 Super Tucano");

            veiculos[0].Mover();
            veiculos[1].Mover();
        }
    }
}
~~~

## Polimorfismo com Sobrecarga de Métodos

~~~csharp
// Arquivo: Program.cs
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
            int myInt = Soma(1, 1);
            double myDouble = Soma(1.2, 1.3);
        }
    }
}
~~~
