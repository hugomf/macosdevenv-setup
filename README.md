# Development Environment Setup

- [Development Environment Setup](#development-environment-setup)
  - [Step 1 -  Download and Install CommandLine Tools for Xcode](#step-1----download-and-install-commandline-tools-for-xcode)
  - [Step 2 - Download and Install HomeBrew](#step-2---download-and-install-homebrew)
  - [Step 3 - Download, Install and configure iTerm2](#step-3---download-install-and-configure-iterm2)
  - [Step 4 - Install version managers for Python, Java and Node](#step-4---install-version-managers-for-python-java-and-node)
  - [Step 5 - Configure git (ssh keys)](#step-5---configure-git-ssh-keys)
  - [Step 6 - Install AWS CLI](#step-6---install-aws-cli)
  - [Step 7 - Install the following Applications](#step-7---install-the-following-applications)
    - [VSCode Plugins](#vscode-plugins)
      - [UI](#ui)
      - [Development](#development)
      - [Java Development](#java-development)
      - [Python Development](#python-development)
      - [Javascript, React, etc](#javascript-react-etc)
    - [Markdown edition](#markdown-edition)

## Step 1 -  Download and Install CommandLine Tools for Xcode

Currently there are two options to install the CommandLine tools

1. Open the Macos Terminal and type the following command:

    ```shell
    xcode-select --install
    ```

2. Download **CommandLine Tools** from the website

   - Download CL Tools From: [Apple Developer Site](https://developer.apple.com/download/all/`), you will have to login with your appleid (iCloud) account.

   - Search `Command Line tools` and download the desired version, for example:

     - Command Line Tools for Xcode 14.2 - [Here](https://download.developer.apple.com/Developer_Tools/Command_Line_Tools_for_Xcode_14.2/Command_Line_Tools_for_Xcode_14.2.dmg)

3. Open the terminal and verify if the CommandLine Tools for Xcode installation was successful by entering the following command:

    ```shell
    xcode-select -p
    ```

## Step 2 - Download and Install HomeBrew

Make sure CommandLine Tools for Xcode is installed.

- Download and Install [HomeBrew](https://brew.sh/) using the following command:

    ```shell
        /bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
    ```

## Step 3 - Download, Install and configure iTerm2

- Download and Install [iterm2](https://iterm2.com/)

- Install [OhmyZsh](https://ohmyz.sh/):

    ```shell
    sh -c "$(curl -fsSL https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"

    ```
  
- Install [Powerlevel10k](https://ohmyz.sh/)
  
    ```shell
    brew install romkatv/powerlevel10k/powerlevel10k
    ```

- Configure `Powerlevel10k` on `.zshrc`
  
    ```shell
    echo "source $(brew --prefix)/opt/powerlevel10k/powerlevel10k.zsh-theme" >>~/.zshrc
    ```

- Close the `iterm2` window and open it again, a menu will appear.

- Install `MesloLGS NF` *font*, configure the icons and the prompt attributes by following the instructions.

- To install  `MesloLGS NF` *font* manually: 

  **powerlevel10k** should do that for you, this step should be done if the font is not installed properly.

  - macos:

    ```shell

      cd ~/Library/Fonts && { 
      curl -Lo 'MesloLGS NF Regular.ttf' 'https://github.com/romkatv/powerlevel10k-media/raw/master/MesloLGS%20NF%20Regular.ttf'
      curl -Lo 'MesloLGS NF Italic.ttf' 'https://github.com/romkatv/powerlevel10k-media/raw/master/MesloLGS%20NF%20Italic.ttf'
      curl -Lo 'MesloLGS NF Bold.ttf' 'https://github.com/romkatv/powerlevel10k-media/raw/master/MesloLGS%20NF%20Bold.ttf'
      curl -Lo 'MesloLGS NF Bold Italic.ttf' 'https://github.com/romkatv/powerlevel10k-media/raw/master/MesloLGS%20NF%20Bold%20Italic.ttf'
      cd -; }

    ```

> **Note:** If you are unable to see the icons, you may need to open the iterm2 **Settings>Profiles>Text>** and in the Font Section you will have to manually set the `MesloLGS NF` font.

## Step 4 - Install version managers for Python, Java and Node

- Install **(Java Version Manager)**

  - Install [sdkman](https://sdkman.io/)

    ```shell
    curl -s "https://get.sdkman.io" | bash

    source "$HOME/.sdkman/bin/sdkman-init.sh"
    ```

  - Verify `sdkman` version:

    ```shell
    sdk version
    ```

  - Usage:

    ```shell
      sdk list java                   # To list all available versions
      sdk list java | grep installed  # To see what versions are installed 
      sdk install java 8.0.362-tem    # Install a Java version

      sdk use java 8.0.362-tem        # To set Java version locally, you need to navigate to the project's directory
      sdk default java 8.0.362-tem    # Sets the specified version of Java as the default version.


      sdk current java                # Check current java version
    ```

- ### Install [nvm](https://sdkman.io/) **(Node Version Manager)**

  - Type the following command to download an install nvm:

    ```shell
        curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.3/install.sh | bash
    ```

  - Close and reopen your terminal

  - Usage:

     ```shell
          nvm ls-remote       # To see all available node versions
          nvm ls              # If you want to list what versions are installed
          nvm install node    # To install the latest version of node
          nvm install 14.7.0  # To install a specific version of node
     ```

- ### Install [pyenv](https://github.com/pyenv/pyenv) **(Python version manager)**

    >**Note:** Make sure HomeBrew is installed (Follow Step 2), and then proceed to install `pyenv` as follows:

  - Install pyenv
    ```shell
    brew update
    brew install pyenv
    ```

  - Add the following configuration at the end of your `.zshrc` or `.bashrc` file

    ```shell
      export PYENV_ROOT="$HOME/.pyenv/shims"
      export PATH="$PYENV_ROOT:$PATH"
      export PIPENV_PYTHON="$PYENV_ROOT/python"
    ```

- Usage:

  - Now you are able to install a python version locally or globally for example:

    ```shell
    pyenv versions        # To see what versions are installed.
    pyenv install -l      # Gives the list of all available versions.
    pyenv install 3.9.4   # just install
    pyenv global 3.9.4    # Sets a python version as the default (global) version.
    pyenv local 3.9.4     # use python version locally
    pyenv uninstall 3.94  # to uninstall
    ```

  - Check your python version
  
    ```shell
    python --version
    ```

- ### Install [gvm](https://github.com/moovweb/gvm) **(GOLang version manager)**

    >**Note:** Make sure `HomeBrew` is installed (Follow Step 2), and then proceed to install `gvm` as follows:
  
  - Install any version of `golang`
  
    ```shell
    brew update
    brew install go  # Install any golang version (this is needed because binary versions are not available anymore)
    brew install mercurial # Version control tool to download "go source code" to compile the desired version
    ```

  - Install `gvm` (Use zsh or bash according your current shell system)

    ```shell
      zsh < <(curl -s -S -L https://raw.githubusercontent.com/moovweb/gvm/master/binscripts/gvm-installer)
    ```

- Usage:

  - Now you are able to install a `golang` version locally or globally for example:

    ```shell
    gvm list                    # To list what versions are installed in your system.
    gvm listall                 # Gives the list of all available versions.
    gvm install go1.16          # Install a specific golang version
    gvm use go1.16 [--default]  # Sets the specified golang version as the default (global) version.
    gvm use go1.16              # use golang version locally
    gvm implode                 # to uninstall
    ```

  - Verify your `golang` version
  
    ```shell
      go version
    ```

## Step 5 - Configure git (ssh keys)

- Set up SSH keys:

    SSH keys allow you to securely connect to remote servers and repositories without entering a password every time. To set up SSH keys, follow the instructions in the GitHub documentation: [SSH Keys Docs](https://docs.github.com/en/github/authenticating-to-github/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent)

## Step 6 - Install AWS CLI

- Open the terminal and type the following command(s):

    ```shell
    curl "https://awscli.amazonaws.com/AWSCLIV2.pkg" -o "AWSCLIV2.pkg"
    sudo installer -pkg AWSCLIV2.pkg -target /
    ```

## Step 7 - Install the following Applications

- [Visual Studio Code](https://code.visualstudio.com/)
- [IntelliJ](https://www.jetbrains.com/idea/)
- [Docker](https://www.docker.com)
- [Rectangle](https://rectangleapp.com/)

### VSCode Plugins

Download the following Plugins:

#### UI

- [Material Icon Theme](https://marketplace.visualstudio.com/items?itemName=PKief.material-icon-theme)
- [Community Material Theme](https://marketplace.visualstudio.com/items?itemName=Equinusocio.vsc-community-material-theme)

#### Development

- [C/C++](https://marketplace.visualstudio.com/items?itemName=ms-vscode.cpptools)
- [Go](https://marketplace.visualstudio.com/items?itemName=golang.Go)
- [GNU Assembler Language Support](https://marketplace.visualstudio.com/items?itemName=basdp.language-gas-x86)

#### Java Development

- [Extension Pack for Java](https://marketplace.visualstudio.com/items?itemName=vscjava.vscode-java-pack)
- [Gradle for Java](https://marketplace.visualstudio.com/items?itemName=vscjava.vscode-gradle)
- [Spring Boot Extension Pack](https://marketplace.visualstudio.com/items?itemName=vscjava.vscode-spring-boot-dashboard)
- [Lombok Annotations](https://marketplace.visualstudio.com/items?itemName=vscjava.vscode-lombok)

#### Python Development

- [Python](https://marketplace.visualstudio.com/items?itemName=ms-python.python)
- [Pylance](https://marketplace.visualstudio.com/items?itemName=ms-python.vscode-pylance)

#### Javascript, React, etc

- [Prettier - Code formatter](https://marketplace.visualstudio.com/items?itemName=esbenp.prettier-vscode)
- [HTML CSS Support](https://marketplace.visualstudio.com/items?itemName=ecmel.vscode-html-css)
- [Live Server](https://marketplace.visualstudio.com/items?itemName=ritwickdey.LiveServer)
- [ESLint](https://marketplace.visualstudio.com/items?itemName=dbaeumer.vscode-eslint)
- [ES7+ React/Redux/React-Native snippets](https://marketplace.visualstudio.com/items?itemName=dsznajder.es7-react-js-snippets)
- [Autorename tag](https://marketplace.visualstudio.com/items?itemName=formulahendry.auto-rename-tag)

### Markdown edition

- [Markdown All in One](https://marketplace.visualstudio.com/items?itemName=yzhang.markdown-all-in-one)
- [Markdown Preview Enhanced](https://marketplace.visualstudio.com/items?itemName=shd101wyy.markdown-preview-enhanced)
