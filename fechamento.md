---
layout: default
---

### Índice

1. [Fechamento de Sprint](https://ianleocadio.github.io/git-flow/fechamento#fechamento-de-sprint)
2. [Fechamento de Release](https://ianleocadio.github.io/git-flow/fechamento#fechamento-de-release)
3. [Fechamento de Hotfix](https://ianleocadio.github.io/git-flow/fechamento#fechamento-de-hotfix)




![alt](https://ianleocadio.github.io/git-flow/fechamento/img/Versoes.png)

>Releases são entregas de momentos da aplicação, cada release demarca um ponto de versionamento definitivo. Para gerar uma release 
> devemos nos atentar primeiramente as versões e tags de identificação.

* Normalmente para cada 10 releases é incrementado +1 na versão da aplicação, ou seja, se o projeto está na versão v1.9 e realiza a relese 10, logo o projeto vai para a versão v2.0. No entanto, isto não se faz obrigatório, cabe a cada gerente de projeto decidir se isto é, ou não, desta forma. Podendo ter versões v1.13 e assim por diante.
* Quanto a Hotfixes não se faz necessário uma limitação de quantos hotfixes podem ser gerados, ou seja, poderão ter versões do tipo: v2.1.12, v3.9.20. Porém, deve-se lembrar que para cada hotfix gerado incrementa-se +1 no terceito dígito da versão.
* Para cada release criada é zerado o terceiro digito. Se a versão do projeto está v1.9.15 então quando a o décimo release, a aplicação irá para sua versão v2.0, ou v.2.0.0.

____
## Fechamento de Sprint
1. Criar __Pull request__
    * __Nomenclatura:__ Fechamento do Sprint @
    * ___base:___ develop -------- ___compare:___ sprint
2. Aceite do Pull request
    * Ação: __Create a merge commit__
        * __Merge pull request__
        * Alterar o nome que será gerado para o nome correto do pull request, incluíndo (#Código do pull request)
3. Trazer o commit gerado pelo pull request para a branch de __sprint__, atualizando-a com a __develop__
      * Atualizando ambiente e removendo branchs locais para garantir integridade do merge
      ```git  
        $ git remote update -p
        $ git branch -d sprint
      ```
      * Trocando para sprint atualizada com a origin e realizando merge com a develop
      ```git
        $ git checkout sprint
        $ git merge --ff-only origin/develop
        -- Se o merge falhar utilize o rebase:
        $ git rebase -p origin/develop
        -- Em seguida realize o push
        $ git push origin
      ```
4. Por fim, verificar se a develop está com o status de commits: "This branch is even with sprint."

[Subir](https://ianleocadio.github.io/git-flow/fechamento#%C3%8Dndice)
____
## Fechamento de Release
1. Criar __Pull request__
    * __Nomenclatura:__ Release v@.@.@
    * ___base:___ master -------- ___compare:___ develop
2. Aceite do Pull request
    * Ação: __Create a merge commit__
        * __Merge pull request__
        * Alterar o nome que será gerado para o nome correto do pull request, incluíndo (#Código do pull request)
3. Trazer o commit gerado pelo pull request para a branch da __develop__ e __sprint__, atualizando-os com a __master__
      * Atualizando ambiente e removendo branchs locais para garantir integridade do merge
      ```git 
        $ git remote update -p
        $ git branch -d develop
        $ git branch -d sprint
      ```
      * Trocando para develop atualizada com a origin e realizando merge com a master
      ```git
        $ git checkout develop
        $ git merge --ff-only origin/master
        -- Se o merge falhar utilize o rebase:
        $ git rebase -p origin/master
        -- Em seguida realize o push
        $ git push origin
      ```
      * Trocando para sprint atualizada com a origin e realizando merge com a master
      ```git
        $ git checkout sprint
        $ git merge --ff-only origin/master
        -- Se o merge falhar utilize o rebase:
        $ git rebase -p origin/master
        -- Em seguida realize o push
        $ git push origin
      ```
4. Criar uma branch de release temporária
    * __Objetivo:__ Branch backup da release e _target branch_ para tag
    * __Nomenclatura:__ release-@.@.@
5. Na aba de releases do repositório, selecione a opção de _Draft a new release_

    ![alt](https://ianleocadio.github.io/git-flow/fechamento/img/gerando_tag.png)
6. Publique a release!

[Subir](https://ianleocadio.github.io/git-flow/fechamento#%C3%8Dndice)
____
## Fechamento de Hotfix
1. Criar __Pull request__
    * __Nomenclatura:__ Hotfix -> Release v@.@.@
    * ___base:___ master -------- ___compare:___ hotfix/release-@.@.@
2. Aceite do Pull request
    * Ação: __Squash and Merge__
        * Alterar o nome que será gerado para o nome correto do pull request, incluíndo (#Código do pull request)
3. Trazer o commit gerado pelo pull request para a branch da __develop__ e __sprint__, atualizando-os com a __master__
      * Atualizando ambiente e removendo branchs locais para garantir integridade do merge
      ```git  
        $ git remote update -p
        $ git branch -d develop
        $ git branch -d sprint
      ```
      * Trocando para develop atualizada com a origin e realizando merge com a master
      ```git
        $ git checkout develop
        $ git merge --ff-only origin/master
        -- Se o merge falhar utilize o rebase:
        $ git rebase -p origin/master
        -- Em seguida realize o push
        $ git push origin
      ```
      * Trocando para sprint atualizada com a origin e realizando merge com a master
      ```git
        $ git checkout sprint
        $ git merge --ff-only origin/master
        -- Se o merge falhar utilize o rebase:
        $ git rebase -p origin/master
        -- Em seguida realize o push
        $ git push origin
      ```
4. Remover a branch de hotfix
5. Criar uma branch de hotfix temporária em cima da __master__ para garantir uma branch backup da release e _target branch_ para gerar a nova tag
    * __Nomenclatura:__ hotfix/release-@.@.@
6. Na aba de releases do repositório, selecione a opção de _Draft a new release_

    ![alt](https://ianleocadio.github.io/git-flow/fechamento/img/gerando_tag_2.png)
7. Publique a release!

[Subir](https://ianleocadio.github.io/git-flow/fechamento#%C3%8Dndice)




