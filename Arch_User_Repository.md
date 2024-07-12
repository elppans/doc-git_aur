# AUR, Criação e configuração da conta e pacotes AUR

- Comandos GIT úteis  

> **`git ls-files`**: Lista os arquivos sob controle de versão, que estão no git.  
> **`git remote remove <nome_do_repositório>`**: Remove um repositório remoto (branch).  
> **`git remote -v`**: Lista os repositórios remotos configurados.  
> **`git branch -r`**: Lista as referências remotas (branches).  
> **`git status`**: Mostra o estado da árvore de trabalho.  
> **`git log`**: Exibe o histórico de commits.  
> **`git show`**: Mostra as mudanças desde o último commit.  
> **`git push`**: Envia commits para um repositório remoto.  
> **`git pull`**: Busca e mescla alterações do repositório remoto.  
> **`git add`**: Adiciona as alterações no diretório de trabalho à área de staging.  
> **`git commit`**: Cria um novo commit com as alterações da área de staging e uma mensagem de descrição.  

## AUR, Conta  

Será usado um nome de usuário, e-mail e nome de pacote ficticio, para poder enviar os exemplos.  
Basta mudar eles para o seu uso.  
Será indicado aqui apenas um resumo dos comandos que são utilizados para configurar a conta AUR e gerenciar os pacotes.  
Para mais informações, acesse os links do final da matéria.  

> Usuário = auruser  
> E-mail = auruser@aur.org  
> Pacote = pacoteaur  
> Diretório de configuração = $HOME/build/custombuild  

## Configurando conta AUR para receber pacotes  

1. Configurar autenticação e acesso de escrita para o AUR  

```bash
echo -e 'Host aur.archlinux.org
  IdentityFile ~/.ssh/aur
  User aur' | tee ~/.ssh/config
```

2. Criar um par de chaves para adicionar em sua conta  

```bash
ssh-keygen -f ~/.ssh/aur
```

3. Verifique o arquivo com a chave e copie e depois adicione em sua conta, no campo `Chave pública SSH`  

```bash
cat ~/.ssh/aur.pub
```
4. **(EM SISTEMA).** Faça configuração global para seu usuário  

```bash
git config --global user.name  "auruser"
git config --global user.email "auruser@aur.org"
```

5. **(EM SISTEMA, Opcional).**Configurando e armazenando a senha

Você pode evitar que o Git solicite sua senha configurando o armazenamento de credenciais em cache.  
Isso permite que o Git use automaticamente seu token de acesso pessoal armazenado em cache quando você efetua pull ou push de um repositório usando HTTPS.  
Opções:  

- **Armazenamento temporário em cache:**  
  
  - Use o comando a seguir para armazenar temporariamente suas credenciais em cache por 5 minutos (padrão):  
    
    ```bash
    git config credential.helper cache
    ```
  
  - Isso é útil se você não é o único a acessar o computador, pois suas credenciais não ficarão expostas a outros usuários após suas edições.  

- **Armazenamento permanente:**  
  
  - Para armazenar suas credenciais de forma definitiva, use o seguinte comando:  
    
    ```bash
    git config credential.helper store
    ```
  
  - Suas credenciais ficarão armazenadas permanentemente.  

Quando você fizer `git pull` ou `git push` pela primeira vez, o Git solicitará suas credenciais. Insira seu token de acesso pessoal (ou senha) quando solicitado.  
  Agora, o Git usará essas informações automaticamente para autenticação.  
___

# Criação e configuração do pacote AUR  

1. Criar diretório de trabalho  

```bash
mkdir -p $HOME/build/custombuild
cd $HOME/build/custombuild
```

2. Criar e acessar diretório do pacote AUR  

```bash
git clone ssh://aur@aur.archlinux.org/pacoteaur.git
cd pacoteaur
```

3. Crie e configure os arquivos .gitignore e PKGBUILD  

Sempre antes de upar a atualização, recrie um novo .SRCINFO com o comando makepkg  
Então adicione, faça um commit e depois faça o upload das modificações  

```bash
makepkg --printsrcinfo > .SRCINFO
git add PKGBUILD .SRCINFO .gitignore
git commit -m "Create Package pacoteaur"
git push
```
___

## Atualização do pacote AUR  

1. Clonar o repositório e entrar no diretório:  
>Se não tem mais o repositório local e/ou precisa baixar do repositório novamente  

```
git clone ssh://aur@aur.archlinux.org/pacoteaur.git && cd pacoteaur
```

2. Adicionar um remoto com opções específicas:

>-f: Faz com que o Git execute um fetch imediatamente após adicionar o remoto.
>-t master: Indica que apenas a branch master deve ser rastreada do remoto.
>-m master: Define a branch master como a branch padrão para o remoto adicionado.

```
git remote add -f -t master -m master pacoteaur ssh://aur@aur.archlinux.org/pacoteaur.git
```

3. Criar e mudar para um novo branch:

```bas
git switch -c pacoteaur pacoteaur/master
```

4. Edite o necessário

Sempre que atualizar o pacote AUR, não pode esquecer de editar o parâmetro `pkgver` e o `pkgrel`  

5. Author identity unknown  

Se receber a seguinte mensagem ao fazer `git commit -m ...`:  

> Author identity unknown  
>   
> *** Please tell me who you are.  
>   
> ....  
>   
> fatal: unable to auto-detect email address (got 'auruser@aur.(none)')  

Logar na sua conta AUR e depois continue fazendo commit novamente e finalmente, o pull.  

## RESUMO E EXEMPLOS  

### Criando/Configurando um pacote AUR:  

Se eu já tenho um diretório com projeto feito, primeiro crio o repositório e depois mando os arquivos pro mesmo:  

```bash
cd ~/build
mv pacoteaur pacoteaur.teste
git clone ssh://aur@aur.archlinux.org/pacoteaur.git
cd pacoteaur
git remote add -f -t master -m master kde-service-menu-reimage-mod ssh://aur@aur.archlinux.org/pacoteaur.git
git switch -c pacoteaur pacoteaur/master
cp -av ../pacoteaur.teste/* .
cp -av ../pacoteaur.teste/.gitignore .
makepkg --printsrcinfo > .SRCINFO
git add PKGBUILD .SRCINFO .gitignore pacoteaur_files etc
git commit -m "Create Package pacoteaur"
git push
```

### Atualizando o pacote AUR:  

Se eu já tenho o projeto no AUR e quero apenas atalizar, basta fazer estes comandos após as modificações feitas. Tenha certeza que está tudo certo antes de enviar pro AUR.  

```bash
makepkg --printsrcinfo > .SRCINFO
git add .
git commit -m "Update ARQUIVO"
PWD: {Senha AUR SSH}
git status
```

* Links e Fontes, Matérias:  

[Arch_User_Repository_(Português)](https://wiki.archlinux.org/title/Arch_User_Repository_(Portugu%C3%AAs))  
[AUR_submission_guidelines_(Português)](https://wiki.archlinux.org/title/AUR_submission_guidelines_(Portugu%C3%AAs))  
[AUR_submission_guidelines_(Português)#Regras_de_envio](https://wiki.archlinux.org/title/AUR_submission_guidelines_(Portugu%C3%AAs)#Regras_de_envio)  
[Creating_packages_(Português)](https://wiki.archlinux.org/title/Creating_packages_(Portugu%C3%AAs))  
[SSH_keys](https://wiki.archlinux.org/title/SSH_keys)  
[Git#Configuration](https://wiki.archlinux.org/title/Git#Configuration)  
[Arch_package_guidelines_(Português)](https://wiki.archlinux.org/title/Arch_package_guidelines_(Portugu%C3%AAs))  
[git-remote](https://git-scm.com/docs/git-remote)  
[[solved]Problem with ssh authentication on AUR#258198](https://bbs.archlinux.org/viewtopic.php?id=258198)  
[The PGP key fingerprint is invalid.#257585](https://bbs.archlinux.org/viewtopic.php?id=257585)  

