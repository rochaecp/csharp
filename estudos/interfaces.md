# C# - Interfaces

- Utilizada para criarmos exclusivamente métodos obrigatórios.
- Uma classe pode implementar várias interfaces.
- Os métodos da interface não possuem implementação na interface.
- A implementação dos métodos da interface fica na classe que implementa a mesma.
- No C# um método criado na interface é por padrão público e abstrato.
- No C# por convenção iniciamos o nome de interfaces com a letra 'I', ex.: IProductService.

## Exemplo

- Arquivo: IPadrao.cs

~~~csharp
namespace MeuProjeto
{
    public interface IPadrao
    {
        // metodo obrigatorio
        void somar(int n1, int n2); // obrigatoriamente abstract e public
        void subtrair(int n1, int n2);
    }
}
~~~

- Arquivo: Calculo.cs

~~~csharp
using System;

namespace MeuProjeto
{
    public class Calculo : IPadrao // Calculo implementa a interface IPadrao, é do mesmo jeito que herança
    {
        public void somar(int n1, int n2) // poderia ser privado se quisesse
        {
            Console.WriteLine(n1 + n2);
        }

        public void subtrair(int n1, int n2)
        {
            Console.WriteLine(n1 - n2);
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
            Calculo obj = new Calculo();
            obj.somar(1, 1);
            obj.subtrair(11, 10);
        }
    }
}
~~~

## Exemplo

~~~csharp
// file Program.cs, dir MyApplication
using System;
namespace MyApplication {
  // Interface
  interface IAnimal {
    void animalSound(); // interface method (does not have a body)
  }

  // Pig "implements" the IAnimal interface
  class Pig : IAnimal {
    public void animalSound() {
      // The body of animalSound() is provided here
      Console.WriteLine("The pig says: wee wee");
    }
  }

  class Program {
    static void Main(string[] args) {
      Pig myPig = new Pig();  // Create a Pig object
      myPig.animalSound();
    }
  }
}
~~~

## Exemplo

~~~csharp
// Interfaces múltiplas
// file Program.cs, dir MyApplication
using System;

namespace MyApplication {
  interface IFirstInterface {
    void myMethod(); // interface method
  }

  interface ISecondInterface {
    void myOtherMethod(); // interface method
  }

  // Implement multiple interfaces
  class DemoClass : IFirstInterface, ISecondInterface {
    public void myMethod() {
      Console.WriteLine("Some text..");
    }
    public void myOtherMethod() {
      Console.WriteLine("Some other text...");
    }
  }

  class Program {
    static void Main(string[] args) {
      DemoClass myObj = new DemoClass();
      myObj.myMethod();
      myObj.myOtherMethod();
    }
  }
}
~~~
