# Git Push Seguro: Evitando o Problema do Branch Errado

## Contexto do Problema

**Prompt original:** "Salve e envie todas alterações locais, incluindo pastas novas, para o repositório"

**O que aconteceu:** O comando `git push` sem destino explícito enviou para `master` (branch local), mas o GitHub usa `main` como branch padrão. Resultado: alterações não apareciam no site.

---

## Causa Raiz

| Comportamento padrão do Git | Problema |
|----------------------------|----------|
| `git push` → envia branch com **mesmo nome** no remote | Se branch local ≠ branch padrão GitHub, falha silenciosamente |

No caso: local=`master`, GitHub padrão=`main` → push foi para `origin/master`, mas site mostra `origin/main`.

---

## Solução Imediata (Comando Único)

```bash
git add . && git commit -m "mensagem" && git push origin HEAD
```

**Por que funciona:** `origin/HEAD` **sempre** aponta para o branch padrão do remote (seja `main`, `master`, `trunk`, etc.).

---

## Solução Definitiva (Configure Uma Vez)

```bash
# Renomeia branch local para main (padrão moderno)
git branch -m master main

# Envia e cria tracking (-u) para o branch principal do remote
git push -u origin main
```

Depois disso: `git push` sozinho **sempre funciona**.

---

## Prompts em Linguagem Natural

### ❌ Prompts que **falham** (geram `git push` simples)

| Prompt | Por que falha |
|--------|---------------|
| "Salva tudo e publica no GitHub" | Não especifica destino |
| "Manda todas mudanças pro GitHub" | Não especifica destino |
| "Commit e push pro branch principal" | Ambíguo: qual branch principal? |
| "Atualiza o GitHub com o que tem aqui" | Não especifica destino |
| "Sobe tudo pro GitHub" | Não especifica destino |

### ✅ Prompt que **funciona** (explícito no destino)

```bash
Commit tudo e execute: git push origin HEAD
```

### ✅ Prompt robusto

```bash
Commit todas as alterações locais (incluindo arquivos e pastas novas) e faça push para o branch padrão do remote (origin/HEAD). Se o branch local não estiver sincronizado com o remote, sincronize antes de enviar.
```

### ✅ Ou Prompt mais curto

```bash
Commit e push para o branch padrão do GitHub (origin/HEAD), criando/atualizando o tracking se necessário.
```

Isso força o uso de origin/HEAD (que aponta para main no GitHub) em vez de assumir o nome do branch local.

---

## Resumo para Leigos

| Conceito | Explicação simples |
|----------|-------------------|
| **Branch** | Uma "linha do tempo" do código |
| **main/master** | Nomes diferentes para "linha principal" |
| **origin** | Apelido para o GitHub (o remote) |
| **HEAD** | "Onde estou agora" (seu commit atual) |
| **origin/HEAD** | "A linha principal do GitHub" (sempre certo) |

**Regra de ouro:** Se não quer surpresa, diga **para onde** enviar: `git push origin HEAD`.

---

## Checklist para Não Repetir

- [ ] Branch local se chama `main`? (`git branch -m master main`)
- [ ] Tracking configurado? (`git push -u origin main`)
- [ ] Prompt futuro inclui destino explícito? (`git push origin HEAD`)

---

## Referência Rápida de Comandos

```bash
# Ver branches locais e remotos
git branch -vv

# Ver para onde origin/HEAD aponta
git remote show origin

# Push seguro (sempre funciona)
git push origin HEAD

# Push com tracking (após configurar main)
git push
```