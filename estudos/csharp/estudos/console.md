# C# - Console

Namespace: System.  

## Ler o próximo caractere - Console.Read()

```csharp
myInt = Console.Read();
myChar = (char)Console.Read();
```

## Ler a próxima linha - Console.ReadLine()

```csharp
myStr = Console.ReadLine();
myInt = Convert.ToInt32(Console.ReadLine());
```

## Escrever sem quebrar a linha - Console.Write()

```csharp
Console.Write("Olá Mundo");
```

## Escrever quebrando a linha - Console.WriteLine()

```csharp
Console.WriteLine("Olá Mundo");
Console.WriteLine("Olá: " + myStr);
Console.WriteLine("Sua idade é: " + myInt);

Console.WriteLine($"Olá {myStr}");
Console.WriteLine($"Seu salário é: {myDouble:F2}");
Console.WriteLine("Olá {0} Salário: {1:F2}", myStr, myDouble);
```
