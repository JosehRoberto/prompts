# Conteúdo detalhado por bloco

**Fonte primária de conteúdo para o Mira-Animator (deck da oficina)**

Este documento expande o `03-oficina/conteudo-programatico-oficina.md` no nível necessário para o pipeline do Mira (`/mira-extract` → `/mira-planner` → `/mira-copywriter` → `/mira-builder` + `/mira-animator` → `/mira-validator`). Aqui cada bloco traz conceitos com definição, metáforas animadas candidatas, exemplo concreto no projeto-base e sugestão de slides com template.

**Papel das fontes em `07-apresentacao/`:**

- `conteudo-detalhado-por-bloco.md` (este arquivo): **fonte primária**. Define tópicos, metáforas e a sequência de slides. É o que determina o que aparece na tela.
- `conteudo-tecnico-aprofundado.md`: **fonte secundária de precisão**. Alimenta o `/mira-copywriter` e o `/mira-animator` para enriquecer as metáforas e garantir exatidão técnica. **A profundidade dele não vai para a tela.**

> **Regra desta pasta:** `07-apresentacao/` é material reservado do ministrante. Não entra no `liberar.sh` nem no repositório público dos alunos.

## Como usar este arquivo

1. O `/mira-extract` lê este arquivo (e, depois, os demais de `07-apresentacao/`) e gera o `briefing.md` do deck.
2. A ordem dos blocos aqui **é** a ordem de exibição na sala. Não reordenar sem atualizar a tabela de amarração.
3. As metáforas foram escritas para virar animação (regra zero do Mira: entrar com coreografia e depois manter loop). O animador pode substituir por metáfora melhor, mantendo a ideia.
4. Os prompts vêm do `03-oficina/roteiro-prompts-oficina.md` e são liberados **um a um** durante a oficina. O deck não deve revelar todos de uma vez.
5. A precisão técnica de cada tópico está em `conteudo-tecnico-aprofundado.md`, que é seu material de estudo e sua fonte de apoio para explicar em voz alta.

## Amarração geral

Esta é a **timeline canônica** da oficina. Ela é a referência única para os horários e alinha `cronograma-oficina.md`, `roteiro-liberacao-conteudos.md` e este arquivo.

| Momento | Bloco | Janela (cronograma) | Prompts liberados | Fase de liberação | Slides sugeridos |
|---|---|---|---|---|---|
| Abertura | Acolhimento + Bloco 1 (Contextualização) | 08h30–08h45 | nenhum | `fase-01` | 1–8 |
| Configuração | Suporte aos notebooks | 08h45–09h20 | nenhum | guia já liberado | apoio (à parte) |
| Bloco 2 | Preparação do projeto | 09h20–09h35 | nenhum | `fase-02` | 9–12 |
| Bloco 3 | Construção guiada | 09h35–10h05 e 10h15–10h35 (pausa às 10h05) | Prompts 1, 2, 3, 5, 6 | `fase-02` | 13–18 |
| Blocos 4 e 5 | Refinamento e recursos interativos | 10h35–10h55 | Prompts 4, 7, 8 | `fase-02` | 19–26 |
| Bloco 6 | Personalização | 10h55–11h15 | Prompts 9, 10 | `fase-02` | 27–30 |
| Bloco 7 | Publicação | 11h15–11h55 | — | `fase-03` | 31–36 |
| Encerramento | Revisão e próximos passos | 11h55–12h00 | nenhum | `pos-oficina` | 37–39 |

**Total previsto:** cerca de 39 slides, ritmo de aula densa (template `aula-capitulo`, tema `mira-dark`).

## Resoluções de horário aplicadas

As divergências entre os documentos de origem foram resolvidas e alinhadas em todos os arquivos:

1. **Prompt 5 x pausa:** o Prompt 5 passa de 10h05 para **10h15** (retorno da pausa). Atualizado no `roteiro-liberacao-conteudos.md`.
2. **Prompt 1 x janela do cronograma:** o Prompt 1 passa de 09h30 para **09h35**, dentro da janela "OpenCode: primeiros prompts". O arquivo do roteiro continua sendo liberado às 09h30.
3. **Bloco 5 sem janela:** o Bloco 5 ganhou a janela **10h35–10h55**, criada ao fundir "Ajustes visuais e responsividade" com os recursos interativos no `cronograma-oficina.md`.
4. **Blocos 4 e 5 compartilhados:** ocupam a mesma janela (10h35–10h55), encadeados, sem separação rígida e sem sobreposição de horários.
5. **Prompt 8:** passa de 10h55 para **10h50**, para caber na janela 10h35–10h55.

Horários finais dos prompts: 1 (09h35), 2 (09h40), 3 (09h45), 4 (09h55), 5 (10h15), 6 (10h25), 7 (10h40), 8 (10h50), 9 (11h05), 10 (11h10).

As janelas da amarração são contíguas e **sem sobreposição**, iguais às do `01-planejamento/cronograma-oficina.md`. O Bloco 3 é interrompido pela pausa (10h05–10h15), e o Bloco 7 cobre 11h15–11h55 (GitHub e GitHub Pages).

---

## Abertura: Acolhimento e alinhamento (08h30–08h45)

**Objetivo:** alinhar expectativa, apresentar o escopo real e fixar a regra de acompanhamento sincronizado.

### Conceitos-chave

| Termo | Definição curta | Por que importa no slide |
|---|---|---|
| Oficina prática | Aula introdutória e mão na massa, não um curso completo | Diz ao aluno o que esperar |
| Projeto único | Um só site-modelo para toda a turma | Evita dispersão e nivelamento |
| Escopo | Site estático, sem banco de dados nem login | Limita promessas |
| Acompanhamento sincronizado | Todos no mesmo passo, no mesmo prompt | Mantém a turma junta |

### Metáforas animadas sugeridas

- **Trilha única:** várias pegadas convergindo para o mesmo caminho. Entra desenhando e depois pulsa.
- **Kit de montagem:** uma caixa que se abre e mostra as peças do dia (planejar, construir, refinar, publicar).

### Exemplo no projeto-base

O projeto-base "Portal de Trilhas de Aprendizagem" é o mesmo para todos: cada aluno personaliza no fim, não no começo.

### Slides sugeridos

| # | Título | Template | Conteúdo | Elemento animado |
|---|---|---|---|---|
| 1 | Desenvolvimento de Sites com Inteligência Artificial | `card_capa` | Título, ministrante, PPGCIMES/NITAE/UFPA, 22/10/2026 | Portal que se desenha |
| 2 | O que vamos construir hoje | `card_grid` | Os 7 blocos em pílulas + tempo total (3h30) | 7 nós que acendem em sequência |
| 3 | Um projeto, todos juntos | `card_destaques` | Escopo do dia x expansões futuras | Duas trilhas paralelas |

### Frase-âncora

"Hoje não vamos virar programadores. Vamos aprender a dinâmica de construir um site conversando com a IA."

### Assets

- Logos institucionais (UFPA, PPGCIMES, NITAE).

---

## Bloco 1: Contextualização (08h30–08h45)

**Objetivo:** entender o papel da IA no desenvolvimento inicial de sites, a diferença entre gerar conteúdo e estruturar um projeto, e os limites pedagógicos.

### Conceitos-chave

| Termo | Definição curta | Por que importa no slide |
|---|---|---|
| IA generativa (LLM) | Programa que gera texto e código a partir de um pedido em linguagem natural | Base de tudo o que vem depois |
| Vibe coding | Programar descrevendo em português e deixar um agente escrever o código | Explica a virada de método |
| Prompt | Instrução em linguagem natural dada ao agente | Unidade de trabalho da oficina |
| Gerar conteúdo x estruturar projeto | Pedaços soltos x sistema com arquivos e responsabilidades | Evita a ilusão de "site pronto" |
| Site estático x aplicação | Arquivos que rodam no navegador x sistema com servidor e banco | Delimita o escopo real |
| Limites e cuidados | IA acelera o começo, não garante o fim; responsabilidade é humana | Uso ético e pedagógico |

### Metáforas animadas sugeridas

- **Tijolos x planta:** uma pilha de tijolos de um lado, uma planta de casa do outro. A IA entrega tijolos rápido; a estrutura é decisão sua.
- **Rabisco que vira código:** um desenho à mão se organiza em linhas de código alinhadas. Fala de velocidade no começo, não de garantia no fim.
- **Estagiário velocista:** um assistente que escreve muito rápido, mas para e espera a sua revisão.

### Exemplo no projeto-base

Um site é `index.html` + `style.css` + `script.js` organizados; jogar tudo em um arquivo só é "tijolo empilhado", não projeto.

### Slides sugeridos

| # | Título | Template | Conteúdo | Elemento animado |
|---|---|---|---|---|
| 4 | A IA acelera o começo. A engenharia sustenta o resto. | `card_citacao` | Frase de impacto que abre o tema | Texto que se monta letra a letra |
| 5 | Gerar conteúdo x estruturar um projeto | `card_destaques` | Comparativo (tijolos x planta) | Tijolos empilhando de um lado, planta surgindo do outro |
| 6 | O que a IA faz e o que ela não faz | `card_grid` | Capacidades x limites | Ícones que acendem por categoria |
| 7 | Da ideia ao código | `card_d3` | Fluxo: ideia → prompt → código → revisão | Fluxo que percorre as etapas |
| 8 | Site estático x aplicação com back-end | `card_destaques` | Duas colunas comparativas | Balança que se equilibra |

### Frase-âncora

"A IA não substitui a decisão. Ela tira do caminho a parte chata e devolve tempo para o que importa."

### Erros comuns / cuidados

- Prometer "site profissional" em 3 horas.
- Confundir protótipo com produto final.
- Deixar subentendido que a IA decide sozinha.

### Assets

- Ícone/ilustração de "tijolos x planta".

---

## Bloco 2: Preparação do projeto (09h20–09h35)

**Objetivo:** entender a pasta do projeto, o OpenCode como interface de trabalho e a definição do projeto-base.

### Conceitos-chave

| Termo | Definição curta | Por que importa no slide |
|---|---|---|
| Estrutura de pasta | Onde ficam HTML, CSS e JS do projeto | Organização básica |
| OpenCode | Interface onde o agente escreve e edita os arquivos do projeto | É a bancada de trabalho |
| `/connect` | Comando que liga o OpenCode a um provedor de IA | Desbloqueia o uso |
| Provedores | NVIDIA, Gemini, Groq, OpenRouter (ao menos um) | Infra do dia |
| Projeto-base | O "Portal de Trilhas de Aprendizagem" | Ponto de partida comum |
| Não inserir chaves no projeto | Chave de API fica na configuração, nunca no site | Segurança desde o início |

### Metáforas animadas sugeridas

- **Oficina com gavetas:** uma pasta-mãe que se abre mostrando gavetas rotuladas (html, css, js).
- **Molde único:** uma forma de bolo que todos usam; depois cada um confeita por cima.
- **Copiloto:** o agente no assento ao lado, que escreve enquanto você aponta o destino.

### Exemplo no projeto-base

```
portal-trilhas/
├── index.html
├── style.css
└── script.js
```

### Slides sugeridos

| # | Título | Template | Conteúdo | Elemento animado |
|---|---|---|---|---|
| 9 | Antes de gerar: planejar | `card_timeline` | Prompt 1 pede um plano, não arquivos | Etapas que acendem |
| 10 | A pasta do projeto | `card_d3` | Árvore de arquivos que se monta | Pastas/arquivos surgindo |
| 11 | Prompt 1: planejamento | `card_code` | O prompt 1 na íntegra | Cursor digitando |
| 12 | OpenCode e provedores | `card_grid` | OpenCode + `/connect` + provedores | Nós que se conectam |

### Frase-âncora

"O arquivo certo, na pasta certa, é a diferença entre um experimento e um projeto."

### Erros comuns / cuidados

- Chave de API colada dentro do HTML.
- Provedor sem crédito ou sem acesso gratuito.
- Pedir "crie o site todo" de uma vez.

### Assets

- Captura do OpenCode aberto na pasta do projeto.
- Captura do `/connect`.

---

## Bloco 3: Construção guiada (09h35–10h05 e 10h15–10h35, pausa às 10h05)

**Objetivo:** construir a estrutura inicial do site com prompts, criar seções e menu, inserir trilhas, recursos, portfólio, contato e rodapé.

### Conceitos-chave

| Termo | Definição curta | Por que importa no slide |
|---|---|---|
| HTML | Estrutura e conteúdo da página | O esqueleto |
| CSS | Aparência: cores, tamanhos, espaçamento | A roupa |
| JavaScript | Comportamento e interação | O movimento |
| `index.html` / `style.css` / `script.js` | Os três arquivos base do projeto | Organização do trabalho |
| Seções | Hero, sobre, trilhas, recursos, portfólio, contato, rodapé | Os cômodos do site |
| Menu de navegação | Links que levam às seções (âncoras) | O mapa do site |
| Prompt como ordem de serviço | Você descreve, o agente executa | Método da oficina |

### Metáforas animadas sugeridas

- **Casa por cômodos:** a fachada (HTML) se ergue, a pintura (CSS) colore, as luzes (JS) acendem.
- **Planta x mobília:** o HTML é a planta; o CSS é a mobília; o JS é a automação da casa.
- **Comboio de prompts:** um trem onde cada vagão é um prompt; o trem avança prompt a prompt.

### Exemplo no projeto-base

Prompts 2, 3, 5 e 6 constroem, na ordem: estrutura inicial, página inicial, cartões de trilha e recursos educacionais.

### Slides sugeridos

| # | Título | Template | Conteúdo | Elemento animado |
|---|---|---|---|---|
| 13 | Prompt 2: estrutura inicial | `card_code` | Prompt 2 na íntegra | Três arquivos surgindo |
| 14 | HTML, CSS e JavaScript | `card_d3` | Papel de cada um | Esqueleto, roupa e movimento |
| 15 | Os cômodos do portal | `card_grid` | 7 seções em pílulas | Nós que acendem em sequência |
| 16 | Prompt 3: página inicial | `card_code` | Prompt 3 na íntegra | Seções aparecendo |
| 17 | Cartões de trilha | `card_grid` | Título, descrição, duração, botão (Prompt 5) | Cartões que entram em cascata |
| 18 | Recursos educacionais | `card_lista` | Aulas, minicursos, materiais, portfólio (Prompt 6) | Lista que se preenche |

### Frase-âncora

"Cada prompt é uma ordem de serviço. Você revisa o resultado antes de passar a próxima."

### Erros comuns / cuidados

- Deixar o agente escolher cores antes de fixar a identidade.
- Pular a revisão do resultado para "adiantar".
- Misturar toda a página em um único arquivo.

### Assets

- Captura do site após o Prompt 3.

---

## Bloco 4: Refinamento (10h35–10h55, compartilhada com o Bloco 5)

**Objetivo:** ajustar layout, cores, tipografia, responsividade e revisar o texto.

### Conceitos-chave

| Termo | Definição curta | Por que importa no slide |
|---|---|---|
| Layout | Distribuição dos elementos na página | Organização visual |
| Cores e paleta | Conjunto coerente de cores | Identidade e contraste |
| Tipografia | Escolha de fontes e tamanhos legíveis | Legibilidade |
| Responsividade | O site se adapta a notebook e celular | Alcance real |
| Media query | Regra de CSS que muda o layout por tamanho de tela | Como a responsividade acontece |
| Revisão textual | Clareza, tom e ortografia | Qualidade do conteúdo |

### Metáforas animadas sugeridas

- **Vestiário:** o mesmo corpo (conteúdo) experimentando roupa larga e roupa justa (telas).
- **Elástico:** um layout que estica e encolhe sem quebrar.
- **Pintura e voz:** a paleta é a pintura; a tipografia é a voz do site.

### Exemplo no projeto-base

Prompt 4 pede layout para notebook e celular, com boa legibilidade e navegação simples.

### Slides sugeridos

| # | Título | Template | Conteúdo | Elemento animado |
|---|---|---|---|---|
| 19 | Antes e depois do layout | `card_destaques` | Duas telas comparadas | Transição entre as duas |
| 20 | O mesmo site, qualquer tela | `card_d3` | Notebook → tablet → celular | Moldura que se estreita |
| 21 | Prompt 4: layout responsivo | `card_code` | Prompt 4 na íntegra | Cursor digitando |
| 22 | Checklist de refinamento | `card_lista` | Contraste, espaçamento, tipografia, legibilidade | Itens sendo marcados |

### Frase-âncora

"Bonito é o que continua legível no celular de alguém."

### Erros comuns / cuidados

- Contraste baixo (texto claro em fundo claro).
- Fonte decorativa demais.
- Ignorar o celular.

### Assets

- Capturas "antes x depois" do layout.

---

## Bloco 5: Recursos interativos simples (10h35–10h55, compartilhada com o Bloco 4)

**Objetivo:** criar indicador de progresso e área de anotações salvos localmente, sem back-end.

### Conceitos-chave

| Termo | Definição curta | Por que importa no slide |
|---|---|---|
| JavaScript básico | Código que reage a cliques e eventos | Interação |
| `localStorage` | Memória pequena que o navegador guarda no próprio dispositivo | Persistência sem servidor |
| Indicador de progresso | Marca visual do quanto o aluno avançou | Recurso do produto educacional |
| Anotações locais | Campo de texto salvo no navegador | Engajamento |
| Sem back-end | Tudo roda e vive no computador do usuário | Limite e cuidado |

### Metáforas animadas sugeridas

- **Gaveta do navegador:** o dado não vai para a nuvem, fica numa gaveta do próprio navegador.
- **Marcador de livro:** o progresso é o marcador que diz onde você parou.
- **Post-it no espelho:** a anotação cola onde você vê, mas só no seu espelho.
- **Sem porão:** casa sem cofre e sem porão; nada fica guardado no servidor.

### Exemplo no projeto-base

Prompts 7 e 8 implementam progresso e anotações com `localStorage`, sem backend.

### Slides sugeridos

| # | Título | Template | Conteúdo | Elemento animado |
|---|---|---|---|---|
| 23 | Onde o dado vive | `card_d3` | Navegador x servidor | Dado que fica parado no navegador |
| 24 | Prompt 7: progresso local | `card_code` | Prompt 7 na íntegra | Barra que se preenche |
| 25 | Prompt 8: anotações locais | `card_code` | Prompt 8 na íntegra | Texto que aparece |
| 26 | Progresso na prática | `card_progresso` | Exemplo de indicador | Barra subindo |

### Frase-âncora

"Sem servidor, o dado mora no seu computador. Trocar de navegador é trocar de gaveta."

### Erros comuns / cuidados

- Prometer sincronização entre dispositivos (não existe sem back-end).
- Guardar dado sensível no `localStorage`.
- Esquecer de tratar o caso "sem dado salvo".

### Assets

- Captura do indicador de progresso em uso.

---

## Bloco 6: Personalização (10h55–11h15)

**Objetivo:** adaptar o projeto-base ao contexto individual, trocar textos, seções e identidade visual, e definir próximos passos.

### Conceitos-chave

| Termo | Definição curta | Por que importa no slide |
|---|---|---|
| Adaptação ao contexto | Trocar o conteúdo pelo do produto de cada aluno | Torna o projeto significativo |
| Identidade visual | Paleta, tipografia e tom próprios | Reconhecimento |
| Projeto-base x projeto pessoal | O mesmo esqueleto, conteúdo diferente | Fecha o arco da oficina |
| Expansões futuras | Login, banco de dados, certificados, app | Próximos passos realistas |

### Metáforas animadas sugeridas

- **Receita adaptável:** a mesma receita com o ingrediente de cada cozinha.
- **Impressão digital:** cada site ganha a marca única do dono.
- **Degraus:** do projeto-base para o projeto pessoal, um degrau de cada vez.

### Exemplo no projeto-base

Prompt 9 adapta textos e identidade visual para um produto educacional universitário.

### Slides sugeridos

| # | Título | Template | Conteúdo | Elemento animado |
|---|---|---|---|---|
| 27 | Prompt 9: personalização e identidade | `card_code` | Prompt 9 na íntegra | Paleta que muda |
| 28 | Traga o seu contexto | `card_cta` | Chamada para transformar o molde no seu projeto | Chamada pulsando |
| 29 | O que vem depois | `card_grid` | Expansões futuras marcadas como futuro | Blocos desbloqueando |
| 30 | Do molde ao seu projeto | `card_destaques` | Projeto-base x projeto pessoal | Transformação lado a lado |

### Frase-âncora

"O molde é o mesmo. O sabor é o seu."

### Erros comuns / cuidados

- Copiar o exemplo sem adaptar.
- Prometer recursos que exigem back-end.
- Perder a organização ao personalizar.

---

## Bloco 7: Publicação (11h15–11h55)

**Objetivo:** criar repositório, enviar os arquivos e publicar o site no GitHub Pages.

### Conceitos-chave

| Termo | Definição curta | Por que importa no slide |
|---|---|---|
| Git | Ferramenta de versionamento, guarda o histórico | Máquina do tempo do projeto |
| GitHub | Serviço na nuvem que hospeda repositórios Git | Pasta compartilhada |
| Repositório | O projeto versionado | Onde o código vive |
| Commit | Registro de um ponto do projeto | Ponto de salvamento |
| Push | Envia os commits locais para o GitHub | Publicar o histórico |
| Repositório público x privado | Quem pode ver | Cuidado com dados |
| GitHub Pages | Publica o site estático a partir de um repositório | O site no ar |

### Metáforas animadas sugeridas

- **Máquina do tempo:** cada commit é um ponto salvo ao qual se pode voltar.
- **Pasta na nuvem:** o repositório é a pasta que sai do notebook e passa a viver online.
- **Vitrine:** publicar é abrir a loja e acender a placa da frente.

### Exemplo no projeto-base

Fluxo: `git init` → `git add .` → `git commit` → `git remote add origin` → `git push`, e depois Settings → Pages → Deploy from a branch → `main` → `/(root)`.

### Slides sugeridos

| # | Título | Template | Conteúdo | Elemento animado |
|---|---|---|---|---|
| 31 | Git não é GitHub | `card_destaques` | Comparativo das duas coisas | Duas colunas paralelas |
| 32 | Do commit ao repositório | `card_d3` | commit → push → repositório | Dado que viaja |
| 33 | Comandos essenciais | `card_code` | `init`, `add`, `commit`, `remote`, `push` | Terminal digitando |
| 34 | O que nunca pode subir | `card_lista` | Chaves, `.env`, `auth.json`, sqlite, segredos | Itens bloqueados |
| 35 | Publicar no GitHub Pages | `card_timeline` | Settings → Pages → Deploy from a branch → main → /(root) | Passos que acendem |
| 36 | Seu site no ar | `card_progresso` | Validação da URL publicada | URL surgindo |

### Frase-âncora

"Não publique no mundo o que você não quer que o mundo veja. Revise antes de subir."

### Erros comuns / cuidados

- Subir chave de API ou `.env`.
- Confundir Git com GitHub.
- Escolher a pasta errada no GitHub Pages.

### Assets

- Captura da tela de Pages do GitHub.
- Captura do site publicado.

---

## Encerramento (11h55–12h00)

**Objetivo:** verificar entregas, recolher dúvidas e apontar caminhos para continuar.

### Slides sugeridos

| # | Título | Template | Conteúdo | Elemento animado |
|---|---|---|---|---|
| 37 | O que levamos hoje | `card_lista` | Síntese dos 7 blocos | Itens acendendo |
| 38 | Continue construindo | `card_cta` | Próximos passos e materiais liberados | Chamada pulsando |
| 39 | Obrigado | `card_citacao` | Agradecimento e canais | Constelação respirando |

### Frase-âncora

"Vocês não aprenderam a fazer um site. Aprenderam o método para fazer o próximo."

---

## Glossário consolidado (para o copywriter)

- **IA generativa / LLM:** gera texto e código a partir de um pedido.
- **Vibe coding:** programar conversando em linguagem natural.
- **Prompt:** instrução dada ao agente.
- **OpenCode:** interface onde o agente trabalha na pasta do projeto.
- **HTML / CSS / JavaScript:** estrutura / aparência / comportamento.
- **Seção:** parte da página (hero, sobre, trilhas, recursos, portfólio, contato, rodapé).
- **Responsividade:** adaptação a diferentes telas.
- **`localStorage`:** memória do navegador, sem servidor.
- **Git / GitHub:** versionamento local / hospedagem na nuvem.
- **Commit / Push:** ponto de salvamento / envio para a nuvem.
- **GitHub Pages:** publicação de site estático a partir do repositório.
- **Projeto-base:** "Portal de Trilhas de Aprendizagem".

## Assets a coletar (pasta `07-apresentacao/assets/`)

- [ ] Logos UFPA, PPGCIMES, NITAE.
- [ ] Captura do OpenCode aberto na pasta do projeto.
- [ ] Captura do `/connect` com provedor.
- [ ] Captura do site após o Prompt 3.
- [ ] Capturas "antes x depois" do layout responsivo.
- [ ] Captura do indicador de progresso em uso.
- [ ] Captura da tela de Pages do GitHub.
- [ ] Captura do site publicado (URL aberta).

---

## Arquivos desta pasta

- `conteudo-detalhado-por-bloco.md` (este arquivo): fonte primária do deck.
- `conteudo-tecnico-aprofundado.md`: estudo do ministrante e fonte secundária de precisão para o Mira.

## Próximos arquivos desta pasta

1. `prompts-detalhados.md` (objetivo, resultado esperado, erro comum e ponto de ensino de cada prompt).
2. `roteiro-apresentacao.md` (arco narrativo e notas de fala, sincronizado ao cronograma).
3. `dados-e-numeros.md` (versões homologadas, tempos, URLs e números da turma).
