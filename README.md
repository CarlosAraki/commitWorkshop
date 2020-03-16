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


    git config --global alias.lg "log --color --graph --pretty=format:'%Cred%H%Creset -%C(yellow)%d%Creset %s %Cgreen(%cr) %C(bold blue)<%an>%Creset' --abbrev-commit --"


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

    "scripts":{
        "commit":"git-cz"
    }

## Testando Padrões em projetos diferentes

### React 
    create-react-app git_app_react
    cd git_app_react
    yarn start

### PHP 
    mkdir git_app_php
    New-Item index.php 



## Comandos Hub

    hub issue show 1
    hub issue update 2 -m "Tem que ser um Ola mundo" 
    hub issue create -l bug -m "Tem que estar em Português" 
        labels: bug 
                documentation
                duplicate 
                enhancement 
                good first issue 
                help wanted
                invalid 
                question 
                wontfix

## Fluxo Basico

git versiona o código e cria pontos na história... (são os commits)
GitHub ele visualiza todo esse versosionamento de forma mais amigável

Imagina que vc pode alem de ir pra frente e para tras na história do código vc pode criar universos paralelos do mesmo código

    `hub init`
    `hub status`
        Untracking mostra o que não está versionado
        Changes to be committed mostra mudanças salvas na história mas sem nenhuma documentacao 
    `hub add `
        Adiciona um ponto na história na minha versão do codigo
    `hub commit`
        Adiciona documentacao do ponto na história
    `hub log`
        mostra os pontos na história com a documentação pronta
    `hub diff`
        mostra diferenças dos commits em relação a sua base
    `hub checkout` 
        Permite que pule para algum ponto na história ou em algum universo paralelo (incluindo branchs)
    `hub branch -a`
        Mosta os branchs 
    `hub branch minhabranch`
        cria para nova branch
    `hub merge minhabranch`
        junta o ramo na branch em que vc deu checkout
    `hub branch -D minhabranch`
        deleta a branch local
    `hub create` = 
        `git remote add origin https repositorio`
    hub branch --set-upstream-to=origin/<branch> <branch> 