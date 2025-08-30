# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a Blazor Server application built with .NET 9 called "Forge Server Manager" - a game server management platform with an expanding roster of supported games. It uses Blazor's Interactive Server Components for a responsive web UI.

## Project Structure

- **Program.cs**: Application entry point configuring Blazor Server with interactive components
- **Components/**: Contains all Razor components
  - **App.razor**: Main application HTML template with Bootstrap styling
  - **Layout/**: Layout components (MainLayout, NavMenu)  
  - **Pages/**: Routable page components (Home, Counter, Weather, Error)
  - **Routes.razor**: Routing configuration
  - **_Imports.razor**: Global using statements for components
- **wwwroot/**: Static web assets including Bootstrap CSS/JS libraries
- **Properties/launchSettings.json**: Development server configuration (HTTP: 5108, HTTPS: 7191)

## Common Development Commands

### Build and Run
```bash
dotnet build                    # Build the project
dotnet run                      # Run in development mode
dotnet run --launch-profile http   # Run on HTTP only
dotnet run --launch-profile https  # Run on HTTPS
```

### Development Tools
```bash
dotnet watch                    # Run with hot reload during development
dotnet clean                    # Clean build artifacts
dotnet restore                  # Restore NuGet packages
dotnet format                   # Apply code formatting
```

### Testing and Deployment
```bash
dotnet test                     # Run unit tests (if any exist)
dotnet publish                  # Publish for deployment
dotnet publish -c Release       # Release build for production
```

## Architecture Notes

- **Blazor Server**: Uses SignalR for real-time communication between client and server
- **Interactive Server Components**: Enabled for dynamic UI updates without page refreshes
- **Bootstrap 5**: Used for responsive styling and layout
- **Static Assets**: Managed through ASP.NET Core's static asset system
- **HTTPS Redirection**: Configured for production with HSTS
- **Antiforgery**: Enabled for CSRF protection

## Development Environment

- **Target Framework**: .NET 9.0
- **Nullable Reference Types**: Enabled
- **Implicit Usings**: Enabled
- **Default Ports**: HTTP 5108, HTTPS 7191
- **Assembly Name**: Automatically handles spaces in project name