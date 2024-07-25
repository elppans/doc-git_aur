Para desfazer as alterações não rastreadas no Git e evitar que sejam adicionadas ao commit, você pode usar o comando `git clean`. Existem algumas opções para isso:

1. **Desfazer alterações mantendo os arquivos não rastreados no diretório de trabalho (não adicionados ao commit):**
   ```bash
   git clean -n
   ```

2. **Remover completamente os arquivos não rastreados (incluindo os arquivos modificados) e retornar ao estado anterior:**
   ```bash
   git clean -f
   ```

Se você deseja apenas remover os arquivos não rastreados no diretório, exemplo `teste`, você pode especificar o caminho:
```bash
git clean -f teste/
```

O primeiro comando mostrará quais arquivos seriam excluídos (modo de teste).  
O segundo efetivamente os removerá.  

