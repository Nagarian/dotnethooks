# DotnetHooks

This project has only one goal, execute the following command: `git config core.hooksPath hooks` when the restore command is executed. In that's way you could enforce policy on you project when executing basic Git command.

For more information about git hooks please read [this article](https://git-scm.com/book/en/v2/Customizing-Git-Git-Hooks)

## Installation

In order to use this package you will only need to install this package from command line :

```sh
dotnet add package DotnetHooks
```

After this you can customize the path of the hooks folder by specifing `HooksPath` variable. By default it's set to `hooks` which means the folder will be relative to the `.git` folder. For example :
```
- .git
- hooks/
  - commit-msg
- src/
  - MyProject/
    - MyProject.csproj
  - MyProject.sln
```

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <TargetFramework>netstandard2.0</TargetFramework>
    <HooksPath>custom_hooks</HooksPath>
  </PropertyGroup>

  <ItemGroup>
    <PackageReference Include="DotnetHooks" Version="1.0.0" IncludeAssets="build" />
  </ItemGroup>

</Project>
```
