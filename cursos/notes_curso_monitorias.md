# Desenvolvimento de Monitorias com Serviços Windows utilizando .NET 8 e C# 12

## Módulo 1: Introdução ao Desenvolvimento de Monitorias com .NET e C#

- **Objetivo**: Entender os conceitos básicos e a arquitetura de monitorias em serviços Windows.
    - Visão geral do .NET 8 e C# 12.
    - Tipos de monitorias: bancos de dados, web services, sistemas internos.
    - Conceitos de serviços Windows e Background Services.
    - Configuração do ambiente de desenvolvimento no Visual Studio.

### **Aula 1.1**: Visão Geral do .NET 8 e C# 12

- .NET 8 
    - é uma platafaorma de desenvolvimento que unifica .NET Core, .NET Framework e Xamarin
    - é cross-platform

### **Aula 1.2**: Conceitos Básicos de Monitorias

- Monitorias
    - são processos contínuos de observação e análise de sistemas, bancos de dados, serviços web, e outros serviços tecnológicos para garantir o seu bom funcionamento.
- Tipos de Monitorias
    - Monitorias de Bancos de Dados    
    - Monitoria de Web Services e APIs
    - ...
- Os serviços Windows são ideais para a implementação de monitorias, pois rodam continuamente em segundo plano sem intervenção do usuário.
- Utilizam Background Services do .NET Core, que oferecem um ambiente robusto e eficiente para executar tarefas de monitoria.    

### **Aula 1.3**: Serviços Windows e Background Services

- Serviços Windows
    - São aplicações que executam em segundo plano no sistema operacional Windows.
    - São projetados para iniciar automaticamente com o sistema ou manualmente conforme a necessidade e funcionam sem interação direta do usuário.
    - Utilizados para executar tarefas contínuas, como monitoramento, backup, gerenciamento de redes, e outros processos que exigem operação constante.
    - Suportam início, pausa, e término controlados pelo sistema ou administrador.
- Vantagens dos Serviços Windows
    - Serviços Windows garantem que o processo de monitoria esteja sempre rodando, mesmo após reinícios do sistema.
- Background Services
    - São classes em .NET Core (e .NET 8) que permitem a criação de tarefas contínuas que rodam em segundo plano dentro de uma aplicação .NET.
    - Eles são comumente usados para implementar lógica de monitoria.
    - Implementação com IHostedService: Interface que define os métodos StartAsync e StopAsync, que controlam o ciclo de vida do serviço.        
    - Worker Service: Um tipo de projeto em .NET Core que configura automaticamente um Background Service, fornecendo uma estrutura pronta para desenvolvimento.

### **Aula 1.4**: Configuração do Ambiente de Desenvolvimento no Visual Studio    

- Verificando a versão do C#
    - A versão do C# usada é determinada pelo SDK do .NET instalado. No Visual Studio, você pode verificar e ajustar a versão do C# nas configurações do projeto.
- Configurando o Serviço para Rodar no Windows
    - Para transformar o Worker Service em um Serviço Windows real, adicione o pacote Microsoft.Extensions.Hosting.WindowsServices e ajuste o código no Program.cs para integrar com o Windows Service Host.    
- Instalação do Serviço:
    - Utilize sc.exe ou PowerShell para instalar e gerenciar o serviço no Windows, permitindo que ele inicie automaticamente.

## Módulo 2: Criação de Serviços Windows com .NET 8

- **Objetivo**: Configurar e desenvolver um serviço Windows básico em .NET 8.
    - Estrutura de um Worker Service em .NET 8.
    - Configurando o projeto: criação, setup e execução no Visual Studio.
    - Ciclo de vida de um serviço Windows: start, stop, e execução contínua.
    - Configurando o Logger para monitoramento de execução.

### **Aula 2.1**: Estrutura de um Worker Service em .NET 8

### **Aula 2.2**: Configuração do Projeto: Criação, Setup e Execução no Visual Studio

### **Aula 2.3**: Ciclo de Vida de um Serviço Windows: Start, Stop e Execução Contínua

### **Aula 2.4**: Configurando o Logger para Monitoramento de Execução    
