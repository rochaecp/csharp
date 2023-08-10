# C# - Console

- Console.Read()
    - Ler o próximo caractere
    ```csharp
    myInt = Console.Read();
    myChar = (char)Console.Read();
    ```

- Console.ReadLine()
    - Ler a próxima linha
    ```csharp
    myStr = Console.ReadLine();
    myInt = Convert.ToInt32(Console.ReadLine());
    ```

- Console.Write()
    - Escrever sem quebrar a linha
    ```csharp
    Console.Write("Olá Mundo");
    ```

- Console.WriteLine()
    - Escrever quebrando a linha
    ```csharp
    Console.WriteLine("Olá Mundo");
    Console.WriteLine("Olá: " + myStr);
    Console.WriteLine("Sua idade é: " + myInt);

    Console.WriteLine($"Olá {myStr}");
    Console.WriteLine($"Seu salário é: {myDouble:F2}");
    Console.WriteLine("Olá {0} Salário: {1:F2}", myStr, myDouble);
    ```
