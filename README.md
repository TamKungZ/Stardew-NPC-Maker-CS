# Stardew NPC Maker Project

This project is a complete rewrite of the original Stardew Valley NPC Maker, rebuilt from the ground up using C\# and .NET 8.

The primary goal is to create a modern, cross-platform desktop application using Avalonia UI. This allows for development on a Linux environment while being able to compile and publish self-contained executables for Windows, macOS, and Linux.

The application provides a comprehensive, multi-page wizard interface (GUI) to input all necessary NPC data, select image files, and generate a complete, ready-to-use Content Patcher mod folder.

## Features

  * **Cross-Platform GUI:** Built with Avalonia UI, allowing the application to run on Windows, macOS, and Linux.
  * **Multi-Page Wizard Interface:** A step-by-step wizard that guides you through:
    1.  Basic Info (Name, Author)
    2.  Images (Portraits & Sprites)
    3.  Dialogue & Schedules
    4.  Detailed Disposition
    5.  Custom Events
  * **Image Selection with Previews:** Select portrait and sprite files from your computer and see a live preview directly in the application.
  * **Advanced Data Editors:**
      * **Detailed Disposition Editor:** A dedicated page to visually configure all 15 fields of `NPCDispositions` (Age, Manner, Gender, Gifts, etc.) using dropdowns and text boxes.
      * **Custom Dialogue Editor:** A list editor to add any number of custom dialogue keys (e.g., `Mon`, `AcceptGift_Loved`, `Introduction`) and their corresponding text.
      * **Custom Schedule Editor:** A UI-assisted editor to build complex schedule lines, including season, time, location, X/Y coordinates, and direction.
      * **Custom Event Editor:** A simple editor to add custom event keys and their full event script strings.
  * **Smart File Handling:**
      * Copies and renames your `_Portraits.png` and `_Sprite.png` files to match the NPC's Internal ID.
  * **Full Mod Generation:** Generates the complete directory structure (`manifest.json`, `content.json`, and `assets` folder) based on all the custom data you entered.

## Technology Stack

  * **Language:** C\#
  * **Framework:** .NET 8
  * **UI:** Avalonia UI (with FluentTheme)
  * **JSON Handling:** System.Text.Json

## How to Build and Run

You must have the **.NET 8 SDK** installed on your system.

### 1\. Clone the Repository

```bash
git clone https://github.com/TamKungZ/NPCmaker-CS.git
cd NPCmaker-CS
```

### 2\. Run Locally (for Development)

Navigate to the project directory (e.g., `NPCMaker`) and run:

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

The compiled application will be located in the `bin/Release/net8.0/[YOUR-RUNTIME]/publish/` folder.
