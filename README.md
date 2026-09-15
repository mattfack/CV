directory to keep my CV up-to-date

Here's the repo structure

# Repository Organization

This document describes the recommended directory structure for the CV repository to improve organization and maintainability.

## Proposed Structure

```
CV/
├── README.md                          # Repository overview and instructions
├── .gitignore                         # Git ignore rules
├── .github/
│   └── workflows/
│       └── build-pdf.yml              # (Optional) Auto-build PDF on push
│
├── src/                               # LaTeX source files
│   ├── cv_main.tex                    # Main CV document (entry point)
│   ├── preamble.tex                   # Shared preamble & styling
│   └── sections/                      # Modular content sections
│       ├── 01_personal.tex            # Personal info & contact
│       ├── 02_education.tex           # Education & training
│       ├── 03_experience.tex          # Work experience
│       ├── 04_publications.tex        # Academic publications
│       ├── 05_conferences.tex         # Conferences & courses
│       └── 06_skills.tex              # Technical & language skills
│
├── assets/                            # Static assets
│   └── images/
│       └── profile-photo.jpg          # Profile photograph (single, modern version)
│
├── output/                            # Generated PDFs (gitignored)
│   └── CV_Matteo_Facchini_IT.pdf      # Compiled output
│
├── archive/                           # Historical versions (for reference)
│   ├── 2016/
│   ├── 2017/
│   ├── 2018/
│   ├── 2019/
│   └── 2020/
│
└── templates/                         # (Optional) Alternative template versions
    └── modern/                        # Modern template experiments
```

## Directory Details

### `src/` — LaTeX Source Files
Contains the active CV sources. Main file is `cv_main.tex` which includes modular sections from `sections/`.

- **cv_main.tex**: Entry point. Sets document class, includes preamble, and compiles all sections
- **preamble.tex**: Shared configuration (packages, custom commands, colors, fonts)
- **sections/**: Individual content modules numbered for clear ordering

### `assets/images/` — Media Files
Single location for images:
- Store one high-quality profile photo (replace duplicates)
- Use consistent naming: `profile-photo.jpg` or similar

### `output/` — Generated Artifacts
- PDFs compiled from LaTeX sources
- Add to `.gitignore` (don't commit generated files)
- Include in `.gitignore`: `output/**/*.pdf`, `src/**/*.log`, `src/**/*.aux`, etc.

### `archive/` — Version History
- Organize old CV versions by year
- Keep for reference, but don't maintain actively
- Optional: compress older versions to reduce repo size

## Updated .gitignore

```gitignore
# LaTeX build artifacts
*.aux
*.bbl
*.blg
*.dvi
*.fdb_latexmk
*.fls
*.log
*.out
*.pdf
*.synctex.gz
texput.log

# macOS
.DS_Store
*.swp

# IDE
.vscode/
.idea/

# Generated output
output/
build/

# Temporary files
*~
*.tmp
```
