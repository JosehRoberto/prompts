---
layout: default
title: Analisar e Corrigir Acentuação
---

# Prompt: Analisar e Corrigir Acentuação UTF-8 (com Backup)

Analise o arquivo `/caminho/do/arquivo.md` para detectar caracteres acentuados em português do Brasil corrompidos (ex: `፧` no lugar de `ç`, `íµ³`/`í` no lugar de `í`, `ó³³³`/`ó` no lugar de `ó`, `é` no lugar de `é`, `ã` no lugar de `ã`, `õ` no lugar de `õ`, `ê` no lugar de `ê`, `â` no lugar de `â`, `ô` no lugar de `ô`, `ú` no lugar de `ú`, `ü` no lugar de `ü`, `ñ` no lugar de `ñ`, ou sequências como `√†` → `à`, `√∫` → `ú`, `√≠` → `í`, `√≥` → `ó`, `√o` → `ã`, `√©` → `é`, `√™` → `ê`, `√µ` → `õ`, `√ß·o` → `ções`, etc.).

> "Arquivo já está em UTF-8 correto"

**Se HOUVER caracteres corrompidos:**
1. Faça backup de segurança: `cp /caminho/do/arquivo.md /caminho/do/arquivo.md.bak-$(date +%Y%m%d-%H%M%S)`
2. Reescreva o arquivo mantendo **exatamente o mesmo conteúdo lógico**, apenas com acentos corretos
3. Valide: `file /caminho/do/arquivo.md` (deve retornar "UTF-8 Unicode text") e `grep -E "análise|técnica|ação|seção|relatório|configuração|próximo|último|propósito" /caminho/do/arquivo.md`
4. Informe: "Correção aplicada. Informe o local e nome do Backup que foi salvo