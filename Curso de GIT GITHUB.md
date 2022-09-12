# Curso de GIT/GITHUB → 12.09 -13.09

- Ver log de arquivos

```bash
git log 
```

- Ver log com nome e status

```bash
git log --name-status
```

- Logs personalizados

```bash
git log --pretty=format:"%h - %an, %ar : %s"

#H - commit hash
#h - abbreviated commit hash
#T - tree hash
#t - abbreviated treee hash
#P - parent hashes
#p - abbreviated parent hashes
#s - subject
#an - author name
#ae - autor email
#ad - author date
#ar - author date, relative
#cn - commiter name
#cd - commiter date
#cr - commiter date, relative
```

- Diff → mostra alterações que foram feitas

```bash
git diff 
```

- Diff → vai comparar com o que está em staged

```bash
git diff --staged 
```

- Diff → ver alterações somente em um arquivo específico

```bash
git diff <file>
```

- Diff → mostrar comparações entre commits

```bash
git diff <id_commit>
#ou
git diff <id_commit_1> <id_commit_2> 
#mostra o que foi alterado desde o commit 1 até o 2
```

- Remover arquivo da árvore de diretórios do git

```bash
git rm <file>
```

- Adicionar(trackear) arquivos deletados

```bash
git add -all #ou
git add -A
```

- Gitignore → um arquivo de configuração. Um dot file por começar com ponto, um arquivo oculto.

```bash
#para ver o que tem dentro do .gitignore
vim .gitignore

#para adicionar arquivos do .gitignore que estão no staged area
git rm <file> --cached #para não apagar o arquivo, só remover do staged area
```

- Arquivo de configuração do .gitignore → deixa as configurações padrões na máquina

```bash
git config --global core.excludesfile 
```

- Adicionar e commitar ao mesmo tempo

```bash
git commit -a -m "mensagem"
```

- Fazer um commit sem parâmetros irá abrir o editor de texto padrão definido no git config

```bash
git commit #abre o editor
```

- Fazer commit utilizando mesma mensagem anterior, o commit anterior é sobrescrito

```bash
git commit -m "mensagem" -amend #somente se não fez o push ainda
```

- Mais opções do git log

```bash
git log --pretty=oneline #traz em uma unica linha o log
git log --abbrev-commit #abrevia o commit
git log --stat #da algumas estatísticas do log
git log -p <numero> #mostra a alteração que foi feita, o numero é a qtd de linhas

```

- Branch

```bash
git branch
git branch <nome> #cria nova branch
git checkout <nome_branch> #muda para a branch alvo
git checkout -b <nome_branch> #cria e ja muda para branch
git branch -m <novo_nome> #altera o nome da branch
git branch -D <nome_branch> #remove a branch
git checkout --orphan <nome_branch> #cria branch vazia

```

- Merge

```bash
#muda pra branch que vc quer trazer a outra branch
git merge <branch_quer_juntar>
```

- Criar repositórios

```bash
#criar um repositorio na propria maquina
cd ../my-project.git
git init --bare #dentro do repositório criado
```

- Adicionar arquivos no repositorio

```bash
git remote add <nome_repositorio> <caminho_url> #por definição chamamos o repositorio de origin
```

- Sincronizando projetos local com repositório

```bash
git remote -v
git push <origin> <branch>
```

- Clonar repositório

```bash
git clone <repositorio> 
```

- Puxar dados do repositório

```bash
git pull origin <branch> 
```

- Automerge → conflitos… o head é a branch que vc está no momento

```bash
git diff #para ver o conflito com as diferenças

#primeira solução do conflito: abortar merge
git merge --abort
#segunda solução é resolver conflito manual, fazer commit e continuar com o merge
```

- Merge tool → meld

```bash
git config --global mergel.tool meld
```

- Ver alterações ignorando espaços

```bash
git diff -w
```

- Outros usos git checkout

```bash
git checkout <file> #para desfazer mudanças não commitadas
git checkout <id_commit> #volta no id do commit especificado
```

- Stash → salva o seu estado

```bash
git stash list #mostra a lista dos seus stashs
git stash apply #volta para o último stash
git stash drop <num_stash> #remove o stash
git stash pop #aplica o ultimo stash e já remove
git stash apply <num_stash> #vai para o stash especifico
```