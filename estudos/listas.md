# C# - Listas

#### Criar

~~~csharp
List<int> myIntList = new List<int>(); // Namespace: System.Collections.Generic
List<int> myIntList2 = new List<int>() { 10, 20, 30, 40 };
~~~

#### Incluir

~~~csharp
myIntList.Add(10);
~~~

#### Remover

~~~csharp
myBool = myIntList.Remove(0); // Primeiro Elemento
~~~

#### Indexar

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

#### Count

~~~csharp
myInt = myIntList.Count;
~~~

#### Sort()

~~~csharp
myIntList.Sort();
~~~

#### Coverter listas em arrays

~~~csharp
int[] meuArray = minhaLista.ToArray();
~~~
