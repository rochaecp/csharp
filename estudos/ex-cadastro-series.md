# Cadastro de Séries em .NET 

- Alguns conceitos aplicados
    - Orientação a Objetos
    - Interfaces
    - Classes Abstratas
    - Enumerações
    - Repositórios com Interfaces

## Projeto

~~~csharp
// Diretório: classes, Arquivo: EntidadeBase.cs
namespace Series
{
    public abstract class EntidadeBase
    {
        public int Id { get; protected set; }
    }
}
~~~

~~~csharp
// Diretório: classes, Arquivo: Serie.cs
using System;

namespace Series
{
    public class Serie : EntidadeBase
    { // herança
        private Genero Genero { get; set; }
        private string Titulo { get; set; }
        private string Descricao { get; set; }
        private int Ano { get; set; }

        public bool Excluido { get; set; } // marcar como excluido é melhor que excluir

        public Serie(int id, Genero genero, string titulo, string descricao, int ano)
        {
            this.Id = id; // EntidadeBase
            this.Genero = genero;
            this.Titulo = titulo;
            this.Descricao = descricao;
            this.Ano = ano;
            this.Excluido = false;
        }

        public override string ToString()
        {
            string retorno = "";
            retorno += "Genero: " + this.Genero + Environment.NewLine; // Environment == nova linha para cada SO
            retorno += "Titulo: " + this.Titulo + Environment.NewLine;
            retorno += "Descrição: " + this.Descricao + Environment.NewLine;
            retorno += "Ano: " + this.Ano;

            return retorno;
        }

        public string retornaTitulo()
        {
            return this.Titulo;
        }

        public int retornaId()
        {
            return this.Id;
        }

        public void Excluir()
        {
            this.Excluido = true;
        }
    }
}
~~~

~~~csharp
// Diretório: classes, Arquivo: SerieRepositorio.cs
using System;
using System.Collections.Generic;
using Series.Interfaces;

namespace Series
{
    /* Implementa uma interface Irepositorio de Séries
    Estamos reaproveitando a interface, poderiamos fazer
    um repositório de filmes, de documentarios, etc */

    public class SerieRepositorio : IRepositorio<Serie>
    { // implementa interface

        private List<Serie> listaSerie = new List<Serie>();
        public void Atualiza(int id, Serie objeto)
        {
            listaSerie[id] = objeto;
        }

        public void Exclui(int id)
        {
            listaSerie[id].Excluir(); //nao usaremos o listaSerie.RemoveAt(id)      
        }

        public void Insere(Serie objeto)
        {
            listaSerie.Add(objeto);
        }

        public List<Serie> Lista()
        {
            return listaSerie;
        }

        public int ProximoId()
        {
            return listaSerie.Count; // num de elementos == id do prox elem
        }

        public Serie RetornaPorId(int id)
        {
            return listaSerie[id];
        }
    }
}
~~~

~~~csharp
// Diretório: enum, Arquivo: Genero.cs
namespace Series
{
    public enum Genero
    {
        Acao = 1,
        Aventura = 2,
        Comedia = 3,
        Documentario = 4,
        Drama = 5,
        Musical = 6
    }
}
~~~

~~~csharp
// Diretório: interfaces, Arquivo: IRepositorio.cs
using System.Collections.Generic;

namespace Series.Interfaces
{
    /* quem implementar a interface estará implementando 
    um repositório dessa classe T */
    public interface IRepositorio<T>
    {
        List<T> Lista(); // T == tipo genérico, List<T> == lista de T, T pode ser a Classe Serie

        T RetornaPorId(int id); // retorna um T
        void Insere(T objeto);
        void Exclui(int id);
        void Atualiza(int id, T objeto);
        int ProximoId(); // retorna o proximo Id

        // metodos que quem implementar a interface tera que implementar
    }
}
~~~

~~~csharp
// Diretório: raiz do projeto, Arquivo: Program.cs
using System;

namespace Series
{
    class Program
    {
        static SerieRepositorio repositorio = new SerieRepositorio();
        static void Main(string[] args)
        {
            string opcaoUsuario = ObterOpcaoUsuario();
            while (opcaoUsuario.ToUpper() != "X")
            {
                switch (opcaoUsuario)
                {
                    case "1":
                        ListarSeries();
                        break;
                    case "2":
                        InserirSerie();
                        break;
                    case "3":
                        AtualizarSerie();
                        break;
                    case "4":
                        ExcluirSerie();
                        break;
                    case "5":
                        VisualizarSerie();
                        break;
                    case "C":
                        Console.Clear();
                        break;
                    default:
                        throw new ArgumentOutOfRangeException();
                }
                opcaoUsuario = ObterOpcaoUsuario();
            }
        }

        private static void InserirSerie()
        {
            Console.WriteLine("Inserir nova serie:");

            foreach (int i in Enum.GetValues(typeof(Genero)))
            {
                Console.WriteLine("{0}.{1}", i, Enum.GetName(typeof(Genero), i));
            }

            Console.WriteLine("Digite o Genero da Série");
            int entradaGenero = int.Parse(Console.ReadLine());

            Console.Write("Digite o Título da Série: ");
            string entradaTitulo = Console.ReadLine();

            Console.Write("Digite o Ano de Início da Série: ");
            int entradaAno = int.Parse(Console.ReadLine());

            Console.Write("Digite a Descrição da Série: ");
            string entradaDescricao = Console.ReadLine();

            Serie novaSerie = new Serie(id: repositorio.ProximoId(),
                        genero: (Genero)entradaGenero,
                        titulo: entradaTitulo,
                        ano: entradaAno,
                        descricao: entradaDescricao);

            repositorio.Insere(novaSerie);
        }

        private static void ListarSeries()
        {
            Console.WriteLine("Listar series:");
            var lista = repositorio.Lista();

            if (lista.Count == 0)
            {
                Console.WriteLine("Nenhuma série cadastrada.");
                return;
            }

            foreach (var serie in lista)
            {
                Console.WriteLine("#ID {0}: - {1}", serie.retornaId(), serie.retornaTitulo());
            }
        }

        private static void AtualizarSerie()
        {
            Console.Write("Digite o ID da série: ");
            int indiceSerie = int.Parse(Console.ReadLine());

            foreach (int i in Enum.GetValues(typeof(Genero)))
            {
                Console.WriteLine("{0}-{1}", i, Enum.GetName(typeof(Genero), i));
            }

            Console.Write("Digite o gênero entre as opções acima: ");
            int entradaGenero = int.Parse(Console.ReadLine());

            Console.Write("Digite o Título da Série: ");
            string entradaTitulo = Console.ReadLine();

            Console.Write("Digite o Ano de Início da Série: ");
            int entradaAno = int.Parse(Console.ReadLine());

            Console.Write("Digite a Descrição da Série: ");
            string entradaDescricao = Console.ReadLine();

            Serie atualizaSerie = new Serie(id: indiceSerie,
                        genero: (Genero)entradaGenero,
                        titulo: entradaTitulo,
                        ano: entradaAno,
                        descricao: entradaDescricao);

            repositorio.Atualiza(indiceSerie, atualizaSerie);
        }

        private static void ExcluirSerie()
        {
            Console.Write("Digite o ID da série: ");
            int indiceSerie = int.Parse(Console.ReadLine());

            repositorio.Exclui(indiceSerie);
        }

        private static void VisualizarSerie()
        {
            Console.Write("Digite o ID da série: ");
            int indiceSerie = int.Parse(Console.ReadLine());

            var serie = repositorio.RetornaPorId(indiceSerie);
            Console.WriteLine(serie);
        }

        private static string ObterOpcaoUsuario()
        {
            Console.WriteLine();
            Console.WriteLine("Informe a opção desejada:");
            Console.WriteLine("1 - Listar series");
            Console.WriteLine("2 - Inserir nova serie");
            Console.WriteLine("3 - Atualizar serie");
            Console.WriteLine("4 - Excluir serie");
            Console.WriteLine("5 - Visualizar serie");
            Console.WriteLine("C - Limpar tela");
            Console.WriteLine("X - SAIR");
            Console.WriteLine();

            string opcaoUsuario = Console.ReadLine().ToUpper();
            Console.WriteLine();
            return opcaoUsuario;
        }
    }
}
~~~
