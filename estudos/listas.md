# C# - Listas

> Namespace: System.Collections.Generic - ``` using System.Collections.Generic; ```

## Criação

~~~csharp
List<int> myIntList = new List<int>();
List<int> myIntList2 = new List<int>() { 10, 20, 30, 40 };
~~~

## Inclusão

~~~csharp
myIntList.Add(10);
~~~

## Remoção

### Primeiro Elemento

~~~csharp
myBool = myIntList.Remove(0);
~~~

## Acesso

### Um elemento

~~~csharp
myInt = myIntList[0];
~~~

### Todos Elementos - For

~~~csharp
for (int i = 0; i < myIntList.Count; i++)
    Console.WriteLine(myIntList[i]);
~~~

### Todos Elementos - Foreach

~~~csharp
foreach (int myInt in myIntList)
    Console.WriteLine(myInt);
~~~  

### Todos Elementos - Foreach        

~~~csharp
myIntList.ForEach(delegate (int myInt)
{
    Console.WriteLine(myInt);
});
~~~

## Propriedades

### Count

~~~csharp
myInt = myIntList.Count;
~~~


## Métodos

### Sort()

~~~csharp
myIntList.Sort();
~~~

## Exemplos

### Covertendo listas em arrays

~~~csharp
int[] meuArray = minhaLista.ToArray();
~~~
