 # C# - Escrita no Console

 ## Console.Write()

- Escrever sem quebrar a linha

~~~csharp
Console.Write("Olá Mundo");
~~~

## Console.WriteLine()

- Escrever quebrando a linha

~~~csharp
Console.WriteLine("Olá Mundo");
Console.WriteLine("Olá: " + myStr);
Console.WriteLine("Sua idade é: " + myInt);

Console.WriteLine(string.Format("Idade: {0}", variavel));

Console.WriteLine($"Olá {myStr}");
Console.WriteLine($"Seu salário é: {myDouble:F2}");
Console.WriteLine("Olá {0} Salário: {1:F2}", myStr, myDouble);
~~~
