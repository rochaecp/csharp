# .NET - Command-Line Interface (CLI) 

#### Diversos

~~~bash
dotnet --version
dotnet --help 
dotnet --info
dotnet new --help 
dotnet new console --help     
~~~

- Criar aplicação console
    ~~~bash
    dotnet new console -n meuPrimeiroProjeto 
    ~~~

    ~~~bash
    dotnet new console # usa nome do dir pai

    dotnet restore 
    ~~~

- Compilar
    ~~~bash
    dotnet build 
    ~~~

- Rodar    
    ~~~bash
    dotnet run 
    ~~~

## Exemplos completos

- Criando aplicação de console

~~~bash
# jeito 1
mkdir nomeProjeto
dotnet new console

# jeito 2
dotnet new console -n nomeProjeto
~~~

- Criando solution com api

~~~bash
## criando uma solução
dotnet new sln

## criando um projeto de testes
dotnet new xunit -n minhaapi.tests -o tests/minhaapi.tests

## adiciona a api a solution
dotnet sln add src/minhaapi/
dotnet sln add tests/minhaapi.tests/

## adiciona referencia dos testes à api
dotnet add tests/minhaapi.tests/ reference src/minhaapi/
~~~
