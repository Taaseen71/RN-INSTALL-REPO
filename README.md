List of Commands

# Install Homebrew

  - ```
    /bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
    ```
# Install Warp Terminal    

  -  ```
     brew install --cask warp
     ```
  - ```vim ~/.zshrc```
  - ```source ~/.zshrc```

# Install ZSH

  - ```
    brew install zsh
    ```
  - ```
    chsh -s $(which zsh)
    ```
  - ```vim ~/.zshrc```
  - ```source ~/.zshrc```
    
  - Install OhMyZsh
    - [walkthrough](https://github.com/ohmyzsh/ohmyzsh)
    - ```
      sh -c "$(curl -fsSL https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
      ```
    - 
    - ```
      git clone https://github.com/TamCore/autoupdate-oh-my-zsh-plugins ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/autoupdate
      ```



# INSTALL IOS 15.2 and Android Studio from online

  - [XCode Releases](https://xcodereleases.com/)
    - ```
      https://download.developer.apple.com/Developer_Tools/Xcode_15.2/Xcode_15.2.xip
      ```
    - Before moving to application folder, rename it to Xcode-15.2.app
    - ```
      sudo xcode-select -switch /Applications/Xcode-15.2.app
      ```
    - ```xcode-select --install```
    - ```xcode-select --print-path```
    - ```xcodebuild -version```
    - ```sudo xcodebuild -license accept```
  - [Android Studio Download Here](https://developer.android.com/studio/)




- Install Java
  - ```
    brew install --cask zulu@17
    ```
  - or 
    ```
    brew install --cask zulu@11
    ```
  - installs Java 11 or 17
  - ```
    brew list --cask
    ```
  - To Switch Java Version:
    - go to ```vim ~/.zshrc``` or use zprofile
    - edit java Version
    - ```
          #export JAVA_HOME=/Library/Java/JavaVirtualMachines/Zulu-11.jdk/Contents/Home
          export JAVA_HOME=/Library/Java/JavaVirtualMachines/Zulu-17.jdk/Contents/Home
      ```
    - ```source ~/.zshrc```
    - Verify the change
      ```java --version```





# Install NVM

  - ```
    curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.7/install.sh | bash
    ```
  - copy the last message and paste in the terminal, or close and reopen the terminal
  - ```nvm --version```
  - ```vim ~/.zshrc```
  - ```source ~/.zshrc```
  - ```nvm --version```
    - ```nvm install v20.10.0```
    - ```nvm install v21.6.2```
    - ```node -v```
  - To switch node versions:
    - ```nvm alias default 21.6.2```
      (will update to load everytime a new terminal is opened)
    - ```nvm use 20.10.0```
      (will apply change only to current terminal window)
    - ```node -v```
   



# INSTALL YARN

  - check if yarn is installed through npm or brew (brew: 
    - ```
      npm list -g yarn
      ```
    - ```
      brew list yarn
      ```
    - check directory: ```which yarn```
  - ```
    brew install yarn@1.22.21
    ```
  - ```yarn -v```
  - ```
    npm install -g yarn@1.22.21
    ```
  - ```yarn -v```
  - ```npm --version``` (10.2.3)

  
#### Using Corepack (use a specific version of yarn in a specific directory) 

  - if the package.json has a "packageManager": "yarn@x.x.x" line added.
  - brew install corepack
  - go to the root of the repo
  - ```corepack enable```
  - ```yarn set version stable```
    - yarn will search for available versions

        

# Install Watchman
  - ```
    brew install watchman
    ```


# INSTALL COCOAPODS

  - First install Ruby gems
    - ```brew install rbenv ruby-build```
    - ```
        rbenv install 3.0.6
      ```
    - ```
        rbenv local 3.0.6
      ```
    - ```
        rbenv global 3.0.6
      ```
  - Cocoapods
    - (sudo gem install drb -v 2.0.6)
    - ```
      sudo gem install cocoapods -v 1.15.2
      ```
    - ```
      sudo gem install cocoapods-switch
      ```
      - ```cocoapods-switch 1.15.2```

# Install VSCODE
  - ```brew install --cask vscodium```
  - Install shell shortcut
  - Cmd + shift + p
  - Type in >shell
  - Create shell command.
  - It will create shell command ```code .```  
  - Create alias function for this in ~/.zshrc
    - ```
      #VSCODE shortcut
        function code(){
          codium "$1"
        }
      ```
  - Now we’re allowed to use code .







# ```vim ~/.zshrc``` file
```
################################EDITBELOW#######################
##PATHS##
export PATH="/opt/homebrew/bin:$PATH"

##NVM
export NVM_DIR="$HOME/.nvm"
[ -s "$NVM_DIR/nvm.sh" ] && \. "$NVM_DIR/nvm.sh"  # This loads nvm
[ -s "$NVM_DIR/bash_completion" ] && \. "$NVM_DIR/bash_completion"  # Th

##Android
export ANDROID_HOME=$HOME/Library/Android/sdk
export PATH=$PATH:$ANDROID_HOME/emulator
export PATH=$PATH:$ANDROID_HOME/platform-tools

##Java
#export JAVA_HOME=/Library/Java/JavaVirtualMachines/Zulu-11.jdk/Contents/Home
export JAVA_HOME=/Library/Java/JavaVirtualMachines/Zulu-17.jdk/Contents/Home
export PATH=$JAVA_HOME/bin:$PATH

################################################################


##ALIASES
#VSCODE shortcut
function code(){
    codium "$1"
}

#APP DIRECTORY Shortcut
alias diamond="cd ~/CodingFolder/Walmart/Diamond-Flex"
alias personal="cd ~/CodingFolder/Personal"

alias home="cd ~/"

################################################################

# export NO_PROXY="*.ghcr.io,*.ssl.scandit.com, *.github.com, *.googlesource.com"

################################################################

export ZSH="$HOME/.oh-my-zsh"

ZSH_THEME="agnoster"
#ZSH_THEME="robbyrussell"

plugins=(git)

source $ZSH/oh-my-zsh.sh


###################################################################

eval "$(rbenv init -)"
```
