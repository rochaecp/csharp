# C# - Listas

- Namespace: System.Collections.Generic

## Tamanho

~~~csharp
myInt = myIntList.Count;
~~~

## Criar

~~~csharp
using System.Collections.Generic;
// ...
List<int> myIntList = new List<int>();
List<int> myIntList2 = new List<int>() { 10, 20, 30, 40 };
~~~

## Exibir 

~~~csharp
List<int> myIntList = new List<int>() { 10, 20, 30 };
myIntList.ForEach(x => Console.WriteLine(x));
~~~

## Incluir

~~~csharp
myIntList.Add(10);
~~~

## Remover

~~~csharp
myBool = myIntList.Remove(0); // Primeiro Elemento
~~~

## Indexar

~~~csharp
myInt = myIntList[0];
~~~

~~~csharp
for (int i = 0; i < myIntList.Count; i++)
    Console.WriteLine(myIntList[i]);
~~~

~~~csharp
foreach (int myInt in myIntList)
    Console.WriteLine(myInt);
~~~  

~~~csharp
myIntList.ForEach(delegate (int myInt)
{
    Console.WriteLine(myInt);
});
~~~

## Ordenar

#### Ordem Crescente

~~~csharp
myIntList.Sort();
~~~

#### Ordem Decrescente

~~~csharp
myIntList.Sort();
myIntList.Reverse();
~~~

## Coverter

#### Coverter listas em arrays

~~~csharp
int[] meuArray = minhaLista.ToArray();
~~~
