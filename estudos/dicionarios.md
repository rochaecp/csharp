# C# - Dicionários

#### Criar

~~~csharp
Dictionary<string, string> myDict = new Dictionary<string, string>() // String, String
{
    { "txt", "notepad" },
    { "bmp", "paint" },
    { "svg", "inkscape"}
};    
~~~  

~~~csharp
Dictionary<int, string> myDict2 = new Dictionary<int, string>() // Int, String
{
    { 1, "Maurício" },
    { 2, "Maria" },
    { 3, "Joana"}
};    
~~~

#### Incluir

~~~csharp
myDict.Add("dwg", "autocad"); // String, String
~~~

~~~csharp
myDict2.Add(4, "Bernadete"); // Int, String
~~~

#### Remover

~~~csharp
myDict.Remove("dwg"); // String, String - Pela Chave
~~~

#### Indexar

~~~csharp
myStr = myDict["txt"];
myStr2 = myDict2[1]; 
~~~

~~~csharp
for (int i = 0; i < myDict.Count; i++)
    Console.WriteLine(myDict.Keys.ElementAt(i));
~~~

~~~csharp
for (int i = 0; i < myDict.Count; i++)
    Console.WriteLine(myDict[myDict.Keys.ElementAt(i)]);        
~~~

#### Count

~~~csharp
myInt = myDict.Count;
~~~

#### Keys.Contains

~~~csharp
myBool = myDict.Keys.Contains("txt");
~~~

#### Values.Contains

~~~csharp
myBool = myDict.Values.Contains("notepad");
~~~
