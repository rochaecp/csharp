# C# - Exceções

## Exemplos

- Index Outside 

    - Arquivo: Program.cs

        ~~~csharp
        using System;

        namespace MyApplication
        {
            class Program
            {
                static void Main(string[] args)
                {
                    try
                    {
                        int[] myNumbers = { 1, 2, 3 };
                        Console.WriteLine(myNumbers[10]);
                    }
                    catch (Exception e)
                    {
                        Console.WriteLine(e.Message);
                    }
                }
            }
        }
        ~~~

- ArithmeticException

    - Arquivo: Program.cs

        ~~~csharp
        using System;

        namespace MyApplication
        {
            class Program
            {
                static void checkAge(int age)
                {
                    if (age < 18)
                    {
                        throw new ArithmeticException("Access denied - You must be at least 18 years old.");
                    }
                    else
                    {
                        Console.WriteLine("Access granted - You are old enough!");
                    }
                }
                static void Main(string[] args)
                {
                    checkAge(20);
                }
            }
        }
        ~~~
