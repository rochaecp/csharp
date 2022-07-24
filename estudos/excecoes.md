# C# - Exceções

> Algumas classes de Exceção:
> - ArithmeticException
> - FileNotFoundException
> - IndexOutOfRangeException
> - TimeOutException

- Criação

    - Try .. Catch

        ~~~csharp
        try
        {
            Console.WriteLine(myIntArr[10]); // mas myIntArr.Length == 4
        }
        catch (Exception e)
        {
            Console.WriteLine(e.Message);
        }        
        ~~~
        
    - Try .. Catch (com mensagem personalizada)

        ~~~csharp
        try
        {
            Console.WriteLine(myIntArr[10]); // mas myIntArr.Length == 4
        }
        catch (Exception e)
        {
            Console.WriteLine("Índice do Array fora do limite.");
        }
        ~~~        
        
    - Try .. Catch .. Finaly

        ~~~csharp
        try
        {
            Console.WriteLine(myIntArr[10]); // mas myIntArr.Length == 4
        }
        catch (Exception e)
        {
            Console.WriteLine("Índice do Array fora do limite.");
        }
        finally
        {
            Console.WriteLine("Fim");
        }        
        ~~~
        
    - Throw (para exceção personalizada)

        ~~~csharp
        if (myInt < 18)
            throw new ArithmeticException("Acesso Negado");
        else
            Console.WriteLine("Ok");        
        ~~~      
