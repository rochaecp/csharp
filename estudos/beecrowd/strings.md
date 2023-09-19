# C# - Soluções Beecrowd

## 1024 - Criptografia

~~~csharp
using System.Linq;
using System;
using System.Globalization;
using System.Collections.Generic;

namespace TreinosBeecrowd
{
    enum TabelaAscii : int
    {
        InicioMaiusculo = 65,
        FimMaiusculo = 90,
        InicioMinusculo = 97,
        FimMinusculo = 122
    }
    class Result
    {
        public static string criptografa(string s)
        {
            char[] arrayStr = s.ToCharArray();
            int numChar;
            string strCript = "";

            for (int i = 0; i < arrayStr.Length; i++)
            {
                numChar = (int)arrayStr[i];
                if (ehCaractere(numChar))
                {
                    numChar += 3;
                    arrayStr[i] = (char)numChar;
                }
            }

            Array.Reverse(arrayStr);

            for (int i = (arrayStr.Length) / 2; i < arrayStr.Length; i++)
            {
                numChar = (int)arrayStr[i];
                numChar -= 1;
                arrayStr[i] = (char)numChar;

            }

            strCript = (new string(arrayStr));

            return strCript;
        }

        public static bool ehCaractere(int numAsciiChar)
        {
            if ((numAsciiChar >= (int)TabelaAscii.InicioMaiusculo && numAsciiChar <= (int)TabelaAscii.FimMaiusculo) || (numAsciiChar >= (int)TabelaAscii.InicioMinusculo && numAsciiChar <= (int)TabelaAscii.FimMinusculo))
                return true;
            else
                return false;
        }
    }
    class Program
    {
        static void Main(string[] args)
        {
            CultureInfo.CurrentCulture = new CultureInfo("en-US");
            int num_entradas = 0;
            string str_lida = "";

            num_entradas = int.Parse(Console.ReadLine());

            for (int i = 0; i < num_entradas; i++)
            {
                str_lida = Console.ReadLine();
                Console.WriteLine(Result.criptografa(str_lida));
            }
        }
    }
}
~~~