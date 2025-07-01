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
