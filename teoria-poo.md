# C# - POO 

- Os 4 pilares da POO são: Abstração, Encapsulamento, Herança e Polimorfismo.

- **Classes**
    - Nomes de classe iniciam com letra maiúscula.

- **Objetos**

- **Membros de uma classe**

- **Propriedades de uma classe**

- **Encapsulamento**
    - Restringir o acesso aos membros da classe.

- **Modificadores de acesso**
    - public:     atributo/metodo visivel em qualquer classe  
    - private:    atributo/metodo visivel apenas na classe onde foi criado  
    - protected:  atributo/metodo visivel em classes onde são criados ou herdados

- **Métodos**
    - Métodos são blocos de códigos que só são executados quando chamados.

- **Métodos Construtores**
    - São métodos que são executados assim que instanciamos um objeto de uma classe.
    - São sempre public.
    - Possuem sempre o nome da classe.

- **Métodos Getters e Setters**
    - São utilizados para obtermos e modificarmos atributos privados.
    - São sempre public.
    - Pode-se utilizar um ou outro ou ambos.

- **Comando this**
    - Utilizado para referenciar atributos de uma classe. Ex.: this.nomeAtributo = 10;
    - Em C# utilizamos o caractere '_' antes do nome do atributo.

- **Sobrecarga de Métodos**

- **Herança**
    - Em C# não existe herança múltipla: uma classe só pode extender uma única classe por vez.

- **Polimorfismo**

- **Sobrescrita de Métodos**
    - Em C# para um método poder ser sobrescrito ele precisa da palavra reservada *virtual*.
    - Em C# para um método poder sobrescrever outro precisamos adicionar a palavra reservada *override*.

- **Atributos Estáticos**
    - Podemos ter acesso a atributos Static sem a necessidade de instanciar um objeto a partir de uma classe.

- **Métodos Estáticos**
    - Podemos ter acesso a métodos Static sem a necessidade de instanciar um objeto a partir de uma classe.

- **Abstração**
    - **Classes abstratas**
        - Classe que pode conter métodos obrigatórios para todas as classes que a herdarem.
        - Métodos obrigatórios podem ser públicos ou protegidos.
        - Podem conter também métodos convencionais (não obrigatórios) para que as classes que a herdam possam utilizar.
        - Não se pode instanciar um objeto a partir de uma classe abstrata.
        - Garante uma estrutura pré moldada de métodos que devem ser implementados.
        - É uma forma de criar um padrão para os projetos.
        - Cada classe pode herdar apenas de uma classe abstrata.
    - **Métodos abstratos**
        - É um método obrigatório de uma classe abstrata.
        - Precisa obrigatóriamente ser sobrescrito na classe que herdar da classe abstrata que o contém.

- **Interfaces**
    - Utilizada para criarmos exclusivamente métodos obrigatórios.
    - Uma classe pode implementar várias interfaces.
    - Os métodos da interface não possuem implementação na interface.
    - A implementação dos métodos da interface fica na classe que implementa a mesma.
    - No C# um método criado na interface é por padrão público e abstrato.
    - No C# por convenção iniciamos o nome de interfaces com a letra 'I', ex.: IProductService.

- **Interfaces Múltiplas**

- **Enums**

- **Exceções**

## Classes

- OOP helps to keep the C# code DRY "Don't Repeat Yourself", and makes the code easier to maintain, modify and debug
- The "Don't Repeat Yourself" (DRY) principle is about reducing the repetition of code.
- Class: Fruit, Objects: Apple, Banana, Mango
- So, a class is a template for objects, and an object is an instance of a class.
- A Class is like an object constructor, or a "blueprint" for creating objects.
- When a variable is declared directly in a class, it is often referred to as a field (or attribute).

> It is not required, but it is a good practice to start with an uppercase first letter when naming classes.
> Also, it is common that the name of the C# file and the class matches, as it makes our code organized. 
> However it is not required (like in Java).

- **Class Members**
  - Fields and methods inside classes are often referred to as "Class Members".
  - Methods normally belongs to a class, and they define how an object of a class behaves.

- **Constructors**
  - A constructor is a special method that is used to initialize objects. 
  - The advantage of a constructor, is that it is called when an object of a class is created. 
  - It can be used to set initial values for fields.
  - Note that the constructor name must match the class name, and it cannot have a return type (like void or int). 
  - Also note that the constructor is called when the object is created.
  - All classes have constructors by default: if you do not create a class constructor yourself, C# creates one for you.
  - Just like other methods, constructors can be overloaded by using different numbers of parameters.

~~~csharp
// file Car.cs, dir: MyApplication
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

// file Program.cs, dir: MyApplication
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

## Access Modifiers

- **public**: The code is accessible for all classes.
- **private**: The code is only accessible within the same class.
- **protected**: The code is accessible within the same class, or in a class that is inherited from that class. 
- **internal**: The code is only accessible within its own assembly, but not from another assembly. 
- **protected internal**: The code is only accessible within the same class or in a class that is inherited from that class or in its own assembly.

> There's also two combinations: protected internal and private protected.
> By default, all members of a class are private if you don't specify an access modifier

## Properties and Encapsulation

- The meaning of Encapsulation, is to make sure that "sensitive" data is hidden from users. To achieve this, you must:
  - declare fields/variables as private
  - provide public get and set methods, through properties, to access and update the value of a private field
- A property is like a combination of a variable and a method, and it has two methods: a get and a set method.
- The Name property is associated with the name field. It is a good practice to use the same name for both the property and the private field, but with an uppercase first letter.
- C# also provides a way to use short-hand / automatic properties, where you do not have to define the field for the property, and you only have to write get; and set; inside the property.
- Fields can be made read-only (if you only use the get method), or write-only (if you only use the set method)

~~~csharp
// file Person.cs, dir: MyApplication
using System;
namespace MyApplication {
  class Person {
    private string name;  // field
    public string Name {    // property
      get { return name; }
      set { name = value; }
      // or short hand: get; set; 
    }
  }
}

// file Program.cs, dir: MyApplication
using System;
namespace MyApplication {
  class Program {
    static void Main(string[] args) {
      Person myObj = new Person();
      myObj.Name = "Mauricio";
      Console.WriteLine(myObj.Name);
    }
  }
}
~~~

## Inheritance

- Inheritance lets us inherit fields and methods from another class. 
- We group the "inheritance concept" into two categories:
  - Derived Class (child) - the class that inherits from another class
  - Base Class (parent) - the class being inherited from
- To inherit from a class, use the : symbol.
- It is useful for code reusability: reuse fields and methods of an existing class when you create a new class.
- If you don't want other classes to inherit from a class, use the **sealed** keyword.

~~~csharp
// file Vehicle.cs, dir MyApplication
using System;
namespace MyApplication {
  class Vehicle { // Base class
    public string brand = "Ford";  // Vehicle field
    public void honk() {            // Vehicle method 
      Console.WriteLine("Tuut, tuut!");
    }
  }
}

// file Car.cs, dir MyApplication
using System;
namespace MyApplication {
  class Car : Vehicle {  // Derived class
    public string modelName = "Mustang";  // Car field
  }
}

// file Program.cs, dir MyApplication
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

// Another Examples

// If you don't want other classes to inherit from a class, use the sealed keyword.
sealed class Vehicle {
  ...
}
~~~

## Polymorphism

- Polymorphism means "many forms", and it occurs when we have many classes that are related to each other by inheritance.
- Polymorphism uses those methods to perform different tasks. This allows us to perform a single action in different ways.
- C# provides an option to override the base class method, by adding the **virtual keyword** to the method inside the base class, and by using the override keyword for each derived class methods.

~~~csharp
// file Program.cs, dir MyApplication
using System;
namespace MyApplication {
  class Animal { // Base class (parent) 
    public virtual void animalSound() { // note virtual keyword
      Console.WriteLine("The animal makes a sound");
    }
  }

  class Pig : Animal { // Derived class (child) 
    public override void animalSound() {
      Console.WriteLine("The pig says: wee wee");
    }
  }

  class Dog : Animal { // Derived class (child) 
    public override void animalSound() {
      Console.WriteLine("The dog says: bow wow");
    }
  }

  class Program {
    static void Main(string[] args) {
      Animal myAnimal = new Animal(); // Create a Animal object
      Animal myPig = new Pig();  // Create a Pig object
      Animal myDog = new Dog();  // Create a Dog object

      myAnimal.animalSound();
      myPig.animalSound();
      myDog.animalSound();
    }
  }
}
~~~

## Abstraction

- Data abstraction is the process of hiding certain details and showing only essential information to the user.
- **Abstract class**: is a restricted class that cannot be used to create objects (to access it, it must be inherited from another class).
- **Abstract method**: can only be used in an abstract class, and it does not have a body. The body is provided by the derived class (inherited from).
- An abstract class can have both abstract and regular methods.

~~~csharp
// file Program.cs, dir MyApplication
using System;
namespace MyApplication {
  // Abstract class
  abstract class Animal {
    // Abstract method (does not have a body)
    public abstract void animalSound();
    // Regular method
    public void sleep() {
      Console.WriteLine("Zzz");
    }
  }

  // Derived class (inherit from Animal)
  class Pig : Animal {
    public override void animalSound() {
      // The body of animalSound() is provided here
      Console.WriteLine("The pig says: wee wee");
    }
  }

  class Program {
    static void Main(string[] args) {
      Pig myPig = new Pig();  // Create a Pig object
      myPig.animalSound();
      myPig.sleep();
    }
  }
}
~~~

## Interfaces

- Another way to achieve abstraction in C#, is with interfaces.
- An interface is a completely "abstract class", which can only contain abstract methods and properties (with empty bodies).
- It is considered good practice to start with the letter "I" at the beginning of an interface, as it makes it easier for yourself and others to remember that it is an interface and not a class.
- By default, members of an interface are abstract and public.
- Interfaces can contain properties and methods, but not fields.
- To access the interface methods, the interface must be "implemented" (kinda like inherited) by another class. 
- The body of the interface method is provided by the "implement" class. Note that you do not have to use the override keyword when implementing an interface.
- Like abstract classes, interfaces cannot be used to create objects.
- Interface methods do not have a body - the body is provided by the "implement" class.
- Interface members are by default **abstract** and **public**.
- An interface cannot contain a constructor (as it cannot be used to create objects).
- C# does not support "multiple inheritance" (a class can only inherit from one base class).
- However, it can be achieved with interfaces, because the class can implement multiple interfaces.

~~~csharp
// file Program.cs, dir MyApplication
using System;
namespace MyApplication {
  // Interface
  interface IAnimal {
    void animalSound(); // interface method (does not have a body)
  }

  // Pig "implements" the IAnimal interface
  class Pig : IAnimal {
    public void animalSound() {
      // The body of animalSound() is provided here
      Console.WriteLine("The pig says: wee wee");
    }
  }

  class Program {
    static void Main(string[] args) {
      Pig myPig = new Pig();  // Create a Pig object
      myPig.animalSound();
    }
  }
}
~~~

### Multiple Interfaces 

~~~csharp
// file Program.cs, dir MyApplication
using System;

namespace MyApplication {
  interface IFirstInterface {
    void myMethod(); // interface method
  }

  interface ISecondInterface {
    void myOtherMethod(); // interface method
  }

  // Implement multiple interfaces
  class DemoClass : IFirstInterface, ISecondInterface {
    public void myMethod() {
      Console.WriteLine("Some text..");
    }
    public void myOtherMethod() {
      Console.WriteLine("Some other text...");
    }
  }

  class Program {
    static void Main(string[] args) {
      DemoClass myObj = new DemoClass();
      myObj.myMethod();
      myObj.myOtherMethod();
    }
  }
}
~~~
