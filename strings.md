# C# - Strings

## Caracteres de Escape

``` \' ``` 
``` \" ```
``` \n ```
``` \t ```
``` \b ```
``` \\ ```

## Concatenação de strings

``` + ```

## Exemplo

~~~csharp
using System;
using System.Text;

namespace Strings
{
    class Program
    {
        static void Main(string[] args)
        {
            string nome = "";
            string primeiroNome = "Mauricio";
            string ultimoNome = "Rocha";
            string frase = "";
            string texto = "";
            bool myBool = false;

            // Array de Strings
            string[] cores = { "Azul", "Amarelo", "Vermelho" };

            // Concatenacao de Strings
            nome = primeiroNome + ultimoNome;

            // Concatenacao de Strings 
            nome = string.Concat(primeiroNome, ultimoNome);

            // Interpolação de Strings C# version 6
            frase = $"Meu nome completo é: {primeiroNome} {ultimoNome}";

            // Accessando Strings - read only
            char primeiraLetra = nome[0]; // M

            // Metodos
            nome = string.Concat(primeiroNome, ultimoNome);
            int myLength = nome.Length;
            int myIndex = nome.IndexOf("M"); // -1 == not find
            texto = nome.Substring(2); // do inicio ate posicao 2
            texto = nome.ToUpper();
            texto = nome.ToLower();
            myBool = string.IsNullOrEmpty(nome);
            myBool = nome.Equals("myText");

            // Obtendo ASCII a partir de char
            char myChar = 'c'; // create char c
            int myAscii = (int)myChar;

            // Convertendo string em array de char
            String myString = "This is String example.";
            char[] myCharArray = myString.ToCharArray();

            // Modificando um caractere de uma string em um determinado índice
            string myStringSetChar = "Mauricio";
            char[] myCharArray2 = myStringSetChar.ToCharArray();
            myCharArray2[0] = 'X';
            myStringSetChar = new string(myCharArray2);

            // Modificando um caractere de uma string em um determinado índice - usando StringBuilder
            string myStringSetCharSB = "Mauricio";
            StringBuilder sb = new StringBuilder(myStringSetCharSB);
            sb[0] = 'X';
            myStringSetCharSB = sb.ToString();
        }
    }
}
~~~
