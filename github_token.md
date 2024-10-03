Para gerar um token de acesso pessoal no GitHub usando Linux, siga os passos abaixo:

1. **Acesse as configurações do GitHub**:
   - Vá para [GitHub](https://github.com) e faça login na sua conta.
   - Clique na sua foto de perfil no canto superior direito e selecione "Configurações".

2. **Configurações do desenvolvedor**:
   - No menu à esquerda, clique em "Configurações do desenvolvedor".
   - Em seguida, clique em "Tokens de acesso pessoal".

3. **Gerar novo token**:
   - Clique em "Generate new token" (Gerar novo token).
   - Dê um nome ao token para identificar seu uso.
   - Selecione as permissões necessárias para o token. Por exemplo, se você precisar de acesso para clonar repositórios, selecione "repo".
   - Defina uma data de expiração para o token, se necessário.

4. **Copiar e armazenar o token**:
   - Clique em "Generate token" (Gerar token).
   - Copie o token gerado e armazene-o em um local seguro, pois você não poderá vê-lo novamente.

5. **Usar o token no Git**:
   - Quando for necessário autenticar no GitHub via linha de comando, use o token no lugar da senha. Por exemplo:
     ```bash
     git clone https://<seu_token>@github.com/usuario/repositorio.git
     ```
___
[documentação oficial do GitHub](https://docs.github.com/pt/authentication/keeping-your-account-and-data-secure/managing-your-personal-access-tokens)⁴.
___


- Fonte:  
[(1) Gerenciar seus tokens de acesso pessoal - GitHub Docs.](https://docs.github.com/pt/authentication/keeping-your-account-and-data-secure/managing-your-personal-access-tokens)   
[(2) GitHub Access Tokens: How To Use Them Properly.](https://www.youtube.com/watch?v=IuiH6cBtc58)   
[(3) [2023] How to generate Personal Access Token on Github | How to generate Github token.](https://www.youtube.com/watch?v=9lGcbQR4k4Y)   
[(4) How To Generate A Personal Access Token In GitHub And Use It To Push Using Git.](https://www.youtube.com/watch?v=iLrywUfs7yU)   
[(5) Autenticação por Token no GitHub | HandsOn | Onebitcode.](https://www.youtube.com/watch?v=pOP2S2PPkHE)   
[(6) Como configurar tokens de acesso pessoal HTTPS para autenticação do Github.](https://pt.linux-console.net/?p=7796)   
[(7) [pt-BR] Como configurar o SSH no Github? - DEV Community.](https://dev.to/dxwebster/como-conectar-ao-github-com-chaves-ssh-1i41)   
[(8) linux - Como atualizar o "personal access token" do github nos projetos ....](https://pt.stackoverflow.com/questions/535995/como-atualizar-o-personal-access-token-do-github-nos-projetos-antigos)   
