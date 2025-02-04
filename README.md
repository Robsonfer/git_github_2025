# Curso de Git e Github do básico ao avançado

## Comandos de iniciais do Git

### _git init_:

**Ação:** O comando _git init_ cria um novo repositório git dentro da pasta selecionada

**Uso:** git init

__________________

### _git status_:

**Ação:** O comando _git status_ nos permite verificar o status do repositório criado. Qualquer modificação no projeto será vista através deste comando.

**Uso:** git status

__________________

### _git add_ ou _git add ._ :

**Ação:** O comando _git add_ é usado para dicionar um arquivo de nome especíico no stage de um diretório git.

**Uso:** git add <nome_do_arquivo_com_extensão>

**Ação:** O comando _git add ._ é usado para adicionar todos os arquivos modificados no stage de um diretório git.

**Uso:** git add .

**OBSERVAÇÃO:** O stage é um local onde os arquivos ficam pendentes aguardando pelo comando de commit.

__________________

### _git commit_:

**Ação:** O comando _git commit_ grava no diretório git todos os arquivos que estão aguardando no stage. Essa ação oficializa a alteração no projeto.

**Uso com add antes:** git commit -m "mensagem de alteração livre"

**Uso sem add antes:** git commit -a -m "mensagem de alteração livre"

**OBSERVAÇÃO:** O commit pode ser usado sem a flag _-m_, mas é extremamente recomendado sempre usá-lo com uma mensagem. Se usarmos junto a flag _-a_ não e preciso realizar um _git add_, mas fica a seu critério!

__________________

### _git push_:

**Ação:** O comando _git push_ é usado para subir as alterações feitas e gravadas no repositório local (git) para o nosso repositório remoto (github).

**Uso:** git push

__________________

### _git pull_:

**Ação:** O comando _git pull_ nos permite sincronizar nosso repositório local com o repositório remoto. Pode ser que a equipe está à frente no desenvolvimento e que as mudanças já tenham sido atualizadas no repositório remoto. Sempre inicie seu dia com um _git pull_ .

**Uso:** git pull

__________________

### _git clone_:

**Ação:** O comando _git clone_ é usado para clonar um repositório remoto (github) para seu repositório local (git). A partir daí, pode-se editar o projeto localmente e tratar seu repositório com todos os comandos acima normalmente.

**Uso:** git clone <https://linkdorepositorioaserclonado.git>

__________________

### _git rm_:

**Ação:** O comando _git rm_ é usado para remover arquivos da monitoração do git. Após remover o arquivo, ele não terá mais suas atualizações consideradas pelo git.

**Uso:** git rm <nome_do_arquivo_com_extensão>

**OBSERVAÇÃO:** O arquivo voltará a ser monitorado pelo git novamente somente depois do comando _git add_ .

__________________

### _git log_:

**Ação:** O comando _git log_ nos permite acessar um log de todos os commits realizados no diretório separadas por período.

**Uso:** git log

__________________

### _git mv_:

**Ação:** O comando _git mv_ nos permite reanomear um arquivo e também movê-lo para outra pasta. Quando usado esse comando o arquivo antigo é deletado e é criado um novo arquivo com o novo nome e/ou na nova pasta.

**Uso para renomear:** git mv <novo_nome_do_arquivo_com_extensão>

**Uso para mover:** git mv <nome_do_arquivo_com_extensão> <diretório\do\destino\desejado>

**OBSERVAÇÃO:** Podemos também renomear e mudar a pasta ao mesmo tempo.

__________________

### _git checkout_:

**Ação:** O comando _git checkout_ pode ser retornado totalmente ao seu estado original, ou seja, no estado que ele se encontra no repositório remoto (github).

**Uso:** git checkout <nome_do_arquivo_com_extensão>

**OBSERVAÇÃO:** Esse comando nos permite limpar o arquivo totalmente de alterações, pois mesmo que mantivermos o arquivo igual antes, uma alteração será computada. Usando este comando, nosso diretório fica realmente original como antes do _git pull_ .

__________________

### _.gitignore_:

**Ação:** É possível fazer com que o git ignore arquivos e diretórios específicos se assim desejar. Existem arquivos/diretórios que outras pessoas não precisam ter acesso dentro de nossos projetos. Geralmente são arquivos de dados sensíveis ou arquivos gerados automaticamente.

**Uso:** Basta criar um arquivo chamado.gitignore dentro do seu repositório. Ao abrí-lo, você pode adicionar os arquivos que deseja que o git ignore, como por exemplo: modelo.txt ou node_modules/*. O uso do * determina que o git deve ignorar tudo o que existir dentro daquela pasta.

__________________

### _git reset_:

**Ação:** Usando o comando _git reset_ é possível também desfazer todas as alterações em um repositório, inclusive as alterações já comitadas. Todas as alterações serão excluídas. É um comando que precisamos ter muito cuidado, pois podemos perder tudo.

**Uso:** git reset --hard <branch_a_ser_resetado> Exemplo: git reset --hard origin/main

__________________

## O que são Branches?

É a forma que o git separa as versões do projeto. Quando um projeto é criado, ele inicia na branch master.

Geralmente cada nova feature de um projeto fica em um branch separado e após a finalização, todos os braches são unidos para ter o código-fonte final.

__________________

### _git branch_:

**Ação de consulta:** O comando _git branch_ nos permite visualizar todos os branchs disponíveis.

**Uso:** git branch

**Ação de criação de nova branch:** Ele também pode ser usado para criar um nova branch.

**Uso:** git branch <nome_do_novo_branch>

__________________

### _git branch -d_ ou _--delete_:

**Ação:** Os comandos _git branch -d_ ou _git branch --delete_ são usados para deletar um branch. Não é comum deletar um branch, afinal e importante guardar o histórico do trabalho.

**Uso _-d_ :** git branch -d <nome_do_branch>

**Uso _--delete_ :** git branch --delete <nome_do_branch>

__________________

### _git checkout_ e _git checkout -b_:

**Ação:** Nós usamos o comando _git checkout_ para mudar de branch de trabalho. E usamos o comando _git checkout -b_ para mudar de branch e já criar um branch novo ao mesmo tempo.

**Uso mudança:** git branch <nome_do_branch_desejado_já_existente>

**Uso mudança + criação:** git branch -b <nome_do_branch_a_ser_criado>

**OBSERVAÇÃO IMPORTANTÍSSIMA:** _ATENÇÃO, É IMPORTANTÍSSIMO QUE TODA ALTERAÇÃO FEITA NO BRANCH ATUAL SEJA COMMITADA ANTES DA MUDANÇA DE BRANCH, POIS QUALQUER ALTERAÇÃO QUE NÃO ESTEJA COMMITADA SERÁ LEVADA PARA O NOVO BRANCH E SERÁ CONSIDERADA COMO UMA ALTERAÇÃO DO BRANCH ATIVO MAIS ATUAL!!!_

__________________

### _git merge_:

**Ação:** O comando _git merge_ nos permite unir dois branches distintos. Este é um dos comandos mais utilizados. Digamos que o branch main atualiza no meio da sua tarefa. Basta dar um merge para ter o branch main atualizado e ainda assim continuar a trabalhar na sua parte sem perder o andamento do seu trabalho.

É por meio dele que recebemos as atualizações dos outros devs. Tudo isso acontece antes mesmo de subir para o respositório remoto.

**Uso:** git merge <nome_do_branch_a_ser_unido_ao_seu>

**OBSERVAÇÃO:** Nunca devemos dar um merge de nosso conteúdo através do branch main, somente devemos mergear nosso branch com o main. Não devemos nunca alterar o main diretamente pelo git. Essa alteração será feita direto pelo github ou bitbucket.

__________________

### _git stash_:

**Ação:** O comando _git stash_ nos permite apagar todas as alterações feitas em um projeto com a diferença que quando o utilizamos, estas alterações vão para um outro local do repositório que não é mais monitorado pelo git, entretanto, fica salvo, como se fosse um stage. Ele traz o código para o último status antes do commit. Se commitar, não dá mais pra usar o stash.

**Uso:** git stash

__________________

### Consultado stashes

### _git stash list_:

**Ação:** O comando _git stash list_ nos permite ver todas as stashes que foram criadas.

**Uso:** git stash list

**Ação:** Quando usamos o _git stash list_, nós conseguimos ver o número do nosso stash. Com o comando _git stash show -p <número>_ podemos ver todas as alteraçõos contidas neste stash de número específico.

**Uso:** git stash show -p <número>

__________________

### Recuperando stashes

### _git stash apply <número>_:

**Ação:** O comando _git stash apply <número>_ nos permite recuperar uma stash criada pelo seu número identificado na consulta _git stash list_. Esta stash é revertida novamente ao nosso branch atual e podemos continuar de onde paramos.

**Uso:** git stash apply <número>

__________________

### Removendo stashes

### _git stash clear_:

**Ação:** Este comando remove todas as stashes do repositório

**Uso:** git stash clear

### _git stash drop_:

**Ação:** Este comando remove somente a stash com o nome específico escolhido

**Uso:** git stash drop <nome>

__________________
