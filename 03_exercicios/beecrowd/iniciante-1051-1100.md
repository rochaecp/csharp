# C# - Soluções Beecrowd

## 1051 - Imposto de Renda

~~~csharp
using System;
using System.Linq;
using System.Collections.Generic;
using System.Globalization;

namespace treinoUri
{
    class Program
    {
        static void Main(string[] args)
        {
            CultureInfo.CurrentCulture = new CultureInfo("en-US");
            double salario = Convert.ToDouble(Console.ReadLine());
            if (salario <= 2000)
                Console.WriteLine("Isento");
            else if (salario > 2000 && salario <= 3000)
                Console.WriteLine($"R$ {((salario - 2000) * 0.08):F2}");
            else if (salario > 3000 && salario <= 4500)
                Console.WriteLine($"R$ {(80 + (salario - 3000) * 0.18):F2}");
            else if (salario > 4500)
                Console.WriteLine($"R$ {(80 +  270 + (salario - 4500) * 0.28):F2}");

        }
    }
}
~~~

## 1052 - Mês

~~~csharp
using System;
using System.Linq;
using System.Collections.Generic;
using System.Globalization;

namespace treinoUri
{
    class Program
    {
        static void Main(string[] args)
        {
            //CultureInfo.CurrentCulture = new CultureInfo("en-US");
            string[] meses = {
                "January", "February", "March", "April", "May", "June",
                "July", "August", "September", "October", "November", "December"
            };

            int opcao = int.Parse(Console.ReadLine());
            Console.WriteLine(meses[opcao - 1]);     
        }
    }
}
~~~

## 1059 - Números Pares

~~~csharp

~~~

## 1060 - Números Positivos

~~~csharp

~~~

## 1061 - Tempo de um Evento

~~~csharp

~~~

## 1064 - Positivos e Média

~~~csharp

~~~

## 1065 - Pares entre Cinco Números

~~~csharp

~~~

## 1066 - Pares, Ímpares, Positivos e Negativos

~~~csharp

~~~

## 1067 - Números Ímpares

~~~csharp

~~~

## 1070 - Seis Números Ímpares

~~~csharp

~~~

## 1071 - Soma de Impares Consecutivos I

~~~csharp

~~~

## 1072 - Intervalo 2

~~~csharp

~~~

## 1073 - Quadrado de Pares

~~~csharp

~~~

## 1074 - Par ou Ímpar

~~~csharp

~~~

## 1075 - Resto 2

~~~csharp

~~~

## 1078 - Tabuada

~~~csharp

~~~

## 1079 - Médias Ponderadas

~~~csharp

~~~

## 1080 - Maior e Posição

~~~csharp

~~~

## 1094 - Experiências

~~~csharp

~~~

## 1095 - Sequencia IJ 1

~~~csharp

~~~

## 1096 - Sequencia IJ 2

~~~csharp

~~~

## 1097 - Sequencia IJ 3

~~~csharp

~~~

## 1098 - Sequencia IJ 4

~~~csharp

~~~

## 1099 - Soma de Ímpares Consecutivos II

~~~csharp

~~~
