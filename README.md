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

- ### Install [nvm](https://sdkman.io/) **(Node Version Manager)**

    ```shell
        curl -s "https://get.sdkman.io" | bash
    ```

- ### Install [pyenv](https://github.com/pyenv/pyenv) **(Python version manager)**

    >**Note:** Make sure HomeBrew is installed (Follow Step 2), and then proceed to install `pyenv` as follows:

    ```shell
    brew update
    brew install pyenv
    ```

- Configure `pyenv` in your `.zshrc`:

  - Open your `~/.zshrc` file in your favorite editor and add the following lines at the end of the file:

    ```shell
    export PYENV_ROOT="$HOME/.pyenv"
    command -v pyenv >/dev/null || export PATH="$PYENV_ROOT/bin:$PATH"
    eval "$(pyenv init -)"
    ```

  - Now you are able to install a python version locally or globally for example:

    ```shell
    pyenv global 3.9.4
    pyenv local 3.9.4
    ```

  - Check your python version
  
    ```shell
    python --version
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