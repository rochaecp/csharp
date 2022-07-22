# C# - Arrays

> Namespace: System - ``` using System; ```  

## Arrays Unidimensionais

- Criação 

    - Int

        ```csharp
        int[] myIntArr = new int[3];
        int[] myIntArr2 = new int[3] { 10, 20, 30 };
        int[] myIntArr3 = new int[] { 10, 20, 30 };
        int[] myIntArr4 = { 10, 20, 30 };

        int[] myIntArr5;
        myIntArr5 = new int[3] { 10, 20, 30 };
        ```

    - String

        ```csharp
        string[] myStrArr = new string[3];
        string[] myStrArr2 = new string[3] { "aaa", "bbb", "ccc" };
        string[] myStrArr3 = new string[] { "aaa", "bbb", "ccc" };
        string[] myStrArr4 = { "aaa", "bbb", "ccc" };
        
        string[] myStrArr5;
        myStrArr5 = new string[3] { "aaa", "bbb", "ccc" };
        ```
        
- Acesso

    - Um elemento

        ~~~csharp
        myItemStr = myStrArr[0];
        ~~~
        
    - Todos elementos - For

        ~~~csharp
        for (int i = 0; i < myArrayString2.Length; i++)
            Console.WriteLine(myStrArr[i]);        
        ~~~

    - Todos elementos - Foreach

        ~~~csharp
        foreach (string i in myArrayString2)
            Console.WriteLine(i);   
        ~~~

- Modificação

    - Um elemento

        ~~~csharp
        myStrArr[0] = "Mauricio";
        ~~~
        
- Propriedades

    - Length

        ~~~csharp
        myInt = myStrArr.Length;
        ~~~

- Métodos

    - Array.Sort()

        ~~~csharp
        Array.Sort(myStrArr);
        ~~~

    - Max()

        > Namespace: System.Linq - ``` using System.Linq; ```

        ~~~csharp
        myInt = myIntArr.Max();
        ~~~        
        
    - Min()

        > Namespace: System.Linq - ``` using System.Linq; ```

        ~~~csharp
        myInt = myIntArr.Min();
        ~~~        

    - Sum()

        > Namespace: System.Linq - ``` using System.Linq; ```

        ~~~csharp
        myInt = myIntArr.Sum();
        ~~~ 

- Exemplos

    - Convertendo String em Array de Char
        
        ~~~csharp
        string myStr = "This is String example";
        char[] myCharArr = myStr.ToCharArray();        
        ~~~
        
    - Convertendo Array de Char em String

    ~~~csharp
        myStr = string.Join("", myCharArr);    
    ~~~

## Arrays Bidimensionais        

- Criação

    - Int

        ~~~csharp
        int [,] myIntArr = new int [3, 2];
        int [,] myIntArr2 = new int[3, 2] { { 1, 2 }, { 3, 4 }, { 5, 6 } };
        ~~~
        
- Acesso

    - Um elemento

        ~~~csharp
        myItemStr = myStrArr[0, 0];
        ~~~        

## Arrays Tridimensionais

- Criação

    - Int

        ~~~csharp
        int [, ,] myIntArr = new int [3, 2, 4];
        ~~~
