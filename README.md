Cheat sheet: quick ZSH setup
ZSH and OhMyZSH Setup Cheat Sheet

Ubuntu (or other "Debian-based" Linux distros)

# update apt-get so it will install the most up-to-date versions of packages
apt-get update
 
# try to install sed, git, and zsh if they aren't already present
# Note: sed is a command for editing text files, we will use it further down
# to configure the ~/.zshrc file
which sed || sudo apt-get install -y sed || echo "linux: could not install sed"
which zsh || sudo apt-get install -y zsh || echo "linux: could not install zsh"
which git \
    || sudo add-apt-repository ppa:git-core/ppa \
    && sudo apt-get update \
    && sudo apt-get install -y git \
    || echo "mac: could not install git"
 
# install OhMyZSH if it isn't already installed
[ -d ~/.oh-my-zsh ] || sh -c "$(curl -fsSL https://raw.github.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
 
# plugin: zsh-autosuggestions
git clone https://github.com/zsh-users/zsh-autosuggestions ${ZSH_CUSTOM:-$HOME/.oh-my-zsh/custom}/plugins/zsh-autosuggestions
 
# plugin: zsh-syntax-highlighting
git clone https://github.com/zsh-users/zsh-syntax-highlighting.git ${ZSH_CUSTOM:-$HOME/.oh-my-zsh/custom}/plugins/zsh-syntax-highlighting
 
# add these two plugins and enable some of the default ones
sed -i 's/\(^plugins=([^)]*\)/\1 python pip pyenv virtualenv web-search zsh-autosuggestions zsh-syntax-highlighting/' "$HOME/.zshrc"
 
# set the ZSH_THEME to "bira"
sed -i 's/_THEME=\".*\"/_THEME=\"bira\"/g' "$HOME/.zshrc"

# connecting to virtual machine
![image](https://github.com/user-attachments/assets/b9e50f01-0bda-41c2-a627-5ce1c5ecffc2)



python-software-development-course --> https://github.com/phitoduck/python-software-development-course

https://github.com/google/styleguide/blob/gh-pages/README.md

https://peps.python.org/pep-0008/

# More content to refer on clean code and refactoring
https://testdriven.io/blog/clean-code-python/

https://martinfowler.com/articles/refactoring-2nd-ed.html

# PYTHON CODE QUALITY TOOL

# Format python code using black in unopiniated way when working in a team a) to fix spacing inconsitencies that arises dring development and b) end disputes in the team.
# Install black on your own machine and configure it to run on autosave using your VS code settings.
![image](https://github.com/user-attachments/assets/85675987-4b46-4c79-81cf-3c265f01494a)

![image](https://github.com/user-attachments/assets/2799cd8e-13fb-4849-b5ab-8abf4f3389d8)

![image](https://github.com/user-attachments/assets/fc0bd469-ebc4-46ab-845d-9342375babd0)

# Pylint and black - integrating with VS Code --> install the extension in VSCode for Pylint and Black formatter
https://ericriddoch.notion.site/Pylint-Part-2-Integrating-with-VS-Code-7ddadf91013c428fbc9cfd0b187a42b4

# Configuring Pylint with a config file and CLI arguments
https://ericriddoch.notion.site/Pylint-Part-3-Configuring-Pylint-with-a-config-file-and-CLI-arguments-5e022c20773d45d59d0c60b176aca694

# Flake8 Part 1 - Usage and background
https://ericriddoch.notion.site/Flake8-Part-1-Usage-and-background-fc834288bb3f45cfa15f668b2759691d

# Flake8 Part 2 - Flake8 plugins with Darglint as an example
https://ericriddoch.notion.site/Flake8-Part-2-Flake8-plugins-with-Darglint-as-an-example-abe1eae877f04e03958f6863073684f9

# isort: sorting import statements
https://ericriddoch.notion.site/isort-sorting-import-statements-4d42577fab484372a0e576a3fbd51a48

# Code metrics” like “cyclomatic complexity” with Radon, Xenon, and McCabe
https://ericriddoch.notion.site/Code-metrics-like-cyclomatic-complexity-with-Radon-Xenon-and-McCabe-197c5286f12642479e93e73ff4c043d5

# Darker: incrementally lint legacy projects
https://ericriddoch.notion.site/Darker-incrementally-lint-legacy-projects-b7cb39ad606f4c10a8bf81f8274ae6ae

# Ruff: the last Python linter ever?
https://ericriddoch.notion.site/Ruff-the-last-Python-linter-ever-8918d70b51364350903753e052bf9936











