# C# - Métodos Construtores

- **Métodos Construtores**:
    - São métodos que são executados assim que instanciamos um objeto de uma classe.
    - São sempre public.
    - Possuem sempre o nome da classe.

## Exemplo

- Arquivo: Pessoa.cs

~~~csharp
using System;
namespace MeuProjeto
{
    public class Pessoa
    {
        // método construtor
        public Pessoa()
        {
            Console.WriteLine("Construtor executado");
        }

        // método construtor sobrecarregado
        public Pessoa(string nome)
        {
            Console.WriteLine("Ola " + nome);
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
            Pessoa p1 = new Pessoa();
            Pessoa p2 = new Pessoa("Mauricio");
        }
    }
}
~~~

