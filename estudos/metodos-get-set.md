# C# - Métodos Getters e Setters

- **Métodos Getters e Setters**:
    - São utilizados para obtermos e modificarmos atributos privados.
    - São sempre public.
    - Pode-se utilizar um ou outro ou ambos.

## Exemplo

- Arquivo: Pessoa.cs

~~~csharp
namespace MeuProjeto
{
    public class Pessoa
    {
        private string nome;

        // Get e Set - sempre maiúsculo - propriedade
        public string Nome
        {
            get { return nome; }
            set { nome = value; }
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
            Pessoa p = new Pessoa();
            p.Nome = "Mauricio"; // p.Nome usando o set
            Console.WriteLine("Ola " + p.Nome); // p.Nome usando o get
        }
    }
}
~~~

    
