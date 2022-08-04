# C# - Polimorfismo

- Polimorfismo é o princípio pelo qual duas ou mais classes derivadas de uma mesma superclasse podem invocar métodos que têm a mesma assinatura mas comportamentos diferentes e especializados para cada classe derivada.
- Permite que classes forneçam diferentes implementações para métodos que possuem o mesmo nome.
- **Tipos de Polimorfismo**
    - Polimorfismo em tempo de compilação (Overloading/Sobrecarga) - usa sobrecarga de métodos e de operadores
    - Polimorfismo em tempo de execução (Overriding/Sobrescrita) - usa herança e métodos virtuais
- Sobrescrita de Métodos:
    - Em C# para um método poder ser sobrescrito ele precisa da palavra reservada *virtual*. 
        - O modificador de acesso virtual indica que o método pode ser sobrescrito na classe derivada.
    - Em C# para um método poder sobrescrever outro precisamos adicionar a palavra reservada *override*.  

## Polimorfismo com herança e métodos virtuais

- Arquivo: Veiculo.cs
    - Em uma implementação mais robusta teríamos a classe ```Veiculo``` como abstrata e os métodos ```Mover()``` e ```Parar()``` seriam abstratos.

~~~csharp
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

- Arquivo: Automovel.cs

~~~csharp
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

- Arquivo: Aeronave.cs

~~~csharp
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

- Arquivo: Program.cs

~~~csharp
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
