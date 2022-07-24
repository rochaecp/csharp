# C# - Exceções

> Exceções são tipos que derivam da classe ``` System.Exception ```  
> Algumas classes de Exceção:
> - ArithmeticException
> - FileNotFoundException
> - IndexOutOfRangeException
> - TimeOutException
> - NotImplementedException
>   - ``` throw new NotImplementedException (); ```

- Criação

    - Try .. Catch

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
        
    - Try .. Catch (com mensagem personalizada)

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
        
    - Try .. Catch .. Finaly

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
        
    - Throw (para exceção personalizada)

        ~~~csharp
        if (myInt < 18)
            throw new ArithmeticException("Acesso Negado");
        else
            Console.WriteLine("Ok");        
        ~~~   
        
- Classes

    - NotImplementedException

        ~~~csharp
        static int MetodoParaDesenvolver ()
        {
            throw new NotImplementedException();
        }        
        ~~~
        
## Exemplos

- Exceção capturada por método
    
    - Arquivo: Program.cs
        
        ~~~csharp
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
        
- Exceção personalizada
    
    - Arquivo: CustomException.cs
        
        ~~~csharp
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

    - Arquivo: Program.cs
        
        ~~~csharp
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
        
- Exceção personalizada - Temperatura negativa
    
    - Arquivo: TempIsNegativeException
        
        ~~~csharp
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
        
    - Arquivo: Temperature.cs
        
        ~~~csharp
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
        
    - Arquivo: Program.cs
        
        ~~~csharp
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


