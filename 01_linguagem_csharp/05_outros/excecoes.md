# C# - Exceções

- Exceções são tipos que derivam da classe System.Exception
- Algumas classes de Exceção:
    - ArithmeticException
    - FileNotFoundException
    - IndexOutOfRangeException
    - TimeOutException
    - NotImplementedException
        - throw new NotImplementedException ();

## Try ... Catch

~~~csharp
try
{
    Console.WriteLine(myIntArr[10]); // mas myIntArr.Length == 4
}
catch (Exception e)
{
    Console.WriteLine(e.Message);
}        
~~~

## Try ... Catch (com mensagem personalizada)

~~~csharp
try
{
    Console.WriteLine(myIntArr[10]); // mas myIntArr.Length == 4
}
catch (Exception e)
{
    Console.WriteLine("Índice do Array fora do limite.");
}
~~~        

## Try ... Catch ... Finally

~~~csharp
try
{
    Console.WriteLine(myIntArr[10]); // mas myIntArr.Length == 4
}
catch (Exception e)
{
    Console.WriteLine("Índice do Array fora do limite.");
}
finally
{
    Console.WriteLine("Fim");
}        
~~~

~~~csharp
try
{
    int x = Convert.ToInt32(Console.ReadLine());
    int result = 100 / x;
    Console.WriteLine(result);
}
catch (DivideByZeroException ex) // se x == 0
{
    Console.WriteLine("Divisão por zero. Error Info: {0}", ex.Message);
}
catch (InvalidOperationException ex) 
{
    Console.WriteLine("Operação inválida. Error Info: {0}", ex.Message);
}
catch (FormatException ex) // se x == 'a'
{
    Console.WriteLine("Operação inválida. Error Info: {0}", ex.Message);
}
catch (Exception ex)
{
    Console.WriteLine("Um erro ocorreu. Error Info: {0}", ex.Message);
}
finally
{
    Console.WriteLine("Bloco finalizado.");
}        
~~~

## Throw (lançar exceção manualmente)

~~~csharp
if (myInt < 18)
    throw new ArithmeticException("Acesso Negado");
else
    Console.WriteLine("Ok");        
~~~   

## Classe NotImplementedException

~~~csharp
static int MetodoParaDesenvolver ()
{
    throw new NotImplementedException();
}        
~~~

## Utilizando Throw

~~~csharp
// Arquivo: Program.cs
using System;

namespace MyApplication
{
    class Program
    {
        static void PrintMyStr(string? str)
        {
            if (str == null)
                throw new NullReferenceException("String não pode ser nula");
            Console.WriteLine(str);
        }
        static void Main(string[] args)
        {
            try
            {
                PrintMyStr(null);
            }
            catch (Exception ex)
            {
                Console.WriteLine("Error info: {0}", ex.Message);
            }
        }
    }
}
~~~

## Utilizando Throw

~~~csharp
// Arquivo: Program.cs
using System;

namespace MyApplication
{
    class Program
    {
        static double DivisaoSegura (double x, double y)
        {
            if (y == 0)
                throw new DivideByZeroException();
            return x / y;                
        }

        static void Main(string[] Args)
        {
            double a = 10, b = 0;
            double result;

            try
            {
                result = DivisaoSegura(a, b);
                Console.WriteLine(result);
            }
            catch (DivideByZeroException)
            {
                Console.WriteLine("Atenção: divisão por zero");
            }
        }
    }
}
~~~

## Exceção personalizada

~~~csharp
// Arquivo: CustomException.cs
namespace MyApplication
{
    public class CustomException : Exception
    {
        public CustomException()
        {
        }
        public CustomException(string message)
            : base(message)
        {
        }
        public CustomException(string message, Exception innerException)
            : base(message, innerException)
        {
        }
    }
}
~~~  

~~~csharp
// Arquivo: Program.cs
using System;   

namespace MyApplication
{
    class Program
    {
        public static bool MelhorPresidente(string name)
        {
            if (name.ToLower().Equals("bozo"))
                throw new CustomException("Minha exceção personalizada!");
            return true;
        }

        static void Main(string[] Args)
        {
            bool result = false;
            try
            {
                result = MelhorPresidente("Bozo");
            }
            catch (CustomException ex)
            {
                Console.WriteLine(ex.Message);
            }
        }
    }
}
~~~    

## Exceção personalizada

~~~csharp
// Arquivo: InvalidStudentNameException.cs
namespace MyApplication
{
    [Serializable]
    public class InvalidStudentNameException : Exception
    {
        public InvalidStudentNameException(string name)
            : base(string.Format("Nome inválido para o estudante: {0}", name))
        {
        }
    }
}
~~~          


~~~csharp
// Arquivo: Program.cs
using System;
using System.Text.RegularExpressions;

namespace MyApplication
{
    class Program
    {
        static bool ValidateStudent(string name)
        {
            Regex regex = new Regex("^[a-zA-Z]+$");
            if (!regex.IsMatch(name))
                throw new InvalidStudentNameException(name);
            return true;
        }

        static void Main(string[] args)
        {
            try
            {
                ValidateStudent("Mauricio1234");
            }
            catch (Exception ex)
            {
                Console.WriteLine(ex.Message);
            }
        }
    }
}
~~~           

## Exceção personalizada - Temperatura negativa

~~~csharp
// Arquivo: TempIsNegativeException
namespace MyApplication
{
    public class TempIsNegativeException : Exception
    {
        public TempIsNegativeException(string message)
            : base(message)
        {
        }
    }
}
~~~    


~~~csharp
// Arquivo: Temperature.cs
using System;

namespace MyApplication
{
    public class Temperature
    {
        int Temp { get; set; } = -10;

        public void showTemperature()
        {
            if (Temp < 0)
                throw new TempIsNegativeException("Temperatura não pode ser negativa");
            else
                Console.WriteLine($"Temperatura = {Temp}");
        }
    }
}
~~~      

~~~csharp
// Arquivo: Program.cs
using System;   

namespace MyApplication
{
    class Program
    {
        static void Main(string[] Args)
        {
            Temperature t = new Temperature();
            try
            {
                t.showTemperature();
            }
            catch (TempIsNegativeException ex)
            {
                Console.WriteLine($"TempIsNegativeException: {ex.Message}");
            }
        }
    }
}
~~~             
