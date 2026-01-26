# Setup Guide for Python Course

This guide will help you set up your development environment for the course.

## Step 1: Install Python

### Windows
1. Visit [python.org](https://www.python.org/downloads/)
2. Download Python 3.11 or later
3. Run the installer
4. **Important:** Check "Add Python to PATH" during installation
5. Verify installation by opening Command Prompt and typing:
   ```
   python --version
   ```

### macOS
1. Python may already be installed. Check by opening Terminal and typing:
   ```
   python3 --version
   ```
2. If not installed, download from [python.org](https://www.python.org/downloads/)
3. Or use Homebrew: `brew install python3`

### Linux
Most Linux distributions come with Python pre-installed. Check with:
```bash
python3 --version
```
If needed, install using your package manager:
```bash
# Ubuntu/Debian
sudo apt-get update
sudo apt-get install python3 python3-pip

# Fedora
sudo dnf install python3 python3-pip
```

## Step 2: Install Visual Studio Code

1. Visit [code.visualstudio.com](https://code.visualstudio.com/)
2. Download and install VS Code for your operating system
3. Launch VS Code

## Step 3: Install Python Extension for VS Code

1. Open VS Code
2. Click the Extensions icon in the left sidebar (or press Ctrl+Shift+X / Cmd+Shift+X)
3. Search for "Python"
4. Install the official Python extension by Microsoft
5. Restart VS Code if prompted

## Step 4: Install GitHub Copilot (Recommended)

GitHub Copilot is an AI assistant that helps you write code. It's highly recommended for this course!

### Get Access
- **Students:** Get free access through [GitHub Student Developer Pack](https://education.github.com/pack)
- **Others:** Start a free trial at [github.com/features/copilot](https://github.com/features/copilot)

### Install in VS Code
1. In VS Code, go to Extensions (Ctrl+Shift+X / Cmd+Shift+X)
2. Search for "GitHub Copilot"
3. Install the extension
4. Sign in with your GitHub account when prompted
5. Follow the authentication process

## Step 5: Verify Your Setup

Create a test file to ensure everything works:

1. Create a new folder for your course work (e.g., `python-course`)
2. Open this folder in VS Code (File → Open Folder)
3. Create a new file called `hello.py`
4. Type the following code:
   ```python
   print("Hello, Python!")
   ```
5. Save the file (Ctrl+S / Cmd+S)
6. Right-click in the editor and select "Run Python File in Terminal"
7. You should see "Hello, Python!" printed in the terminal

## Step 6: Install Git (Optional but Recommended)

### Windows
1. Download from [git-scm.com](https://git-scm.com/downloads)
2. Run the installer with default options
3. Verify: Open Command Prompt and type `git --version`

### macOS
- Git may already be installed
- Check with: `git --version`
- If not, install with: `xcode-select --install`
- Or use Homebrew: `brew install git`

### Linux
```bash
# Ubuntu/Debian
sudo apt-get install git

# Fedora
sudo dnf install git
```

## Troubleshooting

### Python not found
- **Windows:** Ensure Python was added to PATH during installation. You may need to reinstall.
- **macOS/Linux:** Try using `python3` instead of `python`

### VS Code can't find Python
1. Press Ctrl+Shift+P (Cmd+Shift+P on Mac)
2. Type "Python: Select Interpreter"
3. Choose the Python version you installed

### Copilot not working
1. Ensure you're signed in to GitHub
2. Check that your Copilot subscription is active
3. Restart VS Code
4. Check the status bar at the bottom of VS Code for Copilot status

## Additional Setup Tips

### Create a Virtual Environment (Recommended for Later Lessons)
Virtual environments keep your project dependencies isolated:

```bash
# Navigate to your project folder
cd python-course

# Create virtual environment
python -m venv venv

# Activate it
# Windows:
venv\Scripts\activate

# macOS/Linux:
source venv/bin/activate
```

### Useful VS Code Settings

Add these to your VS Code settings (File → Preferences → Settings, then search for each):

- **Auto Save:** Set to "afterDelay" for automatic saving
- **Format On Save:** Enable for automatic code formatting
- **Python Linting:** Enable pylint or flake8 for code quality checks

## You're Ready!

Once you've completed these steps, you're ready to start learning Python! Head over to Lesson 1 to begin your programming journey.

## Need Help?

If you run into issues:
1. Check the troubleshooting section above
2. Search for your error message online
3. Ask in the course discussion forum
4. Attend office hours

Remember: Everyone faces setup challenges. Don't get discouraged! Getting your environment set up is part of learning to be a programmer.
