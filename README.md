# Ubuntu + Python + Git Terminal Cheat Sheet (DAMSL Edition)

## 📁 File & Directory Management
| Command | Description |
| --- | --- |
| ls | List files in current directory |
| ls -la | List all files with details |
| cd folder_name | Change directory |
| cd | Go to home directory |
| cd .. | Go up one directory |
| cd - | Go to previous directory |
| mkdir folder_name | Create a new folder |
| rm file | Delete file |
| rm -rf folder | Force delete folder and contents |
| cp source dest/ | Copy file/folder |
| mv old new | Move or rename file/folder |
| touch file.txt | Create empty file |
## 📄 File Viewing & Editing
| Command | Description |
| --- | --- |
| cat file.txt | Show file contents |
| less file.txt | Scrollable view of file |
| nano file.txt | Edit file in nano editor |
| code . | Open folder in VS Code (if installed) |
## 🔍 Search & Navigation
| Command | Description |
| --- | --- |
| find . -name '*.py' | Find all `.py` files |
| grep "pattern" file.txt | Search for text in a file |
| grep -r "text" folder/ | Recursive search in folder |
| pwd | Show current directory |
| history | View command history |
## 🧰 System Utilities
| Command | Description |
| --- | --- |
| whoami | Show current user |
| df -h | Show disk usage |
| free -h | Show memory usage |
| top / htop | Process monitor (install `htop`) |
| uptime | System uptime |
## 📦 Package Management (APT)
| Command | Description |
| --- | --- |
| sudo apt update | Refresh package index |
| sudo apt upgrade | Upgrade installed packages |
| sudo apt install pkgname | Install package |
| sudo apt remove pkgname | Remove package |
## 🐍 Python & pyenv
| Command | Description |
| --- | --- |
| python3 --version | Show system Python version |
| pyenv install 3.11.13 | Install specific Python version |
| pyenv global 3.11.13 | Set global Python version |
| pyenv local 3.11.13 | Set version only for current folder |
| pyenv versions | List installed versions |
| pyenv which python | Show path to Python binary |
| poetry init | Create new Poetry project |
| poetry env use $(pyenv which python) | Link Poetry to pyenv Python |
| poetry env list | Lists all exiting environments |
| Poetry env remove <env> | Removes poetry environment |
| poetry add <package> | Add dependency |
| Poetry install | Install all libraries in toml |
| poetry shell | Activate project virtual environment |
## 🔐 SSH & Remote Access
| Command | Description |
| --- | --- |
| ssh user@host | Connect to remote machine |
| ssh -i ~/.ssh/id_rsa user@host | Use specific SSH key |
| ssh-keygen -t ed25519 | Generate new SSH key |
| cat ~/.ssh/id_ed25519.pub | Show public key to add to GitHub/remote |
| scp file user@host:/remote/path | Copy file to remote server |
| scp user@host:/remote/file ./local/ | Copy file from remote server |
## 🧠 Shortcuts
| Command | Description |
| --- | --- |
| Ctrl + C | Cancel current command |
| Ctrl + D | Exit terminal or virtual env |
| Ctrl + L | Clear terminal screen |
| ↑ / ↓ | Navigate command history |
| Tab | Autocomplete files or commands |
| !! | Repeat last command |
| Ctrl+ | Move by word instead of character |
## 🌿 Git Essentials
| Command | Description |
| --- | --- |
| git init | Initialize a new Git repository |
| git clone <url> | Clone a remote repository |
| git status | Check status of working directory |
| git add <file> | Stage changes for commit |
| git add . | Stage all changes |
| git commit -m 'msg' | Commit staged changes with message |
| git log | View commit history |
| git branch | List branches |
| git checkout <branch> | Switch to branch |
| git checkout -b <branch> | Create and switch to new branch |
| git merge <branch> | Merge branch into current |
| git pull | Fetch and merge from remote |
| git push | Push local commits to remote |
| git remote -v | List remote connections |
| git config --global user.name/email | Set global Git username/email |
