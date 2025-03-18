# Building the Thesis Document

## Requirements

### Windows
- Install [TeX Live](https://www.tug.org/texlive/) or [MiKTeX](https://miktex.org/)
- Install [Perl](https://strawberryperl.com/) (required for `bibtex` in some cases)
- Add `pdflatex` and `bibtex` to your system's `PATH`

### Linux
- Install TeX Live:
  ```bash
  sudo apt update && sudo apt install texlive-full
  ```
- Ensure `pdflatex` and `bibtex` are installed by running:
  ```bash
  pdflatex --version
  bibtex --version
  ```

## Building the Document

To compile the LaTeX document, run the `build.ps1` script:

### Windows (PowerShell)
```powershell
.\build.ps1
```

### Linux/macOS (Bash)
Since `build.ps1` is a PowerShell script, you can either run it using PowerShell Core (`pwsh`) or execute the commands manually:

Using PowerShell Core:
```bash
pwsh ./build.ps1
```

Running the commands manually:
```bash
pdflatex -shell-escape -synctex=1 main
bibtex main
pdflatex -shell-escape -synctex=1 main
pdflatex -shell-escape -synctex=1 main
```

## Viewing the Compiled Document

After a successful build, the compiled PDF can be found at:

📄 **`RAU-INZ-299531-2025.pdf`**

### Note
The `pdflatex` command is run multiple times to ensure proper cross-referencing and bibliography inclusion.
