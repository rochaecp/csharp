# C# - Abstração

- Classes abstratas:
    - Classe que pode conter métodos obrigatórios para todas as classes que a herdarem.
    - Métodos obrigatórios podem ser públicos ou protegidos.
    - Podem conter também métodos convencionais (não obrigatórios) para que as classes que a herdam possam utilizar.
    - Não se pode instanciar um objeto a partir de uma classe abstrata.
    - Garante uma estrutura pré moldada de métodos que devem ser implementados.
    - É uma forma de criar um padrão para os projetos.
    - Cada classe pode herdar apenas de uma classe abstrata.

- Métodos abstratos:
    - É um método obrigatório de uma classe abstrata.
    - Precisa obrigatóriamente ser sobrescrito na classe que herdar da classe abstrata que o contém.

## Exemplo

~~~csharp
// file Program.cs, dir MyApplication
using System;
namespace MyApplication {
  // Abstract class
  abstract class Animal {
    // Abstract method (does not have a body)
    public abstract void animalSound();
    // Regular method
    public void sleep() {
      Console.WriteLine("Zzz");
    }
  }

  // Derived class (inherit from Animal)
  class Pig : Animal {
    public override void animalSound() {
      // The body of animalSound() is provided here
      Console.WriteLine("The pig says: wee wee");
    }
  }

  class Program {
    static void Main(string[] args) {
      Pig myPig = new Pig();  // Create a Pig object
      myPig.animalSound();
      myPig.sleep();
    }
  }
}
~~~    