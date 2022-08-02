# C# - Herança

- Em C# não existe herança múltipla: uma classe só pode estender uma única classe por vez.
- Impedir herança com ```sealed ```

## Exemplo

- Arquivo: Pessoa.cs

~~~csharp
using System;

namespace MeuProjeto
{
    public class Pessoa
    {
        // note o atributo protected
        protected string nome;
        protected int idade;

        protected void mensagemPessoa()
        {
            Console.WriteLine("Nome " + nome);
            Console.WriteLine("Idade " + idade);
        }
    }
}
~~~

- Arquivo: Colaborador.cs

~~~csharp
using System;

namespace MeuProjeto
{
    public class Colaborador : Pessoa // Colaborador herda de Pessoa
    {
        private double salario;
        public Colaborador(string nome, int idade, double salario)
        {
            this.nome = nome;
            this.idade = idade;
            this.salario = salario;

            mensagemPessoa();
            mensagemColaborador();
        }
        private void mensagemColaborador()
        {
            Console.WriteLine("Salario " + salario);
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
            Colaborador obj = new Colaborador("Mauricio", 29, 4000);
        }
    }
}
~~~

## Exemplo

- Arquivo: Vehicle.cs

~~~csharp
using System;
namespace MyApplication
{
    class Vehicle
    { // Base class
        public string brand = "Ford";  // Vehicle field
        public void honk()
        {            // Vehicle method 
            Console.WriteLine("Tuut, tuut!");
        }
    }
}
~~~

- Arquivo: Car.cs

~~~csharp
using System;
namespace MyApplication
{
    class Car : Vehicle
    {  // Derived class
        public string modelName = "Mustang";  // Car field
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
            // Create a myCar object
            Car myCar = new Car();

            // Call the honk() method (From the Vehicle class) on the myCar object
            myCar.honk();

            // Display the value of the brand field (from the Vehicle class) and the value of the modelName from the Car class
            Console.WriteLine(myCar.brand + " " + myCar.modelName);
        }
    }
}
~~~

## Sobrescrita de Métodos

> Em C# para um método poder ser sobrescrito ele precisa da palavra reservada *virtual*.   
> Em C# para um método poder sobrescrever outro precisamos adicionar a palavra reservada *override*.    

~~~csharp

~~~
