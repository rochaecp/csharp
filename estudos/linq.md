# C# - LINQ (Language-Integrated Query)

> Namespace: System.Linq - ``` using System.Linq; ``` 

- Métodos

    - Select()

        > Select recebe como parâmetro uma função anônima na forma de uma expressão lambda 

        ~~~csharp
        string[] nomes = new string[] { "Maurício", "Maria", "Joana" };
        var resultado = nomes.Select(x => x.ToUpper());        
        ~~~
        
        ~~~csharp
        string[] valores = new string[] { "2", "5", "3", "1", "4" };
        var valoresInt = valores.Select(x => Int32.Parse(x));        
        ~~~
        
    - OrderBy() 
        
        ~~~csharp
        string[] valores = new string[] { "2", "5", "3", "1", "4" };
        var valoresIntOrdenados = valores.Select(x => Int32.Parse(x)).OrderBy(i => i);
        int [] result = numerosStr.Select(x => Int32.Parse(x)).OrderBy(i => i).ToArray(); 
            // outra forma
        ~~~           

    - Where() 
        
        ~~~csharp
        string[] nomesComNulos = new string[] { "Maurício", null, "Maria", "", "Joana", string.Empty };
        var nomes = nomesComNulos.Where(x => !string.IsNullOrEmpty(x));
            // remove strings nulas ou vazias        
        ~~~     
        
        ~~~csharp
        int[] numeros = new int[] { 10, 20, 30, 40, 50, 60 };

        var result = from numero in numeros
                     where numero > 20
                     select numero;        
        ~~~

    - Count()

        ~~~csharp
        bool[] resultados = new bool[] { true, false, false, true, true };
        int totalTrue = resultados.Count(x => x == true);        
        ~~~
        
        ~~~csharp
        int[] notas = { 10, 9, 10, 5, 3 };
        int totAcimaMedia = notas.Count(x => x >= 6);  
        ~~~        
