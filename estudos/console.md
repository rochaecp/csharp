# C# - Console  

- Console.Read()
    - Ler o próximo caractere
    ```csharp
    int myInt = Console.Read(); // le o cvalor ASCII do primeiro caracatere
    char myChar = (char)Console.Read();
    ```

- Console.ReadLine()
    - Ler a próxima linha
    ```csharp
    string myStr = Console.ReadLine();
    int myInt = Convert.ToInt32(Console.ReadLine());
    int numero = Int32.Parse(Console.ReadLine()); // evitar: nem toda entrada poderá ser convertida
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

    Console.WriteLine(string.Format("Idade: {0}", variavel));

    Console.WriteLine($"Olá {myStr}");
    Console.WriteLine($"Seu salário é: {myDouble:F2}");
    Console.WriteLine("Olá {0} Salário: {1:F2}", myStr, myDouble);
    ```
