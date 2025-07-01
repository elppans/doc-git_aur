# Git apenas no repositório local

Dá pra configurar o Git apenas no repositório local sem afetar o restante da máquina

📌 **Configuração local (por repositório):**
No terminal, dentro da pasta do seu projeto, você pode definir o nome e o e-mail apenas para aquele repositório com:

```bash
git config user.name "Seu Nome"
git config user.email "voce@empresa.com"
```

Essas configurações vão ficar salvas no `.git/config` do projeto, e não no sistema como um todo. Assim, você evita misturar credenciais com seu ambiente pessoal.

🔒 **Se for usar autenticação via token (ex: push/pull):**
Em vez de usar `git login` (que não existe), o GitHub usa personal access tokens. Pra não ficar fixo no cache, uma alternativa é:

- Usar o token via prompt, quando o Git pedir (não fica salvo).
- Ou configurar o cache de credenciais pra durar só uns minutos:

```bash
git config credential.helper 'cache --timeout=300'  # 5 minutos
```
___

# Montar um .gitconfig

Crie ou edite o arquivo `.git/config` dentro do repositório com algo assim:

```ini
[core]
	repositoryformatversion = 0
	filemode = true
	bare = false
	logallrefupdates = true
[remote "origin"]
	url = https://github.com/elppans/pdv-Elgini9E1x32.git
	fetch = +refs/heads/*:refs/remotes/origin/*
[branch "main"]
	remote = origin
	merge = refs/heads/main
[user]
	name = seuusuario
	mail = seuemail@mail.com
```

Com esse `.git/config`, está tudo certo pra trabalhar com seu repositório do GitHub usando suas credenciais de trabalho **sem afetar o restante da máquina**.  

---

### ✅ **Próximos Passos**

🔄 **1. Testar comunicação com o GitHub:**

```bash
git remote -v
```

Confirme se a URL de `origin` tá certa. Depois:

```bash
git fetch origin
```

Se funcionar sem erro, você tá conectado com o remoto. 🎯

---

### 📝 **2. Fazer commits com o usuário local:**

Com o `.git/config` local definido, quando você der um commit, o Git já vai usar as credenciais específicas do repositório. Basta seguir o fluxo normal:

```bash
git add .
git commit -m "Mensagem explicativa do que foi feito"
```

✅ O commit vai sair com o `user.name` e `user.email` definidos localmente — ou seja, seu e-mail corporativo (ou o que você colocou) será usado **somente nesse repositório**.

Você pode confirmar isso com:

```bash
git config user.name
git config user.email
```

Esses comandos vão exibir os valores usados **no repositório atual**.

---

Se quiser dar push pro GitHub, aí vale lembrar:

- Se estiver usando HTTPS, o Git vai pedir usuário/senha (ou token) — como você não quer salvar credenciais, o ideal é colar o token manualmente no prompt.
- Se quiser deixar temporariamente salvo (por uns minutos), pode configurar assim:

```bash
git config credential.helper 'cache --timeout=300'
```

Assim você digita o token uma vez e pode dar push/pull durante os próximos 5 minutos sem nova autenticação.

---

- Mais informações, acessar:  

[Clonando com as URLs de HTTPS](https://docs.github.com/get-started/getting-started-with-git/about-remote-repositories#cloning-with-https-urls)  
[Mantendo seus personal access token seguros](https://docs.github.com/pt/authentication/keeping-your-account-and-data-secure/managing-your-personal-access-tokens#keeping-your-personal-access-tokens-secure)  
