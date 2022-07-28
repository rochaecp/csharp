# C# - LINQ (Language-Integrated Query)

> Namespace: System.Linq - ``` using System.Linq; ``` 

- Métodos

    - Select()

        > Select recebe como parâmetro uma função anônima na forma de uma expressão lambda 

        ~~~csharp
        string[] nomes = new string[] { "Maurício", "Maria", "Joana" };
        var resultado = nomes.Select(elemento => elemento.ToUpper());        
        ~~~
        
        ~~~csharp
        string[] valores = new string[] { "2", "5", "3", "1", "4" };
        var valoresInt = valores.Select(x => Int32.Parse(x));        
        ~~~
        
    - OrderBy() 
        
        ~~~csharp
        string[] valores = new string[] { "2", "5", "3", "1", "4" };
        var valoresIntOrdenados = valores.Select(x => Int32.Parse(x)).OrderBy(i => i);
        ~~~           

    - Where() 
        
        ~~~csharp
        
        ~~~     

    - Count()

        ~~~csharp
        
        ~~~
