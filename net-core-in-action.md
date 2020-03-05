
# About

* [.NET Core in Action](https://www.manning.com/books/dotnet-core-in-action)
* by Dustin Metzgar
* published by Manning Press, 2018

# Thoughts

So far a nice, light read with a lot of helpful, practical info for developers haven't been following along with the rise of .NET Core.

# Take-Aways

* .NET Core promises improved containerization by bundling dependencies with apps instead of relying on system packages; helps dev and deployment environments to be consistent
* ASP.NET Core is lean and performant, breaks away from ASP.NET and the System.Web lib
* Microsoft is now focused on a faster release cadence
* The .NET Framework [is open-source](https://referencesource.microsoft.com/) but Microsoft is now accepting community contributions with .NET Core; much more of an open-source community effort
* .NET Framework libraries not ported to Core include WPF, XAML, Transactions, AppDomains, .NET remoting, ASMX, Linq to SQL, WCF services, WF

# Concepts

* Metapackage - set of packages (eg. Microsoft.AspNetCore.All) and / or a framework (eg. .NET Standard Library)
* Platform - general, vague term; what .NET Portability Analyzer calls everything
* Runtime Specification - includes OS and architecture

# Techs

* .NET CLI - command-line tooling, well supported for portability; deprecates DNVM, DNU, and DNX
* .NET Portability Analyzer tool warns about methods or members not available in some build targets
* @ - verbatim string operator
* AfterTargets - MSBuild node to run steps after a build target, eg. use Message to log build events
* Dockerfile EXPOSE command opens a port
* GAC - Global Assembly Cache, relied on by .NET Framework
* ItemGroup - MSBuild node that specifies a list of files, useful with CopyToOutputDirectory and/or EmbeddedResource
* Kestrel - web server built for ASP.NET Core, provided in the WebHost library
* LINQ - Language Integrated Query
* NuGet.config - can add packageSources for other package publishing feeds
* OmniSharp - open source project that provides .NET plug-ins for editors and IDEs
* project.json - old build file format, dropped in .NET Core 2.0
* PropertyGroup - MSBuild node that contains properties as key-value pairs, can have a Condition on it for configurable targets
* Roslyn - modular, extensible C# compiler
* RuntimeIdentifiers - csproj setting that specifies what platforms are supported
* TargetFramework / TFM - project setting, -f on cli; a flavour of .NET, either Framework or Core with a version number; netstandard target is widely supported by future versionsm targeting the lowest version number that your package works for will provide the best compatibility; netcoreapp is the common target for applications and web services; it specifies that an entry point is provided
* Xamarin / Mono - Xamarin acquisition by Microsoft in 2016 lead to .NET Core 1.0; Mono and .NET Framework apps were binary incompatible, the .NET Standard Library introduced a common foundation, now a unified ecosystem
* Xamarin Studio - IDE that has been rebranded as Visual Studio for Mac
* xcopy-deployable - when you can deploy an app with all of its dependencies just by recursively copying a directory; .NET Core apps have this property, .NET Framework apps do not; makes containerization easier
* Yeoman Generator - tool for creating app templates
dotnet run  # launch app

# Publications

* .NET Core weekly community [stand-up meeting](https://live.asp.net/)
* [TechEmpower benchmarks](https://www.techempower.com/benchmarks/)

# Code

`var stream = typeof(Program).GetTypeInfo().Assembly.GetManifestResourceStream("MyNamespace.MyFile.txt"); // method for reading embedded resource file at runtime, uses System.Reflection`

CLI stuff

* `docker run -it microsoft/dotnet:latest`
* `dotnet new console`  # create empty cli project
* `dotnet new web`  # create empty ASP.NET Core project
* `dotnet restore`  # install packages
* `dotnet publish -c Release`  # build app for release
* `dotnet pack -c Release`  # builds a nuget package (nupkg)
* `dotnet build -t:TestTarget`  # runs the given build target from cli
* `dotnet build -p:IsFx=true`  # specify a build property, for Conditions
