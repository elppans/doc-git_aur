# Configurar chave SSH (Sem senha) para o seu computador

Para evitar que o Git peça a senha toda vez que você clona ou faz push para um repositório usando SSH, você pode configurar uma chave SSH e usar um agente SSH para gerenciar a autenticação. Aqui estão os passos:

>Observação: Se não é só você que usa o computador, recomendável criar a **chave COM SENHA**
### 1. Gerar uma chave SSH
Se você ainda não tem uma chave SSH, pode gerar uma com o seguinte comando:

```bash
ssh-keygen -t rsa -b 4096 -C "seu-email@example.com"
```

Siga as instruções e salve a chave no local padrão (`~/.ssh/id_rsa`).

### 2. Adicionar a chave SSH ao agente SSH
Depois de gerar a chave, adicione-a ao agente SSH:

```bash
eval "$(ssh-agent -s)"
ssh-add ~/.ssh/id_rsa
```

### 3. Adicionar a chave SSH ao AUR
Copie o conteúdo da sua chave pública (`~/.ssh/id_rsa.pub`) e adicione-a ao seu perfil no AUR. Você pode fazer isso acessando as configurações da sua conta no AUR e colando a chave pública na seção de chaves SSH.

### 4. Testar a configuração
Para verificar se tudo está configurado corretamente, você pode usar o seguinte comando:

```bash
ssh -T aur@aur.archlinux.org
```

Se tudo estiver configurado corretamente, você verá uma mensagem de boas-vindas.

### 5. Clonar o repositório sem pedir senha
Agora você deve ser capaz de clonar o repositório sem que seja solicitada a senha:

```bash
git clone ssh://aur@aur.archlinux.org/kde-service-menu-reimage-mod.git
```

### Dicas adicionais
- **Armazenar a senha no keychain**: Em sistemas operacionais modernos, você pode armazenar a senha no keychain para não precisar digitá-la novamente.
- **Verificar permissões**: Certifique-se de que as permissões dos arquivos de chave SSH estão corretas (`chmod 600 ~/.ssh/id_rsa`).

Seguindo esses passos, você deve conseguir evitar a solicitação de senha ao usar SSH com Git.  
