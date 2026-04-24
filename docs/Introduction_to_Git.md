# :open_book: Step 1: Introduction to Git Version Control

### What is Version Control?
Version control allows to solve issues like:
* Backup and recovery
* File duplication
* Conflicting changes
* Team collaboration

### How to use Git for Version Control?
* Command Line Interface (CLI)
* Code Editors (e.g., Visual Studio Code)
* Hosting Services (e.g., GitHub)
* Desktop Applications (e.g., GitHub Desktop)

### Git in the CLI
1. To show the current installed version of Git:
```bash
git --version
```

2. To show the Git help documentation:
```bash
git --help
```

3. To set the Git identity:
```bash
git config --global user.name "First Last"

git config --global user.email "email@example.com"
```
:mag: Confirm the changes by viewing the configuration:
```bash
git config --global --list
```