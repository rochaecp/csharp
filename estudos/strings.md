# C# - Strings 

> Namespace: System - ``` using System; ```

## Geral

### Criação

```csharp
string myStr = "";
```

### Concatenação 

```csharp 
myStr = myStr2 + "  " + myStr3;
myStr = string.Concat(myStr2, myStr3);
```

### Interpolação - versão 6 do C#

```csharp
myStr = $"Meu nome completo é: {myStr2} {myStr3}";
```

### Acessar caracteres - read only

```csharp
myChar = myStr[0];
```

### Caracteres de Escape

``` \' ``` 
``` \" ```
``` \n ```
``` \t ```
``` \b ```
``` \\ ```

## Propriedades

### Length

```csharp
myInt = myStr.Length;
```

## Métodos    

### IndexOf()

```csharp
myInt = myStr.IndexOf("M"); // -1 == not find
```

### Substring()

```csharp
myStr = myStr2.Substring(2); // do inicio ate posicao 2    
```

### ToUpper()

```csharp
myStr = myStr2.ToUpper();
```

### ToLower()

```csharp
myStr = myStr2.ToLower();
```

### IsNullOfEmpty()

```csharp
myBool = string.IsNullOrEmpty(myStr);
```

### Equals()

```csharp
myBool = myStr.Equals(myStr);
```

## Exemplos

### Obtendo ASCII a partir de char

```csharp
myChar = 'c'; 
myInt = (int)myChar;
```

### Convertendo string em array de char

```csharp
myStr = "This is String example.";
char[] myCharArray = myStr.ToCharArray();
```

### Modificando um caractere de uma string em um determinado índice

```csharp
myStr = "Mauricio";
char[] myCharArray = myStr.ToCharArray();
myCharArray[0] = 'X';
myStr = new string(myCharArray);
```

### Modificando um caractere de uma string em um determinado índice - usando StringBuilder

> Namespace: System.Text - ``` using System.Text; ```

```csharp
myStr = "Mauricio";
StringBuilder sb = new StringBuilder(myStr);
sb[0] = 'X';
myStr = sb.ToString();
```
