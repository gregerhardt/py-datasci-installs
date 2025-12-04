# Python Setup for Data Science

Welcome! This guide will help you set up a complete Python development environment for data science and statistical analysis.

## Who This Is For

This setup is designed for **beginning programmers** who want to:
- Learn Python programming fundamentals
- Analyze data with Python
- Work with statistics and data visualization
- Use modern AI tools to assist with coding
- Follow professional development practices

**No prior programming experience required!** These guides will walk you through everything step-by-step.

---

## About These Tutorials

These tutorials were created using AI (Claude) as a collaborative tool. The instructor worked with Claude to:
- Select the best modern tools for beginners
- Compare different approaches (e.g., uv vs conda, GitHub-first workflow)
- Design clear, step-by-step instructions
- Ensure cross-platform support (Windows and Mac)

**Want to see how it was made?** Check out [creation-chat.md](creation-chat.md) to see the full conversation that produced these tutorials. It's a great example of how AI can be used as a thought partner in educational design.

**Key philosophy**: These tutorials prioritize modern, fast, industry-standard tools that teach transferable skills. Every choice was made with beginner success in mind.

---

## Getting Started

Follow these tutorials **in order**:

### 1. [Installation Guide](installation-guide.md)

**Start here!** This guide walks you through setting up your development environment on **Windows or Mac**.

You'll install:
- Git (version control)
- Python (programming language)
- uv (package manager)
- VS Code (code editor)
- Claude Code (AI coding assistant)

**Time required**: 1-2 hours (including downloads)

**Important**: Follow every step carefully. Many beginners skip important checkboxes during installation and run into problems later.

---

### 2. [Getting Started Tutorial](getting-started-tutorial.md)

**Do this after completing the installation guide.** This tutorial teaches you the complete workflow you'll use for all your projects.

You'll learn to:
- Create a GitHub repository
- Clone it to your computer
- Set up a Python virtual environment
- Write your first program
- Use Git to track changes
- Push your code to GitHub
- Use Claude AI to write code
- Sync everything online

**Time required**: 30-45 minutes

**Important**: Don't skip this! Understanding this workflow is essential for all future work.

---

## Why These Tools?

Here's why we selected each component of this setup:

### Python (from python.org)

**What it is**: The programming language you'll write code in.

**Why this version**:
- Official Python distribution - the standard
- Lightweight (25 MB vs 3+ GB for Anaconda)
- Teaches best practices used in industry
- Most documentation and tutorials assume this version

**Alternative we didn't choose**: Anaconda is popular in data science but bloated (250+ packages most beginners never use) and creates a non-standard environment that can confuse learners.

---

### uv (Package Manager)

**What it is**: A tool for installing Python packages and managing virtual environments.

**Why uv**:
- **Extremely fast**: 10-100x faster than pip or conda
- **Modern**: Released in 2023, represents the future of Python packaging
- **Simple**: One tool, clear commands, easy to understand
- **Industry-standard workflow**: Uses PyPI (Python Package Index) like the rest of the Python world
- **Great error messages**: Helps beginners understand what went wrong

**Alternative we didn't choose**: Conda/mamba are slower and teach a separate ecosystem (conda-forge) that's primarily used in data science, not in broader Python development.

**What about pip?**: uv is essentially a much faster version of pip with better dependency resolution. Learning uv means you understand pip too.

---

### VS Code (Code Editor)

**What it is**: Where you'll write and run your code.

**Why VS Code**:
- **Free and professional**: Used by millions of developers worldwide
- **Excellent Python support**: IntelliSense, debugging, integrated terminal
- **Jupyter notebook support**: Write notebooks without opening a browser
- **Git integration**: Visual interface for version control
- **Extensible**: Add features as you need them
- **Lightweight**: Fast to start and use
- **Cross-platform**: Works on Windows, Mac, Linux

**Alternatives we didn't choose**:
- **PyCharm**: More powerful but heavier, steeper learning curve
- **Jupyter Lab**: Great for notebooks but not general-purpose
- **Spyder**: Data science focused but less industry-relevant
- **IDLE**: Too basic, lacks modern features

---

### Git & GitHub (Version Control)

**What it is**: A system for tracking changes to your code and backing it up online.

**Why Git/GitHub**:
- **Industry standard**: Every professional developer uses version control
- **Backup**: Your code is safe even if your computer crashes
- **Collaboration**: Share code with instructors and classmates
- **Portfolio**: Show your work to future employers
- **Learning tool**: See how your code evolved over time
- **Free**: GitHub is free for students and individuals

**Key concept**: Git tracks changes locally, GitHub stores them online.

---

### Claude Code (AI Assistant)

**What it is**: An AI tool that helps you write and understand code.

**Why Claude Code**:
- **Learning accelerator**: Get explanations and examples instantly
- **Reduces frustration**: Helps when you're stuck
- **Write better code**: Learn from AI-generated examples
- **Integrated**: Works right in your terminal/VS Code
- **Free tier**: Generous usage limits for students
- **Modern skill**: Learning to work with AI is increasingly important

**How to use it well**:
- Don't just copy code - ask Claude to explain what it does
- Use it to learn, not to skip learning
- Experiment and modify the code Claude writes
- Ask "why" questions to understand concepts

**Important**: Claude is a tool to help you learn faster, not a replacement for understanding the code.

---

### Essential Python Packages

These packages are installed in the Getting Started tutorial:

#### numpy
- **What**: Numerical computing (arrays, matrices, math)
- **Why**: Foundation for all data science work in Python

#### pandas
- **What**: Data manipulation (spreadsheet-like operations)
- **Why**: Industry standard for working with tabular data

#### statsmodels
- **What**: Statistical modeling and testing
- **Why**: Essential for statistical analysis

#### matplotlib
- **What**: Data visualization (plots, charts, graphs)
- **Why**: Most fundamental plotting library

#### seaborn
- **What**: Statistical data visualization (prettier plots)
- **Why**: Built on matplotlib, easier for statistical graphics

#### jupyter
- **What**: Interactive notebooks (mix code, text, and visualizations)
- **Why**: Standard for data science, great for learning and exploration

---

## What About...?

### Why not Anaconda?

Anaconda was revolutionary 10 years ago when installing scientific Python packages on Windows was difficult. Today:
- Modern pip/uv handle binary packages seamlessly
- Anaconda's 3+ GB install is mostly unused packages
- Conda's separate ecosystem causes confusion ("do I use pip or conda?")
- Standard Python + uv is faster and teaches transferable skills

**If you already use Anaconda**: That's fine! But for new learners, the standard Python approach is simpler.

### Why not use the browser for Jupyter?

VS Code's notebook support gives you:
- Everything in one window (no browser tabs)
- Better debugging tools
- Integrated Git
- The same interface for .py files and .ipynb files
- Faster startup

You can still use Jupyter Lab if you prefer - it's installed!

### Why not Docker or other advanced tools?

For beginners:
- Virtual environments (`uv venv`) provide enough isolation
- Docker adds complexity without clear benefits for learning
- Simple setup means less that can go wrong
- Focus should be on learning Python, not DevOps

As you advance, you can add these tools later.

---

## Philosophy of This Setup

This setup follows these principles:

1. **Standard over specialized**: Learn the tools most Python developers use
2. **Simple over powerful**: Minimize complexity while learning
3. **Fast over comprehensive**: Quick installs reduce frustration
4. **Modern over traditional**: Use current best practices
5. **Transferable over specific**: Skills that apply broadly

The goal is to get you writing code quickly while building habits that will serve you throughout your career.

---

## After You Finish

Once you complete both tutorials, you'll be ready to:

1. **Start your coursework**: Create repos for assignments
2. **Experiment**: Try writing simple programs
3. **Explore data**: Load CSV files with pandas
4. **Make visualizations**: Create plots with matplotlib
5. **Ask Claude**: Get help when you're stuck
6. **Build your portfolio**: All your GitHub repos show your progress

---

## Getting Help

If you encounter problems:

1. **Read error messages carefully**: They usually tell you what's wrong
2. **Check the troubleshooting sections**: Both guides have common solutions
3. **Ask Claude**: Start `claude-code` and describe your problem
4. **Search the error**: Copy/paste error messages into Google
5. **Ask your instructor**: That's what they're there for!

---

## Additional Resources

Once comfortable with the basics, explore:

- **Official Python Tutorial**: [docs.python.org/3/tutorial](https://docs.python.org/3/tutorial/)
- **Pandas Documentation**: [pandas.pydata.org](https://pandas.pydata.org/)
- **Python Graph Gallery**: [python-graph-gallery.com](https://python-graph-gallery.com/) (visualization examples)
- **Real Python**: [realpython.com](https://realpython.com/) (tutorials for all levels)

---

## Quick Start Checklist

Ready to begin? Here's your roadmap:

- [ ] Read this README (you're here!)
- [ ] Complete [Installation Guide](installation-guide.md)
- [ ] Verify all installations work
- [ ] Complete [Getting Started Tutorial](getting-started-tutorial.md)
- [ ] Create your first "Hello World!" program
- [ ] Use Claude to write your first AI-assisted program
- [ ] Push everything to GitHub
- [ ] Celebrate! You're now a Python developer!

---

## Learning from the Creation Process

Curious about how these tutorials were designed? The [creation-chat.md](creation-chat.md) file contains the complete conversation between the instructor and Claude AI that produced these materials. It shows:

- How tool choices were evaluated and debated
- Why certain approaches were chosen over others
- The iterative refinement process
- How to use AI as a collaborative partner in education

Reading through the creation process can give you insights into how to use AI effectively for learning and creating educational content.

---

**Ready? Start with the [Installation Guide](installation-guide.md)!**

Good luck, and welcome to the world of Python programming!
