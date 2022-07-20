# C# - Casting

## Casting Implícito

- Ocorre automaticamente.
- Converte um "tipo menor" em um "tipo maior":
    - char -> int 
    - int -> long
    - long -> float
    - float -> double

## Casting Explícito

- Ocorre de modo manual.
- Converte um "tipo maior" em um "tipo menor":
    - double -> float 
    - float -> long 
    - long -> int -
    - int -> char

## Exemplo

~~~csharp
using System;

namespace Casting
{
    class Program
    {
        static void Main(string[] args)
        {
            string myString = "10";
            int myInt = 10;
            double myDouble = 10D;
            long myLong = 10L;
            bool myBool = true;
            decimal myDecimal = 10;

            // casting implícita: char -> int -> long -> float -> double
            myDouble = myInt;

            // casting explícita
            myInt = (int)myDouble;

            // métodos de conversão
            string myStringConv = Convert.ToString(myInt);
            double myDoubleConv = Convert.ToDouble(myInt);
            int myIntConv = Convert.ToInt32(myDouble);
            long myLongConv = Convert.ToInt64(myDouble);
            bool myBoolConv = Convert.ToBoolean(myInt);

            Console.WriteLine($"myStringConv = {myStringConv}");
            Console.WriteLine($"myDoubleConv = {myDoubleConv}");
            Console.WriteLine($"myIntConv = {myIntConv}");
            Console.WriteLine($"myLongConv = {myLongConv}");
            Console.WriteLine($"myBoolConv = {myBoolConv}\n");

            // métodos de Parse()
            double myDoubleParse = Double.Parse(myString);
            int myIntParse = Int32.Parse(myString);
            long myLongParse = Int64.Parse(myString);

            Console.WriteLine($"myDoubleParse = {myDoubleParse}");
            Console.WriteLine($"myIntParse = {myIntParse}");
            Console.WriteLine($"myLongParse = {myLongParse}\n");

            // método ToString()
            Console.WriteLine($"myDouble.ToString() = {myDouble.ToString()}");
            Console.WriteLine($"myInt.ToString() = {myInt.ToString()}");
            Console.WriteLine($"myLong.ToString() = {myLong.ToString()}");
            Console.WriteLine($"myBool.ToString() = {myBool.ToString()}\n");

            Console.WriteLine($"Digite um valor decimal (somente decimal):");
            // métodos TryParse()
            if (decimal.TryParse(Console.ReadLine(), out decimal grade))
                myDecimal = grade;
            else
                throw new ArgumentException("O valor da nota deve ser decimal.");

            Console.WriteLine($"myDecimal = {myDecimal}");
        }
    }
}
~~~

