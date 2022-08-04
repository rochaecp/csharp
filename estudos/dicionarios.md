# C# - Dicionários

> Namespace: System.Collections.Generic - ``` using System.Collections.Generic; ```

## Criação

### String, String

~~~csharp
Dictionary<string, string> myDict = new Dictionary<string, string>()
{
    { "txt", "notepad" },
    { "bmp", "paint" },
    { "svg", "inkscape"}
};    
~~~  

### Int, String

~~~csharp
Dictionary<int, string> myDict2 = new Dictionary<int, string>()
{
    { 1, "Maurício" },
    { 2, "Maria" },
    { 3, "Joana"}
};    
~~~

## Inclusão

### String, String

~~~csharp
myDict.Add("dwg", "autocad");
~~~

### Int, String

~~~csharp
myDict2.Add(4, "Bernadete");
~~~

## Remoção

### String, String - Pela Chave

~~~csharp
myDict.Remove("dwg");
~~~

## Acesso

### Um Valor

~~~csharp
myStr = myDict["txt"];
myStr2 = myDict2[1]; 
~~~

### Todas as Chaves

~~~csharp
for (int i = 0; i < myDict.Count; i++)
    Console.WriteLine(myDict.Keys.ElementAt(i));
~~~

### Todos os Valores        

~~~csharp
for (int i = 0; i < myDict.Count; i++)
    Console.WriteLine(myDict[myDict.Keys.ElementAt(i)]);        
~~~

## Propriedades

### Count

~~~csharp
myInt = myDict.Count;
~~~

## Métodos

### Keys.Contains

~~~csharp
myBool = myDict.Keys.Contains("txt");
~~~

### Values.Contains

~~~csharp
myBool = myDict.Values.Contains("notepad");
~~~
