# Extra Metadata Fullscreen Mode Helper - Development Guide

This document contains development-specific information for the Extra Metadata Fullscreen Mode Helper extension.

## Development Setup

### Prerequisites
- Visual Studio 2019 or later (or Visual Studio Code with C# extensions)
- .NET Framework 4.6.2 or later
- Playnite SDK

### Building the Extension

1. Clone the repository:
```bash
git clone https://github.com/darklinkpower/PlayniteExtensionsCollection.git
cd PlayniteExtensionsCollection
```

2. Open the solution file in Visual Studio or navigate to this extension's directory:
```bash
cd source/ExtraMetadataTools/ExtraMetadataTools
```

3. Restore NuGet packages:
```bash
nuget restore
```

4. Build the project:
```bash
msbuild /p:Configuration=Release
```

### Project Structure

```
ExtraMetadataTools/
├── extension.yaml      # Extension manifest
├── icon.png           # Extension icon
├── *.cs               # C# source files
├── *.xaml             # WPF UI files
├── Localization/      # Translation files
└── Properties/        # Assembly info
```

## Development Guidelines

### Code Style
- Use **4 spaces** for indentation (no tabs)
- Use **PascalCase** for public properties (e.g., `MyProperty`)
- Use **_camelCase** for private fields (e.g., `_myPrivateField`)
- Use **camelCase** for local variables with `var` keyword
- Always use curly braces `{}` for control statements

### Localization
- All user-facing strings should be localized
- Add strings to the localization dictionary in `Localization/`
- Use `ResourceProvider.GetString("LOC_YourKey")` to access localized strings

### Testing
- Test thoroughly in both Desktop and Fullscreen modes
- Test with different themes to ensure compatibility
- Verify that all features work as expected

## Debugging

### Debug Configuration
1. Set the output path in your project to Playnite's extensions directory
2. Set Playnite.DesktopApp.exe as the startup program
3. Use breakpoints as needed
4. Run with debugging (F5 in Visual Studio)

### Common Issues
- Extension not loading: Check extension.yaml for correct plugin ID and type
- Missing dependencies: Ensure all NuGet packages are restored
- UI not rendering: Verify XAML files are included in the project

## Contributing

Please read the [main repository's contribution guidelines](https://github.com/darklinkpower/PlayniteExtensionsCollection#contribution-guidelines) before submitting pull requests.

### Submitting Changes
1. Fork the repository
2. Create a feature branch
3. Make your changes following the code style guidelines
4. Test thoroughly
5. Submit a pull request with a clear description

## Resources

- [Playnite SDK Documentation](https://api.playnite.link/)
- [Playnite Extension Development Guide](https://github.com/JosefNemec/Playnite/wiki/Extensions)
- [Main Repository](https://github.com/darklinkpower/PlayniteExtensionsCollection)

## License

This project is licensed under the MIT License. See the main repository for details.
