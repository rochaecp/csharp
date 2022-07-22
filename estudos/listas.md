# C# - Listas

> Namespace: System.Collections.Generic - ``` using System.Collections.Generic; ```

- Criação

    - Int

        ~~~csharp
        List<int> myIntList = new List<int>();
        ~~~
        
- Inclusão

    - Int

        ~~~csharp
        myIntList.Add(10);
        ~~~
        
- Acesso

    - Um elemento

        ~~~csharp
        myInt = myIntList[0];
        ~~~
        
    - Todos Elementos - For

        ~~~csharp
        for (int i = 0; i < myIntList.Count; i++)
            Console.WriteLine(myIntList[i]);
        ~~~
        
    - Todos Elementos - Foreach

        ~~~csharp
        foreach (int myInt in myIntList)
            Console.WriteLine(myInt);
        ~~~  
        
    - Todos Elementos - Foreach        

        ~~~csharp
        myIntList.ForEach(delegate (int myInt)
        {
            Console.WriteLine(myInt);
        });
        ~~~
        
- Métodos

    - Sort()

        ~~~csharp
        myIntList.Sort();
        ~~~

## Exemplos

- Covertendo listas em arrays

    ~~~csharp
    int[] meuArray = minhaLista.ToArray();
    ~~~
