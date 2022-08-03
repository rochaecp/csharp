# C# - Atributos e Métodos Static

> - Atributos Estáticos
>    - Podemos ter acesso a atributos Static sem a necessidade de instanciar um objeto a partir de uma classe.
> - Métodos Estáticos
>    - Podemos ter acesso a métodos Static sem a necessidade de instanciar um objeto a partir de uma classe.
> - Classes Estáticas
>    - Uma classe Static não pode ser instanciada.    

## Exemplo

- Arquivo: Exemplo.cs

~~~csharp
using System;

namespace MeuProjeto
{
    public class Exemplo
    {
        // atributo estático
        public static string nome = "Mauricio";

        // método estático
        public static void soma(int n1, int n2)
        {
            Console.WriteLine(n1 + n2);
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
            // chamando um método estático
            Exemplo.soma(10, 90);

            // acessando atributo estático
            Console.WriteLine(Exemplo.nome);
        }
    }
}
~~~
