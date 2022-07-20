# Soluções Hacker Rank

# Operators

~~~csharp
using System.CodeDom.Compiler;
using System.Collections.Generic;
using System.Collections;
using System.ComponentModel;
using System.Diagnostics.CodeAnalysis;
using System.Globalization;
using System.IO;
using System.Linq;
using System.Reflection;
using System.Runtime.Serialization;
using System.Text.RegularExpressions;
using System.Text;
using System;

class Result
{

    /*
     * Complete the 'solve' function below.
     *
     * The function accepts following parameters:
     *  1. DOUBLE meal_cost
     *  2. INTEGER tip_percent
     *  3. INTEGER tax_percent
     */

    public static void solve(double meal_cost, int tip_percent, int tax_percent)
    {
        double meals_total_cost = meal_cost + tip_percent * meal_cost / 100 + tax_percent * meal_cost / 100;
        Console.WriteLine($"{Math.Round(meals_total_cost)}");
    }
}

class Solution
{
    public static void Main(string[] args)
    {
        CultureInfo.CurrentCulture = new CultureInfo("en-US");

        double meal_cost = Convert.ToDouble(Console.ReadLine().Trim());

        int tip_percent = Convert.ToInt32(Console.ReadLine().Trim());

        int tax_percent = Convert.ToInt32(Console.ReadLine().Trim());

        Result.solve(meal_cost, tip_percent, tax_percent);
    }
}
~~~

# Class vs. Instance

~~~csharp
using System;
using System.Collections.Generic;
using System.IO;

class Person
{
    public int age;
    public Person(int initialAge)
    {
        if (initialAge > 0)
            this.age = initialAge;
        else
        {
            this.age = 0;
            Console.WriteLine("Age is not valid, setting age to 0.");
        }
    }
    public void amIOld()
    {
        if (age < 13)
            Console.WriteLine("You are young.");
        else if (age >= 13 && age < 18)
            Console.WriteLine("You are a teenager.");
        else
            Console.WriteLine("You are old.");
    }

    public void yearPasses()
    {
        this.age += 1;
    }

    static void Main(String[] args)
    {
        int T = int.Parse(Console.In.ReadLine());
        for (int i = 0; i < T; i++)
        {
            int age = int.Parse(Console.In.ReadLine());
            Person p = new Person(age);
            p.amIOld();
            for (int j = 0; j < 3; j++)
            {
                p.yearPasses();
            }
            p.amIOld();
            Console.WriteLine();
        }
    }
}
~~~

# Strings

~~~csharp
using System;
using System.Collections.Generic;
using System.IO;
class Solution
{
    public static string retornaString(string str)
    {
        string strPar = "", strImpar = "";
        char[] arrayChar = str.ToCharArray();

        for (int i = 0; i < arrayChar.Length; i++)
            if (i % 2 == 0)
                strPar += arrayChar[i];
            else
                strImpar += arrayChar[i];
        return strPar + " " + strImpar;
    }
    static void Main(String[] args)
    {
        string myString;
        int repeticoes;

        repeticoes = int.Parse(Console.ReadLine());

        for (int i = 0; i < repeticoes; i++)
        {
            myString = Console.ReadLine();
            Console.WriteLine(retornaString(myString));
        }
    }
}
~~~

# Arrays 

~~~csharp
using System.Collections.Generic;
using System.Linq;
using System;

class Solution
{
    public static void Main(string[] args)
    {
        int n = Convert.ToInt32(Console.ReadLine().Trim());

        List<int> arr = Console.ReadLine().TrimEnd().Split(' ').ToList().Select(arrTemp => Convert.ToInt32(arrTemp)).ToList();
        int[] myArr = arr.ToArray();

        for (int i = n - 1; i >= 0; i--)
            Console.Write($"{myArr[i]} ");
        Console.WriteLine();
    }
}
~~~

# Dictionaries

~~~csharp
using System.Data;
using System;
using System.Collections.Generic;
using System.IO;
class Solution
{
    static void Main(String[] args)
    {
        IDictionary<string, string> phone_numbers = new Dictionary<string, string>();
        int number_of_entries;
        string name;
        string[] line_values = new string[2];
        string phone_number;
        string query_name;

        number_of_entries = int.Parse(Console.ReadLine());
        for (int i = 0; i < number_of_entries; i++)
        {
            line_values = Console.ReadLine().Split(' ');
            name = line_values[0];
            phone_number = line_values[1];
            phone_numbers.Add(name, phone_number);
        }

        while (true)
        {
            query_name = Console.ReadLine();
            if (string.IsNullOrEmpty(query_name))
                break;
            if (phone_numbers.ContainsKey(query_name))
                Console.WriteLine($"{query_name}={phone_numbers[query_name]}");
            else
                Console.WriteLine("Not found");
        }
    }
}
~~~

# Recursão

~~~csharp

~~~

# x

~~~csharp

~~~