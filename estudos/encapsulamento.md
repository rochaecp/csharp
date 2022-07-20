# C# - Encapsulamento

- Restringir o acesso aos membros da classe.

- Modificadores de acesso:
    - public: The code is accessible for all classes.
    - private: The code is only accessible within the same class.
    - protected: The code is accessible within the same class, or in a class that is inherited from that class. 
    - internal: The code is only accessible within its own assembly, but not from another assembly. 
    - protected Internal: The code is only accessible within the same class or in a class that is inherited from that class or in its own assembly.

> There's also two combinations: protected internal and private protected.
> By default, all members of a class are private if you don't specify an access modifier

## Exemplo

- Arquivo: Aluno.cs

~~~csharp
using System;

namespace Encapsulamento
{
    public class Aluno
    {
        private double nota1, nota2;
        private double media()
        {
            return (nota1 + nota2) / 2;
        }
        public void mensagem()
        {
            Console.WriteLine("Digite as 2 notas");
            nota1 = Convert.ToDouble(Console.ReadLine());
            nota2 = Convert.ToDouble(Console.ReadLine());
            Console.WriteLine("Media = " + media());
        }
    }
}
~~~

- Arquivo: Program.cs

~~~csharp
using System;

namespace Encapsulamento
{
    class Program
    {
        static void Main(string[] args)
        {
            Aluno a = new Aluno();
            a.mensagem();
        }
    }
}
~~~
