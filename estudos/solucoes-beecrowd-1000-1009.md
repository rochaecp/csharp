# C# - problemas do Beecrowd

## 1000

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

## 1001

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

## 1002

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

## 1003

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

## 1004

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

## 1005

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

## 1006

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

## 1007

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

## 1008

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

## 1009

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
