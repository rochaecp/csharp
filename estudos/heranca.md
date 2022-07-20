# C# - Herança

- Em C# não existe herança múltipla: uma classe só pode estender uma única classe por vez.
- Impedir herança com ```sealed ```

## Exemplo

- Arquivo: Vehicle.cs

~~~csharp
using System;
namespace MyApplication {
  class Vehicle { // Base class
    public string brand = "Ford";  // Vehicle field
    public void honk() {            // Vehicle method 
      Console.WriteLine("Tuut, tuut!");
    }
  }
}
~~~

- Arquivo: Car.cs

~~~csharp
using System;
namespace MyApplication {
  class Car : Vehicle {  // Derived class
    public string modelName = "Mustang";  // Car field
  }
}
~~~

- Arquivo: Program.cs

~~~csharp
using System;
namespace MyApplication {
  class Program {
    static void Main(string[] args) {
      // Create a myCar object
      Car myCar = new Car();

      // Call the honk() method (From the Vehicle class) on the myCar object
      myCar.honk();

      // Display the value of the brand field (from the Vehicle class) and the value of the modelName from the Car class
      Console.WriteLine(myCar.brand + " " + myCar.modelName);
    }
  }
}
~~~