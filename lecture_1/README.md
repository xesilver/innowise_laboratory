# My Python Project

A Python project demonstrating proper project structure, virtual environments, dependency management, and version control.

## Project Structure

```
my_project/
├── venv/              # Virtual environment (in .gitignore)
├── .git/              # Git folder (automatic)
├── .vscode/           # VS Code configuration
│   └── launch.json    # Debugging configuration
├── .gitignore         # File to ignore unnecessary files
├── pyproject.toml     # File with dependencies
├── requirements.txt   # Frozen dependencies
├── main.py            # Main executable file
└── README.md          # This file
```

## Setup Instructions

### 1. Clone and Setup

```bash
# Navigate to project directory
cd task_1

# Create and activate virtual environment (if not already created)
python -m venv venv

# On Windows PowerShell:
.\venv\Scripts\Activate.ps1

# On Windows Command Prompt:
venv\Scripts\activate.bat

# On Linux/Mac:
source venv/bin/activate

# Install dependencies
pip install -r requirements.txt
```

### 2. Running the Project

```bash
# Make sure virtual environment is activated
python main.py
```

You should see colored "Hello World" messages in your terminal!

## Part 4: Debugging Setup

### Setting up the Debugger in VS Code

#### Prerequisites
1. **Install Python Extension**: Make sure you have the official Python extension installed in VS Code
   - Press `Ctrl+Shift+X` to open Extensions
   - Search for "Python" by Microsoft
   - Click Install

2. **Install debugpy**: The Python debugger
   ```bash
   # Activate your virtual environment first
   pip install debugpy
   ```

#### How to Use the Debugger

1. **Open the Project in VS Code**
   - File → Open Folder → Select the `task_1` directory

2. **Set Breakpoints**
   - Open `main.py`
   - Click in the left margin (gutter) next to line numbers to set breakpoints
   - A red dot will appear indicating a breakpoint
   - Suggested lines to set breakpoints:
     - Line 4: After colorama initialization
     - Line 7: First print statement
     - Line 8: Second print statement

3. **Start Debugging**
   - **Method 1**: Press `F5`
   - **Method 2**: Click "Run and Debug" icon in the left sidebar (Ctrl+Shift+D), then click "Python: main.py"
   - **Method 3**: Right-click in the editor → "Debug Python File"

4. **Debug Controls**
   - **Continue (F5)**: Resume execution until next breakpoint
   - **Step Over (F10)**: Execute current line and move to next
   - **Step Into (F11)**: Step into function calls
   - **Step Out (Shift+F11)**: Step out of current function
   - **Restart (Ctrl+Shift+F5)**: Restart debugging session
   - **Stop (Shift+F5)**: Stop debugging

5. **Inspect Variables**
   - While paused at a breakpoint, check the "Variables" panel in the left sidebar
   - Hover over variables in the code to see their values
   - Use the "Watch" panel to monitor specific expressions

6. **Debug Console**
   - At the bottom of VS Code, you'll see a "Debug Console" tab
   - Here you can evaluate expressions and interact with your program
   - Try typing `Fore.RED` to see the color code value

### Alternative Debugging Setup for PyCharm

1. **Open Project**: File → Open → Select `task_1` directory
2. **Configure Interpreter**: 
   - File → Settings → Project → Python Interpreter
   - Click gear icon → Add → Existing Environment
   - Select `venv/Scripts/python.exe`
3. **Set Breakpoints**: Click in the left gutter next to line numbers
4. **Debug**: Right-click `main.py` → Debug 'main'

## Git Workflow Summary

This project was built using proper Git workflow:

1. **Initial Setup**
   ```bash
   git init
   git add .gitignore
   git commit -m "Initial commit: Project structure and gitignore"
   ```

2. **Virtual Environment Feature**
   ```bash
   git checkout -b feature/virtual-environment
   # ... create venv, install packages, create pyproject.toml ...
   git add pyproject.toml requirements.txt
   git commit -m "Add virtual environment"
   git checkout main
   git merge feature/virtual-environment
   ```

3. **Main Logic Feature**
   ```bash
   git checkout -b feature/main-logic
   # ... create main.py ...
   git add main.py
   git commit -m "Add main.py with colorama demo"
   git checkout main
   git merge feature/main-logic
   ```

## Dependencies

- **colorama** (0.4.6): Cross-platform colored terminal text

## Notes

- The `.vscode/` directory is excluded from Git (see `.gitignore`)
- The `venv/` directory is excluded from Git
- All dependencies are tracked in both `requirements.txt` and `pyproject.toml`

## Troubleshooting

### Virtual Environment Not Activating
- On Windows, you may need to run: `Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Scope CurrentUser`

### Colors Not Showing
- Make sure you're running the script in a terminal that supports ANSI colors
- colorama automatically initializes for Windows compatibility

### Debugger Not Working
- Ensure the Python extension is installed
- Check that the interpreter is set to your virtual environment
- Restart VS Code if needed

