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

**OBSERVAÇÃO:** Nunca devemos dar um merge de nosso conteúdo através do branch main, somente devemos mergear nosso branch com o main. Não devemos nunca alterar o main diretamente pelo git. Essa alteração será feita direto pelo github ou bitbucket pela pessoa que coordena todos esses processos.

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

**Uso:** git stash drop <número>

__________________

### Criando tags

### _git tag -a <nome> -m "<mensagem>"_:

**Ação:** A tag nos permite criar "checkpoints" dentro de um branch. Basicamente com oum stash ao contrário, pois as tags como o stash, podem ser adicionadas e removidas por etapas. Mas a tag, diferente do stash, nós podemos commitar tranquilamente sem problemas.

**Uso:** git tag -a v1.0 -m "Primeira versão"

__________________

### Verificando e alterando tags

### _git show <nome>_:

**Ação:** Nos permite consultar as tags na tela.

**Uso:** git show "v1.0"

### _git checkout <nome>_:

**Ação:** Nos permite trocar de tag assim como fazemos com os branchs.

**Uso:** git checkout v1.0

__________________

### Enviando tags para o repositório

### _git push origin <nome>_:

**Ação:** Este comando nos permite enviar uma tag específica para o repositório remoto.

**Uso:** git push origin v1.0

### _git push origin --tags_:

**Ação:** Este comando nos permite enviar todas as tags de uma só vez para o repositório remoto.

**Uso:** git push origin --tags


**OBSERVAÇÃO:** É importante lembrar que diferente das stashes, as tags devem ser commitadas.

__________________

### Encontrando branches

### _git fetch_:

**Ação:** Este comando nos ajuda a encontrar branches remotos. Branches novos são criados o tempo todo e o seu git pode não estar mapeando eles. Com o comando _git fetch_ você é atualizado de todos os branches e tags que ainda não estão conhecidos por você. É muito útil para usar o branch de algum outro dev do time, por exemplo.

**Uso:** git fetch

__________________

### Recebendo alterações

### _git pull_:

**Ação:** O camando _git pull_ serve para recebermos atualizações do repositório remoto. Cada branch pode ser atualizado com o git pull. Utilizamos para atualizar a main do repo como também quando trabalhamos em conjunto e queremos receber as atualizações de um dev.

**Uso:** git pull

__________________

### Enviando alterações

### _git push_:

**Ação:** O camando _git pull_ faz o inverso do pull, ele envia as alterações para o remoto. Serve também para enviar as atualizações de um branch específico para outro dev, ou quando terminamos uam tarefa e precisamos enviar ao repo.

**Uso:** git push

__________________

### Utilizando o remote

### _git remote_:

**Ação:** Com o git remote podemos fazer algumas ações como adcionar um repo para trackear ou remover. Sempre que criamos um repo remoto, adicionamos ele com git remote add origin <link>

**Uso:** Digamos que nós mudamos nosso repositório remoto do github para o bitbucket. É neste momento que usamos os comandos:

- git remote -v - para identificar a origin (não é obrigatório)

- git pull - para garantir que teremos o repo local completo antes de tudo.

- git remote rm origin - para remover o vínculo do repo local com o repo remoto do github.

- git remote -v - para confirmar a remoção (não é obrigatório)

- git remote add origin <link> - para adicionar o vínculo do repo local com o remoto do bitbucket.

**OBSERVAÇÃO:** Podemos fazer o git remote rm e o git remote add direto, sem seguir os procedimentos acima, mas é sempre recomendado garantir a segurança dos dados com os demais comandos.

__________________

### Trabalhando com submódulos

### _git sumodule_:

**Ação:** Submódulo é a maneira que temos de possuir dois ou mais projetos em um só repositório. Podemos adicionar uma dependência ao nosso projeto atual, porém mantendo suas estruturas separadas.

**Uso:** Para adicionar o submódulo utilizamos o comando **git sumodule add <repo>** e para verificar os submódulos, o comando é **git submodule**

**OBSERVAÇÃO:** Podemos usar uma biblioteca desta forma para que ela fique dentro do projeto e ainda assim seja um repositório à parte.
__________________

### Atualizando submódulos

### _git push --recurse-submodules=on-demand_:

**Ação:** Para atualizar um submódulo primeiro devemos commitar as mudanças.

**Uso:** E para enviar para o repo do submódulo utilizamos **git push --recurse-submodules=on-demand**. Este fluxo fará a atualização apenas do submódulo.

__________________

### ANÁLISE E INSPEÇÃO

### Exibindo Informações

### _git show_:

**Ação:** O comando _git show_ nos dá diversas informações úteis. Ele nos dá as informações do branch atual e também seus commits. As modificações de arquivos entre cada commit também são exibidas. Podemos exibir as informaç~es de tags também.

**Uso:** Para exibir informações de commits? **git show** e para exibir informações das tags: **git show <tag>**

__________________

### Exibindo Diferenças

### _git diff_:

**Ação:** O comando _git diff_ serve para exibir as diferenças de um branch. Quando utilizado as diferenças do branch atual com o remoto serão exibidas no terminal. Podemos também ver a diferença entre arquivos.

**Uso:** Para exibir diferenças entre o branch atual e o repositório remoto: **git diff**, para exibir a diferença entre branches: **git diff main outro_branch** e para exibir diferenças entre arquivos: **git diff <arquivo_a> <arquivo_b>**

__________________

### Log resumido

### _git shortlog_:

**Ação:** O comando _git shortlog_ nos dá um log resumido do projeto. Cada commit será unido por nome do autor. Podemos então saber quais commits foram enviados ao projeto e por quem.

**Uso:** git shortlog

__________________

### ADMINISTRAÇÃO DO REPOSITÓRIO

### Limpando arquivos untracked

### _git clean_:

**Ação:** O comando _git clean_ vai verificar e limpar aquivos que não estão sendo trackeados, ou seja, arquivos que você não usou _git add_. Utilizado para arquivos que são gerados automaticamente por exemplo, pois atrapalham a visualização.

**Uso:** git clean

__________________

### Otimizando o repositório

### _git gc_:

**Ação:** O comando _git gc_ é uma abreviação para **garbage collector**. Ele identifica arquivos que não são mais necessários e os exclui. Isso fará com que o respositório seja otimizado em questões de performance.

**Uso:** git cg

__________________

### Verificando a integridade dos arquivos

### _git fsck_:

**Ação:** O comando _git fsck_ é uma abreviação de File System Check. Esta instrução verifica a integridade de arquivos e sua conectividade com o respositório. Ele analisa e identifica possíveis corrupções em arquivos. Comando de rotina, utilizado para ver se está tudo certo com nossos arquivos.

**Uso:** git fsck

__________________

### Reflog

### _git reflog_:

**Ação:** O _git reflog_ vai mapear todos os seus passos no repositório. Até uma simples mudança de branch é inserida neste log. Os reflogs ficam salvos até expirar o seu prazo. O tempo padrão de expiração é de 30 dias, mas esse tempo pode ser alterado.

**Uso:** git reflog

__________________

### Aula 68 - Comprimindo o repositório

### _git archive --format zip --output main_files.zip main_:

**Ação:** Com o comando git archive podemos transformar o repo em um arquivo compactado. Então o branch main vai estar zipado no arquivo main_files.zip

**Uso:** git archive --format zip --output main_files.zip main

__________________

### Aula 71 - Técnica de private branch

**Ação:** Há uma técnica chamada private branches onde criamos branches que não serão compartilhados no repositório, então podemos colocar qualquer commit. Ao fim da solução do problema podemos fazer um **rebase**.

E como devemos proceder para criar esse branch privado?
- Primeiro criamos um branch para trabalhar nossa parte do trabalho, por exemplo: _git checkout -b funcao_a_;
- Depois precisamos derivar o branch privado desse branch, pois será feito o rebase aí: _git checkout -b private_funcao_a_;
- Trabalhamos normalmente dentro do branch _private_funcao_a_, commitamos tudo normalmente;
- Então mudamos para o branch da função que não é privado: _git checkout func_a_;
- Neste momento damos o _git rebase funcao_a private_funcao_a -i_;
- Esse comando vai trazer tudo o que fizemos de commit e onde vamos escolher o que queremos e o que não queremos;
- Ele trará da seguinte forma: pick <código> <nome do commit>;
- Então apertamos i e começamos a editar as linhas dos commits;
- Os que queremos deletar digitamos squash, ele vai deletar essa mensagem do commit e vai mergear o código com os demais que temos;
- Os que queremos manter o commit mas queremos renomear, digitamos reword;
- Então damos um ESC, digitamos :x! e damos um ENTER.(isso fará com que o arquivo seja salvo);
- Podemos a qualquer momento das mensagens posteriores digitar i e alterar as informações dos commits que queremos e voltar a salvar com :x!;
- Podemos nessa edição usar # para comentar as mensagens, isso faz com que o título do commit vire um comentário e não suba junto com os demais, mas também não será apagado. O Código daque commit será mergeado com os demais.
- Depois de tudo isso, basta dar um push.

**Uso:** git rebase <atual> <private> -i

**OBSERVAÇÃO:** Mas para que a situação fique completa, devemos também excluir e renomear branches, o que demanda mais dois comandos: o **squash** para excluir os branches ruins e o **reword** para renomear os branches que queremos reaproveitar

__________________

### Aula 72 - Melhorando as mensagens dos commits

**Ação:**
- Separar **assunto** do corpo da mensagem;
- Assunto com no **máximo 50 caracteres**;
- Assunto com **letra inicial maíuscula**;
- Corpo com no **máximo 72 caracteres**;
- Explicar o **por que e como** do commit, e não como o código foi escrito.

__________________

