# C# - Dicionários

## Criar

#### Int, String

~~~csharp
Dictionary<int, string> myDict2 = new Dictionary<int, string>() 
{
    { 1, "Maurício" },
    { 2, "Maria" },
    { 3, "Joana"}
};    
~~~

#### String, String

~~~csharp
Dictionary<string, string> myDict = new Dictionary<string, string>()
{
    { "txt", "notepad" },
    { "bmp", "paint" },
    { "svg", "inkscape"}
};    
~~~

## Tamanho

~~~csharp
myInt = myDict.Count;
~~~

## Incluir

~~~csharp
myDict.Add("dwg", "autocad"); // String, String
~~~

~~~csharp
myDict2.Add(4, "Bernadete"); // Int, String
~~~

## Remover

~~~csharp
myDict.Remove("dwg"); // String, String - Pela Chave
~~~

## Indexar

~~~csharp
myStr = myDict["txt"];
myStr2 = myDict2[1]; 
~~~

## Exibir

#### Exibir Chaves

~~~csharp
for (int i = 0; i < myDict.Count; i++)
    Console.WriteLine(myDict.Keys.ElementAt(i));
~~~

#### Exibir Elementos

~~~csharp
for(int i = 0; i < myDict.Count; i++)
    Console.WriteLine(myDict.Values.ElementAt(i));
~~~

~~~csharp
for (int i = 0; i < myDict.Count; i++)
    Console.WriteLine(myDict[myDict.Keys.ElementAt(i)]);        
~~~

## Verificar

#### Verificar se existe uma determinada chave

~~~csharp
myBool = myDict.Keys.Contains("txt");
~~~

#### Verificar se existe uma determinada chave

~~~csharp
myBool = myDict.Values.Contains("notepad");
~~~
