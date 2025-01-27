# C# - Structs

- Structs são alocadas na pilha
- Structs não permitem herança.

## Struct em um arquivo

~~~csharp
// Arquivo: Point.cs
namespace ConsoleApp
{
    public struct Point
    {
        public int x, y;
        public Point(int x, int y)
        {
            this.x = x;
            this.y = y;
        }
    }
}
~~~

~~~csharp
// Arquivo: Program.cs
using System;

namespace ConsoleApp
{
    class Program
    {
        static void Main(string[] args)
        {
            Point p = new Point(0, 0);
            Console.WriteLine(p.x);
        }
    }
}
~~~        
