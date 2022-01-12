# Comandos do Git
> Estou usando esse arquivo para guardar todos os comandos que aprendi até então estudando Git durante o plano de estágio.  

## Configuração Inicial
`git config --global user.name "seu nome completo"` *// Adicionará seu nome aos commits de forma global.*  
`git config --global user.email "seu email"` *// Adicionará seu email aos commits de forma global.*  
`git config --global core.editor "nome do editor"` *// Informará ao terminal qual editor usar por padrão.*  
`git config credential.helper store` *// Salva a credencial atual autentificar automaticamente.*  
`git config --list `*// Mostra as informações do repositório local.*  

## Criando chave SSH
`ssh-keygen -t rsa -b 2048 -C "seu email"` *// Irá criar uma chave SSH em RSA registrada com seu email.*  
`cat ~/.ssh/id_rsa.pub` *// Irá mostrar a sua chave SSH publica que acabou de ser criada.*  
`eval "$(ssh-agent -s)"`  
`ssh-add ~/.ssh/id_rsa`  *// Inicia o SSH agent na sua máquina.*  

## Outros comandos
`git init` *// Inicia um diretorio git na pasta atual.*  

`git commit -m "mensagem do commit"` *// Cria um novo commit com uma mensagem.*  
`git commit -am "mensagem do commit` *// Adiciona as alterações ao staging area e logo após realizado o commit.*  
`git commit --amend -m "mesagem do novo commit"` *// Irá sobreescrever o último commit, como se fosse uma correção.*  

`git reflog` *// Mostra um log com todas as mudanças de grafos feitas pelo git.*  

`git log `*// Mostra todos os commits realizados.*  
`git log -i graph` *// Mostra o git log parecido com um gráfico.*  
`git log --oneline `*// Mostra todos os commits realizados com informações resumidas em uma linha.*  
`git log -n 5 `*// Limita a quantidade de commits para mostrar apenas os últimos.*  
`git log --since=ano-mes-dia `*// Mostra todos os commits a partir da data informada.*  
`git log --until=ano-mes-dia `*// Mostra todos os commits anteriores a data informada.*  
`git log --author=nome_do_autor_do_commit `*// Mostra todos os commits com base no nome.*  
`git log --grep="expressão" `*// (Global Regular Expression Print) Fará uma busca geral nos commits com base na expressão informada.*

`git add -i` *//(i = interative) Abre uma janela interativa mostrando opções do git add.*  
`git add -p` *//(p= patch) Git irá perguntar quais modificações do arquivo eu desejo commitar. Isso serve para fazer commits de mudanças bem especificas ao invés de todas as mudanças.*  
`git add nome_do_arquivo` *// Adiciona o arquivo a staging area.*  
`git add .` *// Adiciona todos os arquivos para a staging area.*  
`git add *.extensão` *// Irá adicionar ao stage area todos os arquivos com a extensão informada.*  

`git --version` *// Verifica a versão do git.*  

`git help` *// Mostra o manual do git.*  

`git status` *// Mostra o status de todos os arquivos do diretorio atual.*  

`git show` *// Mostra informações do último commit.*  
`git show -- numero_hash_commit pasta/*`  *// Mostra todas as alterações da pasta informada.*  
`git show -- numero_hash_commit pasta/nome_arquivo` *// Mostra todas as alterações do arquivo informado.*  

`git branch` *// Lista todos as branchs do projeto.*  
`git branch nome_da_branch` *// Cria uma nova branch a partir da branch atual.*  
`git branch -D nome_da_branch` *// Irá deletar a branch informada.*  

`git checkout hash_commit -- nome_arquivo` *// Esse comando restaura um arquivo especificado de um commit informado.*  
`git checkout nome_da_branch` *// Irá direcionar para a branch informada.*  

`git merge nome_da_branch` *// Irá fazer um menge da branch com a master.*  

`git remote add origin "link do repositorio remoto"` *// Irá adicionar um repositório remoto a sua máquina.*  
`git remote -v` *// Mostra quais são os repositórios remotos atuais.*  

`git push` *// Irá enviar os seu repositorio local para o repositório remoto.*  
`git push -u origin master` *// Caso seja o primeiro push irá enviar os arquivos para a branch master.*  

`git clone link_do_repositorio` *// Irá fazer um clone do repositório informado.*  

`git rm --cached nome_do_arquivo` *// Remove o arquivo do próximo commit.*  
`git rm -r --cached .` *// Irá remover todos os arquivos do rastreio do git.*  
`git rm nome_arquivo` *// Remove o arquivo do diretorio de maneira permanente.*

`git diff` *// Mostra todas as alterações dos arquivos no working directory. (-) linhas removidas (+) linhas adicionadas*  
`git diff --staged` *// Mostra todas as alterações que serão commitadas.*  
`git diff --color-words` *// Mostra quais palavras foram adicionadas ou removidas.*  

`git reset --` *// Restaura o estado anterior dos arquivos.*  
`git reset -- nome_arquivo` *// Restaura o arquivo ao estado anterior.*  
`git reset HEAD .` *// Irá restaurar todos os arquvios para onde a HEAD está apontada.*  
`git reset HEAD nome_arquivo` *// Irá restaurar o arquivo para onde a HEAD está apontada.*  
`git reset --soft HEAD~numero-de-commits` *// Irá remover os commits do log e enviar as modificações novamente para o stage. O número indicado representa os commits anteriores ao indicado no HEAD.*  
`git reset --hard` *// Fará um reset forçado, e limpará toda a working tree.*  

`git restore .` *// Restaura todos os arquvios para o último commit realizado.*  
`git restore nome_arquivo ` *// Restaura o arquivo para o último commit realizado.*  
`git restore --staged nome_arquivo` *// Remove apenas o arquivo do stage area, mas não restaura suas informações*  

`git mv nome_arquivo novo_nome_arquivo` *// Irá renomear o arquivo.*  
`git mv nome_arquivo pasta/nome_arquivo` *// Irá mover o arquivo para a pasta informada.*  

`git clean -n` *// Mostra quais arquivos não rastreados serão removidos antes de realizar o comando.*  
`git clean -f` *// Força a remoção total dos arquivos não rastreados.*

`git revert HEAD~numero` *// Restaura os arquivos do commit selecionado. O número informado é referente a posição do commit abaixo da HEAD.*  
`git revert numero_hash` *// Restaura os aquivos do commit selecionado.*  

`git rebase` *// Unifica as branches envolvidas, puxando os commits para frente do branch de destino.*  
`git rebase -i HEAD~numero-de-commits` *// Abre uma janela interativa dentro do editor para gerenciar os commits indicados.*  

`git gc` *// (Gargage Collector) É basicamente apagar a lixeira do Git, limpando todos os grafos feitos antes. O Git faz isso automaticamente depois de um tempo.*  

`git short log` *// Mostra apenas as mensagens dos commits, e o nome do autor.*  

# Comandos do terminal
`clear` *// Limpa o terminal.*  
`vim` *// Inicia o editor vim.*  
`cat nome_do_arquivo` *// Irá mostrar as informações contidas no arquivo.*  
`mkdir` *// (make directory) Cria uma nova pasta/diretorio.*  
`cd` *// (change directory) Usado para entrar nas pastas/diretorios.*  
`ls -a` *// Mostra todos os arquivos, incluindo arquivos ocultos.*  
`ls -al` *// Mostra informações detalhadas de todos os arquivos da pasta.*  
`touch` *// Cria um novo arquivo.*  