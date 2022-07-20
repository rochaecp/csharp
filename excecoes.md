# C# - Exceções

- Quando um erro ocorre geralmente o C# para e gera uma mensagem de erro (dispara uma exceção).
- Instruções:
  - try
  - catch
  - finally
  - throw

## Exemplo

~~~csharp
using System;

namespace Excecoes
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

## Exemplo

~~~csharp
using System;

namespace Excecoes
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

## Exemplo

~~~csharp
try {
  int[] myNumbers = { 1, 2, 3 };
  Console.WriteLine(myNumbers[10]);
} catch (Exception e) {
  Console.WriteLine("Something went wrong.");
}


try {
  int[] myNumbers = { 1, 2, 3 };
  Console.WriteLine(myNumbers[10]);
} catch (Exception e) {
  Console.WriteLine("Something went wrong.");
} finally {
  Console.WriteLine("The 'try catch' is finished.");
}


int players = 2, score = 0;
try {
  if (players != 2)
    throw new InvalidOperationException("error: must have 2 players ");
  players = 1 / score;
} catch (InvalidOperationException e) {
  Console.WriteLine(e.Message);
} catch (Exception e) {
  Console.WriteLine($"Generic error: {e.Message}");
}


if (decimal.TryParse(Console.ReadLine(), out decimal grade))
  student.Grade = grade;
else
  throw new ArgumentException("O valor da nota deve ser decimal.");
~~~
