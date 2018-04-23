### Índice
1. [Comandos](https://ianleocadio.github.io/git-flow#comandos)
    * [Clone](https://ianleocadio.github.io/git-flow#clone)
    * [Pull](https://ianleocadio.github.io/git-flow#pull)
    * [Checkout](https://ianleocadio.github.io/git-flow#checkout)
    * [Status](https://ianleocadio.github.io/git-flow#status)
    * [Log](https://ianleocadio.github.io/git-flow#log)
    * [Branch](https://ianleocadio.github.io/git-flow#branch)
    * [Commit](https://ianleocadio.github.io/git-flow#commit)
    * [Merge](https://ianleocadio.github.io/git-flow#merge)
    * [Push](https://ianleocadio.github.io/git-flow#push)
2. [Branches](https://ianleocadio.github.io/git-flow#branches)
    * [Master](https://ianleocadio.github.io/git-flow#master)
    * [Develop](https://ianleocadio.github.io/git-flow#develop)
    * [Sprint](https://ianleocadio.github.io/git-flow#sprint)
    * [Story](https://ianleocadio.github.io/git-flow#story)
    * [Task](https://ianleocadio.github.io/git-flow#task)
3. [GitFlow p/ Scrum](https://ianleocadio.github.io/git-flow#gitflow-p-scrum)
    * [Començando a desenvolver](https://ianleocadio.github.io/git-flow#come%C3%A7ando-a-desenvolver)
        * [@ Story independente](https://ianleocadio.github.io/git-flow#-story-independente)
        * [@ Task _dependente_ de Story](https://ianleocadio.github.io/git-flow#-task-dependente-de-story)
        * [@ Task _independente_ de Story](https://ianleocadio.github.io/git-flow#-task-independente-de-story)
    * [Desenvolvendo...](https://ianleocadio.github.io/git-flow#desenvolvendo)
        * [@ Story e Task](https://ianleocadio.github.io/git-flow#-story-e-task)
        * [Cuidados no desenv.](https://ianleocadio.github.io/git-flow#cuidados-a-serem-tomados-durante-o-desenvolvimento)
    * [Término do desenvolvimento](https://ianleocadio.github.io/git-flow#t%C3%A9rmino-do-desenvolvimento)
        * [@ Story independente e/ou Task _independente_ de Story](https://ianleocadio.github.io/git-flow#-story-independente-eou-task-independente-de-story)
        * [@ Task _dependente_ de Story](https://ianleocadio.github.io/git-flow#-task-dependente-de-story-1)
4. [Pull Request](https://ianleocadio.github.io/git-flow#pull-request)
    * [Nomenclaturas](https://ianleocadio.github.io/git-flow#nomenclaturas)
5. [Versões/Tags](https://ianleocadio.github.io/git-flow#vers%C3%B5estags)


## Comandos

### Clone

* ```$ git clone <HTTPS.git>```
    * Copia o repositório remoto para o local de trabalho.

### Pull

* ```$ git pull```
    * Busca as atualizações no repositório remoto e as trás para o repositório local. Novas branches, novos commits, entre outros

___
### Checkout


* ```$ git checkout <local-branch>```
    * Troca para a branch especificada. Considerando branches  __já existentes__ localmente e remotamente
* ```$ git checkout -b <new-branch>```
    * Cria e troca para branch criada. Após o push a branch será criada remotamente também
* ```$ git checkout -b <new-branch> <existing-branch>``` 
    * Cria uma nova branch a partir de uma branch remota/local. Após o push a branch será criada remotamente também

___
### Status
* ```$ git status```
    * Verifica o estado das mudanças da branch atual

### Log
* ```$ git log -N```
    * Lista os __N__ commits anteriores 

___
### Branch
* ```$ git branch --list```
    * Lista as branches locais.
* ```$ git branch -D <branch>```
    * Exclui a branch local.

___
### Commit

* ```$ git add <archive's-path>```
    *  Adiciona as modificações do arquivo ao versionamento do projeto
* ```$ git add .```
    * Adiciona todos os arquivos que tiveram mudanças ao versionamento do projeto
* ```$ git commit -m "<Commit message>"```
    * Efetiva os arquivos e suas mudanças e atrela-os a uma mesagem

### Merge
* ```$ git merge <branch>```
    * Trás as atualizações e diferenças da branch selecionada na branch atual

### Push
* ```$ git push origin```
    * Manda todas as alterações commitadas localmente para o repositório remoto



## Branches

* Master
* Develop
* Sprint
* Story
* Task

### Master
>    Reflete o código-fonte principal para entregas do projeto.

### Develop
>   Reflete o código-fonte após cada final de sprint

### Sprint
>   Durante o sprint esta branch agrega todos as stories que tiveram seu desenvolvimento e testes finalizados

### Story
* Nomenclatura
    * story/*
>   Visa o versionamento do desenvolvimento do requisito previsto guardando sua progressão

### Task
* Nomenclatura
    * task/*
>    Há duas opções para branches de task:
> > Quando duas pessoas trabalham em somente uma Story 

> Ou

> > Quando há diversas stories semelhantes que dependem uma da outra. Então é criado uma task e atrelada a todas as stories, evitando a crição de diversas branches de Story ou uma branch de Story com nomenclatura errada


___

## GitFlow p/ Scrum

![alt](https://ianleocadio.github.io/git-flow/img/gitflow.png)

### Começando a desenvolver:

#### @ Story independente

> ![alt](https://ianleocadio.github.io/git-flow/img/sprint%20e%20story.png)

> Quando há somente um desenvolvedor no mesmo requisito, somente cria-se a branch de _story_, com base na branch _sprint_,  e seu desenvolvimento é versionado nela.

#### @ Task _dependente_ de Story

> ![alt](https://ianleocadio.github.io/git-flow/img/story%20e%20task.png)

> Quando há mais de um desenvolvedor na _story_ e há diferentes requisitos a serem trabalhados, cria-se a branch de ___story___ e com base nesta, as branches de ___task___ cada uma com seu respectivo código do Jira.

#### @ Task _independente_ de Story

> ![alt](https://ianleocadio.github.io/git-flow/img/sprint%20e%20task.png)

> Quando há a necessidade de desenvolvimento de uma __task__ independente de uma __story__, cria-se a __task__ a partir da __sprint__ adotando-a como branch pai. Importante frisar que neste caso é preciso trazer as constantes mudanças, sempre que houver, da __sprint__ para esta nova branch __task__.
___
### Desenvolvendo...

#### @ Story e Task
> Commits em relação ao requisito deverão ser feitos em suas respectivas branches.
```
-- Adiciona todos os arquivos não versionados ao versionamento
$ git add .
-- Realiza commit local dos arquivos adicionados ao versionamento
$ git commit -m "<Mensagem do commit local>"
-- Realiza o push dos commits locais para a branch remota
$ git push origin
```
#### __Cuidados a serem tomados durante o desenvolvimento:__
   * Sempre manter a branch em que você estiver trabalhando atualizada com a branch pai dela
   * Responsáveis pelas Stories deverão manter a respectiva branch da Story atualizada com a Sprint
   * Tasks dependentes de Story __não precisam de pull request com a Story__ basta mergiá-la diretamente na Story pai



____
### Término do desenvolvimento:
#### @ Story independente e/ou Task _independente_ de Story
> Quando houver o término do requisito o esquema de finalização é o mesmo nestes dois casos. Primeramente deve-se realizar o pull para trazer todas as atualizações da __sprint__ remota para a __sprint__ local. Em seguida realizar o merge da Sprint com a __task__ ou a __story__:
```git
$ git checkout task/* (ou git checkout story/*)
$ git remote update -p
$ git merge --ff-only origin/sprint
-- Se o merge falhar utilize o rebase:
$ git rebase -p origin/sprint
-- Em seguida realize o push
$ git push
-- Caso o push falhe, verifique o log de commits e veja se há alguma divergencia, caso contrário utilize o parâmetro -f no push
```
> Após atualizada, realizar o Pull Request do requisito com a ___base___ no sprint e o ___compare___ na branch que queira finalizar, não esquecendo da nomenclatura padrão para finalização de desenvolvimento de requisitos:

*  Developed -> Task(Story)/*

#### @ Task _dependente_ de Story

> Quando há o término do desenvolvimento de uma ___task___ deve-se mergiar a ____task___ na ___story___ sem a necessidade de um pull request:
```git
$ git checkout story/*
$ git remote update -p
$ git merge --ff-only task/*
-- Se o merge falhar utilize o rebase:
$ git rebase -p task/*
$ git push
-- Caso o push falhe, verifique o log de commits e veja se há alguma divergencia, caso contrário utilize o parâmetro -f no push
```
___

### Pull Request

* #### Nomenclaturas:
     * __Developed -> Task/*__
     > __Propósito:__ Término do desenvolvimento de Task _independente_

     > __Condição de aceite:__ Após aprovação do _code review_

     > __Base__: sprint  _______  __Compare__: task/*
     
     * __Developed -> Story/*__
     > __Propósito:__ Término do desenvolvimento de Story em geral

     > __Condição de aceite:__ Após aprovação do _code review_

     > __Base__: sprint  _______  __Compare__: story/*
     
     * __Fechamento de Sprint *__
     > __Propósito:__ Pull request aberto para finalização de sprint.

     > __Condição de aceite:__ Necessidade do fechamento do sprint e dermacar que naquele ponto da sprint houve seu fechamento na versão <*>

     > __Base__: develop  _______  __Compare__: sprint
     
     * __Release *__
     > __Propósito:__ Realizar entregas

     > __Condição de aceite:__  Grande parte dos requisitos previstos devem estar na develop já desenvolvidos e aprovados por QA. 
     > Correções de pré-release já realizadas.

     > __Base__: master  _______  __Compare__: develop
    

* #### Branches de correções:

    * __Fix -> Sprint *__
     > __Propósito:__ Correções gerais pré finalização de sprint

     > __Condição de aceite:__  Aprovações no _code review_ e _QA_

     > __Base__: sprint  _______  __Compare__: fix/sprint-*

    * __Fix -> Release *__
     > __Propósito:__ Correções gerais pré finalização de release

     > __Condição de aceite:__  Aprovações no _code review_ e _QA_

     > __Base__: develop  _______  __Compare__: fix/release-*

     * __Hotfix -> Release *__
     > __Propósito:__ Correções pós entrega de release

     > __Condição de aceite:__  Aprovações no _code review_ e _QA_

     > __Base__: master  _______  __Compare__: develop



___

### Versões/Tags



* ___v1.0___
> Versão inicial

* ___v1.1___
> Entrega 1 (release)
* ___v1.1.1___
> Hotfix da entrega 1 (release)
* ___v1.2___
> Entrega 2
* ___v1.2.1___
> Hotfix da entrega 2