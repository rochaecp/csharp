# C# - Soluções Beecrowd

### 1000 - Hello World!

~~~csharp
using System;

namespace treinoUri
{
    class Program
    {
        static void Main(string[] args)
        {
            Console.WriteLine("Hello World!");
        }
    }
}
~~~

### 1001 - Extremamente Básico

~~~csharp 
using System;

namespace beecrowd
{
    class Program
    {
        static void Main(string[] args)
        {
            int A = 0;
            int B = 0;
            int X = 0;

            A = Int32.Parse(System.Console.ReadLine().Trim());
            B = Int32.Parse(System.Console.ReadLine().Trim());
            X = A + B;

            Console.WriteLine($"X = {X}");
        }
    }
}
~~~

### 1002 - Área do Círculo

~~~csharp
using System;
using System.Globalization;

namespace beecrowd
{
    class Program
    {
        static void Main(string[] args)
        {
            // adicional - para usar ponto no lugar de vírgula nas casas decimais
            CultureInfo.CurrentCulture = new CultureInfo("en-US"); 
            // Console.WriteLine(CultureInfo.CurrentCulture.TextInfo);

            const double pi = 3.14159D;
            double raio = 0D;
            double area = 0D;

            raio = Convert.ToDouble(System.Console.ReadLine().Trim());
            area = pi * Math.Pow(raio, 2);

            Console.WriteLine("A=" + area.ToString("0.0000"));

        }
    }
}
~~~

### 1003 - Soma Simples

~~~csharp
using System;

namespace beecrowd
{
    class Program
    {
        static void Main(string[] args)
        {
            int a = 0;
            int b = 0;
            int soma = 0;

            a = Int32.Parse(System.Console.ReadLine().Trim()); // ou Convert.ToInt32(Console.ReadLine());
            b = Int32.Parse(System.Console.ReadLine().Trim());
            soma = a + b;

            Console.WriteLine($"SOMA = {soma}");
            Console.ReadKey();
        }
    }
}
~~~

### 1004 - Produto Simples

~~~csharp
using System;

namespace beecrowd
{
    class Program
    {
        static void Main(string[] args)
        {
            int valor1 = 0, valor2 = 0, prod = 0;

            valor1 = Convert.ToInt32(System.Console.ReadLine().Trim());
            valor2 = Convert.ToInt32(System.Console.ReadLine().Trim());
            prod = valor1 * valor2;

            Console.WriteLine($"PROD = {prod}");
        }
    }
}
~~~

### 1005 - Média 1

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

            double valorA = 0D, valorB = 0D, media = 0D;
            valorA = Convert.ToDouble(Console.ReadLine().Trim());
            valorB = Convert.ToDouble(Console.ReadLine().Trim());
            media = (3.5 * valorA + 7.5 * valorB) / 11.0;

            Console.WriteLine($"MEDIA = {media:F5}");
        }
    }
}
~~~

### 1006 - Média 2

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

            double notaA = 0D, notaB = 0D, notaC = 0D, media = 0D;

            notaA = Convert.ToDouble(Console.ReadLine().Trim());
            notaB = Convert.ToDouble(Console.ReadLine().Trim());
            notaC = Convert.ToDouble(Console.ReadLine().Trim());

            media = (notaA * 2 + notaB * 3 + notaC * 5) / 10.0;
            Console.WriteLine($"MEDIA = {media:F1}");
        }
    }
}
~~~

### 1007 - Diferença 

~~~csharp
using System;

namespace beecrowd
{
    class Program
    {
        static void Main(string[] args)
        {
            int a = 0, b = 0, c = 0, d = 0, diferenca = 0;

            a = Convert.ToInt32(System.Console.ReadLine().Trim());
            b = Convert.ToInt32(System.Console.ReadLine().Trim());
            c = Convert.ToInt32(System.Console.ReadLine().Trim());
            d = Convert.ToInt32(System.Console.ReadLine().Trim());

            diferenca = (a * b - c * d);

            System.Console.WriteLine($"DIFERENCA = {diferenca}");
        }
    }
}
~~~

### 1008 - Salário 

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

            int numeroFuncionario = 0;
            int numeroHoras = 0;
            Double valorHora = 0D;
            Double salario = 0D;

            numeroFuncionario = Convert.ToInt32(Console.ReadLine().Trim());
            numeroHoras = Convert.ToInt32(Console.ReadLine().Trim());
            valorHora = Convert.ToDouble(Console.ReadLine().Trim());

            salario = (double)(numeroHoras * valorHora);

            Console.WriteLine($"NUMBER = {numeroFuncionario}");
            Console.WriteLine($"SALARY = U$ {salario:F2}");
        }
    }
}
~~~

### 1009 - Salário com Bônus 

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

            const double COMISSAO = 0.15;
            string nome = "";
            double salario = 0D;
            double totalVendas = 0D;
            double salarioTotal = 0D;

            nome = Console.ReadLine();
            salario = Convert.ToDouble(Console.ReadLine().Trim());
            totalVendas = Convert.ToDouble(Console.ReadLine().Trim());

            salarioTotal = salario + totalVendas * COMISSAO;

            Console.WriteLine($"TOTAL = R$ {salarioTotal:F2}");
        }
    }
}
~~~

### 1010 - Cálculo simples

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

### 1011 - Esfera

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

### 1012 - Área 

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

### 1013 - O Maior

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

### 1014 - Consumo

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

### 1015 - Distância entre dois pontos

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

### 1016 - Distância 

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

### 1017 - Gasto de Combustível

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

### 1018 - Cédulas (solução 1)

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

### 1018 - Cédulas (solução 2 - com dicionários)

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

### 1019 - Conversão de Tempo

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

### 1020 - Idade em dias

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

### 1021 - Notas e moedas

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

### 1035 - Teste de Seleção 1

~~~csharp

~~~

### 1036 - Fórmula de Bhaskara

~~~csharp

~~~

### 1037 - Intervalo

~~~csharp

~~~

### 1038 - Lanche

~~~csharp

~~~

### 1040 - Média 3

~~~csharp

~~~

### 1041 - Coordenadas de um Ponto

~~~csharp

~~~

### 1042 - Sort Simples

~~~csharp

~~~

### 1043 - Triângulo

~~~csharp

~~~

### 1044 - Múltiplos

~~~csharp

~~~

### 1045 - Tipos de Triângulos

~~~csharp

~~~

### 1046 - Tempo de Jogo

~~~csharp

~~~

### 1047 - Tempo de Jogo com Minutos

~~~csharp

~~~

### 1048 - Aumento de Salário

~~~csharp

~~~

### 1049 - Animal

~~~csharp

~~~

### 1050 - DDD

~~~csharp

~~~