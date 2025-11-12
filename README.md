Stardew NPC Maker Project
======================

This project is a complete rewrite of the original Stardew Valley NPC Maker, rebuilt from the ground up using C# and .NET 8.

The primary goal is to create a modern, cross-platform desktop application using Avalonia UI. This allows for development on a Linux environment while being able to compile and publish self-contained executables for Windows, macOS, and Linux.

The application provides a simple graphical user interface (GUI) to input all necessary NPC data, select image files, and generate a complete, ready-to-use Content Patcher mod folder.

Features
--------
-   **Cross-Platform GUI:** Built with Avalonia UI, allowing the application to run on Windows, macOS, and Linux.
-   **Simple Data Entry:** A single-window interface to input core NPC details (Internal Name, Display Name, Author).
-   **File Selection:** Includes "Browse" buttons to select and link portrait and sprite image files.
-   **Full Mod Generation:** Automatically generates the complete directory structure and all necessary files for a basic NPC mod.
-   **Smart File Handling:**
    -   Copies and renames your `_Portraits.png` and `_Sprite.png` files to match the NPC's Internal ID.
-   **JSON Scaffolding:** Generates all essential JSON files with basic, functional data:
    -   **`manifest.json`**: Creates the mod manifest with the correct `UniqueID`.
    -   **`content.json`**: Creates the content file with `Changes` patches for:
        -   Loading the Portrait and Sprite assets.
        -   `Data/NPCDispositions`: (The NPC's core data, gifts, etc.)
        -   `Characters/Dialogue`: (Basic introduction and seasonal dialogue)
        -   `Characters/schedules`: (A basic spring/rain schedule)
        -   `Data/Events`: (A starter 2-heart event)

Technology Stack
----------------
-   **Language:** C#
-   **Framework:** .NET 8
-   **UI:** Avalonia UI
-   **JSON Handling:** System.Text.Json

How to Build and Run
--------------------
You must have the **.NET 8 SDK** installed on your system.
### 1\. Clone the Repository
```bash
git clone https://github.com/TamKungZ/Project-CP-NPCmaker-C-.git
cd Project-CP-NPCmaker-C-
```

### 2\. Run Locally (for Development)
Navigate to the project directory (e.g., NPCMaker) and run:
```bash
dotnet run
```
This will compile and launch the application on your current operating system (e.g., Linux).

### 3\. Publish (Export Executables)
You can compile self-contained applications for all major platforms from your development machine.

**To publish for Windows (win-x64):**
```bash
dotnet publish -c Release -r win-x64 --self-contained
```

**To publish for Linux (linux-x64):**
```bash
dotnet publish -c Release -r linux-x64 --self-contained
```

**To publish for macOS (osx-x64):**
```bash
dotnet publish -c Release -r osx-x64 --self-contained
```
The compiled application will be located in the bin/Release/net8.0/[YOUR-RUNTIME]/publish/ folder.
