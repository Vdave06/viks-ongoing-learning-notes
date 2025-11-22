# Vik's Learning Notes

My personal development reference guide - everything I'm learning about coding, Git, VS Code, and development tools.

**Started:** November 2024  
**Goal:** Build foundation for using GitHub Copilot with repositories and creating prototypes

## Table of Contents
- [Git Workflow](#git-workflow---step-by-step-process)
- [Complete Cheat Sheet](#complete-cheat-sheet)
- [Daily Practice Routine](#your-practice-routine)
- [Backstage Setup](#backstage-local-setup)


## 1. 
## GIT WORKFLOW - STEP-BY-STEP PROCESS
*Practice this sequence repeatedly until it's automatic*

### Initial Setup (One-time per project)
```bash
# 1. Navigate to where you want your project
# MAC:
cd ~/Documents/Projects
# WINDOWS:
cd C:\Users\YourName\Documents\Projects

# 2. Create new project folder
# MAC & WINDOWS (same):
mkdir project-name

# 3. Enter the folder
# MAC & WINDOWS (same):
cd project-name

# 4. Initialize Git
# MAC & WINDOWS (same):
git init

# 5. Create your first file
# MAC:
echo "# Project Name" > README.md
# WINDOWS:
echo # Project Name > README.md

# 6. Check status (should show untracked files)
# MAC & WINDOWS (same):
git status
# VS CODE: Check Source Control panel - files show with "U" (untracked)

# 7. Add files to staging
# MAC & WINDOWS (same):
git add .
# VS CODE: Click + next to files or Changes header

# 8. Make first commit
# MAC & WINDOWS (same):
git commit -m "Initial commit"
# VS CODE: Type message in box, click ✓

# 9. Create GitHub repo (via browser), then link it
# MAC & WINDOWS (same):
git remote add origin https://github.com/Vdave06/repository-name.git

# 10. Push to GitHub
# MAC & WINDOWS (same):
git push -u origin main
# VS CODE: Click ... menu → Push
```

### Daily Workflow (Repeat this constantly)
```bash
# 1. Start your work session - check where you are
# MAC:
pwd
# WINDOWS:
cd (just cd by itself shows current directory)
# MAC & WINDOWS (same):
git status
# VS CODE: Open Source Control panel (Cmd/Ctrl+Shift+G) to see visual status

# 2. Pull latest changes (if working with others)
# MAC & WINDOWS (same):
git pull
# VS CODE: Click ... menu → Pull

# 3. Make your changes - PRACTICE EXERCISES (do one each day)

## OPTION A - Add a daily log entry
# Open VS Code in current folder
# MAC & WINDOWS (same):
code .

# Create or edit a file called daily-log.md
# MAC:
echo "## $(date '+%Y-%m-%d')" >> daily-log.md
echo "Today I practiced Git commands" >> daily-log.md
# WINDOWS:
echo ## %date% >> daily-log.md
echo Today I practiced Git commands >> daily-log.md

## OPTION B - Create a new feature file
# MAC:
touch feature-$(date +%Y%m%d).txt
echo "This is a new feature added on $(date)" > feature-$(date +%Y%m%d).txt
# WINDOWS:
echo This is a new feature > feature-%date:~-4,4%%date:~-10,2%%date:~-7,2%.txt

## OPTION C - Update the README
# MAC:
echo "- Updated on $(date '+%Y-%m-%d')" >> README.md
# WINDOWS:
echo - Updated on %date% >> README.md

## OPTION D - Create a practice Python file
# MAC & WINDOWS (same):
# In VS Code, create a new file called practice.py
# Type this content:
# print("Hello from Vik")
# print("Today's Git practice")
# Save the file (Cmd+S on Mac, Ctrl+S on Windows)

## OPTION E - Modify existing file
# Open any existing file in VS Code
# Add a comment line at the top:
# "# Modified by Vik on [today's date]"
# Save the file

# 4. Check what changed - TWO WAYS TO SEE SAME INFO
# TERMINAL METHOD:
# MAC & WINDOWS (same):
git status
git diff

# VS CODE METHOD:
# Look at Source Control panel (Cmd/Ctrl+Shift+G)
# You'll see files with:
# - M badge (modified) 
# - U badge (untracked/new)
# - Number badge shows count of changed files

# 5. Stage your changes - CHOOSE YOUR METHOD

## TERMINAL METHOD:
git add .
# OR stage specific files
git add filename.txt

## VS CODE METHOD:
# Click the "+" next to each file in Source Control panel
# Files move from "

Changes" section to "Staged Changes" section
# OR click + next to "Changes" header to stage all

# 6. Commit with meaningful message - CHOOSE YOUR METHOD

## TERMINAL METHOD:
git commit -m "Add: daily log entry for practice"
# Other message examples:
# git commit -m "Add: new feature file"
# git commit -m "Update: README with today's date"
# git commit -m "Add: practice Python script"
# git commit -m "Update: added modification comment"

## VS CODE METHOD:
# Type message in the box at top of Source Control
# Click the checkmark ✓ button
# Staged files disappear, commit is made

# 7. Push to GitHub - CHOOSE YOUR METHOD

## TERMINAL METHOD:
git push

## VS CODE METHOD:
# Click "..." menu in Source Control → Push
# OR click the sync icon (circular arrows)

# 8. Verify on GitHub.com that changes appear
# Open browser, go to your repository and check the changes are there


## 2. 
## COMPLETE CHEAT SHEET, TERMINAL/COMMAND LINE BASICS, Navigation Commands
bash# 

MAC:
pwd                 # Where am I? (Print Working Directory)
# WINDOWS:
cd                  # Where am I? (just cd by itself)

# MAC:
ls                  # List files in current folder
# WINDOWS:
dir                 # List files in current folder

# MAC:
ls -la              # List ALL files with details
# WINDOWS:
dir /a              # List ALL files with details

# MAC & WINDOWS (same):
cd folder-name      # Change into a folder
cd ..               # Go up one level

# MAC:
cd ~                # Go to home directory
# WINDOWS:
cd %USERPROFILE%    # Go to home directory

# MAC:
cd ~/Documents      # Go to Documents folder
# WINDOWS:
cd C:\Users\YourName\Documents  # Go to Documents folder

# MAC:
clear               # Clear the terminal screen
# WINDOWS:
cls                 # Clear the terminal screen

##File & Folder Operations
bash#

MAC & WINDOWS (same):
mkdir folder-name   # Create new folder

# MAC:
touch file.txt      # Create new empty file
# WINDOWS:
type nul > file.txt # Create new empty file

# MAC:
echo "text" > file  # Create file with content
# WINDOWS:
echo text > file    # Create file with content (no quotes needed)

# MAC:
cat file.txt        # View file contents
# WINDOWS:
type file.txt       # View file contents

# MAC:
rm file.txt         # Delete file
# WINDOWS:
del file.txt        # Delete file

# MAC:
rm -rf folder       # Delete folder and contents
# WINDOWS:
rmdir /s folder     # Delete folder and contents

# MAC:
cp file1 file2      # Copy file
# WINDOWS:
copy file1 file2    # Copy file

# MAC:
mv file1 file2      # Rename/move file
# WINDOWS:
move file1 file2    # Move file
ren file1 file2     # Rename file

##GIT COMMANDS - Good news - ALL Git commands are the same on Mac and Windows!
Setup & Configuration

bash

git --version               # Check Git is installed
git config --global user.name "Your Name"
git config --global user.email "your.email@example.com"
git config --list          # View all settings

Starting a Repository

bash

git init                    # Initialize new repo
git clone [url]             # Copy existing repo from GitHub

Basic Workflow Commands

bash
git status                  # What's changed? (USE CONSTANTLY!)
git add .                   # Stage all changes
git add file.txt           # Stage specific file
git commit -m "message"    # Save changes with message
git push                   # Upload to GitHub
git pull                   # Download latest from GitHub

Viewing History

bash

git log                    # View commit history
git log --oneline         # Compact history view
git diff                  # See unstaged changes
git diff --staged         # See staged changes

Branches (For later)

bash

git branch                # List branches
git branch new-branch    # Create branch
git checkout branch-name # Switch branches
git merge branch-name    # Merge branch

Fixing Mistakes

bash

git restore file.txt      # Undo changes to file
git restore --staged file # Unstage a file
git reset HEAD~1         # Undo last commit (keep changes)
git reset --hard HEAD~1  # Undo last commit (lose changes)

Remote Repository (GitHub)

bash

git remote -v                    # View remotes
git remote add origin [url]      # Connect to GitHub
git push -u origin main          # First push
git push                         # Regular push
git pull                         # Get latest changes
```

### VS CODE SHORTCUTS

#### Essential Shortcuts (Mac)
```
Cmd + S              # Save file
Cmd + P              # Quick file open
Cmd + Shift + P      # Command palette
Cmd + B              # Toggle sidebar
Cmd + `              # Toggle terminal
Cmd + /              # Comment line
Cmd + F              # Find
Cmd + Shift + F      # Find in all files
Cmd + Z              # Undo
Cmd + Shift + Z      # Redo
Cmd + Shift + G      # Open Source Control panel
```

#### Essential Shortcuts (Windows)
```
Ctrl + S             # Save file
Ctrl + P             # Quick file open
Ctrl + Shift + P     # Command palette
Ctrl + B             # Toggle sidebar
Ctrl + `             # Toggle terminal
Ctrl + /             # Comment line
Ctrl + F             # Find
Ctrl + Shift + F     # Find in all files
Ctrl + Z             # Undo
Ctrl + Shift + Z     # Redo
Ctrl + Shift + G     # Open Source Control panel
```

#### File Management
```
# MAC:
Cmd + N              # New file
Cmd + O              # Open file
Cmd + W              # Close file
Cmd + Shift + T      # Reopen closed file

# WINDOWS:
Ctrl + N             # New file
Ctrl + O             # Open file
Ctrl + W             # Close file
Ctrl + Shift + T     # Reopen closed file
```

#### Terminal in VS Code
```
# MAC:
Cmd + `              # Open/close terminal
Cmd + \              # Split terminal
Clear                # Clear terminal
Cmd + K              # Clear terminal (alternative)

# WINDOWS:
Ctrl + `             # Open/close terminal
Ctrl + \             # Split terminal
cls                  # Clear terminal
Ctrl + K             # Clear terminal (alternative)
```

### VS CODE SOURCE CONTROL PANEL

#### Understanding the Source Control Panel
```
The Source Control panel shows Git status visually
- Same information as 'git status' in terminal
- Updates automatically when files change
- Can perform all Git operations with clicks
```

#### Visual Git Interface Symbols
```
U = Untracked (new file Git doesn't know about)
M = Modified (existing file you changed)
A = Added (staged for commit)
D = Deleted (file removed)
C = Conflicted (merge conflict to resolve)
! = Ignored (file in .gitignore)

Number badges = Count of files in that state
+ button = Stage this file (git add)
- button = Unstage this file
↻ button = Undo changes (git restore)
✓ button = Commit staged changes
... menu = More options (push, pull, etc.)
```

#### Source Control Sections
```
CHANGES section = Unstaged changes (need to git add)
STAGED CHANGES section = Ready to commit (already git added)
MERGE CHANGES section = Files with conflicts (during merge)


## Using Source Control Panel vs Terminal - SAME ACTIONS, DIFFERENT METHODS

bash

# TERMINAL COMMAND          # VS CODE EQUIVALENT
git status                  # Look at Source Control panel
git add file.txt           # Click + next to file
git add .                  # Click + next to "Changes" header
git restore file.txt       # Click ↻ next to file
git restore --staged file  # Click - next to staged file
git commit -m "message"    # Type message, click ✓
git push                   # Click ... → Push
git pull                   # Click ... → Pull
git log                    # Click ... → View History
```

#### When to Use Which Method
```
USE TERMINAL WHEN:
- Learning Git fundamentals
- Fixing complex problems
- Working on remote servers
- Need precise control

USE VS CODE SOURCE CONTROL WHEN:
- Quick commits during coding
- Visual overview of changes
- Reviewing file differences
- Convenient clicking preferred

BOTH ARE VALID - Use what feels natural!


## BACKSTAGE LOCAL SETUP - Prerequisites Check

bash
# Check if Node.js is installed
# MAC & WINDOWS (same):
node --version
# Should show v20.x.x or higher

# Check if Yarn is installed
# MAC & WINDOWS (same):
yarn --version
# Should show 4.x.x or higher
```

#### Method 1: Download from GitHub Website (Simpler)
```
# Step 1: Go to Backstage repository
https://github.com/backstage/backstage

# Step 2: Download as ZIP
- Click green "<> Code" button
- Click "Download ZIP"

# Step 3: Extract the ZIP
# MAC:
- Go to Downloads folder
- Double-click backstage-master.zip
- Move extracted folder to Documents

# WINDOWS:
- Go to Downloads folder
- Right-click backstage-master.zip → Extract All
- Move extracted folder to Documents

# Step 4: Navigate to folder
# MAC:
cd ~/Documents/backstage-master
# WINDOWS:
cd C:\Users\YourName\Documents\backstage-master

## Method 2: Clone with Git (Better for updates)

bash

# Navigate to Documents
# MAC:
cd ~/Documents
# WINDOWS:
cd C:\Users\YourName\Documents

# Clone the repository
# MAC & WINDOWS (same):
git clone https://github.com/backstage/backstage.git

# Enter the folder
# MAC & WINDOWS (same):
cd backstage

## Install and Run Backstage

bash 
# Step 1: Check you're in right folder
# MAC & WINDOWS (same):
pwd                     # Shows current directory
ls                      # Should show packages, plugins, README.md

# Step 2: Install dependencies (takes 5-10 minutes)
# MAC & WINDOWS (same):
yarn install
# WHAT HAPPENS:
# - Downloads all packages (hundreds)
# - Shows progress bars
# - Warnings are normal, errors are not

# Step 3: Run Backstage locally
# MAC & WINDOWS (same):
yarn dev
# WHAT HAPPENS:
# - Starts Backstage on http://localhost:3000
# - Opens browser automatically
# - First run takes few minutes to compile

# Step 4: Stop Backstage
# MAC & WINDOWS (same):
Ctrl + C                # Stops the running server

## Understanding Backstage Files

bash

# Key files to recognize:
package.json            # Node.js project file
yarn.lock              # Locked dependency versions
tsconfig.json          # TypeScript configuration
README.md              # Project documentation

# Main folders:
packages/              # Core Backstage code
plugins/               # Additional features
docs/                  # Documentation
```

#### Setting Up VS Code Command (if not working)
```
# MAC:
1. Open VS Code from Applications
2. Press Cmd+Shift+P
3. Type: shell command
4. Select: "Shell Command: Install 'code' command in PATH"
5. Enter password when asked
6. Restart terminal

# WINDOWS:
1. VS Code usually sets this up automatically
2. If not working, reinstall VS Code
3. Check "Add to PATH" during installation

# Test it works:
# MAC & WINDOWS (same):
code --version         # Should show VS Code version
code .                 # Opens current folder in VS Code


## COMMIT MESSAGE PATTERNS

bash 
"Initial commit"
"Add: new feature description"
"Fix: bug description"
"Update: what was changed"
"Remove: what was deleted"
"Refactor: what was reorganized"


## YOUR PRACTICE ROUTINE
Daily Drill (5-10 minutes)

Open terminal
Navigate to your project:

MAC: cd ~/Documents/Projects/my-first-repo
WINDOWS: cd C:\Users\YourName\Documents\Projects\my-first-repo


Check status BOTH ways:

Terminal: git status
VS Code: Look at Source Control panel


Create a practice file:

MAC: echo "Practice $(date)" > practice.txt
WINDOWS: echo Practice %date% > practice.txt


See changes in BOTH places:

Terminal shows: untracked files
Source Control shows: U badge on file


Add and commit (choose method):

Terminal: git add . then git commit -m "Add: daily practice"
VS Code: Click +, type message, click ✓


Push (choose method):

Terminal: git push
VS Code: Click ... → Push or sync icon


Verify on GitHub.com

Key Habits to Build

ALWAYS check pwd (Mac) or cd (Windows) when you open terminal
ALWAYS run git status before and after changes
ALWAYS check Source Control panel to see visual status
ALWAYS write clear commit messages
NEVER force push unless absolutely sure
CHECK GitHub.com after pushing to verify
REMEMBER Terminal and VS Code show the same Git info differently

## TROUBLESHOOTING QUICK FIXES

bash
# "Not a git repository" error
git init

# "No upstream branch" error  
git push -u origin main

# "Changes not staged" warning
git add .

# "Behind remote" error
git pull

# See what will be pushed
git status
git log origin/main..HEAD

# Source Control panel shows changes after commit
# Click refresh icon or check:
git status  # Terminal is always the truth

# VS Code and Terminal disagree
# Trust terminal, restart VS Code if needed

# Source Control shows number badge but no files
# Files might be hidden, check git status in terminal

# Can't find Source Control panel
# Use Cmd/Ctrl+Shift+G to open it
# Or click Source Control icon in activity bar (left side)

# Backstage yarn install fails
# Check Node version: node --version
# May need Node 18 or 20, not 22

# Backstage won't start
# Check port 3000 isn't in use
# Try: yarn dev --port 3001

# VS Code 'code' command not found
# MAC: Install via Command Palette
# WINDOWS: Reinstall VS Code with PATH option