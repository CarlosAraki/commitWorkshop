# WorkShop GitHub

## Links de Dependência

Set-ExecutionPolicy Bypass -Scope Process -Force; [System.Net.ServicePointManager]::SecurityProtocol = [System.Net.ServicePointManager]::SecurityProtocol -bor 3072; iex ((New-Object System.Net.WebClient).DownloadString('https://chocolatey.org/install.ps1'))

https://github.com/conventional-changelog/commitlint

https://github.com/commitizen/cz-cli

https://github.com/github/hub

Set-ExecutionPolicy Unrestricted

choco install hub

Set-Alias git hub

npm install yarn


git config --global alias.lg "log --color --graph --pretty=format:'%Cred%h%Creset -%C(yellow)%d%Creset %s %Cgreen(%cr) %C(bold blue)<%an>%Creset' --abbrev-commit --"


## Commandos Para ter padronização

yarn init -y

yarn add @commitlint/config-conventional @commitlint/cli -D
New-Item .gitignore
    /node_modules
New-Item commitlint.config.js
    module.exports = {
        extends: ['@commitlint/config-conventional']
    }
yarn add husky -D

    package.json
        "husky": {
            "hooks": {
            "commit-msg": "commitlint -E HUSKY_GIT_PARAMS"
            }
        }

## Commandos para automatizar padronização

yarn add commitizen -D
yarn commitizen init cz-conventional-changelog --yarn --dev --exact


