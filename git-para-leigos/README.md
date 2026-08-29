# Git para Leigos

Um guia simples para pessoas que estão começando a usar Git no dia a dia do trabalho.

## Glossário de Comandos Simples

### 📥 Preparar-se para trabalhar
**Quando você quer começar o dia verificando se há atualizações dos colegas:**
> "Atualize minha cópia local com o que está no repositório"

Comando correspondente: `git pull`

### 💾 Salvar alterações
**Quando você terminou de fazer mudanças e quer registrar elas:**
> "Salve meu trabalho para compartilhar com a equipe"

Comando correspondente: 
```
git add .
git commit -m "Descreva o que você fez"
```

### 💾📤 Salvar e enviar tudo de uma vez (incluindo pastas novas)
**Quando você fez mudanças, criou pastas/arquivos novos e quer salvar e enviar tudo:**
> "Salve e envie todas as alterações locais, incluindo pastas novas"

Comando correspondente:
```
git add .
git commit -m "Descreva o que você fez"
git push
```

---

*Dica: `git add .` pega tudo — arquivos modificados, novos e pastas novas.*

### 📤 Compartilhar trabalho
**Quando você quer enviar suas mudanças registradas para o repositório:**
> "Envie meu trabalho salvo para que outros possam vê-lo"

Comando correspondente: `git push`

### 👀 Ver o que outros fizeram
**Quando você quer ver se alguém fez algo novo enquanto você trabalhava:**
> "Mostre o que aconteceu enquanto eu estava ausente"

Comando correspondente: `git pull`

### 🌱 Começar nova versão
**Quando você precisa fazer uma mudança que pode dar errado e não quer arriscar o trabalho principal:**
> "Crie uma cópia segura para experimentar"

Comando correspondente:
```
git branch nome-da-nova-versao
git checkout nome-da-nova-versao
```

### 🔗 Juntar versões
**Quando você terminou de experimentar na cópia segura e quer juntar com o trabalho principal:**
> "Junte minha experimentação com o trabalho principal"

Comando correspondente:
```
git checkout main
git merge nome-da-nova-versao
```

### 🏷️ Corrigir nome da versão principal
**Quando o nome da sua versão principal está errado (master em vez de main):**
> "Corrija o nome da sua versão principal"

Comando correspondente: `git branch -m master main`

### 📤 Enviar versão principal corrigida
**Depois de corrigir o nome da versão principal, envie para o repositório:**
> "Envie sua versão principal corrigida"

Comando correspondente: `git push -u origin main`

## 📝 Dicas Importantes

1. **Sempre verifique antes de enviar**: Antes de usar `git push`, use `git status` para ver o que será enviado.
2. **Mensagens claras**: No `git commit -m "mensagem"`, escreva o que você fez de forma simples e direta.
3. **Trabalhe em cópias**: Use branches (git branch) para experimentar coisas novas sem quebrar o trabalho principal.
4. **Atualize frequentemente**: Use `git pull` no início do seu trabalho para ter a versão mais recente.

## 🔗 Links Úteis

- [Documentação oficial do Git](https://git-scm.com/doc)
- [Tutorial interativo do Git](https://learngitbranching.js.org/)
- [Guia de comandos Git](https://education.github.com/git-cheat-sheet-education.pdf)

---

*Pronto para começar? Basta copiar e colar os comandos acima quando precisar!*