# C# - Soluções Beecrowd

## 1022

~~~csharp
/*
    Utiliza uma função recursiva para mdc
*/
using System;
using System.Globalization;

namespace TreinosBeecrowd
{
    class Program
    {
        static void Main(string[] args)
        {
            CultureInfo.CurrentCulture = new CultureInfo("en-US");

            int numeroTestes = 0;
            int n1, d1, n2, d2;
            int numeradorResposta = 0, denominadorResposta = 0, numSimpli = 0, denomSimpli = 0;
            int maxDivisor;
            string linha = "";
            string[] valores = new string[7];
            char operacao = '+';

            numeroTestes = Int32.Parse(Console.ReadLine());

            for (int i = 0; i < numeroTestes; i++)
            {
                linha = Console.ReadLine();
                valores = linha.Split(' ');
                n1 = Int32.Parse(valores[0]);
                d1 = Int32.Parse(valores[2]);
                operacao = Convert.ToChar(valores[3]);
                n2 = Int32.Parse(valores[4]);
                d2 = Int32.Parse(valores[6]);

                if (operacao == '+')
                {
                    numeradorResposta = n1 * d2 + n2 * d1;
                    denominadorResposta = d1 * d2;
                }
                else if (operacao == '-')
                {
                    numeradorResposta = n1 * d2 - n2 * d1;
                    denominadorResposta = d1 * d2;
                }
                else if (operacao == '*')
                {
                    numeradorResposta = n1 * n2;
                    denominadorResposta = d1 * d2;
                }
                else if (operacao == '/')
                {
                    numeradorResposta = n1 * d2;
                    denominadorResposta = n2 * d1;
                }

                maxDivisor = mdc(numeradorResposta, denominadorResposta);
                numSimpli = numeradorResposta / maxDivisor;
                denomSimpli = denominadorResposta / maxDivisor;
                Console.WriteLine($"{numeradorResposta}/{denominadorResposta} = {numSimpli}/{denomSimpli}");
            }
        }

        static int mdc(int a, int b)
        {
            if (b > a)
                return mdc(Math.Abs(b), Math.Abs(a));
            else if (b == 0)
                return Math.Abs(a);
            else
                return mdc(Math.Abs(b), Math.Abs(a % b));
        }
    }
}
~~~

## 1023 - nível 10 de dificuldade

~~~csharp
/* 
Exemplo de entrada:
3
3 22
2 11
3 39
5
1 25
2 20
3 31
2 40
6 70
2
1 1
3 2
0
*/
using System;
using System.Globalization;
using System.Collections.Generic;

namespace TreinosBeecrowd
{
    class Program
    {
        static void Main(string[] args)
        {
            CultureInfo.CurrentCulture = new CultureInfo("en-US");

            int quantImoveis = 0;
            int quantMoradores = 0;
            int consumoPorResidencia = 0;
            int consumoMedio = 0;
            int totalMoradores = 0;
            int totalConsumo = 0;
            int contadorCidade = 0;
            decimal consumoMedioTotal = 0;

            SortedList<int, int> mySortedList = new SortedList<int, int>();

            string linha = "";
            string[] valores = new string[2];

            while (true)
            {
                quantImoveis = Int32.Parse(Console.ReadLine());
                if (quantImoveis == 0)
                    break;

                contadorCidade += 1;

                for (int i = 0; i < quantImoveis; i++)
                {
                    linha = Console.ReadLine();
                    valores = linha.Split(' ');
                    quantMoradores = Int32.Parse(valores[0]);
                    consumoPorResidencia = Int32.Parse(valores[1]);
                    consumoMedio = (int)(consumoPorResidencia / quantMoradores);

                    if (!mySortedList.TryAdd(consumoMedio, quantMoradores))
                        mySortedList[consumoMedio] += quantMoradores;

                    totalConsumo += consumoPorResidencia;
                    totalMoradores += quantMoradores;
                }

                Console.WriteLine($"Cidade# {contadorCidade}:");

                foreach (KeyValuePair<int, int> item in mySortedList)
                    Console.Write($"{item.Value}-{item.Key} ");

                consumoMedioTotal = (decimal)totalConsumo / totalMoradores;
                Console.WriteLine($"\nConsumo medio: {(Math.Truncate(consumoMedioTotal * 100) / 100):F2} m3.\n");

                totalMoradores = 0;
                totalConsumo = 0;
                mySortedList.Clear();
            }
        }
    }
}
~~~