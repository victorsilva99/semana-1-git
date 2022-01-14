# Comandos do Git

> Estou usando esse arquivo para guardar todos os comandos que aprendi até então estudando Git durante o plano de estágio.

- [Lista de Comandos - Site Oficial](https://git-scm.com/docs)

## Configuração Inicial

`git config --global user.name "seu nome completo"` *// Adicionará seu nome aos commits de forma global.*  
`git config --global user.email "seu email"` *// Adicionará seu email aos commits de forma global.*  
`git config --global core.editor "nome do editor"` *// Informará ao terminal qual editor usar por padrão.*  
`git config credential.helper store` *// Salva a credencial atual autentificar automaticamente.*  
`git config --list`*// Mostra as informações do repositório local.*  

## Criando chave SSH

`ssh-keygen -t rsa -b 2048 -C "seu email"` *// Irá criar uma chave SSH em RSA registrada com seu email.*  
`cat ~/.ssh/id_rsa.pub` *// Irá mostrar a sua chave SSH publica que acabou de ser criada.*  
`eval "$(ssh-agent -s)"`  
`ssh-add ~/.ssh/id_rsa`  *// Inicia o SSH agent na sua máquina.*  

## Outros comandos

`git --version` *// Verifica a versão do git.*

`git add -i` *//(i = interative) Abre uma janela interativa mostrando opções do git add.*  
`git add -p` *//(p= patch) Git irá perguntar quais modificações do arquivo eu desejo commitar. Isso serve para fazer commits de mudanças bem especificas ao invés de todas as mudanças.*  
`git add <nome_do_arquivo>` *// Adiciona o arquivo a staging area.*  
`git add -A` *// Adiciona todos os arquivos novo, deletados e modificados a staging area*.  
`git add .` *// Adiciona todos os arquivos modificados a staging area.*  
`git add *.extensão` *// Irá adicionar ao stage area todos os arquivos com a extensão informada.*  

`git branch` *// Lista as branchs locais do projeto.*  
`git branch <nome_da_branch>` *// Cria uma nova branch a partir da branch atual.*  
`git branch -a` *// Lista todas as branchs locais e remotas do projeto.*  
`git branch -D <nome_da_branch>` *// Irá deletar a branch informada.*  
`git branch -m <novo-nome>` *// Muda o nome da branch atual.*  
`git branch -m <nome-antigo> <novo-nome>` *// Altera o nome de outra branch, enquanto está na master.*  
`git branch -M "novo-nome"` *// Isso força a mudança de nome da branch, irá sobrescrever uma branch com o mesmo nome.*  
`git branch -r` *// Lista as branchs remotas do projeto.*

`git checkout -b <nome-nova-branch>` *// Cria a já entra na nova branch.*  
`git checkout hash_commit -- <nome_arquivo>` *// Esse comando restaura um arquivo especificado de um commit informado.*  
`git checkout <nome_da_branch>` *// Irá direcionar para a branch informada.*  

`git clean -n` *// Mostra quais arquivos não rastreados serão removidos antes de realizar o comando.*  
`git clean -f` *// Força a remoção total dos arquivos não rastreados.*

`git clone <link_do_repositório>` *// Irá fazer um clone do repositório informado.*
`git clone <link_do_repositório> <nome_pasta>` *// Clona o repositório para a pasta informada.*  

`git commit -m "aspas simples"` *// Com aspas simples você pode deixar mensagens com mais de 1 linha.*  
`git commit -m "mensagem do commit"` *// Cria um novo commit com uma mensagem.*  
`git commit -am "mensagem do commit` *// Adiciona as alterações ao staging area e logo após realizado o commit.*  
`git commit --amend` *// Emenda as alterações ao último commit, mantendo a mesma mensagem.*  
`git commit --amend -m "mensagem do novo commit"` *// Irá sobrescrever o último commit, adicionando outra mensagem*  

`git diff` *// Mostra todas as alterações dos arquivos no working directory. (-) linhas removidas (+) linhas adicionadas*  
`git diff --staged` *// Mostra todas as alterações que serão commitadas.*  
`git diff --color-words` *// Mostra quais palavras foram adicionadas ou removidas.*  

`git fetch` *// Baixar o conteúdo remoto, mas não vai atualizar o estado de trabalho do repositório local*  
`git fetch <nome do repositório>` *// Pega o histórico de mudanças do repositório.*  

`git gc` *// (Gargage Collector) É basicamente apagar a lixeira do Git, limpando todos os grafos feitos antes. O Git faz isso automaticamente depois de um tempo.*  

`git help` *// Mostra o manual do git.*  
`git <comando> -help` *// Mostra um guia referente ao comando informado.*  
`git help --all` *// Mostra todos os comandos do git.*  

`git init` *// Inicia um diretório git na pasta atual.*  

`git log`*// Mostra todos os commits realizados.*  
`git log -i graph` *// Mostra o git log parecido com um gráfico.*  
`git log --oneline`*// Mostra todos os commits realizados com informações resumidas em uma linha.*  
`git log -n 5`*// Limita a quantidade de commits para mostrar apenas os últimos.*  
`git log --since=ano-mes-dia`*// Mostra todos os commits a partir da data informada.*  
`git log --until=ano-mes-dia`*// Mostra todos os commits anteriores a data informada.*  
`git log --author=nome_do_autor_do_commit`*// Mostra todos os commits com base no nome.*  
`git log --grep="expressão"`*// (Global Regular Expression Print) Fará uma busca geral nos commits com base na expressão informada.*  

`git merge <nome_da_branch>` *// Irá fazer um merge da branch com a master.*  
`git merge origin/master` *// Faz um merge da branch atual com a branch master, na origin.*  

`git mv <nome_arquivo> <novo_nome_arquivo>` *// Irá renomear o arquivo.*  
`git mv <nome_arquivo> <pasta/nome_arquivo>` *// Irá mover o arquivo para a pasta informada.*  

`git pull` *// É a combinação dos comandos fetch e merge, ele sincroniza o conteúdo local com o remoto e executa um merge imediatamente para criar um commit de merge.*  
`git pull origin` *// Atualiza a branch atual de sua da sua origin usando apenas um commando.*  

`git push` *// Irá enviar o seu repositório local para o repositório remoto.*  
`git push --set-upstream origin novo-nome` *// Envia a branch renomeada para o repositório remoto.*  
`git push origin` *// Manda a branch atual para a branch origin remota.*  
`git push -u origin master` *// Caso seja o primeiro push irá enviar os arquivos para a branch master.*  
`git push origin --delete <nome-antigo>` *// Deleta a branch do repositório remoto que você apagou localmente.*  
`git push origin :nome-antigo` *// Substitua em "nome-antigo" pelo nome da sua branch antes de renomear.*  
`git push origin <nome-novo>` *// Cria a nova branch no repositório remoto*  
`git push origin -f <nome-branch>` *// Força o Git a manter a branch remota igual a local.*  

`git rebase` *// Unifica as branches envolvidas, puxando os commits para frente do branch de destino.*  
`git rebase -i HEAD~numero-de-commits` *// Abre uma janela interativa dentro do editor para gerenciar os commits indicados.*  

`git reflog` *// Mostra um log com todas as mudanças de grafos feitas pelo git.*  

`git remote rm <nome-repositório>` *// Remove um repositório remoto.*  
`git remote add origin "link do repositório remoto"` *// Irá adicionar um repositório remoto a sua máquina.*  
`git remote -v` *// Mostra quais são os repositórios remotos atuais.*
`git remote rename origin upstream` *// renomeia a origin para upstream.*  
`git remote add <nome-repositório> <link-ssh-repositório>` *// Adiciona um novo repositório usando ssh.*  
`git remote set-url origin <novo-link-repositório>` *// Substitui a url do repositório origin.*  

`git reset --` *// Restaura o estado anterior dos arquivos.*  
`git reset <hash>` *// Reseta o commit com a hash informada.*  
`git reset <nome_arquivo>` *// Restaura o arquivo ao estado anterior.*  
`git reset HEAD .` *// Irá restaurar todos os arquivos para onde a HEAD está apontada.*  
`git reset HEAD <nome_arquivo>` *// Irá restaurar o arquivo para onde a HEAD está apontada.*  
`git reset --soft HEAD~numero-de-commits` *// Irá remover os commits do log e enviar as modificações novamente para o stage. O número indicado representa os commits anteriores ao indicado no HEAD.*  
`git reset --hard HEAD~1` *// Fará um reset forçado, e limpará toda a working tree.*  

`git restore .` *// Restaura todos os arquivos para o último commit realizado.*  
`git restore <nome_arquivo>` *// Restaura o arquivo para o último commit realizado.*  
`git restore --staged nome_arquivo` *// Remove apenas o arquivo do stage area, mas não restaura suas informações*  

`git rm --cached nome_do_arquivo` *// Remove o arquivo do próximo commit.*  
`git rm -r --cached .` *// Irá remover todos os arquivos do rastreio do git.*  
`git rm nome_arquivo` *// Remove o arquivo do diretório de maneira permanente.*  

`git revert HEAD` *// Restaura o último commit realizado.*  
`git revert HEAD~numero` *// Restaura os arquivos do commit selecionado. O número informado é referente a posição do commit abaixo da HEAD.*  
`git revert HEAD --no-edit` *// Reverte o último commit realizado, pulando a mensagem do commit.*  
`git revert <commit_hash>` *// Restaura os aquivos do commit selecionado.*  

`git short log` *// Mostra apenas as mensagens dos commits, e o nome do autor.*  

`git show` *// Mostra informações do último commit.*  
`git show -- numero_hash_commit pasta/*`  *// Mostra todas as alterações da pasta informada.*  
`git show -- numero_hash_commit pasta/nome_arquivo` *// Mostra todas as alterações do arquivo informado.*  

`git stash` *// Salva as alterações sem commit (tanto as preparadas quanto as não preparadas) para uso posterior e as reverte da cópia de trabalho.*  

`git status` *// Mostra o status de todos os arquivos do diretório atual.*  
`git status --short` *// Mostra uma versão compacta do git status.*  

`git tag v.1.0.1` *// Cria uma tag simples.*  
`git tag -a v1.0.1 -m "Descrição da tag` *// Cria uma nova tag. (-a) especifica a versão, (-b) deixa um comentário sobre a tag*  

## Comandos do terminal

`clear` *// Limpa o terminal.*  
`vim` *// Inicia o editor vim.*  
`cat nome_do_arquivo` *// Irá mostrar as informações contidas no arquivo.*  
`mkdir` *// (make directory) Cria uma nova pasta/diretório.*  
`cd` *// (change directory) Usado para entrar nas pastas/diretórios.*  
`ls -a` *// Mostra todos os arquivos, incluindo arquivos ocultos.*  
`ls -al` *// Mostra informações detalhadas de todos os arquivos da pasta.*  
`touch` *// Cria um novo arquivo.*
