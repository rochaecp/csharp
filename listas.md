# C# - Listas

## Covertendo listas em arrays

~~~csharp
int[] meuArray = minhaLista.ToArray();
~~~

## Exemplo

~~~csharp
using System;
using System.Collections.Generic;

namespace Listas
{
    class Program
    {
        static void Main(string[] args)
        {
            // cria a lista
            List<int> lista_numeros = new List<int>();

            // adiciona elementos
            lista_numeros.Add(3);
            lista_numeros.Add(2);
            lista_numeros.Add(1);

            // acessa elementos
            for (int i = 0; i < lista_numeros.Count; i++)
                Console.WriteLine($"Elemento = {lista_numeros[i]}");
            Console.WriteLine();

            // acessa elementos
            foreach (int e in lista_numeros)
                Console.WriteLine($"Elemento = {e}");
            Console.WriteLine();

            // acessa elementos
            lista_numeros.ForEach(delegate (int x)
            {
                Console.WriteLine($"Elemento = {x}");
            });
            Console.WriteLine();

            // ordena itens ordenados
            lista_numeros.Sort();


        }
    }
}
~~~
