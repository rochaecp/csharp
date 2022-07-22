# C# - Arrays

- String

    ```csharp
    string[] cores = { "Azul", "Amarelo", "Vermelho" };
    ```

## Exemplo

~~~csharp
using System;
using System.Linq;

namespace Arrays
{
    class Program
    {
        static void Main(string[] args)
        {

            // *****************************************************************
            // Criando Arrays
            // *****************************************************************

            // Array unidimensional de Inteiros
            int[] myArrayUniInt1 = new int[3];
            int[] myArrayUniInt2 = new int[3] { 10, 20, 30 };
            int[] myArrayUniInt3 = new int[] { 10, 20, 30 };
            int[] myArrayUniInt4 = { 10, 20, 30 }; // easier to read

            // Array unidimensional de Strings 
            string[] myArrayUniString1 = { "Volvo", "BMW", "Ford" };
            string[] myArrayString2;
            myArrayString2 = new string[] { "Volvo", "BMW", "Ford" };

            // Array bi e tridimensional de Inteiros
            int[,] myArrayBiInt1 = new int[3, 2] { { 1, 2 }, { 3, 4 }, { 5, 6 } };
            int[,] myArrayBiInt2 = new int[10, 5];
            int[,,] myArrayTriInt1 = new int[10, 5, 2];

            // *****************************************************************
            // Acessando elementos de um Arrays
            // *****************************************************************

            // Acessando um elemento de um array unidimensional
            string myItemStr1 = myArrayUniString1[0];

            // Acessando um elemento de um array bidimensional
            int myItemInt1 = myArrayBiInt1[0, 0];

            // Acessando todos elementos do Array
            Console.WriteLine("Acessando todos elementos do Array com for");
            for (int i = 0; i < myArrayString2.Length; i++)
                Console.WriteLine(myArrayString2[i]);

            // Acessando todos elementos do Array com foreach
            Console.WriteLine("\nAcessando todos elementos do Array com forach");
            foreach (string i in myArrayString2)
                Console.WriteLine(i);

            // *****************************************************************
            // Modificando elementos de um Array
            // *****************************************************************

            // Mudando um elemento de um array unidimensional
            myArrayUniString1[0] = "Opel";

            // *****************************************************************
            // Propriedades de um Array
            // *****************************************************************

            int myLength = myArrayUniString1.Length;

            // *****************************************************************
            // Métodos um Array
            // *****************************************************************

            Array.Sort(myArrayUniString1); // sort a string
            Array.Sort(myArrayUniInt2);        // sort a int
            int myMax = myArrayUniInt2.Max();   // using System.Linq;
            int myMin = myArrayUniInt2.Min();   // using System.Linq;
            int mySum = myArrayUniInt2.Sum();   // using System.Linq;

            // Convertendo String em Array de Char
            String myString = "This is String example.";
            char[] myCharArray = myString.ToCharArray();
        }
    }
}
~~~
