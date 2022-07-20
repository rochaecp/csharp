# C# - Dicionários

## Exemplo

~~~csharp
using System;
using System.Collections.Generic;
using System.Globalization;

namespace TreinosBeecrowd
{
    class Program
    {
        static void Main(string[] args)
        {
            CultureInfo.CurrentCulture = new CultureInfo("en-US");

            int valor = 0;
            int[] notas = new int[7];

            IDictionary<int, int> dict = new Dictionary<int, int>()
            {
                {100, 0}, // ou dict[100] = 0;
                {50, 0},  // ou dict[50] = 0;
                {20, 0},  // ou dict[20] = 0;
                {10, 0},  // ou dict[10] = 0;
                {5, 0},   // ou dict[5] = 0;
                {2, 0},   // ou dict[2] = 0;
                {1, 0}    // ou dict[1] = 0;
            };

            valor = Convert.ToInt32(Console.ReadLine());

            dict[100] = valor / 100;
            valor = valor % 100;

            dict[50] = valor / 50;
            valor = valor % 50;

            dict[20] = valor / 20;
            valor = valor % 20;

            dict[10] = valor / 10;
            valor = valor % 10;

            dict[5] = valor / 5;
            valor = valor % 5;

            dict[2] = valor / 2;
            valor = valor % 2;

            dict[1] = valor;

            foreach (KeyValuePair<int, int> item in dict)
            {
                Console.WriteLine("{0} nota(s) de R$ {1:F2}", item.Value, item.Key);
            }
        }
    }
}
~~~
