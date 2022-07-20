# C# - problemas do Beecrowd

## 1020

~~~csharp
using System;
using System.Globalization;

namespace TreinosBeecrowd
{
    class Program
    {
        static void Main(string[] args)
        {
            CultureInfo.CurrentCulture = new CultureInfo("en-US");

            int idadeEmDias = 0;
            int anos = 0, meses = 0, dias = 0;

            idadeEmDias = Int32.Parse(Console.ReadLine());

            anos = idadeEmDias / 365;
            idadeEmDias = idadeEmDias % 365;
            meses = idadeEmDias / 30;
            idadeEmDias = idadeEmDias % 30;
            dias = idadeEmDias;

            Console.WriteLine($"{anos} ano(s)\n{meses} mes(es)\n{dias} dia(s)");
        }
    }
}
~~~

## 1021

~~~csharp
using System;
using System.Globalization;

namespace TreinosBeecrowd
{
    class Program
    {
        static void Main(string[] args)
        {
            CultureInfo.CurrentCulture = new CultureInfo("en-US");

            double[] valoresNotasMoedas = new double[12] { 100, 50, 20, 10, 5, 2, 1, 0.50, 0.25, 0.10, 0.05, 0.01 };
            int[] quantNotasMoedas = new int[12];
            double valor;

            valor = Convert.ToDouble(Console.ReadLine());

            for (int i = 0; i < valoresNotasMoedas.Length - 1; i++)
            {
                quantNotasMoedas[i] = (int)(valor / valoresNotasMoedas[i]);
                valor = (valor % valoresNotasMoedas[i]);
            }

            valor = Math.Round(valor, 2);
            quantNotasMoedas[11] = (int)(valor / 0.01);

            Console.WriteLine("NOTAS:");
            for (int i = 0; i < valoresNotasMoedas.Length - 6; i++)
                Console.WriteLine($"{quantNotasMoedas[i]} nota(s) de R$ {valoresNotasMoedas[i]:F2}");

            Console.WriteLine("MOEDAS:");
            for (int i = 6; i < valoresNotasMoedas.Length; i++)
                Console.WriteLine($"{quantNotasMoedas[i]} moeda(s) de R$ {valoresNotasMoedas[i]:F2}");
        }
    }
}
~~~

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

## 1024

~~~csharp
using System.Linq;
using System;
using System.Globalization;
using System.Collections.Generic;

namespace TreinosBeecrowd
{
    enum TabelaAscii : int
    {
        InicioMaiusculo = 65,
        FimMaiusculo = 90,
        InicioMinusculo = 97,
        FimMinusculo = 122
    }
    class Result
    {
        public static string criptografa(string s)
        {
            char[] arrayStr = s.ToCharArray();
            int numChar;
            string strCript = "";

            for (int i = 0; i < arrayStr.Length; i++)
            {
                numChar = (int)arrayStr[i];
                if (ehCaractere(numChar))
                {
                    numChar += 3;
                    arrayStr[i] = (char)numChar;
                }
            }

            Array.Reverse(arrayStr);

            for (int i = (arrayStr.Length) / 2; i < arrayStr.Length; i++)
            {
                numChar = (int)arrayStr[i];
                numChar -= 1;
                arrayStr[i] = (char)numChar;

            }

            strCript = (new string(arrayStr));

            return strCript;
        }

        public static bool ehCaractere(int numAsciiChar)
        {
            if ((numAsciiChar >= (int)TabelaAscii.InicioMaiusculo && numAsciiChar <= (int)TabelaAscii.FimMaiusculo) || (numAsciiChar >= (int)TabelaAscii.InicioMinusculo && numAsciiChar <= (int)TabelaAscii.FimMinusculo))
                return true;
            else
                return false;
        }
    }
    class Program
    {
        static void Main(string[] args)
        {
            CultureInfo.CurrentCulture = new CultureInfo("en-US");
            int num_entradas = 0;
            string str_lida = "";

            num_entradas = int.Parse(Console.ReadLine());

            for (int i = 0; i < num_entradas; i++)
            {
                str_lida = Console.ReadLine();
                Console.WriteLine(Result.criptografa(str_lida));
            }
        }
    }
}
~~~

## 102X

~~~csharp

~~~