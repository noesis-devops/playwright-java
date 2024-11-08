
Motivação:

Playwright é uma biblioteca de automação robusta e fiável que permite testar aplicações web em vários sistemas operativos e navegadores, com suporte a múltiplas linguagens de programação.
Este projeto de exemplo demonstra como utilizar o Playwright com Java para testar aplicações web em diferentes navegadores, como Chrome, Firefox e Safari além de requisições Rest.


## Índice


- [Pre-requisitos](#pre-requisitos)
- [Estrutura](#estrutura-do-projeto)
- [Configuração](#configuração)
- [Instalação](#instalação)
- [Como testar](#como-testar)
- [Relatório](#relatórios-allure)
- [CodeGen](#gerador-de-código-playwright-codegen)
- [TraceView](#trace-view)
- [ToDo](#todo)


## Pre-requisitos

- [JDK 22+](https://www.oracle.com/java/technologies/javase-downloads.html)
- [Maven](https://maven.apache.org/install.html)
- [IntelliJ ou outra IDE](https://www.jetbrains.com/idea/download/)
- [Allure Report](https://allurereport.org/docs/install/)
- [Playwright com Maven](https://playwright.dev/java/docs/intro)



## Estrutura do projeto
```
CoEx_Playwright/
├── pom.xml
├── src/
│   └── test/
│       ├── java/
│       │   ├── commons/
│       │   │   └── BaseTests/
│       │   │       └── BaseE2E.java
│       │   ├── e2e/
│       │   │   ├── page/
│       │   │   │   ├── LoginPage.java
│       │   │   │   └── ProductPage.java
│       │   │   └── tests/
│       │   │       └── [E2E test files]
│       │   ├── api/
│       │   │   ├── requests/
│       │   │   │   └── [Request files]
│       │   │   ├── requestData/
│       │   │   │   └── [Map parameters]
│       │   │   └── tests/
│       │   │       └── [API test files]
│       │   └── resources/
│       │       ├── browsers.json
│       │       ├── environment.json
│       │       └── [test resource files]
└── target/
    ├── screenshots/
    └── allure-results/
```



## Configuração

> Configure as variáveis de ambiente JAVA

> Configure as variáveis de ambiente MAVEN
> 

## Instalação

- Clone este repositório para a sua máquina local usando http ou ssh, por exemplo:

`git clone https://github.com/vargasroberto/CoEx_Playwright.git`

- Instale todas as dependências (pom.xml) mvn install e execute os testes:

`cd /your_project`

`mvn install`

Orientações:
- Utilize o arquivo pom.xml para baixar novas bibliotecas e manter o projeto em execução via terminal


## Como testar

Maven:
- Remover o ficheiro target

    `mvn clean`

- Compilar o projeto

    `mvn compile`

- Executar todos os testes

    `mvn test`

- Executar somente testes E2E

    `mvn clean test -PE2E`

- Executar somente testes de API

    `mvn clean test -PAPI`

## Relatórios Allure

`allure serve .\target\allure-results\ --report-name 'COEX - Playwright'`


## Gerarador de código Playwright (CodeGen)
- Sobre: https://playwright.dev/java/docs/codegen

`mvn exec:java -e -D exec.mainClass=com.microsoft.playwright.CLI -D exec.args="codegen http://10.255.0.150:32012"`


## Trace view
- Sobre: https://playwright.dev/java/docs/trace-viewer

`npx playwright show-trace target/trace_chromium.zip`




## TODO

```
[] Restringir screenshot as falhas
[] Limitar traceview ao cenário desejado
[] Session Storage com multi browser
[] Paralelismo E2E
[] Paralelismo CI
[] Implementar versão com BDD
[] Aprimorar tratamento de exceções
[] Runner class
[] Customizar assertions
[] Parametrizar ambientes com mvn
[] Jenkins
[] Docker
```


