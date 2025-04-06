# C# - LINQ (Language-Integrated Query)

- Namespace: System.Linq
- Permite fazer consultas em qualquer coleção que implemente a interface IEnumerable<T> como por exemplo: arrays, listas, etc.

## Exibir

#### Exibir um array utilizando linq com foreach (converte em lista)

~~~csharp
int[] meuArray = { 5, 3, 8, 4, 1 };
meuArray.ToList().ForEach(e => Console.WriteLine(e));
~~~

## Converter

#### Converter um Array de strings em um Array de Inteiros

~~~csharp
string[] arrStr = new string[] {"3", "2", "1"}; // cria array de string
int[] arrInt = arrStr.Select(e => int.Parse(e)).ToArray(); // converte cada elem em int
foreach(int e in arrInt) // exibe
    Console.WriteLine(e * 10);
~~~

~~~csharp
string[] valores = new string[] { "2", "5", "3", "1", "4" };
var valoresInt = valores.Select(x => Int32.Parse(x));   
~~~

#### Converter um Array de Strings em uma Lista de Inteiros

~~~csharp
string[] ArrEntrada = new string[] { "3", "2", "1" };
List<int> lista = ArrEntrada.Select(e => int.Parse(e)).ToList(); // converte
lista.ForEach(e => Console.WriteLine(e)); // exibe
~~~

## Ordenar

#### Ordenar uma Lista

~~~csharp
List<int> lista = new List<int> {3, 2, 1};
List<int> listaOrdenada = lista.OrderBy(e => e).ToList();
listaOrdenada.ForEach(e => Console.WriteLine(e));
~~~

#### Converter e ordenar

~~~csharp
string[] valores = new string[] { "2", "5", "3", "1", "4" };
var valoresIntOrdenados = valores.Select(x => Int32.Parse(x)).OrderBy(i => i); // lista
int [] result = numerosStr.Select(x => Int32.Parse(x)).OrderBy(i => i).ToArray(); // array
~~~       

## Fatiar

#### Obter todos elementos que satisfazem a uma condição

~~~csharp
int[] meuArray = new int[] {1, 2, -15, 72, 6, 5, 4, 3, 2, 1};
int[] meuArray2 = meuArray.Where(e => e > 3).ToArray(); // só elementos maiores que 3
foreach(int e in meuArray2)
    Console.WriteLine(e);
~~~

#### Selecionar apenas elementos não nulos

~~~csharp
string[] nomesComNulos = new string[] { "Maurício", null, "Maria", "", "Joana", string.Empty };
var nomes = nomesComNulos.Where(x => !string.IsNullOrEmpty(x));
~~~     

## Contar

#### Contar o total de elementos com uma determinada condição

~~~csharp
bool[] resultados = new bool[] { true, false, false, true, true };
int totalTrue = resultados.Count(x => x == true);        
~~~

~~~csharp
int[] notas = { 10, 9, 10, 5, 3 };
int totAcimaMedia = notas.Count(x => x >= 6);  
~~~    

## Outros

#### Tornar todos elementos maiúsculos

~~~csharp
string[] nomes = new string[] { "Maurício", "Maria", "Joana" };
var resultado = nomes.Select(x => x.ToUpper());        
~~~

#### Encadear Operadores de Consulta

~~~csharp
int[] numeros = new int[] { 10, 20, 30, 40, 50, 60 };

var result = from numero in numeros
            where numero > 20
            select numero;        
~~~

~~~csharp
string[] nomes = { "Geise", "Maurício", "Maria", "Gaby", "Jennifer" };

IEnumerable<string> result = nomes
    .Where(x => x.Contains('a'))
    .OrderBy(x => x.Length)
    .Select(x => x.ToUpper());    
~~~
