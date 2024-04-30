# .NET - Command-Line Interface (CLI) 

## Diversos

~~~bash
dotnet --version
dotnet --help 
dotnet --info
dotnet new --help 
dotnet new console --help     
~~~

## Criar aplicação console
    
~~~bash
dotnet new console -n meuPrimeiroProjeto 
~~~

~~~bash
dotnet new console # usa nome do dir pai

dotnet restore 
~~~

## Compilar

~~~bash
dotnet build 
~~~

## Rodar    

~~~bash
dotnet run 
~~~

## Exemplos completos

## Criar uma aplicação de console

~~~bash
# jeito 1
mkdir nomeProjeto
dotnet new console

# jeito 2
dotnet new console -n nomeProjeto
~~~

## Criar uma solution com api

~~~bash
## criar uma solução
dotnet new sln

## criar um projeto de testes
dotnet new xunit -n minhaapi.tests -o tests/minhaapi.tests

## adicionar a api a solution
dotnet sln add src/minhaapi/
dotnet sln add tests/minhaapi.tests/

## adicionar referencia dos testes à api
dotnet add tests/minhaapi.tests/ reference src/minhaapi/
~~~

## Ler um arquivo .txt como pelo console

~~~bash
cat .\arquivo.txt | dotnet run # basta ter um Console.ReadLine(); no Program.cs para ler
~~~
