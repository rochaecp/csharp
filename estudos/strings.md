# C# - Strings 

Namespace: System.  

## Criar uma string

```csharp
string minhaString = "abacaxi";
```

## Concatenar strings 

```csharp 
minhaString = minhaString2 + " " + minhaString3;
minhaString = string.Concat(minhaString2, minhaString3);
```

## Interpolar 2 ou mais strings 

Utiliza a versão 6 do C#.    

```csharp
minhaString = $"Meu nome completo é: {minhaString2} {minhaString3}";
```

## Acessar um caractere de uma string - readonly

```csharp
caractere = minhaString[0];
```

## Caracteres de Escape

``` \' ``` 
``` \" ```
``` \n ```
``` \t ```
``` \b ```
``` \\ ```

## Obter o tamanho de uma string

```csharp
int tamanho = minhaString.Length;
```

## Obter o índice de um caractere de uma string

```csharp
int indice = minhaString.IndexOf("a"); // -1 == não encontrou
```

## Obter uma fatia da string

```csharp
minhaString = minhaString2.Substring(2); // do inicio ate posicao 2    
```

## Converter uma string em maiúsculo

```csharp
minhaString = minhaString2.ToUpper();
```

## Converter uma string em minúsculo

```csharp
minhaString = minhaString2.ToLower();
```

## Verificar se uma string é vazia

```csharp
myBool = string.IsNullOrEmpty(minhaString);
```

## Verificar se duas strings são iguais

```csharp
myBool = minhaString.Equals(minhaString2);
```

## Obter o ASCII a partir de um char

```csharp
caractere = 'c'; 
int tamanho = (int)caractere;
```

## Converter string em array de char

```csharp
minhaString = "meu pastel é mais barato";
char[] caractereArray = minhaString.ToCharArray();
```

## Modificar um caractere de uma string em um determinado índice

```csharp
minhaString = "abacaxi";
char[] caractereArray = minhaString.ToCharArray();
caractereArray[0] = 'O';
minhaString = new string(caractereArray);
```

## Modificar um caractere de uma string em um determinado índice - usando StringBuilder

Namespace: System.Text.  

```csharp
minhaString = "Mauricio";
StringBuilder sb = new StringBuilder(minhaString);
sb[0] = 'X';
minhaString = sb.ToString();
```

## Converter uma string em um array

~~~csharp
string minhaString = "Sejam bem vindos";
string [] minhaStringArray = minhaString.Split(' ');
foreach (string str in minhaStringArray)
    Console.WriteLine(str); // sejam
                            // bem
                            // vindos
~~~
