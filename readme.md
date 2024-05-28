Руководство по созданию среды разработки на Windows для Python, JavaScript, Web Development и Java

Примечания:
-  вместо %USERPROFILE% пишите название вашего пользователя.
-  копируйте и делайте всё пошагово так как иногда могут возникать ошибки.
-  так же используя команду choco install <название программы> вы можете скачать нужные вам программы

```powershell
# Установка Chocolatey (менеджер пакетов)
Set-ExecutionPolicy Bypass -Scope Process -Force; `
[System.Net.ServicePointManager]::SecurityProtocol = [System.Net.ServicePointManager]::SecurityProtocol -bor 3072; `
iex ((New-Object System.Net.WebClient).DownloadString('https://community.chocolatey.org/install.ps1'))

# Установка Windows Terminal
winget install --id Microsoft.WindowsTerminal -e

# Установка WSL (Windows Subsystem for Linux)
wsl --install

# Установка Visual Studio Code
winget install --id Microsoft.VisualStudioCode -e

# Установка расширений для Visual Studio Code
code --install-extension ms-python.python
code --install-extension ms-vscode.vscode-typescript-tslint-plugin
code --install-extension vscjava.vscode-java-pack
code --install-extension dbaeumer.vscode-eslint
code --install-extension esbenp.prettier-vscode
code --install-extension eamodio.gitlens
code --install-extension ritwickdey.LiveServer

# Установка Python и pyenv
pip install pyenv-win --target C:\Users\%USERPROFILE%\.pyenv

# Установка Node.js и nvm-windows
iwr https://raw.githubusercontent.com/coreybutler/nvm-windows/master/nvm-setup.zip -OutFile nvm-setup.zip
Expand-Archive nvm-setup.zip -DestinationPath .
.\nvm-setup.exe
nvm install latest
nvm use latest

# Установка SDKMAN! и Java
curl -s "https://get.sdkman.io" | bash
source "$HOME/.sdkman/bin/sdkman-init.sh"
sdk install java

# Установка Git
winget install --id Git.Git -e

# Установка GitHub CLI
winget install --id GitHub.cli -e

# Установка PostgreSQL, MySQL и MongoDB
choco install postgresql
choco install mysql
choco install mongodb

# Установка Docker
winget install --id Docker.DockerDesktop -e

# Установка Kubernetes CLI
choco install kubernetes-cli

# Установка Postman и Insomnia
winget install --id Postman.Postman -e
winget install --id Insomnia.Insomnia -e

# Установка npm и Yarn
npm install -g npm
npm install -g yarn

Write-Host "Среда разработки успешно настроена!"
```
