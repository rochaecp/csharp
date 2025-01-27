# C# - Classe Random

## Gerar 10 números inteiros aleatórios de 0 a 9

~~~csharp
Random random = new Random();
int numeroAleatorio = random.Next(10); // inteiro de 0 a 9
~~~
    
## Gerar 10 números inteiros aleatórios de 1 a 10

~~~csharp
Random random = new Random();
int numeroAleatorio = random.Next(1, 11); // inteiro de 1 a 10
~~~
