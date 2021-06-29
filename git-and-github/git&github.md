# ANOTAÇÕES CURSO GIT E GITHUB - PREPWORK LE WAGON

- git init: para criar o repositório 
- git status: para ver o status dos arquivos; quais arquivos foram modificados etc.
- git add <"nome do arquivo">:  para adicionar o arquivo; snapshot do arquivo
- git . : adiciona todos os arquivos
- git commit --message <"mensagem">: mensagem que aparecerá no commit 
- git commit -m <"mensagem">: 
- git diff <"nome do arquivo">: mostra quais linhas foram modificadas desde o último commit
- git log: mostra os históricos dos commits
- git lg (log --graph --all --pretty=format:'%Cred%h%Creset - %s %Cgreen(%cr) %C(bold blue)%an%Creset %C(yellow)%d%Creset'): mostra os históricos dos commits de uma forma mais direta 



## BRANCHING 

Quebramos a linha contínua do tempo a criamos branch, uma ramificação paralela para trabalharmos até decidirmos se está tudo ok para "mergiar" com a master 

- git branch <"nome da branch">: comando para criar uma branch
- git branch: comando para ver quais branches eu tenho e em qual eu estou
- git checkout <"nome da branch">: comando para mudar de branch

Para "mergiar" com a master, fazemos em duas etapas: primeiro voltamos para a master (git checkout master) e depois fazemos o merge (git merge --no-f <"nome da branch">). Depois que colocamos o trabalho que estava na branch na master, podemos deletar a branch:

- git branch -d <"nome da branch">: para deletar a branch depois do merge (os commits não são deletados)

## PUSH

Para compartilhar o código com o time. git push = mande o commit para algum lugar (origin -> github) (master - é a branch principal)

- git push <"remote"> <"branch">: comando genérico
- git push origin master
- git pull origin master

Para acessar o remoto: 

- git remote -v
- git remote add (url que aparece no github)

