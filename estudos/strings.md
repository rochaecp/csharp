# C# - Strings 

## Criar

~~~csharp
string minhaString = "abacaxi";
~~~

## Concatenar 

~~~csharp 
minhaString = minhaString2 + " " + minhaString3;
minhaString = string.Concat(minhaString2, minhaString3);
~~~

## Interpolar

~~~csharp
minhaString = $"Meu nome completo é: {minhaString2} {minhaString3}"; // versão 6 do C#
~~~

## Indexar

~~~csharp
caractere = minhaString[0]; // readonly
~~~

## Caracteres de Escape

- \\' 
- \\"
- \\n
- \\t
- \\b
- \\\

## Tamanho

~~~csharp
int tamanho = minhaString.Length;
~~~

## Índice de caractere

~~~csharp
int indice = minhaString.IndexOf("a"); // -1 == não encontrou
~~~

## Fatia

~~~csharp
minhaString = minhaString2.Substring(2); // do inicio ate posicao 2    
~~~

## Converter Maiúsculo

~~~csharp
minhaString = minhaString2.ToUpper();
~~~

## Converter Minúsculo

~~~csharp
minhaString = minhaString2.ToLower();
~~~

## Verificar se string é vazia

~~~csharp
myBool = string.IsNullOrEmpty(minhaString);
~~~

## Verificar se duas são iguais

~~~csharp
myBool = minhaString.Equals(minhaString2);
~~~

## Obter o ASCII a partir de um char

~~~csharp
caractere = 'c'; 
int tamanho = (int)caractere;
~~~

## Converter string em array de char

~~~csharp
minhaString = "meu pastel é mais barato";
char[] caractereArray = minhaString.ToCharArray();
~~~

## Modificar um caractere de string em determinado índice

~~~csharp
minhaString = "abacaxi";
char[] caractereArray = minhaString.ToCharArray();
caractereArray[0] = 'O';
minhaString = new string(caractereArray);
~~~

## Modificar caractere de string em determinado índice

~~~csharp
minhaString = "Mauricio";
StringBuilder sb = new StringBuilder(minhaString); // Namespace: System.Text.  
sb[0] = 'X';
minhaString = sb.ToString();
~~~

## Converter string em array

~~~csharp
string minhaString = "Sejam bem vindos";
string [] minhaStringArray = minhaString.Split(' ');
foreach (string str in minhaStringArray)
    Console.WriteLine(str); // sejam
                            // bem
                            // vindos
~~~
