[Back to README](README.md)
# Develop & run your first .NET Core application on Linux
The .NET Core SDK ships with a command line interface for developing and running .NET Core apps. Typing `dotnet version` will confirm that .NET Core is installed and which version of the SDK you have.

> _Running dotnet for the first time will result in the local nuget package cache for the .NET Core Framework being populated_

The following command sequence will create a simple Hello World .NET Core app:
```
mkdir HelloLinux
cd HelloLinux
dotnet new console
```

The 'console' option tells 'dotnet new' to create a new Console application. Other project types e.g. Class Library, ASP.NET Core Web App etc. You can see the available project types by typing `dotnet new -all`

Listing the contents of the working folder (`ls` or `dir`) should result in two files being shown:
* Program.cs
* HelloLinux.csproj

If you view the Program.cs file (using the `cat` command) you will see that it contains familiar boiler plate code for a console application. You can also edit the code if you wish; `nano` is a good editor if you're not familiar with the editors available on Linux and want to get going quickly.

To compile the code, type the following:

```
dotnet restore
dotnet build
```
The first command ensures that all the packages associated with the .NET Core Framework and any other referenced in the csproj file are available in the package cache.

Assuming the above has compiled successfully, you can run the application by typing:

```
dotnet run
```

[Back to README](README.md)
