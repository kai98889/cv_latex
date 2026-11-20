# Kai Zhu - LaTeX CV

Personal English CV for Kai Zhu, based on the supplied self-introduction. Includes education, project details, technical background, a portrait, and the approved phone contact. Dates not supplied are omitted.

## Build and publish

- Edit `main.tex` and push to `main` or `master`.
- GitHub Actions compiles the CV with XeLaTeX and saves a `cv-pdf` artifact.
- The publication job creates or updates the `release` branch with only `main.pdf`, preserving previous release commits.
- A GitHub Release attaches the PDF and tags the corresponding publication commit.
- Pull requests compile the document without publishing. Manual runs are available in Actions.
- No local LaTeX, Docker, plugin, or manually configured token is needed for the GitHub Actions build.

The source template is [reveurmichael/cv_latex](https://github.com/reveurmichael/cv_latex). The original setup documentation below describes alternative local and Docker build methods; the current workflow is `.github/workflows/build-cv.yml`.

## Original template documentation

This repository demonstrates a LaTeX CV template with **multiple build methods**, providing flexibility and redundancy across different platforms and workflows.

## Why Multiple Build Methods?

Having multiple ways to build the same document provides several key benefits:

- **Redundancy**: If one method fails, you can easily switch to another
- **Platform Independence**: Works on Windows, macOS, and Linux
- **Flexibility**: Choose the approach that fits your environment and needs
- **Team Compatibility**: Different team members can use different methods

## Build Methods Comparison

| Build Method | Advantages | Disadvantages | Best For |
|--------------|------------|--------------|----------|
| **Local** | - Fast compilation<br>- Direct feedback<br>- No internet required<br>- Full editor integration | - Requires LaTeX installation<br>- Environment setup needed<br>- OS-dependent | Daily development<br>Frequent edits<br>Personal projects |
| **Docker** | - Consistent environment<br>- No local LaTeX install<br>- Works across platforms<br>- Reproducible builds | - Requires Docker<br>- Slower initial setup<br>- Container overhead | Team projects<br>Complex documents<br>Environment isolation |
| **GitHub Actions** | - Fully automated<br>- Continuous integration<br>- PDF release management<br>- No local setup | - Requires internet<br>- Not for frequent iteration<br>- GitHub dependency | Production builds<br>Public sharing<br>Version control |

## Build Method Documentation

Each build method has its own detailed guide:

1. **[Local Build](./Readme-Local.md)** - Build directly on your machine using VSCode/Cursor and LaTeX Workshop
2. **[Docker Build](./Readme-Docker.md)** - Build using Docker without installing LaTeX locally
3. **[GitHub Actions](./Readme-GitHub-Actions.md)** - Automated builds and releases with GitHub Actions

## Configuration Scripts

This repository includes utility scripts to simplify setup:

- `config_vscode_local.py` - Creates `.vscode/settings.json` for local LaTeX development
- `config_vscode_devcontainer.py` - Creates `.devcontainer/devcontainer.json` for Docker-based development
- `docker_build.py` - Cross-platform Python script to build with Docker
- `docker_build.sh` - Shell script for Docker builds (Unix-based systems)

The inclusion of both Python and shell scripts provides redundancy across platforms:
- Python scripts work on all platforms (Windows, macOS, Linux)
- Shell scripts provide native performance on Unix-based systems
- Multiple tools ensure you can always build your CV, regardless of your environment

### Usage

```bash
# Configure VSCode for local builds
python config_vscode_local.py

# Configure VSCode DevContainer
python config_vscode_devcontainer.py

# Build with Docker (Python script - cross-platform)
python docker_build.py

# Build with Docker (Shell script - Unix systems)
./docker_build.sh
```

## Sample CV

This repository includes a sample CV for demonstration purposes.

## Template Sources

You can also explore other templates:
- https://www.overleaf.com/gallery/tagged/cv

## Project Repository

https://github.com/reveurmichael/cv_latex

