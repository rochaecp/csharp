# C# - Arquivos

Métodos do namespace System.IO:
- AppendText() - Appends text at the end of an existing file
- Copy() - Copies a file
- Create() - Creates or overwrites a file
- Delete() - Deletes a file
- Exists() - Tests whether the file exists
- ReadAllText() - Reads the contents of a file
- Replace() - Replaces the contents of a file with the contents of another file
- WriteAllText() - Creates a new file and writes the contents to it. If the file already exists, it will be - overwritten.

## Exemplo

~~~csharp
using (System.IO.TextWriter w = System.IO.File.CreateText("test.txt")) {
  w.WriteLine("Line 1");
  w.WriteLine("Line 2");
  w.WriteLine("Line 3");
}
~~~

## Exemplo

~~~csharp
using System;
using System.IO;

namespace Arquivos
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
