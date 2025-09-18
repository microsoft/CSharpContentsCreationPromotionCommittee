# C# Contents Creation Promotion Committee Repository

The C# Contents Creation Promotion Committee repository is a Microsoft initiative for coordinating and promoting C# educational content, best practices, and community resources. This repository serves as a collaboration hub for committee activities, content planning, and C# development projects.

**CRITICAL: Always reference these instructions first and fallback to search or additional commands only when you encounter unexpected information that does not match the information provided here.**

## Working Effectively

### Prerequisites and Environment Setup
- **System Requirements**: Ubuntu 24.04 LTS environment with .NET 8.0.119 SDK pre-installed
- **Available Tools**: git (2.51.0), nano, vim, dotnet CLI
- **Note**: Visual Studio Code is not available in this environment - use nano or vim for text editing

### Basic Repository Operations
- Clone and setup: Repository is pre-cloned in development environment
- **Available .NET Version**: .NET 8.0.119 with ASP.NET Core 8.0.19 runtime
- Verify setup: `dotnet --info` (takes <1 second)
- Repository structure: Currently minimal with SECURITY.md only

### Creating C# Projects (Committee Work)
- **Create console application**: `dotnet new console -n [ProjectName]` (takes ~8 seconds, NEVER CANCEL)
- **Create class library**: `dotnet new classlib -n [LibraryName]` (takes ~1-2 seconds)
- **Create test project**: `dotnet new xunit -n [ProjectName].Tests` (takes ~10 seconds, NEVER CANCEL - includes NuGet restore)
- **Create Web API**: `dotnet new webapi -n [ApiName]` (takes ~3-4 seconds)
- **Create solution**: `dotnet new sln -n [SolutionName]` (takes <1 second)

### Building and Testing C# Projects
- **Build project**: `dotnet build` (takes ~8 seconds for simple projects, NEVER CANCEL - set timeout to 60+ seconds for complex solutions)
- **Run console application**: `dotnet run` (takes ~1-2 seconds)
- **Run tests**: `dotnet test` (takes ~4-5 seconds for basic xUnit projects, NEVER CANCEL - set timeout to 120+ seconds for large test suites)
- **Restore packages**: `dotnet restore` (automatic during build, but can run manually, takes ~1-2 seconds)

### Package Management
- **Add NuGet package**: `dotnet add package [PackageName]` (takes ~2-3 seconds, requires internet access)
- **List packages**: `dotnet list package`
- **Remove package**: `dotnet remove package [PackageName]`
- **Example tested package**: Newtonsoft.Json installs successfully

### Solution Management
- **Add project to solution**: `dotnet sln add [ProjectPath]/[ProjectName].csproj` (takes <1 second)
- **Remove project**: `dotnet sln remove [ProjectPath]/[ProjectName].csproj`
- **List projects**: `dotnet sln list`

## Validation Requirements

### MANDATORY: Always Validate Changes
- **Build validation**: Always run `dotnet build` after making code changes
- **Test validation**: Always run `dotnet test` if test projects exist
- **Runtime validation**: For console apps, run `dotnet run` and verify expected output
- **Web API validation**: For Web APIs, build successfully and check for compilation errors

### Testing Scenarios for Committee Content
When creating educational content or examples:
1. **Create sample project**: Use `dotnet new console -n SampleProject`
2. **Verify compilation**: Run `dotnet build` and ensure clean build
3. **Test execution**: Run `dotnet run` and verify expected output
4. **Document timing**: Note actual execution times for learners

### No Automated CI/CD Currently
- **Note**: Repository does not have GitHub Actions workflows for C# projects
- **Manual verification required**: Always test locally before committing
- **No linting tools**: Standard Visual Studio/.NET formatting applies

## Repository-Specific Guidelines

### Committee Structure and Purpose
- **Primary Focus**: Educational content creation and promotion for C# developers
- **Content Types**: Code samples, tutorials, best practices documentation
- **Target Audience**: C# developers at all skill levels

### File Organization Best Practices
- **Projects**: Place new C# projects in descriptively named subdirectories
- **Documentation**: Use markdown files for content documentation
- **Examples**: Create self-contained, runnable examples with clear README files

### Collaboration Workflow
- **Content Review**: All educational content should be peer-reviewed
- **Code Standards**: Follow standard C# coding conventions
- **Documentation**: Include clear explanations and comments for educational value

## Common Development Tasks

### Quick Start for New Content Creation
1. **Create project directory**: `mkdir [ContentName] && cd [ContentName]`
2. **Initialize project**: `dotnet new console -n [ProjectName]` (8 seconds, set timeout to 60+ seconds)
3. **Build and verify**: `dotnet build` (8 seconds, set timeout to 60+ seconds)
4. **Test run**: `dotnet run` (1-2 seconds)
5. **Add to repository**: Use git commands to add and commit

### Performance Expectations (Based on Testing)
- **Console project creation**: ~8 seconds including restore
- **Class library creation**: ~1-2 seconds
- **Test project creation**: ~10 seconds (includes xUnit packages)
- **Web API creation**: ~3-4 seconds
- **Build operations**: ~8 seconds for simple projects
- **Test execution**: ~4-5 seconds for basic test suites
- **Package installation**: ~2-3 seconds (requires internet)

### CRITICAL Timeout Settings
- **NEVER CANCEL build operations** - Set timeout to minimum 60 seconds, prefer 120+ seconds for safety
- **NEVER CANCEL test operations** - Set timeout to minimum 120 seconds for test suites
- **NEVER CANCEL package operations** - Network dependent, allow 60+ seconds

## Educational Content Guidelines

### Code Sample Standards
- **Simplicity**: Keep examples focused and understandable
- **Comments**: Include explanatory comments for learning purposes
- **Self-contained**: Examples should run without external dependencies when possible
- **Progressive complexity**: Start with basic concepts, build to advanced

### Content Validation Checklist
- [ ] Code compiles cleanly with `dotnet build`
- [ ] Examples run successfully with expected output
- [ ] Documentation is clear and accurate
- [ ] Code follows C# naming conventions
- [ ] Educational value is clear and appropriate for target audience

## Troubleshooting Common Issues

### Build Failures
- **Check .NET version**: `dotnet --version` should show 8.0.119
- **Clean and rebuild**: `dotnet clean && dotnet build`
- **Restore packages**: `dotnet restore`

### Package Issues
- **Internet connectivity required**: Package operations need external access
- **Cache issues**: Clear with `dotnet nuget locals --clear all` if needed

### Performance Notes
- **First builds slower**: Initial builds include package restoration
- **Subsequent builds faster**: Incremental compilation applies
- **Test discovery**: xUnit test discovery adds startup time

## Key Repository Locations

### Current Structure
```
/
├── .github/
│   └── copilot-instructions.md (this file)
└── SECURITY.md
```

### Recommended Structure for Future Content
```
/
├── examples/
│   ├── basics/
│   ├── intermediate/
│   └── advanced/
├── tutorials/
├── best-practices/
└── community-resources/
```