# C# - Structs

- Structs são alocadas na pilha
- Structs não permitem herança.

## Exemplo

~~~csharp
// file Program.cs, dir: MyApplication
public struct Point {
  public int x, y;
  public Point(int x, int y) {
    this.x = x;
    this.y = y;
  }
}
~~~
