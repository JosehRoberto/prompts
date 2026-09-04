---
layout: default
title: Reversa – Estado corrompido
---

# Reversa – Estado corrompido

## Problema
> "Reversa: Update Reversa not installed in this directory"
 aparece mesmo após `npx reversa install`. O motivo costuma ser `state.json` invalido (vírgulas/ chaves ausentes) devido a interrupção ou bug ao salvar.

## Verificação
```bash
jq . .reversa/state.json
```
Se falhar, o JSON está corrompido.

## Correção
```bash
# backup opcional
cp .reversa/state.json .reversa/state.json.bak
# remover arquivo corrompido
rm .reversa/state.json
# reinstalar Reversa (recria state.json válido)
npx reversa install
```

## Pós‑correção
Execute novamente `npx reversa update` para confirmar que o Reversa está reconhecido.

## Como usar no projeto
1. Copiar este README para a pasta do projeto que usa Reversa.
2. Seguir os passos acima quando o erro surgir.
