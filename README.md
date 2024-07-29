# .NET Aspire

## What is it?

.NET Aspire is an opinionated stack for building observable, production ready, distributed applications.​

## Install Aspire

https://learn.microsoft.com/en-us/dotnet/aspire/fundamentals/setup-tooling?tabs=visual-studio

dotnet workload list
dotnet workload update --include-previews -v d
dotnet workload install aspire
dotnet workload list

## Updates

https://learn.microsoft.com/en-us/dotnet/aspire/whats-new/preview-4
https://learn.microsoft.com/en-us/dotnet/aspire/whats-new/preview-5

## Aspire - First look

.NET Aspire: How it works behind the scenes? https://www.youtube.com/watch?v=9U3Mt02gkvE
dotnet workload install aspire
dotnet new aspire-starter --use-redis-cache --output AspireSample

## 3 ways to add a (new or existing) project to an existing Aspire solution

### Option 1: manually

1. add your project to the existing Aspire Solution (under the solution folder, my new project is called `MyApp.MyWebApi`)
  - make sure you DO NOT select this: `[ ] Enlist in .NET Aspire orchestration`
2. add project reference from your new project to AppHost
3. build Aspire Solution to run a magic Aspire code generator... (todo: what happens exactly?)
4. add this line to AppHost: `builder.AddProject<Projects.MyApp_MyWebApi>("myapp-mywebapi");`
  - because my new project is called `MyApp.MyWebApi` - may differ depending on your project name

### Option 2: during 'add project dialog'

1. add your project to the existing Aspire Solution (under the solution folder, my new project is called `MyApp.MyWebApi`)
  - make sure you select this: `[x] Enlist in .NET Aspire orchestration`
2. check this line which has been added to AppHost project: `builder.AddProject<Projects.MyApp_MyWebApi>("myapp-mywebapi");` (may differ depending on your project name)

### Option 3: add existing project

1. make sure, your existing project folder is under the existing Aspire Solution
2. make sure your project is added to solution
3. right-click on project: Add: Add Aspire Orchestration Support
4. check this line which has been added to AppHost project: `builder.AddProject<Projects.MyApp_MyWebApi>("myapp-mywebapi");` (may differ depending on your project name)

## Learn Aspire

### .NET User Group: April UG – Cloud Native Aspirations with .NET Aspire

https://www.youtube.com/live/udn6onn2Z28?feature=shared&t=1678 
- What is Apire: minute 28 - 51
- Workshop ab Minute 51
- Deployments: ab Minute 1h37

- App Host
- Resource
- Reference

Context - eShop App: https://github.com/dotnet-presentations/eshop-app-workshop (on preview 3)
https://github.com/wicksipedia/eshop-app-workshop (on preview 5)

1) create eShop.AppHost
2) config:
	- add database: aspire.hosting.progress "postgres"
	- add pgAdmin
	- create db + catalog "catalogDb"
	- add project: Catalog.Data.Manager "catalog-db-mgr"
	- AddServiceDefaults, MapDefaultEndpoints
	- nur 1 Telemetry call: 1:14:30
	- db volume, pw in user-secrets
	- add project: Catalog.Api "catalog-api"
	- add OpenApi...
	- add Web.App
	- url re-mapping for images

## Tools

### Aspir8

> Create install-scripts from existing Aspire Solution

<https://prom3theu5.github.io/aspirational-manifests/installing-as-a-global-tool.html>

### SteelToe 

for cf, aspire ? NEIN - ist Konkurrenz...
https://steeltoe.io/why-steeltoe
https://github.com/SteeltoeOSS/Steeltoe/issues/1244
- Steeltoe was originally started by Pivotal (cf)
- The launch of .NET Aspire, along with Microsoft.Extensions.ServiceDiscovery 
- mark Microsoft’s genuine entry into the domain Steeltoe has occupied all this time. 
- We are excited to contribute our own expertise to the Aspire project and continue moving towards even stronger and more approachable solutions 
- to cloud native constructs in Microsoft namespaces. 
- Steeltoe is not going away.
- David Fowler: https://github.com/dotnet/aspire/issues/893

## Information

- <https://learn.microsoft.com/en-us/dotnet/aspire/get-started/aspire-overview>
- todo
  - <https://learn.microsoft.com/en-us/dotnet/aspire/deployment/manifest-format>
  - <https://learn.microsoft.com/en-us/dotnet/aspire/fundamentals/networking-overview>
- Samples
  - <https://learn.microsoft.com/en-us/samples/browse/?expanded=dotnet&products=dotnet-aspire>
