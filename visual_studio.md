# Visual Studio



## Local tool installation

When a user tries to install a .NET tool as a local tool on a folder that does not contain the manifest, we get an error `Cannot find a manifest file`.

```
> dotnet tool install --local Cake.Tool --version 0.38.4
Cannot find a manifest file.
For a list of locations searched, specify the "-d" option before the tool name.
If you intended to install a global tool, add `--global` to the command.
If you would like to create a manifest, use `dotnet new tool-manifest`, usually in the repo root directory.
```

However, if the user tries to update an existing local tool, `dotnet tool` is able to update the existing manifest:

```
dotnet new tool-manifest
dotnet tool install --local Cake.Tool --version 0.38.4
dotnet tool update --local Cake.Tool
```

```
Tool 'cake.tool' was successfully updated from version '0.38.4' to version '0.38.5' (manifest file /Users/augustoproiete/.config/dotnet-tools.json).
```