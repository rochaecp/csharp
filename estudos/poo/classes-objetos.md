# C# - Classes e Objetos

- Os 4 pilares da POO são: Abstração, Encapsulamento, Herança e Polimorfismo.
- Nomes de classe iniciam com letra maiúscula.
- Classes possuem membros (campos/atributos, propriedades e métodos)
- Classe
    - Conjunto de métodos e propriedades que definem um escopo.
- Objeto
    - Elemento com características definidas por uma classe.
- Atributos
    - Conjunto de características definidas por uma classe.
- Métodos
    - Comportamentos de uma classe.
- Construtor
    - Método que inicializa um objeto.                

## Criar uma classe e instanciar um objeto a partir dela

~~~csharp
// Arquivo: Carro.cs
using System;

namespace MyApplication
{
    class Carro
    {
        // campo ou atributo
        public string cor; 

        // método construtor
        public Carro(string cor)
        { 
            this.cor = cor;
        }

        // método construtor sobrecarregado
        public Carro()
        { 
            this.cor = "azul";
        }

        // método
        public void printCor()
        { 
            Console.WriteLine($"Cor = {cor}");
        }
    }
}
~~~

~~~csharp
// Arquivo: Program.cs
using System;
namespace MyApplication
{
    class Program
    {
        static void Main(string[] args)
        {
            Carro c = new Carro("vermelho");
            c.printCor();
        }
    }
}
~~~ 
