# Curso de Git e Github do básico ao avançado

__________________

## Comandos de iniciais do Git

__________________

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

**Uso:** git commit -m "mensagem de alteração livre"

**OBSERVAÇÃO:** O commit pode ser usado sem a flag _-m_, mas é extremamente recomendado sempre usá-lo com uma mensagem.

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

