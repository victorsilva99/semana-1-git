# Comandos do Git
***
## Configuração Inicial
`git config --global user.name "seu nome completo"` *// adicionará seu nome aos commits de forma global* <br>
`git config --global user.email "seu email"` *// adicionará seu email aos commits de forma global*<br>
`git config --global core.editor "nome do editor"` *// informará ao terminal qual editor usar por padrão*<br>
`git config credential.helper store` *// salva a credencial atual para não precisar adicionar a senha a cada requisição*<br>
`git config --list `*// mostra as informações do repositório local*<br>
***
## Criando chave SSH
`ssh-keygen -t rsa -b 2048 -C "seu email"` *// irá criar uma chave SSH em RSA registrada com seu email*<br>
`cat ~/.ssh/id_rsa.pub` *// irá mostrar a sua chave SSH publica que acabou de ser criada*<br><br>
`eval "$(ssh-agent -s)"`<br>
`ssh-add ~/.ssh/id_rsa`<br>
*// inicia o SSH agent na sua máquina*
***
## Outros comandos
`git init` *// inicia um diretorio git na pasta atual*<br><br>
`git commit -m "mensagem do commit"` *// cria um novo commit com uma mensagem*<br>
`git commit -am "mensagem do commit` *// Adiciona as alterações ao stage area e logo após realizado o commit, sem precisar usar o comando git add. Funciona apenas com arquivos já rastreados*<br>
`git commit --amend -m "mesagem do novo commit"` *// Irá sobreescrever o último commit, como se fosse uma correção*<br><br>
`git log `*// mostra todos os commits realizados*<br>
`git log --oneline `*// mostra todos os commits realizados com informações resumidas em uma linha*<br>
`git log -n 5 `*// limita a quantidade de commits para mostrar apenas os últimos*<br>
`git log --since=ano-mes-dia `*// mostra todos os commits a partir da data informada*<br>
`git log --until=ano-mes-dia `*// mostra todos os commits anteriores a data informada*<br>
`git log --author=nome_do_autor_do_commit `*// mostra todos os commits com base no nome*<br>
`git log --grep="expressão" `*// (Global Regular Expression Print) fará uma busca geral nos commits com base na expressão informada*<br><br>
`git add nome_do_arquivo` *// adiciona o arquivo a stage area*<br>
`git add .` *// adiciona todos os arquivos para a stage area*<br>
`git add *.extensão` *// irá adicionar ao stage area todos os arquivos com a extensão informada*<br><br>
`git --version` *// verifica a versão do git*<br><br>
`git help` *// mostra o manual do git*<br><br>
`git status` *// mosra o status de todos os arquivos do diretorio atual*<br><br>
`git show` *// mostra informações do último commit*<br>
`git show -- numero_hash_commit pasta/*`  *// mostra todas as alterações da pasta informada*<br>
`git show -- numero_hash_commit pasta/nome_arquivo` *//mostra todas as alterações do arquivo informado*<br><br>
`git branch` *// lista todos as branchs do projeto*<br>
`git branch nome_da_branch` *// cria uma nova branch a partir da branch atual*<br>
`git branch -D nome_da_branch` *// irá deletar a branch informada*<br><br>
`git checkout começo_hash_commit -- nome_arquivo` *// Esse comando restaura um arquivo em especifico de um dos commits realizados, é necessário adicionar a hash do comimit (por garantia, no minimo os 5 primieiros), os dois traços idicam que você quer fazer a alteração no ponto atual da história*<br>
`git checkout nome_da_branch` *// irá direcionar para a branch informada*<br><br>
`git merge nome_da_branch` *// irá fazer um menge da branch com a master*<br><br>
`git remote add origin "link do repositorio remoto"` *// irá adicionar um repositório remoto a sua máquina*<br>
`git remote -v` *// mostra quais são os repositórios remotos atuais*<br><br>
`git push` *// irá enviar os seu repositorio local para o repositório remoto*<br>
`git push -u origin master` *// caso seja o primeiro push irá enviar os arquivos para a branch master*<br><br>
`git clone link_do_repositorio` *// irá fazer um clone do repositório informado*<br><br>
`git rm --cached nome_do_arquivo` *// remove o arquivo do próximo commit*<br>
`git rm nome_arquivo` *// remove o arquivo do diretorio, porém ele não vai para a lixeira do computador, ele é totalmente deletado*<br><br>
`git diff` *// mostra todas as alterações dos arquivos no working directory em comparação com o diretorio. (-) significa linhas removidas, (+) significa linhas adicionadas*<br>
`git diff --staged` *// mostra todas as alterações dos arquivos na stage area em comparação com o directorio.* <br>
`git diff --color-words` *// mostra quais palavras foram adicionadas ou removidas <br><br>
`git reset HEAD .` *// irá restaurar todos os arquvios para onde a HEAD está apontada*<br>
`git reset HEAD nome_arquivo` *// irá restaurar o arquivo para onde a HEAD está apontada*<br><br>
`git restore .` *// restaura todos os arquvios para o último commit realizado.* <br>
`git restore nome_arquivo ` *// restaura o arquivo para o último commit realizado.* <br>
`git restore --staged nome_arquivo` *// remove apenas o arquivo do stage area, mas não restaura suas informações* <br><br>
`git mv nome_arquivo novo_nome_arquivo` *// irá renomear o arquivo*<br>
`git mv nome_arquivo pasta/nome_arquivo` *// irá mover o arquivo para a pasta informada*<br><br>
`git clean -n` *// mostra quais arquivos não rastreados serão removidos antes de realizar o comando*<br>
`git clean -f` *// força a remoção dos arquivos não rastreados. Os arquivos deletados são completamente excluidos, não vvão para a lixeira*<br><br>
`git revert HEAD~numero` *// restaura os arquivos do commit selecionado. O numero informado é a referente ao commit abaixo da head, e não da hash.*<br>
`git revert numero_hash` *// restaura os aquivos do commit selecionado. Basta informar os primeiros números da hash*
***
# Comandos do terminal
`clear` *// limpa o terminal*<br>
`vim` *// inicia o editor vim*<br>
`cat nome_do_arquivo` *// irá mostrar as informações contidas no arquivo*<br>
`mkdir` *// (make directory) cria uma nova pasta/diretorio*<br>
`cd` *// (change directory) usado para entrar nas pastas/diretorios*<br>
`ls -a` *// mostra todos os arquivos, incluindo arquivos ocultos*<br>
`ls -al` *// mostra informações detalhadas de todos os arquivos da pasta*<br>
`touch` *// cria um novo arquivo*<br>
