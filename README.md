# Development Environment Setup

## Step 1

- Install [OhmyZsh](https://ohmyz.sh/)


```shell
sh -c "$(curl -fsSL https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"

```


- Install [Powerlevel10k](https://ohmyz.sh/)


```shell
brew install romkatv/powerlevel10k/powerlevel10k

echo "source $(brew --prefix)/opt/powerlevel10k/powerlevel10k.zsh-theme" >>~/.zshrc
```


## Step 2 Install version managers for Python, Java and Node


- Install [sdkman](https://sdkman.io/) (Java Version Manager)

```shell
    curl -s "https://get.sdkman.io" | bash

    source "$HOME/.sdkman/bin/sdkman-init.sh"
```

Check sdkman version:

```shell
sdk version
```

- Install [nvm](https://sdkman.io/) (Node Version Manager)

```shell
    curl -s "https://get.sdkman.io" | bash
```


- Install [pyenv]() Python version manager


Install dependencies for Homebrew (Xcode Command Line tools)

```shell
xcode-select --install
```
 make sure xcode command line tools are already installed

```shell
 xcode-select -p
```


Install [Brew](https://brew.sh/):


```shell
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```

Once Brew is installed, proceed to install pyenv
```shell
brew update
brew install pyenv
```

Configure pyenv:

open your `~/.zshrc` file in your favorite editor and add the following lines at the end of the file:

```shell
export PYENV_ROOT="$HOME/.pyenv"
command -v pyenv >/dev/null || export PATH="$PYENV_ROOT/bin:$PATH"
eval "$(pyenv init -)"
```

Now are able to install a python version locally or globally for example:


```shell
pyenv global 3.9.4
pyenv local 3.9.4
```shell
Check your python version
```shell
python --version
```


## Step 3: Install AWS CLI:

```shell
curl "https://awscli.amazonaws.com/AWSCLIV2.pkg" -o "AWSCLIV2.pkg"
sudo installer -pkg AWSCLIV2.pkg -target /
```


## Step 4:  Install the following Applications

- [Visual Studio Code](https://code.visualstudio.com/)
- [iTerm2](https://iterm2.com/)
- [IntelliJ](https://www.jetbrains.com/idea/)
- [Docker](https://www.docker.com)




### Configuring Visual Studio Code

Download the following Plugins:

- [Python](https://marketplace.visualstudio.com/items?itemName=ms-python.python)
- [Pylance](https://marketplace.visualstudio.com/items?itemName=ms-python.vscode-pylance)
- [Prettier - Code formatter](https://marketplace.visualstudio.com/items?itemName=esbenp.prettier-vscode)
- [Live Server](https://marketplace.visualstudio.com/items?itemName=ritwickdey.LiveServer)
- [ESLint](https://marketplace.visualstudio.com/items?itemName=dbaeumer.vscode-eslint)
- [Extension Pack for Java](https://marketplace.visualstudio.com/items?itemName=vscjava.vscode-java-pack)
- [Gradle for Java](https://marketplace.visualstudio.com/items?itemName=vscjava.vscode-gradle)
- [HTML CSS Support](https://marketplace.visualstudio.com/items?itemName=ecmel.vscode-html-css)
- [Spring Boot Extension Pack](https://marketplace.visualstudio.com/items?itemName=vscjava.vscode-spring-boot-dashboard)
- [Lombok Annotations](https://marketplace.visualstudio.com/items?itemName=vscjava.vscode-lombok)
- [Material Icon Theme](https://marketplace.visualstudio.com/items?itemName=PKief.material-icon-theme)
- [Community Material Theme](https://marketplace.visualstudio.com/items?itemName=Equinusocio.vsc-community-material-theme)
- [ES7+ React/Redux/React-Native snippets](https://marketplace.visualstudio.com/items?itemName=dsznajder.es7-react-js-snippets)
- [C/C++](https://marketplace.visualstudio.com/items?itemName=ms-vscode.cpptools)
- [Go](https://marketplace.visualstudio.com/items?itemName=golang.Go)