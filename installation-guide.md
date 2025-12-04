# Python Development Setup Guide

This guide will walk you through setting up a complete Python development environment on **Windows** or **Mac**. Follow each step carefully and in order.

**Note**: Each step that differs by platform will have expandable sections - click on your platform to see the instructions.

## Table of Contents
1. [Create GitHub Account](#1-create-github-account)
2. [Install Git](#2-install-git)
3. [Install Python](#3-install-python)
4. [Install uv (Package Manager)](#4-install-uv-package-manager)
5. [Install VS Code](#5-install-vs-code)
6. [Install VS Code Extensions](#6-install-vs-code-extensions)
7. [Create Claude Account](#7-create-claude-account)
8. [Install Claude Code](#8-install-claude-code)
9. [Verify Installation](#9-verify-installation)

---

## 1. Create GitHub Account

If you don't already have a GitHub account:

1. Go to [github.com](https://github.com)
2. Click **Sign up** in the top right
3. Follow the prompts to create your account
   - Use an email you check regularly
   - Choose a professional username (you may use this for years!)
   - Verify your email address
4. Once created, keep this browser tab open - you'll need it later

---

## 2. Install Git

Git is the version control system that tracks changes to your code.

<details>
<summary><b>Windows Instructions</b></summary>

### Download and Install:

1. Go to [git-scm.com/download/win](https://git-scm.com/download/win)
2. Download the installer (64-bit recommended)
3. Run the installer with these settings:
   - **Select Components**: Keep all defaults checked
   - **Default editor**: Choose "Use Visual Studio Code as Git's default editor" (if you see this option; otherwise skip)
   - **PATH environment**: Choose "Git from the command line and also from 3rd-party software"
   - **HTTPS transport**: Choose "Use the OpenSSL library"
   - **Line ending conversions**: Choose "Checkout Windows-style, commit Unix-style"
   - **Terminal emulator**: Choose "Use MinTTY"
   - **Default git pull behavior**: Choose "Default (fast-forward or merge)"
   - Keep all other defaults and click through to finish

### Configure Git:

1. Open **Command Prompt** or **PowerShell**:
   - Press `Windows Key + R`
   - Type `cmd` and press Enter

2. Set your name and email (use the same email as your GitHub account):
   ```bash
   git config --global user.name "Your Name"
   git config --global user.email "your.email@example.com"
   ```

3. Verify it worked:
   ```bash
   git --version
   ```
   You should see something like `git version 2.43.0`

</details>

<details>
<summary><b>Mac Instructions</b></summary>

### Check if Git is Already Installed:

1. Open **Terminal**:
   - Press `Cmd + Space` to open Spotlight
   - Type "Terminal" and press Enter

2. Check for Git:
   ```bash
   git --version
   ```

3. If you see a version number (like `git version 2.39.x`), Git is already installed! Skip to "Configure Git" below.

4. If you get a prompt to install Command Line Developer Tools, click **Install** and follow the prompts. This will install Git.

### Install Git (if needed):

If Git isn't installed and you didn't get the prompt:

**Option 1: Using Homebrew (Recommended)**

1. First, install Homebrew if you don't have it:
   ```bash
   /bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
   ```

2. Follow any on-screen instructions to add Homebrew to your PATH

3. Install Git:
   ```bash
   brew install git
   ```

**Option 2: Download Installer**

1. Go to [git-scm.com/download/mac](https://git-scm.com/download/mac)
2. Download and run the installer
3. Follow the prompts with default settings

### Configure Git:

1. In Terminal, set your name and email (use the same email as your GitHub account):
   ```bash
   git config --global user.name "Your Name"
   git config --global user.email "your.email@example.com"
   ```

2. Verify it worked:
   ```bash
   git --version
   ```
   You should see something like `git version 2.39.0` or higher

</details>

---

## 3. Install Python

We'll use the official Python distribution from Python.org.

<details>
<summary><b>Windows Instructions</b></summary>

### Download and Install:

1. Go to [python.org/downloads](https://www.python.org/downloads/)
2. Click the **Download Python 3.12.x** button (version number may vary slightly)
3. Run the installer with these **IMPORTANT** settings:
   - ✅ **CHECK** "Add python.exe to PATH" (at the bottom - VERY IMPORTANT!)
   - Click **Install Now**
   - If prompted for administrator access, click Yes
   - Wait for installation to complete
   - Click **Close**

### Verify Installation:

1. Open a **NEW** Command Prompt or PowerShell window (important - must be new!)
2. Type:
   ```bash
   python --version
   ```
   You should see `Python 3.12.x`

3. Also verify pip (Python's package installer):
   ```bash
   pip --version
   ```
   You should see something like `pip 24.x.x`

**Troubleshooting**: If you get "python is not recognized", you likely forgot to check "Add to PATH". Uninstall and reinstall Python, making sure to check that box.

</details>

<details>
<summary><b>Mac Instructions</b></summary>

### Check if Python 3 is Already Installed:

Macs come with Python 2.7, which is outdated. We need Python 3.

1. Open **Terminal** (if not already open)

2. Check Python version:
   ```bash
   python3 --version
   ```

3. If you see `Python 3.11.x` or higher, you're good! Skip to "Verify Installation" below.

### Download and Install:

1. Go to [python.org/downloads](https://www.python.org/downloads/)

2. Click the **Download Python 3.12.x** button (get the latest stable version)

3. Download the **macOS 64-bit universal2 installer**

4. Run the downloaded `.pkg` file

5. Follow the installer:
   - Click **Continue** through the introduction
   - Accept the license agreement
   - Use default install location
   - Click **Install**
   - Enter your password when prompted
   - Wait for installation to complete
   - Click **Close**

6. If prompted to move the installer to trash, click **Move to Trash**

### Verify Installation:

1. Open a **NEW** Terminal window (important - must be new!)

2. Check Python 3:
   ```bash
   python3 --version
   ```
   You should see `Python 3.12.x`

3. Verify pip:
   ```bash
   pip3 --version
   ```
   You should see something like `pip 24.x.x`

**Note**: On Mac, you use `python3` and `pip3` instead of `python` and `pip` to ensure you're using Python 3, not the old system Python 2.

**Optional - Create aliases**: To use `python` and `pip` instead of `python3` and `pip3`, add these lines to your `~/.zshrc` file:
```bash
alias python=python3
alias pip=pip3
```
Then restart Terminal or run `source ~/.zshrc`

</details>

---

## 4. Install uv (Package Manager)

uv is a modern, extremely fast Python package manager that we'll use instead of traditional pip/conda.

<details>
<summary><b>Windows Instructions</b></summary>

### Install uv:

1. Open PowerShell (not Command Prompt this time):
   - Press `Windows Key`
   - Type "PowerShell"
   - Click **Windows PowerShell**

2. Run this command:
   ```powershell
   powershell -ExecutionPolicy ByPass -c "irm https://astral.sh/uv/install.ps1 | iex"
   ```

3. Close and reopen PowerShell (important!)

4. Verify installation:
   ```bash
   uv --version
   ```
   You should see something like `uv 0.5.x`

**Note**: If you get a security warning about execution policies, that's normal. The command above bypasses it safely for this one install.

</details>

<details>
<summary><b>Mac Instructions</b></summary>

### Install uv:

1. Open **Terminal** (if not already open)

2. Run this command:
   ```bash
   curl -LsSf https://astral.sh/uv/install.sh | sh
   ```

3. Follow any on-screen instructions to add uv to your PATH. You may need to run:
   ```bash
   source $HOME/.cargo/env
   ```

4. Close and reopen Terminal (important!)

5. Verify installation:
   ```bash
   uv --version
   ```
   You should see something like `uv 0.5.x`

**Alternative - Using Homebrew**: If you installed Homebrew earlier, you can also install uv with:
```bash
brew install uv
```

</details>

---

## 5. Install VS Code

VS Code (Visual Studio Code) is the code editor we'll use for writing Python.

<details>
<summary><b>Windows Instructions</b></summary>

### Download and Install:

1. Go to [code.visualstudio.com](https://code.visualstudio.com/)
2. Click **Download for Windows**
3. Run the installer with these settings:
   - Accept the license agreement
   - Keep default install location
   - ✅ **CHECK** "Add to PATH" (important!)
   - ✅ **CHECK** "Create a desktop icon" (optional but convenient)
   - ✅ **CHECK** "Register Code as an editor for supported file types"
   - ✅ **CHECK** "Add 'Open with Code' action to Windows Explorer context menu" (both options)
   - Click **Install**
   - Launch VS Code when installation completes

</details>

<details>
<summary><b>Mac Instructions</b></summary>

### Download and Install:

1. Go to [code.visualstudio.com](https://code.visualstudio.com/)

2. Click **Download for Mac**
   - For Apple Silicon Macs (M1/M2/M3): Download "Apple Silicon"
   - For older Intel Macs: Download "Intel Chip"
   - If unsure, click the Apple menu → "About This Mac" to check your processor

3. Download will save a `.zip` file

4. Double-click the `.zip` file to extract it (if it doesn't extract automatically)

5. Drag the **Visual Studio Code** app to your **Applications** folder

6. Open VS Code:
   - Go to your Applications folder
   - Double-click **Visual Studio Code**
   - If you get a warning that it's from the internet, click **Open**

7. Add VS Code to your PATH (important!):
   - Open VS Code
   - Press `Cmd+Shift+P` to open the Command Palette
   - Type "shell command"
   - Select **Shell Command: Install 'code' command in PATH**
   - Enter your password if prompted

8. Verify PATH setup:
   - Open Terminal
   - Type: `code --version`
   - You should see version information

</details>

---

## 6. Install VS Code Extensions

Extensions add Python support and other useful features to VS Code.

**Note**: This process is the same for both Windows and Mac.

### Install Extensions:

1. In VS Code, click the **Extensions** icon in the left sidebar
   - Windows: Press `Ctrl+Shift+X`
   - Mac: Press `Cmd+Shift+X`

2. Search for and install each of these extensions (click the **Install** button for each):

   **Required:**
   - **Python** (by Microsoft) - Core Python support
   - **Jupyter** (by Microsoft) - Notebook support
   - **Pylance** (by Microsoft) - Advanced Python language support

   **Highly Recommended:**
   - **Python Indent** (by Kevin Rose) - Better auto-indentation
   - **Error Lens** (by Alexander) - Shows errors inline
   - **GitLens** (by GitKraken) - Enhanced Git features

3. After installing, you may see a prompt to reload VS Code - click **Reload** if prompted

### Verify:

1. Click the Extensions icon again
2. You should see all installed extensions listed
3. They should all show "Installed" (not "Install")

---

## 7. Create Claude Account

Claude is an AI assistant that can help you write and understand code.

### Create Account:

1. Go to [claude.ai](https://claude.ai)
2. Click **Sign up**
3. You can sign up with:
   - Email and password, OR
   - Google account
4. Verify your email if required
5. You'll get a free account with generous usage limits
6. Keep this browser tab open - you'll need to log in for the next step

---

## 8. Install Claude Code

Claude Code is a CLI tool that integrates Claude AI into your development environment.

**Note**: This process is the same for both Windows and Mac.

### Install Claude Code:

<details>
<summary><b>Windows Instructions</b></summary>

1. Open a **NEW** PowerShell or Command Prompt window

2. Run this command:
   ```bash
   npx -y @anthropics/claude-code install
   ```

   **Note**: If you don't have Node.js installed, you'll be prompted to install it. Follow the prompts to install Node.js, then run the command again.

3. The installer will:
   - Download Claude Code
   - Ask you to authenticate (a browser window will open)
   - Log in with your Claude account when prompted
   - Grant the necessary permissions

4. Once complete, verify installation:
   ```bash
   claude-code --version
   ```

**Troubleshooting**: If `npx` is not recognized, you need to install Node.js:
- Go to [nodejs.org](https://nodejs.org)
- Download the LTS (Long Term Support) version
- Install with default settings
- Close and reopen your terminal
- Try the `npx` command again

</details>

<details>
<summary><b>Mac Instructions</b></summary>

1. Open a **NEW** Terminal window

2. Run this command:
   ```bash
   npx -y @anthropics/claude-code install
   ```

   **Note**: If you don't have Node.js installed, you'll be prompted to install it. You can install it with Homebrew or from nodejs.org.

3. The installer will:
   - Download Claude Code
   - Ask you to authenticate (a browser window will open)
   - Log in with your Claude account when prompted
   - Grant the necessary permissions

4. Once complete, verify installation:
   ```bash
   claude-code --version
   ```

**Troubleshooting**: If `npx` is not recognized, you need to install Node.js:
- **Using Homebrew**: `brew install node`
- **Or from website**: Go to [nodejs.org](https://nodejs.org), download the LTS version, and install
- Close and reopen Terminal
- Try the `npx` command again

</details>

---

## 9. Verify Installation

Let's make sure everything is working correctly.

### Quick Verification Checklist:

<details>
<summary><b>Windows Instructions</b></summary>

Open a **NEW** Command Prompt or PowerShell and run each command:

```bash
# Check Python
python --version

# Check pip
pip --version

# Check uv
uv --version

# Check Git
git --version

# Check VS Code
code --version

# Check Claude Code
claude-code --version
```

All commands should return version numbers without errors.

### VS Code Check:

1. Open VS Code
2. Press `` Ctrl+` `` (that's Ctrl + backtick) to open the integrated terminal
3. The terminal should open at the bottom
4. Try typing `python --version` in that terminal - it should work

</details>

<details>
<summary><b>Mac Instructions</b></summary>

Open a **NEW** Terminal window and run each command:

```bash
# Check Python (use python3 on Mac)
python3 --version

# Check pip
pip3 --version

# Check uv
uv --version

# Check Git
git --version

# Check VS Code
code --version

# Check Claude Code
claude-code --version
```

All commands should return version numbers without errors.

**Note**: Remember on Mac you use `python3` and `pip3` unless you set up aliases.

### VS Code Check:

1. Open VS Code
2. Press `` Cmd+` `` (that's Cmd + backtick) to open the integrated terminal
3. The terminal should open at the bottom
4. Try typing `python3 --version` in that terminal - it should work

</details>

---

## You're All Set! 🎉

Your Python development environment is now fully configured. You're ready to:
- Write Python code
- Use Jupyter notebooks
- Manage packages with uv
- Track code with Git and GitHub
- Get AI assistance from Claude

**Next Step**: Continue to the **Getting Started Tutorial** to create your first project!

---

## Quick Reference Commands

Here are the key commands you'll use regularly (same for both platforms unless noted):

### Python:
```bash
# Windows:
python --version
pip --version

# Mac:
python3 --version
pip3 --version
```

### uv (Package Management):
```bash
uv venv myenv          # Create virtual environment
uv pip install package # Install a package
uv pip list            # List installed packages
```

### Git:
```bash
git status             # Check what's changed
git add .              # Stage all changes
git commit -m "msg"    # Commit changes
git push               # Push to GitHub
git pull               # Get latest changes
```

### VS Code:
```bash
code .                 # Open current folder in VS Code
code filename.py       # Open a specific file
```

---

## Getting Help

- **VS Code**:
  - Windows: Press `F1` or `Ctrl+Shift+P` to open the Command Palette
  - Mac: Press `F1` or `Cmd+Shift+P` to open the Command Palette
- **Python**: Type `help()` in the Python interactive shell
- **Git**: Type `git --help` or `git <command> --help`
- **uv**: Type `uv --help`

If you run into issues, check that you:
1. Restarted your terminal after each installation
2. Checked the "Add to PATH" options during installation (Windows) or followed PATH setup steps (Mac)
3. Have administrator/admin privileges on your computer
