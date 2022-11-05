# The Missing Semester

This page contains notes of past editions of *The Missing Semester* event at the University of Zurich. *The Missing Semester* aims to create an exchange of information between students of Computational or Digital Linguistics, focusing on technical and practical tools which make our lives as CL/DL students easier.

This [repository](https://github.com/saeub/missing-semester/) is currently maintained by [bernai](https://github.com/bernai/), [dominikmartinez](https://github.com/dominikmartinez/), [saeub](https://github.com/saeub/), and [vera-bernhard](https://github.com/vera-bernhard/).

## 04.11.2021: *Show How You Code*

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
