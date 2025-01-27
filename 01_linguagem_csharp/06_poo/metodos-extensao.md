# C# - Métodos de Extensão

- Permitem adicionar novos métodos a tipos existentes, sem a necessidade de modificar o código-fonte desses tipos.
- Proporcionam uma maneira flexível de estender funcionalidades de classes já existentes, tanto do próprio .NET quanto de classes personalizadas.
- São criados de forma estática dentro de clases estáticas.
- Vantagens: flexibilidade, legibilidade, reutilização de código e integração com tipos existentes.

## Criar um método de extensão para o tipo int para calcular o quadrado de um número inteiro

~~~csharp
namespace ConsoleApp2
{
    public static class IntExtension
    {
        public static int Quadrado(this int numero) //a palavra reservada this intica que se trata de um método de extensão para inteiros
        {
            return numero * numero;
        }
    }

    class Program
    {
        static void Main(string[] args)
        {
            int num = 3;
            int resultado = num.Quadrado(); // acessamos o método como se fosse um método de instância
            Console.WriteLine($"Resultado = {resultado}"); // Resultado = 9
        }
    }
}
~~~