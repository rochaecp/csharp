# C# - Arquivos

> Namespace: System.IO - ``` using System.IO; ```

## Classe File (static)

- Métodos

    - WriteAllText()

        ~~~csharp
        File.WriteAllText("arquivo.txt", "Ola mundo");
        ~~~
        
    - AppendAllText()

        ~~~csharp
        File.AppendAllText("arquivo.txt", Environment.NewLine + "Linha 2");
        ~~~
    
    - ReadAllText()

        ~~~csharp
        myStr = File.ReadAllText("arquivo.txt");
        ~~~
        
    - Create()

        ~~~csharp
        File.Create("arquivo.txt");
        ~~~
        
    - Exists()

        ~~~csharp
        myBool = File.Exists("arquivo.txt");
        ~~~        
        
    - Copy()

        ~~~csharp
        File.Copy("arquivo.txt", "arquivoDestino.txt");
        ~~~         
       
    - Delete()

        ~~~csharp
        File.Delete("arquivo2.txt");
        ~~~  

        
## Classe FileStream (herda da classe abstrata Stream)

- Métodos

    - Construtor

        ~~~csharp
        FileStream myFileStream = new FileStream("arquivo.txt", FileMode.Open, FileAccess.Read, FileShare.Read);
        /*
         *  FileMode:
         *      Open, OpenOrCreate, Append, Create, CreateNew, Truncate
         *  FileAccess:
         *      Read, ReadWrite, Write
         *  FileShare:
         *      Inheritable, None, Read, ReadWrite, Write
         */        
        ~~~

    - WriteByte()

        ~~~csharp
        FileStream myFileStream = new FileStream("arquivo.dat", FileMode.OpenOrCreate, FileAccess.ReadWrite);
        myFileStream.WriteByte((byte)myInt);
        myFileStream.Close();
        ~~~
            
    - ReadByte()

        ~~~csharp
        FileStream myFileStream = new FileStream("arquivo.dat", FileMode.OpenOrCreate, FileAccess.ReadWrite);
        myInt = myFileStream.ReadByte();
        myFileStream.Close();        
        ~~~
        
- Atributos

    - Position

        ~~~csharp
        myFileStream.Position = 0;
        ~~~

- Exemplos

    - WriteByte() e ReadByte()

        ~~~csharp
        using System;
        using System.IO;

        namespace MyApplication
        {
            class Program
            {
                static void Main(string[] args)
                {
                    FileStream myFileStream = new FileStream("arquivo.dat", FileMode.OpenOrCreate, FileAccess.ReadWrite);

                    for(int i = 1; i <= 10; i++)
                        myFileStream.WriteByte((byte)i);

                    myFileStream.Position = 0;

                    for (int i = 1; i <= 10; i++)
                        Console.WriteLine(myFileStream.ReadByte());

                    myFileStream.Close();
                }
            }

        }        
        ~~~
        
## Classe StreamReader (herda das classes abstratas Stream e TextReader)

- Exemplos

    - ReadLine()

        ~~~csharp
        try
        {
            using (StreamReader myStreamReader = new StreamReader("arquivo.txt"))
            {
                string? myStr = string.Empty;

                while((myStr = myStreamReader.ReadLine()) != null)
                    Console.WriteLine(myStr);
            }
        } 
        catch(Exception ex)
        {
            Console.WriteLine("Arquivo não pode ser lido: {0}", ex.Message);
        }        
        ~~~

## Classe StreamWriter (herda da classe abstrata Stream)
