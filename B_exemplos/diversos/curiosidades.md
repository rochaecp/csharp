# Curiosidades

#### 0.1 + 0.2 != 0.3 ????

~~~csharp
double x = 0.1; 
double y = 0.2;
Console.WriteLine($"{x + y}"); // 0,30000000000000004 

// O problema se resolve usando o tipo decimal
decimal x2 = 0.1m; // m == indica ao compilador que o valor é decimal
decimal y2 = 0.2m;
Console.WriteLine($"{x2 + y2}"); //0,3
~~~