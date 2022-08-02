# C# - Soluções Beecrowd

## 1010

~~~csharp
/*
Exemplo de entrada via console:
    12 1 5.30
    16 2 5.10
*/
using System;
using System.Globalization;

namespace beecrowd
{
    class Program
    {
        static void Main(string[] args)
        {
            CultureInfo.CurrentCulture = new CultureInfo("en-US");

            int codPeca1 = 0;
            int qntPecas1 = 0;
            double valorUnitario1 = 0D;

            int codPeca2 = 0;
            int qntPecas2 = 0;
            double valorUnitario2 = 0D;

            double totalPagar = 0D;

            string linha1 = Console.ReadLine();
            string linha2 = Console.ReadLine();

            string[] values1 = linha1.Split(' ');
            string[] values2 = linha2.Split(' ');

            codPeca1 = Convert.ToInt32(values1[0]);
            qntPecas1 = Convert.ToInt32(values1[1]);
            valorUnitario1 = Convert.ToDouble(values1[2]);

            codPeca2 = Convert.ToInt32(values2[0]);
            qntPecas2 = Convert.ToInt32(values2[1]);
            valorUnitario2 = Convert.ToDouble(values2[2]);

            totalPagar = qntPecas1 * valorUnitario1 + qntPecas2 * valorUnitario2;

            Console.WriteLine($"VALOR A PAGAR: R$ {totalPagar:F2}");
        }
    }
}
~~~

## 1011

~~~csharp
using System;
using System.Globalization;

namespace beecrowd
{
    class Program
    {
        static void Main(string[] args)
        {
            CultureInfo.CurrentCulture = new CultureInfo("en-US");
            const double pi = 3.14159;
            double raio = 0D;
            double volume = 0D;

            raio = Convert.ToDouble(Console.ReadLine().Trim());
            volume = (4 / 3.0) * pi * Math.Pow(raio, 3);
            Console.WriteLine($"VOLUME = {volume:F3}");
        }
    }
}
~~~

## 1012

~~~csharp
using System;
using System.Globalization;

namespace beecrowd
{
    class Program
    {
        static void Main(string[] args)
        {
            CultureInfo.CurrentCulture = new CultureInfo("en-US");

            const double pi = 3.14159;

            double a = 0D;
            double b = 0D;
            double c = 0D;

            double areaTriangulo = 0D;
            double areaCirculo = 0D;
            double areaTrapezio = 0D;
            double areaQuadrado = 0D;
            double areaRetangulo = 0D;

            string linha = Console.ReadLine();
            string[] valores = linha.Split(' ');

            a = Convert.ToDouble(valores[0]);
            b = Convert.ToDouble(valores[1]);
            c = Convert.ToDouble(valores[2]);

            areaTriangulo = (a * c) / 2.0;
            areaCirculo = pi * Math.Pow(c, 2);
            areaTrapezio = (a + b) * c / 2.0;
            areaQuadrado = Math.Pow(b, 2);
            areaRetangulo = a * b;

            Console.WriteLine($"TRIANGULO: {areaTriangulo:F3}");
            Console.WriteLine($"CIRCULO: {areaCirculo:F3}");
            Console.WriteLine($"TRAPEZIO: {areaTrapezio:F3}");
            Console.WriteLine($"QUADRADO: {areaQuadrado:F3}");
            Console.WriteLine($"RETANGULO: {areaRetangulo:F3}");
        }
    }
}
~~~

## 1013

~~~csharp
using System;

namespace TreinosBeecrowd
{
    class Program
    {
        static void Main(string[] args)
        {
            int a = 0;
            int b = 0;
            int c = 0;
            int maior = 0;
            string linha = "";
            string[] valores;

            linha = System.Console.ReadLine();
            valores = linha.Split(' ');

            a = Int32.Parse(valores[0]);
            b = Int32.Parse(valores[1]);
            c = Int32.Parse(valores[2]);

            maior = retornaMaior(a, b);
            maior = retornaMaior(maior, c);

            System.Console.WriteLine($"{maior} eh o maior");
        }

        static int retornaMaior(int a, int b)
        {
            return (int)((a + b + Math.Abs(a - b)) / 2);
        }
    }
}
~~~

## 1014

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

            int distanciaPercorrida = 0;
            double totalCombustivelGasto = 0F;
            double consumoMedio = 0D;

            distanciaPercorrida = Convert.ToInt32(Console.ReadLine().Trim());
            totalCombustivelGasto = Convert.ToDouble(Console.ReadLine().Trim());

            consumoMedio = (double)distanciaPercorrida / totalCombustivelGasto;

            System.Console.WriteLine($"{consumoMedio:F3} km/l");
        }
    }
}
~~~

## 1015

~~~csharp
/*
    tentar fazer com struct
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

            double x1 = 0D;
            double y1 = 0D;
            double x2 = 0D;
            double y2 = 0D;
            double distancia = 0D;

            string linha1 = Console.ReadLine();
            string linha2 = Console.ReadLine();

            string[] valores1 = linha1.Split(' ');
            string[] valores2 = linha2.Split(' ');

            x1 = Convert.ToDouble(valores1[0]);
            y1 = Convert.ToDouble(valores1[1]);

            x2 = Convert.ToDouble(valores2[0]);
            y2 = Convert.ToDouble(valores2[1]);

            distancia = Math.Sqrt(Math.Pow(x2 - x1, 2) + Math.Pow(y2 - y1, 2));

            System.Console.WriteLine($"{distancia:F4}");
        }
    }
}
~~~

## 1016

~~~csharp
using System;

namespace TreinosBeecrowd
{
    class Program
    {
        static void Main(string[] args)
        {
            int dist = Convert.ToInt32(Console.ReadLine());
            System.Console.WriteLine($"{dist * 2} minutos");
        }
    }
}
~~~

## 1017

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

            int consumoPorLitro = 12;
            int tempoViagem = 0;
            int velocMedia = 0;
            double consumo = 0D;

            tempoViagem = Convert.ToInt32(Console.ReadLine());
            velocMedia = Convert.ToInt32(Console.ReadLine());

            // casting implicito
            consumo = ((double)(velocMedia * tempoViagem)) / (consumoPorLitro);

            System.Console.WriteLine($"{consumo:F3}");
        }
    }
}
~~~

## 1018 (solução 1)

~~~csharp
using System;
using System.Globalization;

namespace TreinosBeecrowd
{
    class Program
    {
        static void Main(string[] args)
        {
            CultureInfo.CurrentCulture = new CultureInfo("pt-BR");

            int valorLido = 0;
            int valor = 0;
            int[] cedulas = new int[7] { 100, 50, 20, 10, 5, 2, 1 };
            int[] quantidadeCedulas = new int[7];

            valorLido = Convert.ToInt32(Console.ReadLine());
            valor = valorLido;

            for (int i = 0; i < cedulas.Length; i++)
            {
                if ((valor / cedulas[i]) > 0)
                {
                    quantidadeCedulas[i] = valor / cedulas[i];
                    valor = valor % cedulas[i];
                }
                else
                {
                    quantidadeCedulas[i] = 0;
                }
            }

            Console.WriteLine(String.Format("{0}", valorLido));
            for (int i = 0; i < cedulas.Length; i++)
            {
                Console.WriteLine("{0} nota(s) de R$ {1:F2}", quantidadeCedulas[i], cedulas[i]);
            }
        }
    }
}
~~~

## 1018 (solução 2 - com dicionários)

~~~csharp
/*
    utiliza dicionários para treinar
*/
using System;
using System.Collections.Generic;
using System.Globalization;

namespace TreinosBeecrowd
{
    class Program
    {
        static void Main(string[] args)
        {
            CultureInfo.CurrentCulture = new CultureInfo("pt-BR");

            int valorLido = 0;
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

            valorLido = Convert.ToInt32(Console.ReadLine());
            valor = valorLido;

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

            Console.WriteLine($"{valorLido}");
            foreach (KeyValuePair<int, int> item in dict)
            {
                Console.WriteLine("{0} nota(s) de R$ {1:F2}", item.Value, item.Key);
            }
        }
    }
}
~~~

## 1019

~~~csharp
using System;
//using System.Globalization;

namespace TreinosBeecrowd
{
    class Program
    {
        static void Main(string[] args)
        {
            //CultureInfo.CurrentCulture = new CultureInfo("en-US");

            int tempo = 0;
            int horas = 0;
            int minutos = 0;
            int segundos = 0;

            tempo = Int32.Parse(Console.ReadLine());

            horas = tempo / 3600;
            tempo = tempo % 3600;
            minutos = tempo / 60;
            tempo = tempo % 60;
            segundos = tempo;

            Console.WriteLine($"{horas}:{minutos}:{segundos}");
        }
    }
}
~~~
