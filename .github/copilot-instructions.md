# Copilot Instructions for PlayniteExtensionsCollection

This repository contains a collection of extensions for [Playnite](https://github.com/JosefNemec/Playnite), a video game library manager. The extensions are primarily written in C# and some PowerShell scripts.

## Project Structure

- `source/Common/` - Shared common libraries used across multiple extensions
- `source/Generic/` - Generic plugins that work with any library
- `source/Library/` - Library-specific plugins for different game platforms
- `source/Metadata/` - Metadata provider plugins
- `source/GenericTests/` - Tests for generic plugins
- `source/MetadataTests/` - Tests for metadata plugins
- `source/PlayniteExtensions.sln` - Main Visual Studio solution file

## Code Formatting Standards

### C# Code Style

1. **Indentation**: Use **4 spaces** for indentation. **Tabs are not allowed**.

2. **Naming Conventions**:
   - Public properties: Use **PascalCase**, e.g., `MyProperty`
   - Private fields: Must begin with an **underscore** and use **camelCase**, e.g., `_myPrivateField`
   - Local variables: Use `var` keyword and **camelCase**, e.g., `var myVariable = "text";`

3. **Control Flow Statements**:
   - Always use curly braces `{}` for code blocks after control statements (`if`, `for`, `foreach`, `while`, etc.)
   - Example:
     ```csharp
     if (condition)
     {
         DoSomething();
     }
     ```

### PowerShell Code Style

1. **Function Names**: Use approved verbs from [Microsoft's approved verb list](https://docs.microsoft.com/en-us/powershell/scripting/developer/cmdlet/approved-verbs-for-windows-powershell-commands?view=powershell-5.1)

2. **Cmdlets**: Always use the full cmdlet name without abbreviations
   - ✅ Correct: `Get-Service | Where-Object {$_.Status -eq "Stopped"}`
   - ❌ Incorrect: `Get-Service | Where {$_.Status -eq "Stopped"}`

## Localization Requirements

If your code includes new strings (e.g., text displayed in the UI), ensure they are properly implemented as localization strings within the localization dictionary. This repository supports translations through [Crowdin](https://crowdin.com/project/darklinkpower-playnite-extensi).

## Development Guidelines

1. **Extension Development**: Extensions should follow the Playnite SDK patterns and guidelines
2. **Dependencies**: Extensions in `source/Generic/`, `source/Library/`, and `source/Metadata/` may depend on libraries in `source/Common/`
3. **Testing**: Add appropriate tests to `GenericTests` or `MetadataTests` directories when modifying extension logic
4. **Assembly Versioning**: Update assembly version numbers in `Properties/AssemblyInfo.cs` when making changes to extensions

## Common Patterns in This Repository

- **IPlayniteAPI**: The main API interface for interacting with Playnite
- **GenericPlugin**: Base class for generic plugins
- **Settings ViewModels**: Most extensions have a `*SettingsViewModel` class for managing settings
- **Localization**: Extensions use resource dictionaries for localized strings
- **Path Handling**: Common path utilities are available in `PluginsCommon.Paths`

## Building and Testing

- The solution file is `source/PlayniteExtensions.sln`
- Build using Visual Studio or MSBuild
- Extensions output to their respective directories under `source/`
- Test projects are located in `source/GenericTests/` and `source/MetadataTests/`
