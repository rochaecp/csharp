# C# - Classes e Objetos

- Os 4 pilares da POO são: Abstração, Encapsulamento, Herança e Polimorfismo.
- Nomes de classe iniciam com letra maiúscula.

## Exemplo

- Arquivo: Pessoa.cs

~~~csharp
using System;

namespace MeuProjeto
{
    public class Pessoa
    {
        // atributos
        public string nome;
        public int idade;

        // metodos
        public void mensagem()
        {
            Console.WriteLine("Ola " + nome + " você tem " + idade + " anos.");
        }
    }
}
~~~

- Arquivo: Program.cs

~~~csharp
using System;

namespace MeuProjeto
{
    class Program
    {
        static void Main(string[] args)
        {
            // instanciar um objeto
            Pessoa obj = new Pessoa();
            obj.nome = "Mauricio";
            obj.idade = 29;

            obj.mensagem();
        }
    }
}
~~~

## Exemplo

- Arquivo: Car.cs

~~~csharp
using System;

namespace MyApplication
{
    class Car
    {
        public string color; // field (or attribute)
        public Car(string color)
        { // constructor
            this.color = color;
        }
        public Car()
        { // overloaded constructor 
            this.color = "blue";
        }
        public void printColor()
        { // method
            Console.WriteLine($"Color: {color}");
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
            Car myObj = new Car("red");
            myObj.printColor();
        }
    }
}
~~~    
