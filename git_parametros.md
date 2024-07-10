# Descrições dos parâmetros git

1. **`git ls-files`**: Este comando lista os arquivos que estão sob controle de versão no Git. Ele exibe os nomes dos arquivos que fazem parte do índice (staging area) e também os que estão no diretório de trabalho. É útil para verificar quais arquivos estão sendo rastreados pelo Git.

2. **`git remote remove <nome_do_repositório>`**: Onde `<nome_do_repositório>` é o nome do repositório remoto que você deseja remover.

3. **`git remote -v`**: Esse comando lista os repositórios remotos configurados para o seu projeto Git. Ele exibe os URLs dos repositórios remotos, permitindo que você veja de onde você está buscando e para onde está enviando alterações.

4. **`git branch -r`**: O comando `git branch -r` lista as referências remotas (branches) disponíveis no repositório remoto. Isso inclui as branches que você ainda não possui localmente, mas que estão no servidor remoto.

5. **`git status`**: O `git status` mostra o estado atual da sua árvore de trabalho. Ele informa se há arquivos modificados, novos arquivos ou arquivos excluídos. Também exibe informações sobre a branch atual e se há alterações pendentes para commit.

6. **`git log`**: O `git log` exibe o histórico de commits do repositório. Ele mostra informações sobre os commits, como autor, data, mensagem e hash do commit. É útil para entender o histórico de desenvolvimento do projeto.

7. **`git show`**: O `git show` exibe as mudanças feitas em um commit específico. Ele mostra as diferenças entre o commit atual e o commit anterior. Você pode especificar um hash de commit ou usar `HEAD` para o último commit.

8. **`git push`**: O comando `git push` é usado para transferir ou enviar o commit feito em um branch local no seu computador para um repositório remoto, como o GitHub. A sintaxe para fazer o push para o GitHub é a seguinte:
   
   ```
   git push <nome_do_repositório_remoto> <nome_do_branch_local>
   ```
   
   Por exemplo, para enviar as alterações do branch local "main" para o repositório remoto chamado "origin", você usaria:
   
   ```
   git push origin main
   ```

9. **`git pull`**: O comando `git pull` é usado para buscar as alterações do repositório remoto e mesclá-las com o seu branch local. Ele combina os passos de buscar (fetch) e mesclar (merge). A sintaxe é simples:
   
   ```
   git pull <nome_do_repositório_remoto> <nome_do_branch_local>
   ```
   
   Por exemplo, para trazer as alterações do branch remoto "main" para o seu branch local, você usaria:
   
   ```
   git pull origin main
   ```

Lembre-se de substituir `<nome_do_repositório_remoto>` e `<nome_do_branch_local>` pelos valores corretos do seu projeto!

# Descrição mais detalhada

1. **`git ls-files`**:
   
   - **Descrição**: Exibe informações sobre os arquivos no índice (staging area) e no diretório de trabalho. Ele lista os arquivos que estão sob controle de versão no Git.
   - **Exemplo**: `git ls-files -z` exibe os nomes dos arquivos com terminação nula (útil para scripts).

2. **`git remote remove <nome_do_repositório>`**:
   
   - **Descrição**: Remove um repositório remoto configurado no seu projeto Git.
   - **Exemplo**: `git remote remove origin` remove o repositório remoto chamado "origin".

3. **`git remote -v`**:
   
   - **Descrição**: Lista os repositórios remotos configurados para o seu projeto Git. Exibe os URLs dos repositórios remotos.
   - **Exemplo**: `git remote -v` mostra os nomes e URLs dos repositórios remotos.

4. **`git branch -r`**:
   
   - **Descrição**: Lista as referências remotas (branches) disponíveis no repositório remoto.
   - **Exemplo**: `git branch -r` exibe os branches remotos.

5. **`git status`**:
   
   - **Descrição**: Mostra o estado atual da sua árvore de trabalho. Exibe as diferenças entre o índice, o último commit e os arquivos não rastreados.
   - **Exemplo**: `git status` mostra as alterações pendentes.

6. **`git log`**:
   
   - **Descrição**: Exibe o histórico de commits do repositório. Mostra informações sobre os commits, como autor, data, mensagem e hash.
   - **Exemplo**: `git log` mostra os logs de commit.

7. **`git show`**:
   
   - **Descrição**: Mostra as mudanças feitas em um commit específico. Exibe as diferenças entre o commit atual e o anterior.
   - **Exemplo**: `git show HEAD` mostra as alterações desde o último commit.

8. **`git push`**:
   
   - **Descrição**: Envia commits para um repositório remoto.
   - **Exemplo**: `git push origin main` envia as alterações do branch local "main" para o repositório remoto "origin".

9. **`git pull`**:
   
   - **Descrição**: Busca e mescla alterações do repositório remoto no seu branch local.
   - **Exemplo**: `git pull origin main` traz as alterações do branch remoto "main".

10. **`git add`**:
    
    - **Descrição**: Adiciona as alterações no diretório de trabalho à área de staging.
    - **Exemplo**: `git add arquivo.txt` adiciona o arquivo "arquivo.txt" ao índice.

11. **`git commit`**:
    
    - **Descrição**: Cria um novo commit com as alterações da área de staging e uma mensagem de descrição.
    - **Exemplo**: `git commit -m "Corrige bug na função X"` cria um commit com a mensagem especificada.
