# **First Interaction with PowerShell**

### **1. Download PowerShell**

- **Windows:**
  - PowerShell is pre-installed on most Windows operating systems (version 5.1 or lower).
  - To download the latest version of PowerShell (PowerShell 7 or higher), visit the [official GitHub repository](https://github.com/PowerShell/PowerShell) or [Microsoft Store](https://www.microsoft.com/store).
  - Installation steps:
    1. Go to the [PowerShell releases page on GitHub](https://github.com/PowerShell/PowerShell/releases).
    2. Download the `.msi` installer for your Windows version (x64/x86).
    3. Run the installer and follow the prompts.

- **macOS/Linux:**
  - PowerShell is also available for macOS and various Linux distributions.
  - You can install it via package managers (e.g., Homebrew for macOS, APT for Ubuntu).
  - Example for macOS using Homebrew:
    ```bash
    brew install --cask powershell
    ```
  - Example for Ubuntu:
    ```bash
    sudo apt-get install -y wget apt-transport-https software-properties-common
    wget -q https://packages.microsoft.com/config/ubuntu/20.04/packages-microsoft-prod.deb
    sudo dpkg -i packages-microsoft-prod.deb
    sudo apt-get update
    sudo apt-get install -y powershell
    ```

### **2. Method of Interaction**

- **PowerShell Console:**
  - Launch the PowerShell application (`powershell.exe` for Windows, `pwsh` for macOS/Linux).
  - This is an interactive command-line interface (CLI) where you can execute commands and scripts directly.

- **Integrated Scripting Environment (ISE):**
  - Windows PowerShell ISE provides a GUI-based interface where you can write, test, and debug PowerShell scripts.
  - It offers features like syntax highlighting and IntelliSense.
  - To open it, search for "Windows PowerShell ISE" in the Start menu.

- **Visual Studio Code (VS Code):**
  - A widely-used code editor with a PowerShell extension available.
  - It supports advanced features like debugging, script analysis, and Git integration.

### **3. Command Syntax**

- **Cmdlets:**
  - PowerShell commands are known as cmdlets (pronounced "command-lets").
  - Cmdlets follow a `Verb-Noun` naming convention.
  - Example:
    ```powershell
    Get-Process    # Retrieves a list of processes running on the local machine.
    Start-Service  # Starts a service.
    Stop-Computer  # Shuts down the local computer.
    ```

- **Parameters:**
  - Cmdlets often require parameters to specify what action to perform or on which object.
  - Parameters can be named or positional.
  - Example:
    ```powershell
    Get-Process -Name "notepad"
    ```

- **Pipelines:**
  - PowerShell uses pipelines (`|`) to pass the output of one cmdlet as input to another.
  - Example:
    ```powershell
    Get-Process | Where-Object { $_.CPU -gt 100 }
    ```

### **4. Basic Commands**

- **File System Navigation:**
  - `Get-Location`: Shows the current directory.
  - `Set-Location`: Changes the current directory.
  - `Get-ChildItem`: Lists the contents of a directory.

- **File Operations:**
  - `New-Item`: Creates a new file or directory.
  - `Copy-Item`: Copies a file or directory.
  - `Move-Item`: Moves a file or directory.
  - `Remove-Item`: Deletes a file or directory.

- **System Information:**
  - `Get-Date`: Displays the current date and time.
  - `Get-Process`: Lists currently running processes.
  - `Get-Service`: Retrieves the status of services.

- **Help System:**
  - `Get-Help`: Displays help information about cmdlets.
  - `Update-Help`: Downloads the latest help files.

### **5. Aliases**

- **Understanding Aliases:**
  - Aliases are shortcuts or alternate names for cmdlets.
  - They are primarily used for convenience, especially for users familiar with other shells like Command Prompt or Unix shells.

- **Common Aliases:**
  - `ls` → `Get-ChildItem`
  - `cd` → `Set-Location`
  - `dir` → `Get-ChildItem`
  - `pwd` → `Get-Location`
  - `cp` → `Copy-Item`
  - `mv` → `Move-Item`
  - `rm` → `Remove-Item`

- **Managing Aliases:**
  - `Get-Alias`: Lists all current aliases.
  - `Set-Alias`: Creates a new alias.
  - `Remove-Item`: Deletes an alias.
  - Example:
    ```powershell
    Set-Alias ll Get-ChildItem
    ```