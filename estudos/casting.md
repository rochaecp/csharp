# C# - Casting

## Casting Implícito

- Ocorre automaticamente.
- Converte um "tipo menor" em um "tipo maior":
    - char -> int 
    - int -> long
    - long -> float
    - float -> double
- Exemplo:

    ```csharp 
    int myInt = 10;
    double myDouble = 10D;
    myDouble = myInt;
    ```

## Casting Explícito

- Ocorre de modo manual.
- Converte um "tipo maior" em um "tipo menor":
    - double -> float 
    - float -> long 
    - long -> int -
    - int -> char
- Exemplo:

    ```csharp 
    int myInt = 10;
    double myDouble = 10D;
    myInt = (int)myDouble;
    ```

## Métodos de Conversão

- ToString:

    ```csharp
    myStr = myDouble.ToString();
    myStr = myInt.ToString();
    myStr = myLong.ToString();
    myStr = myBool.ToString();
    ```

- Convert:

    ```csharp 
    myString = Convert.ToString(myInt);
    myDouble = Convert.ToDouble(myStr);
    myInt = Convert.ToInt32(myDouble);
    myLong = Convert.ToInt64(myDouble);
    myBool = Convert.ToBoolean(myInt);
    ```
    
- Parse:

    ```csharp
    myDouble = Double.Parse(myString);
    myInt = Int32.Parse(myString);
    myLong = Int64.Parse(myString);    
    ```

- TryParse:

    ```csharp
    float notaAluno = 0F;
    string myString = Console.ReadLine();

    if (float.TryParse(myString, out float myFloat))
        notaAluno = myFloat;
    else
        throw new ArgumentException("O valor da nota deve ser float");
    ```
