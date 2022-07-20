# C# - Classes e Objetos

- Os 4 pilares da POO são: Abstração, Encapsulamento, Herança e Polimorfismo.
- Nomes de classe iniciam com letra maiúscula.

## Exemplo

- Arquivo: Car.cs

~~~csharp
using System;
namespace MyApplication {
  class Car {
    public string color; // field (or attribute)
    public Car(string color) { // constructor
      this.color = color;
    }
    public Car() { // overloaded constructor 
      this.color = "blue";
    }
    public void printColor() { // method
      Console.WriteLine($"Color: {color}");
    }
  }
}
~~~

- Arquivo: Program.cs

~~~csharp
using System;
namespace MyApplication {
  class Program {
    static void Main(string[] args) {
      Car myObj = new Car("red");
      myObj.printColor();
    }
  }
}
~~~    
