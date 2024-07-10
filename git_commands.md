# Comandos GIT úteis

## Uma lista de comandos git mais utilizados

___

Criar/Clonar o repositório

```bash
git clone ssh://aur@aur.archlinux.org/pacoteaur.git
```

Clonar o repositório

```bash
git clone https://aur.archlinux.org/pacoteaur.git
```

- Configuração global para seu usuário
1. Nome de usuário

```bash
git config --global user.name  "auruser"
```

2. Conta do usuário

```bash
git config --global user.email "auruser@aur.org"
```

___

Lista os arquivos sob controle de versão

```bash
git ls-files
```

Lista os repositórios remotos configurados

```bash
git remote -v
```

Lista as referências remotas (branches)

```bash
git branch -r
```

Mostra o estado da árvore de trabalho

```bash
git status
```

Exibe o histórico de commits

```bash
git log
```

Mostra as mudanças desde o último commit

```bash
git show
```

Envia commits para um repositório remot.

```bash
git push
```

Busca e mescla alterações do repositório remoto

```bash
git pull
```

Adiciona as alterações no diretório de trabalho à área de staging

```bash
git add
```

Cria um novo commit com as alterações da área de staging e uma mensagem de descrição

```bash
git commit -m "Mensagem de modificação"
```

___

Remove um repositório remoto

```bash
git remote remove <nome_do_repositório>
```

___

Armazenamento temporário em cache (5 minutos (padrão)) **{OPCIONAL}**

```bash
git config credential.helper cache
```

Armazenamento permanente **{OPCIONAL}**

```bas
git config credential.helper store
```

___

### Mais alguns detalhes que podem ser úteis:

1. **`git checkout`**: Este comando permite alternar entre branches (ramificações) existentes no repositório. Por exemplo:
   
   ```bash
   git checkout nome-da-branch
   ```
2. **`git stash`**: Se você estiver trabalhando em algo e precisar alternar para outra tarefa sem fazer commit das alterações, pode usar o `git stash` para armazenar temporariamente as mudanças em um local seguro. Depois, você pode recuperá-las quando voltar à tarefa original:
   
   ```bash
   git stash save "Descrição da mudança"
   git stash apply  # Para recuperar as mudanças
   ```
3. **`git diff`**: Exibe as diferenças entre o diretório de trabalho e a área de staging ou entre commits. Útil para verificar as alterações antes de fazer commit:
   
   ```bash
   git diff
   ```
4. **`git reset`**: Permite desfazer commits ou reverter alterações. Por exemplo, para desfazer o último commit:
   
   ```bash
   git reset HEAD~1
   ```
5. **`git cherry-pick`**: Selecione commits específicos de uma branch e aplique-os a outra. Útil para trazer alterações específicas de uma branch para outra:
   
   ```bash
   git cherry-pick <hash-do-commit>
   ```
