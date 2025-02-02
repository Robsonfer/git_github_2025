# Curso de Git e Github do básico ao avançado

## Comandos de iniciais do Git

### _git init_:

**Ação:** O comando _git init_ cria um novo repositório git dentro da pasta selecionada
**Uso:** git init

### _git status_:

**Ação:** O comando _git status_ nos permite verificar o status do repositório criado. Qualquer modificação no projeto será vista através deste comando.
**Uso:** git status

### _git add_ ou _git add ._:

**Ação:** O comando _git add_ é usado para dicionar um arquivo de nome especíico no stage de um diretório git.
**Uso:** git add <nome_do_arquivo_com_extensão>

**Ação:** O comando _git add ._ é usado para adicionar todos os arquivos modificados no stage de um diretório git.
**Uso:** git add .

**OBSERVAÇÃO:** O stage é um local onde os arquivos ficam pendentes aguardando pelo comando de commit.

### _git commit_:

**Ação:** O comando _git commit_ grava no diretório git todos os arquivos que estão aguardando no stage. Essa ação oficializa a alteração no projeto.
**Uso:** git commit -m "mensagem de alteração livre"

**OBSERVAÇÃO:** O commit pode ser usado sem a flag _-m_, mas é extremamente recomendado sempre usá-lo com uma mensagem.
