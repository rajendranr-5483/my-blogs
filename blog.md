# Build and Debug ASP.NET Core Apps Seamlessly with Visual Studio Code

TL; DR: A guide on using Visual Studio Code for ASP.NET Core application development, covering prerequisites, project setup, building, running, debugging, and testing with modern .NET CLI tools.

Meta Description: Learn to develop, debug, test, and deploy ASP.NET Core applications using Visual Studio Code with this updated guide covering setup, project creation, running, and more.

Focus Keyword: Debug ASP.NET Core

Secondary keyword: Visual studio code

Visual Studio Code (VS Code) is more than just a code editor—it's a powerful, lightweight development tool trusted by developers across platforms. Whether you're on Windows, Linux, or macOS, VS Code provides a fast, flexible, and highly customizable environment that keeps you close to your code and in control of your workflow.

Unlike the full Visual Studio IDE, VS Code strips away the excess, offering just what you need to develop, debug, test, and deploy applications with maximum efficiency. If you're looking to streamline your ASP.NET Core development without compromising on power, you're in the right place.

In this blog, we'll walk through how to build, test, and deploy ASP.NET Core applications using Visual Studio Code, covering:

- [Install essential extensions](#install-essential-extensions)
- [Create an ASP.NET Core application](#create-an-asp-net-core-application)
- [How to run the project](#how-to-run-the-project)
- [How to set breakpoints and debug the source](#how-to-set-breakpoints-and-debug-the-source)
- [Run unit test cases](#run-unit-test-cases)
- [Hot Reload support](#hot-reload-support)
- [Advantages](#advantages)
- [Limitations](#limitations)
- [Commands, shortcuts, and extensions](#commands-shortcuts-and-extensions)

## Prerequisites

The following packages should be installed on your machine:

- [.NET SDK](https://dotnet.microsoft.com/download) (latest version)
- [Visual Studio Code](https://code.visualstudio.com/download)

## Install essential extensions

1. Install the [C# Dev Kit](https://marketplace.visualstudio.com/items?itemName=ms-dotnettools.csdevkit), which provides comprehensive support for .NET development in VS Code. To open the list of extensions, select the extensions icon on the left side menu or use the **Ctrl + Shift + X** shortcut key.

2. Install the [.NET Core Tools](https://marketplace.visualstudio.com/items?itemName=formulahendry.dotnet-core-tools) extension to easily execute .NET CLI commands from within VS Code.

3. Install the [NuGet Package Manager](https://marketplace.visualstudio.com/items?itemName=jmrog.vscode-nuget-package-manager) extension to add and update NuGet packages in VS Code.

## Create an ASP.NET Core application

Modern .NET development uses the .NET CLI to create and manage projects. Follow these steps to create a new ASP.NET Core project in VS Code:

1. Create an empty directory in your local disk.

2. Open that directory in VS Code by selecting **File -> Open Folder**.

3. Open the terminal by using the shortcut **Ctrl + Shift + `** or **Terminal -> New Terminal**.

4. After opening the terminal, type and execute the following command to create a new ASP.NET Core MVC web application:

```bash
dotnet new mvc -n SampleCoreApp
```

5. Navigate to the project directory:

```bash
cd SampleCoreApp
```

6. Build the application to verify everything is working correctly:

```bash
dotnet build
```

7. The source will be built and show any errors if they exist.

8. To create a solution file for the project (optional but recommended for larger projects):

```bash
dotnet new sln -n SampleCoreApp
dotnet sln add SampleCoreApp.csproj
```

## How to run the project

Now, let's run and debug the source in the VS Code editor. To run the source, we can either:

- Use the command line with the command **dotnet run**
- Use the built-in run option in VS Code

The built-in option is more convenient as it integrates with VS Code's debugging features. VS Code now automatically detects .NET projects and can create the necessary configuration files for you.

To run the project:

1. Click on the Run and Debug icon in the left sidebar (or press **Ctrl + Shift + D**)

2. If this is your first time debugging, click on "create a launch.json file" and select ".NET Core" from the environment options.

3. VS Code will automatically create a launch.json file with appropriate configurations. For web applications, make sure you have a configuration with "serverReadyAction" that opens a browser.

4. Select the ".NET Core Launch (web)" configuration from the dropdown at the top of the Run and Debug panel.

5. Click the green play button or press F5 to start debugging.

The ASP.NET Core app will launch and automatically open in your default browser.

## How to set breakpoints and debug the source

Breakpoints in VS Code work the same as in Visual Studio. Simply click in the gutter to the left of the line number where you want to set a breakpoint. When debugging:

- A red dot indicates an active breakpoint
- The debug toolbar provides options for step over, step into, continue, and stop
- The Variables panel shows current variable values
- The Watch panel allows you to monitor specific expressions
- The Call Stack panel shows the current execution path

The debugging experience in VS Code has improved significantly and now offers features comparable to Visual Studio, including:

- Data tips (hover over variables to see values)
- Edit and continue (modify code while debugging)
- Conditional breakpoints (right-click a breakpoint to add conditions)
- Exception breakpoints (break when exceptions occur)

## Run unit test cases

VS Code provides excellent support for running and debugging unit tests. To run tests:

1. Using the .NET CLI, you can run all tests with:

```bash
dotnet test
```

2. For a better testing experience, install the [.NET Core Test Explorer](https://marketplace.visualstudio.com/items?itemName=formulahendry.dotnet-test-explorer) extension.

3. Once installed, the Test Explorer will appear in the sidebar, showing all your test projects and test cases.

4. You can run or debug individual tests or test classes by clicking the run or debug icons next to them.

5. Test results are displayed directly in the Test Explorer, with passed tests showing green checkmarks and failed tests showing red X's.

## Hot Reload support

.NET 6+ includes Hot Reload support, which allows you to modify your code and see changes immediately without restarting the application:

1. Start your application with:

```bash
dotnet watch
```

2. Make changes to your C# code or Razor views
3. Save the file, and the changes will be applied immediately
4. For changes that can't be hot reloaded, the application will automatically restart

This feature significantly speeds up the development cycle and makes VS Code an even more powerful environment for ASP.NET Core development.

## Advantages

- VS Code offers a lightweight, fast development environment with excellent .NET support
- The C# Dev Kit provides IntelliSense, refactoring, and navigation features comparable to Visual Studio
- Cross-platform support allows consistent development across Windows, macOS, and Linux
- Extensive extension ecosystem lets you customize your environment to your specific needs
- Integrated terminal and Git support streamline your workflow
- Hot Reload support enables rapid iteration during development
- Open-source and free to use

## Limitations

- Some advanced Visual Studio features like built-in database tools are not available
- Large enterprise solutions with multiple project types might be more challenging to manage
- Some specialized project templates are only available in Visual Studio
- The initial setup requires more configuration compared to Visual Studio's all-in-one approach

## Commands, shortcuts, and extensions

Let's look at the essential commands, shortcuts, and extensions for .NET development in VS Code.

### Essential .NET CLI commands

- `dotnet new` - Creates a new .NET project or file
- `dotnet build` - Builds the project
- `dotnet run` - Runs the application
- `dotnet watch` - Runs the application with hot reload support
- `dotnet test` - Runs unit tests
- `dotnet add package` - Adds a NuGet package reference
- `dotnet publish` - Publishes the application for deployment
- `dotnet clean` - Cleans build outputs

### VS Code shortcuts for .NET development

- **Ctrl + Shift + P** - Command palette
- **Ctrl + Shift + D** - Run and Debug panel
- **Ctrl + Shift + `** - Terminal
- **Ctrl + Shift + E** - Explorer
- **Ctrl + Shift + F** - Search across files
- **F5** - Start debugging
- **Ctrl + F5** - Run without debugging
- **F9** - Toggle breakpoint
- **F10** - Step over
- **F11** - Step into
- **Shift + F11** - Step out
- **Ctrl + .** - Quick fixes and refactorings

### Recommended extensions for .NET development

- **C# Dev Kit** - Comprehensive C# development support
- **.NET Core Test Explorer** - Discover and run tests
- **NuGet Package Manager** - Manage NuGet packages
- **REST Client** - Test APIs directly from VS Code
- **GitLens** - Enhanced Git capabilities
- **Prettier** - Code formatting
- **GitHub Copilot** - AI-assisted coding
- **Docker** - Docker integration for containerized development

## Conclusion

Thanks for reading! Using Visual Studio Code for ASP.NET Core development offers a fast, flexible, and modern workflow. With the right extensions and configurations, you can build, debug, and test .NET applications efficiently—without needing the full Visual Studio IDE.

The modern .NET CLI tools combined with VS Code's powerful features create a development experience that's both productive and enjoyable. Hot Reload support further enhances this experience by allowing you to see your changes in real-time.

The Syncfusion ASP.NET Core UI control library further enhances your development experience with a rich collection of high-performance, responsive UI components.

For existing customers, the newest version is available for download from the [License and Downloads](https://www.syncfusion.com/account/downloads) page. If you are not yet a Syncfusion customer, you can try our 30-day [free trial](https://www.syncfusion.com/downloads) to check out our available features. Also, try our samples in this [GitHub](https://github.com/syncfusion) location.

You can also contact us through our [support forum](https://www.syncfusion.com/forums), [support portal](https://support.syncfusion.com/), or [feedback portal](https://www.syncfusion.com/feedback/aspnet-core). We are always happy to assist you!