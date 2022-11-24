# The Missing Semester

This page contains notes of past editions of *The Missing Semester* event at the University of Zurich. *The Missing Semester* aims to create an exchange of information between students of Computational or Digital Linguistics, focusing on technical and practical tools which make our lives as CL/DL students easier.

This [repository](https://github.com/saeub/missing-semester/) is currently maintained by [bernai](https://github.com/bernai/), [dominikmartinez](https://github.com/dominikmartinez/), [saeub](https://github.com/saeub/), and [vera-bernhard](https://github.com/vera-bernhard/).

## 2022/11/14: *Show How You Code (2nd ed.)*

### VS Code (Vera, Andreas)
- Why VSCode: Multilinguality: one tool for (nearly) everything via extension -> just install extension to support any programming lanugage or framework
- [VS Code](https://code.visualstudio.com/)
- Extensions: Python, LaTeX Workshop
- Some usefule shortcuts:
    - Find any command/setting in VSCode: Ctrl+Shift+P -> opens the Command Palette
    - Find any file: Ctrl+P -> opens Quick Open
    - Open integrated terminal: Ctrl+`
- For Windows Users: [WSL + VSCode](https://code.visualstudio.com/docs/remote/wsl)
- [Integrated Git GUI](https://code.visualstudio.com/docs/sourcecontrol/overview)
- How to get help:
    - VSCode Navigation: [Peek Defition](https://code.visualstudio.com/docs/editor/editingevolved#_peek), [Go to Definition](https://code.visualstudio.com/docs/editor/editingevolved#_go-to-definition), hover over function name
    - [VSCode debugger](https://code.visualstudio.com/docs/editor/debugging)
    - in Terminal: `<some_command> --help` or `man <some_command>`

### Dirty but lightweight alternatives to IDEs (Dominik)
If you don't depend on IntelliSense and other cool IDE features, there are some interesting alternative tools:
- For Windows users, if you want to work in a UNIX environment (but don't want to rely on virtual machines or dual-boot options): [Windows Subsystem for Linux (WSL)](https://learn.microsoft.com/en-us/windows/wsl/install). You can even run multiple Linux distributions!
    - WSL uses its own Linux file system. However, both file systems can be accessed from both environments:
        - `/mnt/c/` in WSL points to Windows' `C:\`.
        - `\\wsl$\<distribution>` in Windows points to the system root directory of the specified Linux distribution.
    - Pro tip: You can create shortcuts to access the file systems:
        - If you use the GUI file explorer on Windows, just create a shortcut to the directory mentioned above.
        - In WSL, use `ln -s <target> <symlink name>` to create a so-called symbolic link (which acts like a shortcut) to a directory.
    - If you want to work with multiple terminals, use [byobu](https://www.byobu.org/). With this tool, you can open and manage multiple terminals within one single WSL window.
- If you use WSL or any other UNIX environment, there are some tools that help you make your life easier:
    - [nano](https://en.wikipedia.org/wiki/GNU_nano) is a handy text editor if you need to edit a file in your terminal.
    - For Windows users: To work more comfortably, you can use [Notepad++](https://notepad-plus-plus.org/) on Windows and execute your scripts in WSL. Notepad++ offers syntax highlighting for multiple languages! Of course, there are alternative notepad editors if you work on other operating systems.
    - If you want to shorten commands you frequently use, you can do so by using aliases. It's as easy as defining them using `alias [alias_name]="[command]"`, but you find more details (e.g., on how to create persistent aliases) in [this tutorial](https://www.shell-tips.com/bash/alias/#gsc.tab=0).
- What if you don't work on a Python project, but on a web development project that involves HTML, CSS and JavaScript? One simple option is to work on the text files using your preferred text editor, and run the website using Python's [http.server module](https://docs.python.org/3/library/http.server.html). After running`python -m http.server 1111` (e.g., in your WSL terminal), the directory's content will be hosted on `http://localhost:1111`, so you can display it in your web browser on Windows.

## 2022/03/30: *Hidden Gems of Python*

- [atexit](https://docs.python.org/3/library/atexit.html)
- [dataclasses](https://docs.python.org/3/library/dataclasses.html)

## 2021/11/04: *Show How You Code*

### zsh (Berna)

- [zsh](https://www.zsh.org/) (install it using your package manager)
- Use `chsh -s $(which zsh)` to set it as your default shell
- [oh-my-zsh](https://ohmyz.sh/) (for installing plugins, themes etc.)

### VS Code, Pylance, Docstring Generator (Niclas)

- [VS Code](https://code.visualstudio.com/)
- [Python in VS Code](https://code.visualstudio.com/docs/python/python-tutorial)
- [Pylance](https://marketplace.visualstudio.com/items?itemName=ms-python.vscode-pylance): An extension for VSCode that helps with developing in Python. Especially interesting is the setting `python.analysis.typeCheckingMode`. When set to `basic` or `strict`, it highlights ambiguities and even mistakes in your code!
- [Type Hints](https://realpython.com/python-type-checking/): Python is a dynamically typed programming language. This means that the type (string, integer, dictionary, ...) of a variable can change over its lifetime. This gives lots of freedom, but can also lead to problems. With type hints, you can specify the types a variable may take, for example in function definitions. IDEs such as VSCode can then use these type hints to point out errors before you even run your code!
- [Docstring Generator](https://marketplace.visualstudio.com/items?itemName=njpwerner.autodocstring): Docstrings are used to document code in Python. This extension for VSCode automatically generates these docstrings for you, where you simply have to fill in your descriptions of the variables.

### Debugging, VS Code Hacks (Vera)

- [Debugging in VS Code](https://code.visualstudio.com/docs/editor/debugging): Set some breakpoints and run the debugger
- [pdb](https://docs.python.org/3/library/pdb.html):
  ```py
  import pdb
  pdb.set_trace()  # script stops exactly at this line
  ```
  useful for bigger project, when you can't just run the file
- `Ctrl`+`P`: quickly search for a specific file hidden somewhere deep in the directory
- `Ctrl`+`K` `Ctrl`+`<fold level>`: collapse/[fold](https://code.visualstudio.com/docs/editor/codebasics#_folding) functions/classes/loops

### Code formatting, Pandoc (Andreas)

- [Black](https://black.readthedocs.io/en/stable/): Use in VS Code by applying the "Format Document" command (search it in the command palette or right click in the editor)
- [Pandoc](https://pandoc.org/): Convert between many text document formats (Markdown, DOCX, PDF, LaTeX, ...)
  ```bash
  pandoc -o output.pdf input.md
  ```
