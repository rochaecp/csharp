# C# - Break e Continue

- Break: sai do loop
- Continue: pula para próxima iteração

## Exemplo

~~~csharp
// Break
for (int i = 0; i < 10; i++) {
  if (i == 4)   {
    break;
  }
  Console.WriteLine(i);
}

// Continue
for (int i = 0; i < 10; i++) {
  if (i == 4) {
    continue;
  }
  Console.WriteLine(i);
}

// Continue
int i = 0;
while (i < 10) {
  if (i == 4) {
    i++;
    continue;
  }
  Console.WriteLine(i);
  i++;
}
~~~
