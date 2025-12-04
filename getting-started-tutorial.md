# Getting Started: Your First Python Project

This tutorial will walk you through creating your first Python project, from creating a GitHub repository to writing code with AI assistance.

**Prerequisites**: You must have completed the [Installation Guide](installation-guide.md) first.

## What You'll Learn

By the end of this tutorial, you'll know how to:
1. Create a GitHub repository
2. Clone it to your computer
3. Set up a Python virtual environment
4. Write and run a "Hello World!" program
5. Commit and push your code to GitHub
6. Use Claude AI to write a program
7. Sync your AI-assisted code to GitHub

**Time Required**: 30-45 minutes

---

## Step 1: Create a GitHub Repository

A repository (or "repo") is where your code lives on GitHub.

### Create the Repo:

1. Go to [github.com](https://github.com) and sign in

2. Click the **+** button in the top right, then **New repository**

3. Fill in the details:
   - **Repository name**: `my-first-python-project` (or any name you like)
   - **Description**: "My first Python project for learning"
   - **Public** or **Private**: Choose Public (so your instructor can see it)
   - ✅ **CHECK** "Add a README file" (IMPORTANT - makes the next steps easier)
   - **Add .gitignore**: Choose "Python" from the dropdown
   - **License**: None (or choose MIT if you want)

4. Click **Create repository**

### What You Created:

You now have a repository with two files:
- `README.md` - A description file
- `.gitignore` - Tells Git which files to ignore (like Python cache files)

---

## Step 2: Clone the Repository to Your Computer

"Cloning" means downloading the repository to your computer so you can work on it.

### Clone Using VS Code:

1. On your GitHub repository page, click the green **<> Code** button

2. Make sure **HTTPS** is selected (should be underlined)

3. Click the **copy icon** next to the URL to copy it
   - Should look like: `https://github.com/your-username/my-first-python-project.git`

4. Open **VS Code**

5. Press `Ctrl+Shift+P` to open the Command Palette

6. Type "git clone" and select **Git: Clone**

7. Paste the URL you copied and press Enter

8. Choose where to save it:
   - I recommend creating a folder like `C:\Users\YourName\Documents\Code`
   - Navigate there and click **Select as Repository Destination**

9. When prompted "Would you like to open the cloned repository?", click **Open**

### What Happened:

VS Code downloaded your repository and opened it. You should see:
- Your folder name in the Explorer sidebar (left side)
- The `README.md` and `.gitignore` files

---

## Step 3: Set Up a Virtual Environment

A virtual environment keeps your project's packages separate from other projects.

### Create and Activate Virtual Environment:

1. In VS Code, open the integrated terminal:
   - **Windows**: Press `` Ctrl+` `` (that's Ctrl + backtick)
   - **Mac**: Press `` Cmd+` `` (that's Cmd + backtick)
   - Or go to **Terminal → New Terminal**

2. You should see a terminal at the bottom of VS Code

3. Create a virtual environment named `class-env`:
   ```bash
   uv venv class-env
   ```

4. Wait a few seconds. You should see a message like "Created virtual environment"

5. Activate the environment:

   **Windows**:
   ```bash
   class-env\Scripts\activate
   ```

   **Mac**:
   ```bash
   source class-env/bin/activate
   ```

6. Your terminal prompt should now show `(class-env)` at the beginning:

   Windows example:
   ```
   (class-env) PS C:\Users\YourName\Documents\Code\my-first-python-project>
   ```

   Mac example:
   ```
   (class-env) username@computer my-first-python-project %
   ```

### Install Required Packages:

Now install the packages we'll use in this class:

```bash
uv pip install numpy pandas statsmodels matplotlib seaborn jupyter
```

This should complete in just a few seconds (uv is very fast!).

### Verify:

Check what's installed:
```bash
uv pip list
```

You should see numpy, pandas, matplotlib, seaborn, statsmodels, jupyter, and their dependencies.

**Important**: Every time you open this project in a new terminal, you'll need to activate the environment:
- Windows: `class-env\Scripts\activate`
- Mac: `source class-env/bin/activate`

---

## Step 4: Write Your First Program

Let's write a classic "Hello World!" program.

### Create the File:

1. In VS Code, in the Explorer sidebar, hover over your project name

2. Click the **New File** icon (looks like a page with a +)

3. Name it: `hello.py`

4. The file opens in the editor

### Write the Code:

Type this into `hello.py`:

```python
# My first Python program
print("Hello World!")
print("My name is [Your Name]")
print("I'm learning Python!")
```

(Replace `[Your Name]` with your actual name)

5. Save the file:
   - Windows: `Ctrl+S`
   - Mac: `Cmd+S`

---

## Step 5: Run Your Program

### Run from Terminal:

1. Make sure your terminal is still open
   - Windows: `` Ctrl+` `` if not
   - Mac: `` Cmd+` `` if not

2. Make sure `(class-env)` shows in your prompt (if not, activate it):
   - Windows: `class-env\Scripts\activate`
   - Mac: `source class-env/bin/activate`

3. Run your program:

   **Windows**:
   ```bash
   python hello.py
   ```

   **Mac**:
   ```bash
   python3 hello.py
   ```

   Or if you set up the alias in the installation guide:
   ```bash
   python hello.py
   ```

4. You should see output like:
   ```
   Hello World!
   My name is [Your Name]
   I'm learning Python!
   ```

**Congratulations!** You just wrote and ran your first Python program!

### Alternative: Run with VS Code Button:

You can also click the **▶ Run** button in the top right of the editor. This does the same thing.

---

## Step 6: Commit and Push to GitHub

Now let's save your changes to Git and upload them to GitHub.

### Understanding Git:

- **Working directory**: Your files right now
- **Staging**: Selecting which changes to save
- **Commit**: Saving a snapshot with a message
- **Push**: Uploading commits to GitHub

### Make Your First Commit:

1. In VS Code, click the **Source Control** icon in the left sidebar (looks like a branch)

2. You should see your changed files listed:
   - `hello.py` (new file)
   - `class-env/` might show (we'll ignore this)

3. We don't want to commit the `class-env` folder (it's huge and recreatable). Check that `.gitignore` is working:
   - Open `.gitignore`
   - You should see lines about ignoring virtual environments
   - If `class-env/` shows in Source Control, add this line to `.gitignore`:
     ```
     class-env/
     ```
   - Save `.gitignore`

4. Now in Source Control, hover over `hello.py` and click the **+** icon (Stage Changes)
   - If you modified `.gitignore`, stage that too

5. In the text box at the top that says "Message", type:
   ```
   Add hello world program
   ```

6. Click the **✓ Commit** button (or press `Ctrl+Enter`)

7. Click **Sync Changes** (or the cloud icon with an arrow)

8. If prompted "Would you like to periodically run 'git fetch'?", click **Yes**

### Verify on GitHub:

1. Go to your repository on GitHub (in your web browser)

2. Refresh the page

3. You should now see `hello.py` in your repository!

4. Click on it to see your code online

**Success!** Your code is now backed up on GitHub and visible to others.

---

## Step 7: Use Claude AI to Write a Program

Now let's use AI assistance to write a more interesting program.

### Start Claude Code:

1. In your VS Code terminal (make sure you're still in your project folder):
   ```bash
   claude-code
   ```

2. Claude Code should start up. You'll see a welcome message and a prompt

3. If prompted to authenticate, follow the instructions to log in with your Claude account

### Ask Claude to Write a Program:

At the Claude prompt, type:

```
Write a Python program that asks the user for their name and age, then calculates and tells them what year they were born. Save it to a file called age_calculator.py
```

Press Enter and watch Claude work!

### What Claude Does:

Claude will:
- Write the code for you
- Create the file `age_calculator.py`
- Explain what the code does

### Review the Code:

1. Look at the `age_calculator.py` file Claude created in your Explorer

2. Read through it to understand what it does

3. Claude might use concepts like:
   - `input()` - Getting user input
   - `int()` - Converting text to numbers
   - Current year calculation
   - Basic arithmetic

### Test the Program:

1. Exit Claude Code (type `exit` or press `Ctrl+C`)

2. Run the program:
   ```bash
   python age_calculator.py
   ```

3. Follow the prompts and enter your information

4. Check that the output makes sense!

### Optional: Ask Claude to Improve It:

If you want, restart `claude-code` and ask:
```
Can you add error handling to age_calculator.py in case the user enters something that's not a number?
```

Claude will update the file with better error handling.

---

## Step 8: Commit and Push Your AI-Assisted Code

Let's save this new program to GitHub too.

### Commit the Changes:

1. Click the **Source Control** icon again

2. You should see `age_calculator.py` (and possibly other files Claude created)

3. Review the changes:
   - Click on `age_calculator.py` to see what's new (marked in green)

4. Stage the changes:
   - Click the **+** icon next to `age_calculator.py`
   - Stage any other Python files Claude created

5. Write a commit message:
   ```
   Add age calculator program with Claude AI
   ```

6. Click **✓ Commit**

7. Click **Sync Changes** to push to GitHub

### Verify on GitHub:

1. Refresh your GitHub repository page

2. You should now see both:
   - `hello.py` (your first program)
   - `age_calculator.py` (Claude's program)

3. Click **Commits** (below the green Code button) to see your commit history

**Excellent!** You've now completed the full workflow from idea to code to GitHub.

---

## Summary: Your New Workflow

Here's the workflow you'll use for every project:

### One-Time Setup (Per Project):
1. Create GitHub repo (with README)
2. Clone to your computer
3. Create virtual environment with `uv venv class-env`
4. Activate environment:
   - Windows: `class-env\Scripts\activate`
   - Mac: `source class-env/bin/activate`
5. Install packages: `uv pip install [packages]`

### Regular Workflow:
1. Open project in VS Code
2. Open terminal and activate environment
3. Write/edit code (with or without Claude's help)
4. Test your code (run with `python` on Windows, `python3` on Mac)
5. Stage changes (Source Control → + icon)
6. Commit (write message → ✓)
7. Push to GitHub (Sync Changes)
8. Repeat!

---

## Common Tasks Reference

### Opening Your Project Later:

1. Open VS Code
2. **File → Open Folder**
3. Navigate to your project folder
4. Click **Select Folder**
5. Open terminal:
   - Windows: `` Ctrl+` ``
   - Mac: `` Cmd+` ``
6. Activate environment:
   - Windows: `class-env\Scripts\activate`
   - Mac: `source class-env/bin/activate`

### Installing More Packages:

```bash
# Make sure environment is activated first!
uv pip install package-name
```

### Using Claude Code:

```bash
# Start Claude Code
claude-code

# Ask questions like:
# - "Explain what this code does"
# - "Write a function that [does something]"
# - "How can I fix this error?"
# - "Add comments to this code"

# Exit Claude Code
exit
```

### Git Commands (Terminal):

```bash
git status              # See what changed
git add filename.py     # Stage a specific file
git add .               # Stage all changes
git commit -m "message" # Commit with message
git push                # Push to GitHub
git pull                # Get latest changes from GitHub
```

---

## Troubleshooting

### "python is not recognized" or "command not found"
- Make sure you activated your virtual environment:
  - Windows: `class-env\Scripts\activate`
  - Mac: `source class-env/bin/activate`
- You should see `(class-env)` in your prompt
- On Mac, try `python3` instead of `python`

### Can't activate virtual environment
- Make sure you're in the project folder (where `class-env` exists)
- **Windows**: Use PowerShell or Command Prompt, not Git Bash
  - Try: `.\class-env\Scripts\activate` (with the dot-slash)
- **Mac**: Make sure you're using `source class-env/bin/activate`
  - Check permissions: `ls -la class-env/bin/activate`

### VS Code doesn't see my virtual environment
- Open Command Palette:
  - Windows: `Ctrl+Shift+P`
  - Mac: `Cmd+Shift+P`
- Type "Python: Select Interpreter"
- Choose the one that shows `class-env`

### Claude Code won't start
- Make sure you're logged in: the first time requires authentication
- Check you have internet connection
- Try logging out and back in to claude.ai

### Git won't push to GitHub
- Make sure you're logged into GitHub in your browser
- VS Code may prompt for GitHub login - click Sign In
- Check your internet connection

### "Permission denied" errors
- **Windows**: You may need to run VS Code as administrator
  - Right-click VS Code icon → Run as administrator
- **Mac**: Check file permissions
  - Try: `chmod +x filename.py` to make a file executable
  - Or use `sudo` if modifying system files (rare for beginners)

---

## What's Next?

Now that you have the basics down, you can:

1. **Practice the workflow**: Create more small programs and commit them

2. **Explore Claude Code**: Ask it to explain Python concepts or write example code

3. **Learn Python fundamentals**: Variables, functions, loops, conditions

4. **Try Jupyter Notebooks**:
   - Create a new file with `.ipynb` extension
   - VS Code will open it as a notebook
   - Great for data science and learning!

5. **Work on class assignments**: Use this same workflow for all your coursework

---

## Tips for Success

1. **Commit often**: Small, frequent commits are better than huge ones
   - Good: "Add input validation"
   - Bad: "Updated everything" after 3 days of work

2. **Write clear commit messages**: Your future self will thank you
   - Good: "Fix calculation error in age_calculator"
   - Bad: "stuff" or "changes"

3. **Always activate your environment**: Before running any code, make sure you see `(class-env)`

4. **Use Claude as a learning tool**: Don't just copy code - ask Claude to explain it too

5. **Read the code Claude writes**: Understand it before using it

6. **Test your code**: Always run it to make sure it works

7. **Push to GitHub regularly**: Your code is backed up and your instructor can see your progress

---

## Need Help?

- **Python errors**: Read the error message carefully - it usually tells you what's wrong
- **Git confused**: When in doubt, check `git status` to see what's happening
- **VS Code questions**: Press `F1` for the Command Palette and search for what you need
- **Claude Code help**: Just ask Claude! Try: "How do I [do something]?"

**Remember**: Everyone struggles with this stuff at first. The more you practice this workflow, the more natural it becomes!

---

## Congratulations! 🎉

You've completed your first Python project from start to finish:
- ✅ Created a GitHub repository
- ✅ Cloned it locally
- ✅ Set up a virtual environment
- ✅ Wrote and ran a program
- ✅ Committed and pushed to GitHub
- ✅ Used AI assistance to write code
- ✅ Synced everything back to GitHub

You're now ready to start coding! Every project from here will follow this same basic pattern.

**Happy coding!**
