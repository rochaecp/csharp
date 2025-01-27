# C# - Break e Continue

## Break

~~~csharp
for (int i = 0; i < 10; i++)
{
    if (i == 4) 
        break; // sai do loop
Console.WriteLine(i);
}
~~~

## Continue 

~~~csharp
for (int i = 0; i < 10; i++) 
{
    if (i == 4)
        continue; // pula para próxima iteração
Console.WriteLine(i);
}
~~~

~~~csharp
int i = 0;
while (i < 10) 
{
    if (i == 4) 
    {
        i++;
        continue;
    }
    Console.WriteLine(i);
    i++;
}
~~~
