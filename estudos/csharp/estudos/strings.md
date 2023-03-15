# C# - Strings 

Namespace: System.  

## Criar uma string

```csharp
string myStr = "";
```

## Concatenar strings 

```csharp 
myStr = myStr2 + "  " + myStr3;
myStr = string.Concat(myStr2, myStr3);
```

## Interpolar 2 ou mais strings 

Utiliza a versão 6 do C#.    

```csharp
myStr = $"Meu nome completo é: {myStr2} {myStr3}";
```

## Acessar um caractere de uma string - readonly

```csharp
myChar = myStr[0];
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
myInt = myStr.Length;
```

## Obter o índice de um caractere de uma string

```csharp
myInt = myStr.IndexOf("M"); // -1 == not find
```

## Obter uma fatia da string

```csharp
myStr = myStr2.Substring(2); // do inicio ate posicao 2    
```

## Converter uma string em maiúsculo

```csharp
myStr = myStr2.ToUpper();
```

## Converter uma string em minúsculo

```csharp
myStr = myStr2.ToLower();
```

## Verificar se uma string é vazia

```csharp
myBool = string.IsNullOrEmpty(myStr);
```

## Verificar se duas strings são iguais

```csharp
myBool = myStr.Equals(myStr);
```

## Obter o ASCII a partir de um char

```csharp
myChar = 'c'; 
myInt = (int)myChar;
```

## Converter string em array de char

```csharp
myStr = "This is String example.";
char[] myCharArray = myStr.ToCharArray();
```

## Modificar um caractere de uma string em um determinado índice

```csharp
myStr = "Mauricio";
char[] myCharArray = myStr.ToCharArray();
myCharArray[0] = 'X';
myStr = new string(myCharArray);
```

## Modificar um caractere de uma string em um determinado índice - usando StringBuilder

Namespace: System.Text.  

```csharp
myStr = "Mauricio";
StringBuilder sb = new StringBuilder(myStr);
sb[0] = 'X';
myStr = sb.ToString();
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
