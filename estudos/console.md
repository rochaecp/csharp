# C# - Console

> Namespace: System - ``` using System; ```

## Métodos 

### Console.Read() - Le próximo caractere

```csharp
myInt = Console.Read();
myChar = (char)Console.Read();
```

### Console.ReadLine() - Lê próxima linha

```csharp
myStr = Console.ReadLine();
myInt = Convert.ToInt32(Console.ReadLine());
```

### Console.Write()

```csharp
Console.Write("Olá Mundo");
```

### Console.WriteLine()

```csharp
Console.WriteLine("Olá Mundo");
Console.WriteLine("Olá: " + myStr);
Console.WriteLine("Sua idade é: " + myInt);

Console.WriteLine($"Olá {myStr}");
Console.WriteLine($"Seu salário é: {myDouble:F2}");
Console.WriteLine("Olá {0} Salário: {1:F2}", myStr, myDouble);
```
