# C# - Operadores

##  Operadores de Atribuição

``` = ```

## Operadores Aritméticos

``` + ```
``` - ```
``` * ```
``` / ```
``` % ```
 
## Operadores Aritméticos de Atribuição Reduzida

``` += ```
``` -= ```
``` *= ```
``` /= ```
``` %= ```
  
## Operadores Incrementais (prefixo ou sufixo)

``` ++ ```

## Operadores Decrementais (prefixo ou sufixo)

``` -- ```

## Operadores Relacionais

``` == ```
``` != ```
``` > ```
``` < ```
``` >= ```
``` <= ```

## Operadores Lógicos

``` && ```
``` || ```
``` ! ```

## Operador Ternário

``` teste lógico ? valor se verdadeiro : valor se falso; ```

## Exemplo

~~~csharp
using System;

namespace Operadores
{
    class Program
    {
        static void Main(string[] args)
        {
            int a = 5;
            int b = 10;
            int c = 15;
            int d = 20;
            int x = 5;

            // Operadores Aritméticos
            Console.WriteLine("Operadores Aritmeticos");
            Console.WriteLine(a + d);
            Console.WriteLine(c - a);
            Console.WriteLine(b * c);
            Console.WriteLine(d / b);
            Console.WriteLine(c % b);

            // Operadores Aritméticos de Atribuição Reduzida
            Console.WriteLine("\nOperadores Aritmeticos de Atribuição Reduzida");
            x += 5; // é a mesma coisa que x = x + 5
            Console.WriteLine("Valor do x = " + x);

            // Operadores incrementais e decrementais
            Console.WriteLine("\nOperadores incrementais e decrementais");
            x = 0;
            Console.WriteLine("x = 0 e ++x +20 = " + (++x + 20));
            x = 0;
            Console.WriteLine("x = 0 e x++ +20 = " + (x++ + 20));

            // Operadores Relacionais
            Console.WriteLine("\nOperadores relacionais");
            Console.WriteLine("a == d: " + (a == d));
            Console.WriteLine("b != c: " + (b != c));
            Console.WriteLine("a > b : " + (a > b));
            Console.WriteLine("c < d : " + (c < d));
            Console.WriteLine("c >= a: " + (c >= a));
            Console.WriteLine("d <= b: " + (d <= b));

            // Operadores Lógicos
            Console.WriteLine("\nOperadores lógicos");
            Console.WriteLine("a == 5 && d == 10: " + (a == 5 && d == 10));
            Console.WriteLine("c < b || d == 20: " + (c < b || d == 20));
            Console.WriteLine("!(b > a): " + (!(b > a)));

            // Operador Ternário
            Console.WriteLine("\nOperadore ternário");
            Console.WriteLine("a < b ? " + (a < b ? "sim" : "não"));
        }
    }
}
~~~
