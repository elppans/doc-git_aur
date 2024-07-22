# Comandos GIT úteis
___

Criar/Clonar o repositório (SSH)
>Para clonar um repositório **privado**, os arquivos de chave (`id_rsa` e `id_rsa.pub`) devem ser copiados para o diretório `~/.ssh` do sistema alvo.
>O mesmo só funciona com a clonagem via `ssh`, não `https`.  
```bash
git clone ssh://aur@aur.archlinux.org/pacoteaur.git
```

Clonar o repositório

```bash
git clone https://aur.archlinux.org/pacoteaur.git
```

- **Configuração global para seu usuário**
1. Nome de usuário

```bash
git config --global user.name  "auruser"
```

2. Conta do usuário

```bash
git config --global user.email "auruser@aur.org"
```
- **Credenciais do usuário**
1. Armazenamento temporário em cache (5 minutos (padrão)) **{OPCIONAL}**

```bash
git config credential.helper cache
```

2. Armazenamento permanente **{OPCIONAL}**

```bas
git config credential.helper store
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

Envia commits para um repositório remoto

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

Remove um repositório remoto (**Branch**)

```bash
git remote remove <nome_do_repositório>
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
   ```
   ```bash
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
___

## git fetch

- Buscar alterações de outros repositórios
```
git fetch
```

O comando `git fetch` é usado para buscar alterações de um repositório remoto e atualizá-las no repositório local, sem modificar o diretório de trabalho atual. 
Uma explicação resumida com exemplos:

1. **Buscando Alterações**:
   - O `git fetch` recupera commits, arquivos, branches e tags de um repositório remoto.
   - Ele atualiza as referências locais para refletir as mudanças no remoto, mas não afeta o diretório de trabalho nem a área de staging.

2. **Exemplo**:
   - Suponha que você esteja trabalhando em um projeto com uma equipe e um colega faça um novo commit no repositório remoto.
   - Você pode usar `git fetch` para atualizar seu repositório local com esse commit.
   - Em seguida, inspecione as alterações antes de decidir se deseja mesclá-las em seu branch atual.

- Alguns exemplos de uso do comando `git fetch`:

1. **Buscar as últimas alterações do repositório remoto padrão ("upstream")** (se configurado):
   ```
   git fetch
   ```

2. **Buscar novos branches de um repositório remoto específico ("upstream")**:
   ```
   git fetch nome_do_repositorio_remoto
   ```

3. **Buscar as últimas alterações de todos os repositórios remotos ("upstream")**:
   ```
   git fetch --all
   ```

4. **Buscar também as tags do repositório remoto ("upstream")**:
   ```
   git fetch --tags
   ```

5. **Excluir referências locais a branches remotos que foram excluídos no repositório remoto**:
   ```
   git fetch --prune
   ```

