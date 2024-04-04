# C# - Herança

- Herança é um mecanismo que permite que características comuns a diversas classes sejam agrupadas em uma classe base, ou superclasse. 
- Classe base (pai): classe cujos membros são herdados.
- Classe derivada (filha): classe que herda, estende ou modifica o comportamento de uma classe base.
- Em C# não existe herança múltipla: uma classe só pode estender uma única classe por vez.
- Impedir herança com sealed
- Tipos de Herança:
    - Simples: Uma classe base e uma classe derivada.
    - Hierárquica: Mais de uma classe deriva de uma mesma classe base.
    - Multinível: Uma classe deriva de uma classe que deriva de outra.
    - Múltipla: Não suportada em C# (usamos interfaces)  

## Herança Simples

~~~csharp
// Arquivo Pessoa.cs
using System;

namespace MyApplication
{
    public class Pessoa
    {
        private string nome;
        private int idade;

        public Pessoa(string n, int i)
        {
            this.nome = n;
            this.idade = i;
        }
        
        // observar modificador protected
        protected void MensagemPessoa()
        {
            Console.WriteLine(nome);
            Console.WriteLine(idade);
        }
    }
}
~~~

~~~csharp
// Arquivo Colaborador.cs
using System;

namespace MyApplication
{
    public class Colaborador : Pessoa // Colaborador herda de Pessoa
    {
        private double salario;

        public Colaborador(string nome, int idade, double salario)
            : base (nome, idade)
        {
            this.salario = salario;
        }

        public void MensagemColaborador()
        {
            MensagemPessoa();
            Console.WriteLine(salario);
        }
    }
}
~~~

~~~csharp
// Arquivo Program.cs
using System;

namespace MyApplication
{
    class Program
    {
        static void Main(string[] args)
        {
            Colaborador c = new Colaborador("Maurício", 30, 7000.00);

            c.MensagemColaborador();
        }
    }
}
~~~
