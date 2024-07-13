> `git init`

```
hint: Using 'master' as the name for the initial branch. This default branch name
hint: is subject to change. To configure the initial branch name to use in all
hint: of your new repositories, which will suppress this warning, call:
hint:
hint:   git config --global init.defaultBranch <name>
hint:
hint: Names commonly chosen instead of 'master' are 'main', 'trunk' and
hint: 'development'. The just-created branch can be renamed via this command:
hint:
hint:   git branch -m <name>
Initialized empty Git repository in /home/suporte4/Público/git/teste/.git/
```
```
 dica: usando 'master' como nome do branch inicial.  Este nome de branch padrão
 dica: está sujeito a alterações.  Para configurar o nome inicial da filial a ser usada em todos
 dica: dos seus novos repositórios, que suprimirão este aviso, chame:
 dica:
 dica: git config --global init.defaultBranch <nome>
 dica:
 dica: Os nomes comumente escolhidos em vez de 'master' são 'main', 'trunk' e
 dica: 'development'.  O branch recém-criado pode ser renomeado através deste comando:
 dica:
 dica: git branch -m <nome>
 Repositório Git vazio inicializado em /home/suporte4/Público/git/teste/.git/

```
___

> `git pull --tags origin main`
```
From https://github.com/user/repo
 \* branch            main       -> FETCH_HEAD
hint: You have divergent branches and need to specify how to reconcile them.
hint: You can do so by running one of the following commands sometime before
hint: your next pull:
hint:
hint:   git config pull.rebase false  # merge
hint:   git config pull.rebase true   # rebase
hint:   git config pull.ff only       # fast-forward only
hint:
hint: You can replace "git config" with "git config --global" to set a default
hint: preference for all repositories. You can also pass --rebase, --no-rebase,
hint: or --ff-only on the command line to override the configured default per
hint: invocation.
fatal: Need to specify how to reconcile divergent branches.
```
```
 \* branch            main       -> FETCH_HEAD
dica: Você tem ramificações divergentes e precisa especificar como reconciliá-las.
dica: Você pode fazer isso executando um dos seguintes comandos algum tempo antes
dica: seu próximo pull:
dica:
dica: git config pull.rebase false # merge
dica: git config pull.rebase true # rebase
dica: git config pull.ff only # fast-forward only
dica:
dica: Você pode substituir "git config" por "git config --global" para definir uma
dica: preferência padrão para todos os repositórios. Você também pode passar --rebase, --no-rebase,
dica: ou --ff-only na linha de comando para substituir o padrão configurado por
dica: invocação.
fatal: Precisa especificar como reconciliar ramificações divergentes.
```
___
> `git pull --tags origin main`
```
From https://github.com/user/repo
 \* branch            main       -> FETCH_HEAD
hint: Diverging branches can't be fast-forwarded, you need to either:
hint:
hint: 	git merge --no-ff
hint:
hint: or:
hint:
hint: 	git rebase
hint:
hint: Disable this message with "git config advice.diverging false"
fatal: Not possible to fast-forward, aborting.
```
```
 \* branch            main       -> FETCH_HEAD
dica: Ramos divergentes não podem ser acelerados, você precisa:
dica:
dica: git merge --no-ff
dica:
dica: ou:
dica:
dica: git rebase
dica:
dica: Desabilite esta mensagem com "git config advice.diverging false"
fatal: Não é possível avançar rapidamente, abortando.
```
