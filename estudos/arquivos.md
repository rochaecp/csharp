# C# - Arquivos

> Namespace: System.IO - ``` System.IO ```

- Métodos

    - CreateText()

        ~~~csharp
        using (System.IO.TextWriter w = System.IO.File.CreateText("arquivo.txt")) 
        {
            w.WriteLine("Line 1");
            w.WriteLine("Line 2");
            w.WriteLine("Line 3");
        }
        ~~~

## Exemplos

- Escrita e Leitura

    - Arquivo: Program.cs

        ~~~csharp
        using System;
        using System.IO;

        namespace MyProject
        {
            class Program
            {
                static void Main(string[] args)
                {
                    string writeText = "Escrevendo e lendo em Arquivos em C#";  // Create a text string
                    File.WriteAllText("filename.txt", writeText);  // Create a file and write the contents of writeText to it

                    string readText = File.ReadAllText("filename.txt"); // Read the contents of the file
                    Console.WriteLine(readText); // Output the content
                }
            }
        }
        ~~~
