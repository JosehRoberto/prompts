# OpenCode — Retomada segura após truncamento de resposta

Guia de prompts para lidar com interrupções, respostas truncadas e fragmentos de chamadas de ferramenta no **OpenCode**, especialmente ao usar o **Free Models Router** via OpenRouter.

## Problema

Ao usar modelos gratuitos roteados pelo OpenRouter, é comum a execução ser interrompida no meio de uma chamada de ferramenta — por exemplo, durante a geração do conteúdo de um arquivo. Na tela podem aparecer fragmentos como:

```text
</parameter>
</invoke>
```

Isso normalmente indica que a resposta foi truncada antes de a ferramenta concluir a ação. Um simples `continue` pode fazer o modelo retomar a tarefa, mas sem garantir que o arquivo anterior foi gravado por completo ou que não há código duplicado, incompleto ou inconsistente.

## Objetivo

Transformar o comando `continue` em uma **retomada segura**:

1. Auditar o estado real dos arquivos.
2. Identificar a última ação interrompida.
3. Corrigir apenas o que for necessário, sem duplicar alterações.
4. Validar o resultado.
5. Só então continuar a tarefa original.

## Prompt permanente para `AGENTS.md`

Adicione este bloco ao arquivo `AGENTS.md` na raiz do projeto ou, para valer em todos os projetos, em `~/.config/opencode/AGENTS.md`.

```markdown
# Regras de execução segura para codificação

## Trabalho incremental

Ao executar tarefas de codificação, trabalhe em etapas pequenas e verificáveis. Antes de considerar qualquer alteração concluída, confirme o conteúdo real do arquivo no disco.

Nunca deixe código parcial, imports órfãos, funções vazias, classes incompletas, blocos não fechados, rotas quebradas ou configurações incompletas.

## Recuperação após interrupção ou truncamento

Se uma resposta for interrompida, truncada ou se restarem fragmentos de chamada de ferramenta na tela — por exemplo, `</parameter>`, `</invoke>` ou conteúdo de arquivo incompleto — não presuma que a última ação foi concluída.

Na próxima mensagem, execute uma **retomada segura**:

1. Identifique a última etapa lógica que estava sendo executada.
2. Inspecione o estado real dos arquivos afetados antes de escrever código novo.
3. Verifique se há arquivos parcialmente criados, conteúdo truncado, edições duplicadas, imports ausentes, funções incompletas ou configurações pendentes.
4. Corrija apenas o que for necessário, de forma idempotente, preservando o que já está correto.
5. Não repita cegamente a última ação nem duplique arquivos, funções, blocos ou alterações.
6. Valide o código com as ferramentas disponíveis no projeto — por exemplo, linter para detectar erros de sintaxe e más práticas, testes automatizados para confirmar o comportamento e build/compilação para confirmar que o projeto continua funcionando.
7. Se nenhuma ferramenta estiver configurada, pelo menos revise a sintaxe, os imports e a integridade dos arquivos alterados.
8. Somente depois de corrigir e validar o ponto de interrupção, continue a tarefa original a partir do próximo passo lógico.

## Validação obrigatória

Antes de declarar uma tarefa concluída:

- Confirme que os arquivos existem e possuem o conteúdo completo esperado.
- Verifique sintaxe, imports, referências e integração entre os arquivos alterados.
- Execute os comandos de verificação disponíveis no projeto.
- Informe quais arquivos foram criados ou alterados, o que foi corrigido e qual é o próximo passo.

## Preferência para tarefas grandes

Se uma tarefa exigir criar ou modificar vários arquivos, divida-a em etapas menores. Confirme cada arquivo após a escrita antes de avançar para a próxima etapa.
```

## Prompt curto para usar após interrupção

Use este texto quando aparecerem fragmentos como `</parameter>` ou `</invoke>`:

```text
continue — retomada segura conforme AGENTS.md: a resposta anterior pode ter sido truncada durante uma chamada de ferramenta. Antes de prosseguir, audite o estado real dos arquivos e do projeto; identifique a última ação; verifique se há código, arquivo, import, configuração ou refatoração incompleta; corrija apenas o que for necessário de forma idempotente, sem duplicar alterações; valide com lint/testes/build quando aplicável; depois continue a tarefa original do próximo passo lógico. Não presuma que a última escrita foi concluída.
```

## O que é lint

**Lint** é uma verificação automática do código-fonte, feita sem executar o programa, para identificar erros prováveis, trechos suspeitos e desvios de padrão. A ferramenta que realiza essa análise é chamada de **linter**.

Um linter pode detectar:

- Erros de sintaxe, como parêntese, chave ou aspas não fechados.
- Variáveis declaradas, mas nunca utilizadas.
- Uso de variável, função ou classe não definida.
- Imports duplicados, desnecessários ou inexistentes.
- Indentação, espaçamento e convenções de nomenclatura inconsistentes.
- Código duplicado, linhas muito longas ou funções excessivamente complexas.

### Exemplo

```python
def calcular_total(preco, quantidade):
    total = preco * quantidade
    return valor
```

Um linter pode indicar que `valor` não foi definido e que a função deveria retornar `total`.

### Diferença entre lint, testes e build

| Verificação | Finalidade |
|---|---|
| **Lint** | Analisa o código sem executá-lo e procura erros, más práticas e inconsistências. |
| **Testes** | Executa o código em cenários controlados para verificar se o comportamento está correto. |
| **Build** | Compila, empacota ou gera o artefato final, confirmando que o projeto pode ser construído. |

### Exemplos de comandos

Python:

```bash
ruff check .
```

```bash
flake8 .
```

JavaScript ou TypeScript:

```bash
npx eslint .
```

PHP:

```bash
vendor/bin/phpcs --standard=PSR12 .
```

## Boas práticas complementares

- Prefira tarefas menores: “crie apenas o módulo X”, depois “adicione os testes”.
- Para arquivos grandes, solicite escrita em partes ou use patches/diffs.
- Mantenha o projeto sob Git e verifique `git status` e `git diff` antes e depois das alterações.
- Ao usar o Free Models Router, lembre-se de que o modelo selecionado pode variar; instruções persistentes no `AGENTS.md` ajudam a padronizar o comportamento.
- Se o OpenCode permitir, aumente o limite de saída do modelo e reduza contexto desnecessário para diminuir truncamentos.

## Local recomendado no repositório

```text
prompts/
└── opencode/
    └── retomada-segura-apos-truncamento/
        └── README.md
```

## Referência rápida

| Situação | Prompt recomendado |
|---|---|
| Resposta truncada com fragmentos de tool call | Use o **Prompt curto para usar após interrupção** |
| Prevenir problemas em qualquer projeto de código | Adicione o **Prompt permanente** ao `AGENTS.md` |
| Evitar truncamento | Divida tarefas grandes e escreva arquivos em partes |
| Verificar código após retomada | Rode lint, testes e build disponíveis no projeto |
