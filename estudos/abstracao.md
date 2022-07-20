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

- Arquivo: Padrao.cs

~~~csharp
using System;

namespace MeuProjeto
{
    // classe abstrata
    public abstract class Padrao
    {
        // metodo obrigatorio
        public abstract void taxaEmprestimo(double valor); // quem implementar a classe padrão precisa implementar esse método.

        // metodo opcional
        public void calculoPoupanca(double valor, double taxa)
        {
            Console.WriteLine("Ganho poupança: " + valor * taxa);
        }
    }
}
~~~

- Arquivo: PessoaFisica.cs

~~~csharp
using System;

namespace MeuProjeto
{
    public class PessoaFisica : Padrao
    {
        // metodo obrigatorio
        public override void taxaEmprestimo(double valor)
        {
            Console.WriteLine("Taxa Emprestimo PF = " + valor * 0.1);
        }
    }
}
~~~

- Arquivo: PessoaJuridica.cs

~~~csharp
using System;

namespace MeuProjeto
{
    public class PessoaJuridica : Padrao
    {
        // metodo obrigatorio
        public override void taxaEmprestimo(double valor)
        {
            Console.WriteLine("Taxa Emprestimo PJ = " + valor * 0.2);
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
            PessoaFisica pf = new PessoaFisica();
            PessoaJuridica pj = new PessoaJuridica();

            pf.taxaEmprestimo(1000);
            pf.calculoPoupanca(1000, 0.1);

            pj.taxaEmprestimo(1000);
            pj.calculoPoupanca(1000, 0.1);
        }
    }
}
~~~

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
