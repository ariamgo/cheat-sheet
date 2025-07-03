# Ubuntu + Python + Git Terminal Cheat Sheet (DAMSL Edition)


## 📺 Table of Contents
- [📁 File & Directory Management](#-file--directory-management)
- [📄 File Viewing & Editing](#-file-viewing--editing)
- [🔍 Search & Navigation](#-search--navigation)
- [🧰 System Utilities](#-system-utilities)
- [📦 Package Management (APT)](#-package-management-apt)
- [🐍 Python & pyenv](#-python--pyenv)
- [🔐 SSH & Remote Access](#-ssh--remote-access)
- [📡 FTP & File Transfer](#-ftp--file-transfer)
- [🧠 Shortcuts](#-shortcuts)
- [🌿 Git Essentials](#-git-essentials)
- [🧹 Pre-commits](#-pre-commits)
- [📝 NumPy Docstrings](#-numpy-docstrings)
- [📄 Generating Documentation](#-generating-documentation)


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
| poetry env remove <env> | Removes poetry environment |
| poetry add <package> | Add dependency |
| poetry install | Install all libraries in toml |
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

## 📡 FTP & File Transfer

| Command | Description |
|--------|-------------|
| ftp host | Connect to an FTP server |
| sftp user@host | Connect securely via SFTP |
| scp file user@host:/path | Copy file to remote server |
| scp user@host:/file ./ | Copy file from remote server |
| rsync -avz file user@host:/path | Sync file/directory over SSH |
| rsync -avz user@host:/path ./ | Download file/directory via rsync |
| mput *.txt | Upload multiple files in FTP |
| mget *.txt | Download multiple files in FTP |
| put file.txt | Upload file in FTP |
| get file.txt | Download file in FTP |
| bye | Exit FTP session |

## 🧠 Shortcuts
| Command | Description |
| --- | --- |
| Ctrl + C | Cancel current command |
| Ctrl + D | Exit terminal or virtual env |
| Ctrl + L | Clear terminal screen |
| ↑ / ↓ | Navigate command history |
| Tab | Autocomplete files or commands (use this like you life depends on it!)|
| !! | Repeat last command |
| Ctrl+ | Move by word instead of character |

## 🌿 Git Essentials
| Command | Description |
| --- | --- |
| git init | Initialize a new Git repository |
| git config --global user.name/email | Set global Git username/email |
| git clone <url> | Clone a remote repository |
| git status | Check status of working directory |
| git add <file> | Stage changes for commit |
| git add . | Stage all changes |
| git diff | Shows unstaged changes |
| git diff --staged | Shows staged changes |
| git diff HEAD | Shows changes since last commit |
| git diff commit1 commit2 | Shows changes between commits |
| git diff branch1 branch2 | Shows changes between branches |
| git commit -m 'msg' | Commit staged changes with message |
| git commit --amend | Edit and replace the most recent commit. |
| git log | View commit history |
| git branch | List branches |
| git checkout <branch> | Switch to branch |
| git checkout -b <branch> | Create and switch to new branch |
| git merge <branch> | Merge branch into current |
| git pull | Fetch and merge from remote |
| git push | Push local commits to remote |
| git remote -v | List remote connections |
| git restore  <file> | Restore a file to its last commited state |
| git reset --soft HEAD~1 | Undo the last commit, keep changes staged |
| git stash | Temporarily save uncommited changes |
| git stash pop | Apply and remove the most recent stash |



## 🧹 Pre-commits

Pre-commits are scripts that run automatically before a commit is made. These can be used to ensure code quality by running linters, formatters, and other checks on the codebase.

### 🔧 Install & Set Up

```bash
poetry add pre-commit
pre-commit install
```

This adds the `.pre-commit-config.yaml` file, where you define the hooks you want to run.

### 📄 Example Configuration

Here's an example of a `.pre-commit-config.yaml` file:

```yaml
repos:
  - repo: https://github.com/pre-commit/pre-commit-hooks
    rev: v3.4.0
    hooks:
      - id: trailing-whitespace
      - id: end-of-file-fixer
      - id: check-yaml
  - repo: https://github.com/psf/black
    rev: 21.12b0
    hooks:
      - id: black
```

### 🔄 Usage

- Run all hooks against all files: `pre-commit run --all-files`
- Run hooks only on changed files: `pre-commit run`
- Update pre-commit hooks: `pre-commit autoupdate`

### 🪝 Linters

Analyze the code for syntax, style and potential bugs.
Catch issues like:
- Unused variables
- Wrong import order
- Missing docstrings
- 
### 🪝 Formatters

Automatically reformat code to follow a consistent style.
- Indentation
- Quote style
- Line breaks
- Comma placements

Linters and formatters get their config from `pyproject.toml`

### 📄 Example Configuration

```toml
[tool.ruff]
exclude = ["docs"]
line-length = 88
target-version = "py311"

[tool.ruff.lint]
ignore = [
  # pylint
  # No pylints
  # ruff
  "RUF001",
  # flake8-bandit
  "S101",
  ...
  "ISC001",
  "N806",
  "N803",
  "SLF001"
]
select = ["ALL"]

[tool.ruff.lint.flake8-quotes]
inline-quotes = "double"

[tool.ruff.lint.pydocstyle]
convention = "numpy"
```

## 📝 NumPy Docstrings

NumPy docstrings follow a specific format to ensure consistency and clarity. Here's a basic template for writing NumPy-style docstrings:

```python
def example_function(param1, param2):
    """
    Brief summary of the function.

    Extended description of the function, which can cover
    multiple lines and provide more detailed information.

    Parameters
    ----------
    param1 : int
        Description of the first parameter.
    param2 : str
        Description of the second parameter.

    Returns
    -------
    bool
        Description of the return value.

    Raises
    ------
    ValueError
        If `param1` is not a positive integer.

    See Also
    --------
    related_function : Description of related function.
    
    Notes
    -----
    Additional notes about the function, its usage, or implementation details.

    Examples
    --------
    >>> example_function(3, 'test')
    True
    """

    if param1 <= 0:
        raise ValueError("param1 must be a positive integer")
    # Example function logic
    return True
```

### Key Sections

- **Summary**: A one-line summary that starts with a capital letter and ends with a period.
- **Parameters**: A list of parameters with types and descriptions.
- **Returns**: Description of the return value, including type information.
- **Raises**: Any exceptions that the function may raise and the conditions under which they occur.
- **See Also**: References to related functions or methods within the module.
- **Notes**: Additional information about the function, which may include implementation details.
- **Examples**: Usage examples with the expected output, helpful for understanding function behavior.

# 📄 Generating Documentation
 
 Assuming you already have numpy docstrings in your code.

1. Add necessary packages
```bash
poetry add --group docs numpydoc sphinx sphinx-rtd-theme sphinx-math-dollar myst-parser
```

- numpydoc: Parses NumPy-style docstrings for Sphinx.
- sphinx: Turns reStructuredText or Markdown + docstrings into HTML, LaTeX, PDF, etc.
- sphinx-math-dollar: Allows you to write math equations with LaTeX dollar signs (`$...$` for inline, `$$...$$` for block).
- sphinx-rtd-theme: The [ReadTheDocs theme](https://readthedocs.io/)
- myst-parser: Enables writing docs in Markdown `.md` instead of `.rst`

2. Set up sphinx in the docs folder of your repo
```bash
poetry run sphinx-quickstart docs
```
Follow prompts on the terminal.

3. Configure conf.py
For example
```
# -- General configuration ---------------------------------------------------

extensions = [
    "sphinx.ext.autosummary",
    "sphinx.ext.autodoc",
    "numpydoc",
    "sphinx_math_dollar",
    "sphinx.ext.mathjax",
    "sphinx_rtd_theme",
    "myst_parser",  # enables Markdown support via MyST
]

templates_path = ["_templates"]
exclude_patterns = []

autosummary_generate = True
numpydoc_class_members_toctree = False

# -- Options for HTML output -------------------------------------------------

html_theme = "sphinx_rtd_theme"

# -- Options for napoleon extension ------------------------------------------
napoleon_google_docstring = False
napoleon_numpy_docstring = True
```

4. Autogenerate `.rst` files for your code
```bash
sphinx-apidoc -o docs/source your_module
```

5. Include modules into `index.rst`
Include something like:
```rst
.. toctree::
   :maxdepth: 2
   :caption: API Reference

   your_module # don't forget the indent
```

6. 📚 Build your documentation
```bash
sphinx-build -b html docs/source docs/build
```