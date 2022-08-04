# C# - Polimorfismo

- Sobrescrita de Métodos:
    - Em C# para um método poder ser sobrescrito ele precisa da palavra reservada *virtual*.   
    - Em C# para um método poder sobrescrever outro precisamos adicionar a palavra reservada *override*.  

## Exemplo

- Arquivo: Imposto.cs

~~~csharp
using System;

namespace MeuProjeto
{
    public class Imposto
    {
        public virtual void valeAlimentacao(double salario)
        {
            Console.WriteLine("Desconto VA: " + salario * 0.1);
        }
        public void valeTransporte(double salario)
        {
            Console.WriteLine("Desconto VT: " + salario * 0.06);
        }
    }
}
~~~

- Arquivo: Gerente.cs

~~~csharp
using System;

namespace MeuProjeto
{
    public class Gerente : Imposto
    {
        public override void valeAlimentacao(double salario)
        {
            Console.WriteLine("Desconto gerente VA: " + salario * 0.15);
        }
    }
}
~~~

- Arquivo: Atendente.cs

~~~csharp
using System;

namespace MeuProjeto
{
    public class Atendente : Imposto
    {
        public override void valeAlimentacao(double salario)
        {
            Console.WriteLine("Desconto atendente VA: " + salario * 0.12);
        }
    }
}
~~~

- Arquivo: Estagiário.cs

~~~csharp
using System;

namespace MeuProjeto
{
    public class Estagiario : Imposto
    {

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
            // Instanciando objetos
            Imposto objE = new Estagiario();
            objE.valeAlimentacao(1000);
            objE.valeTransporte(1000);

            Imposto objA = new Atendente();
            objA.valeAlimentacao(2000);
            objA.valeTransporte(2000);

            Imposto objG = new Gerente();
            objG.valeAlimentacao(5000);
            objG.valeTransporte(5000);
        }
    }
}

~~~
