# .NET Aspire

## What is it?

.NET Aspire is an opinionated stack for building observable, production ready, distributed applications.​

## 3 ways to add a (new or existing) project to an existing Aspire solution

## Option 1: manually

1. add your project to the existing Aspire Solution (under the solution folder, my new project is called `MyApp.MyWebApi`)
  - make sure you DO NOT select this: `[ ] Enlist in .NET Aspire orchestration`
2. add project reference from your new project to AppHost
3. build Aspire Solution to run a magic Aspire code generator... (todo: what happens exactly?)
4. add this line to AppHost: `builder.AddProject<Projects.MyApp_MyWebApi>("myapp-mywebapi");`
  - because my new project is called `MyApp.MyWebApi`

## Option 2: during 'add project dialog'

1. add your project to the existing Aspire Solution (under the solution folder, my new project is called `MyApp.MyWebApi`)
  - make sure you select this: `[x] Enlist in .NET Aspire orchestration`

## Option 3: add existing project

1. add your project to the existing Aspire Solution (under the solution folder, my new project is called `MyApp.MyWebApi`)
  - make sure you DO NOT select this: `[ ] Enlist in .NET Aspire orchestration`
2. make sure your project is added to solution
3. right-click on project: Add: Add Aspire Orchestration Support

## Information

<https://learn.microsoft.com/en-us/dotnet/aspire/get-started/aspire-overview>
