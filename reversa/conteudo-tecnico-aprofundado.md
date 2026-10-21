# Conteúdo técnico aprofundado

**Estudo do ministrante + fonte de precisão para o Mira-Animator**

Este documento é o material de estudo profundo da oficina. Ele existe para que, no momento em que o slide exibe apenas o **tópico** e a **metáfora**, você tenha segurança para explicar o conceito de forma didática, responder perguntas e corrigir equívocos comuns.

## Papel deste documento

- **Para você (ministrante):** estude na ordem da sessão. Cada tópico traz definição rigorosa, funcionamento interno, analogia, o que dizer em voz alta, erro comum do aluno e pergunta provável da turma.
- **Para o Mira-Animator:** é a **fonte secundária de precisão**. O `/mira-extract`, o `/mira-copywriter` e o `/mira-animator` podem lê-lo para conferir exatidão técnica e enriquecer metáforas. Regra fixa: **a profundidade daqui não vai para a tela.** O deck mostra apenas tópico e metáfora (ver `conteudo-detalhado-por-bloco.md`, que é a fonte primária).

## Ordem da sessão (timeline canônica)

| Janela | Bloco | Prompt |
|---|---|---|
| 08h30–08h45 | Abertura + Bloco 1: Contextualização | — |
| 08h45–09h20 | Configuração | — |
| 09h20–09h35 | Bloco 2: Preparação do projeto | — |
| 09h35–10h35 (com pausa) | Bloco 3: Construção guiada | 1, 2, 3, 5, 6 |
| 09h55–10h55 (encadeado) | Bloco 4: Refinamento | 4 |
| 10h35–10h55 | Bloco 5: Recursos interativos | 7, 8 |
| 10h55–11h15 | Bloco 6: Personalização | 9, 10 |
| 11h15–11h55 | Bloco 7: Publicação | — |
| 11h55–12h00 | Encerramento | — |

---

## Abertura e enquadramento (08h30–08h45)

### O papel da IA nesta oficina

**O que é:** a IA aqui é **ferramenta de apoio à construção**, não autora do produto. Você descreve, ela escreve, você revisa.

**Analogia:** um copiloto. Ele segura o volante com você, mas quem define o destino e confere a rota é você.

**Para dizer em voz alta:**
1. "A IA escreve rápido, mas quem decide e revisa somos nós."
2. "Hoje vamos construir um site por conversa, e a cada passo vamos conferir o resultado."
3. "O objetivo não é decorar código. É entender a dinâmica."

**Pergunta provável:** "A IA vai substituir o programador?" **Resposta:** ao contrário. Ela reduz o custo de começar e aumenta a importância de quem revisa, testa e decide. O trabalho sobe de nível, não desaparece.

---

## Bloco 1: Contextualização (08h30–08h45)

### 1.1 IA generativa e LLM

**O que é:** um LLM (Large Language Model, grande modelo de linguagem) é um modelo estatístico treinado em enormes volumes de texto e código. Ele gera a continuação mais provável para um trecho de entrada. "Generativa" porque produz conteúdo novo a cada resposta.

**Como funciona por dentro:** o texto é quebrado em pedaços (tokens). O modelo calcula, para cada posição, qual token tem maior probabilidade de vir a seguir, dado todo o contexto anterior. Ele não consulta um banco de respostas: ele **prevê**. Isso explica duas coisas: por que a resposta muda a cada execução e por que ele pode **alucinar** (inventar com confiança).

**Analogia:** um previsor de palavras que já leu uma biblioteca inteira. Ele "chuta" muito bem, mas chuta.

**No projeto-base:** quando você pede "crie um cartão de trilha", o modelo não tem um cartão guardado; ele escreve um cartão plausível com o padrão que aprendeu.

**Erro comum do aluno:** acreditar que, se a IA escreveu, está correto. Sempre revisar e testar.

**Pergunta provável:** "Ele entende o que escreve?" **Resposta:** não como uma pessoa. Ele modela padrões de linguagem. É por isso que precisamos verificar fatos, nomes e comandos.

**Para dizer em voz alta:**
1. "O modelo não busca a resposta pronta, ele prevê a continuação mais provável."
2. "Por isso ele pode errar com naturalidade, e por isso a revisão é obrigatória."
3. "Pense nele como um previsor treinado, não como uma autoridade."

### 1.2 Vibe coding (desenvolvimento assistido por IA)

**O que é:** programar descrevendo a intenção em linguagem natural e deixando um agente de IA escrever o código. O termo foi popularizado em 2025 por Andrej Karpathy, originalmente com a ideia radical de "aceitar tudo sem ler". Nesta oficina usamos a versão responsável: **gerar rápido e revisar sempre**.

**Como funciona por dentro:** você conversa com um agente (o OpenCode). Ele tem acesso a ferramentas: lê e escreve arquivos, roda comandos, pesquisa. Cada pedido seu é um ciclo: descreve, o agente propõe, você confere, ajusta.

**Analogia:** um croqui feito em conversa que vira planta. A conversa é rápida; a planta precisa ficar de pé.

**No projeto-base:** todos os arquivos do site nascem de prompts, e cada prompt é revisado antes do próximo.

**Erro comum do aluno:** pedir "faça o site inteiro" de uma vez e não saber o que recebeu. Regra da oficina: um passo por vez.

**Pergunta provável:** "Preciso saber programar para fazer isso?" **Resposta:** para começar, não. Para evoluir e manter, sim, e é aí que está o valor.

**Para dizer em voz alta:**
1. "Vibe coding é programar conversando, mas com revisão."
2. "A velocidade está no começo; a garantia está na sua conferência."
3. "Quem descreve bem, recebe melhor."

### 1.3 Prompt

**O que é:** uma instrução em linguagem natural dada ao modelo. É a unidade de trabalho da oficina.

**Como funciona por dentro:** o prompt vira parte do contexto do modelo. Quanto mais claro o objetivo, o formato e as restrições, menor o espaço para o modelo "adivinhar". Contexto longo ajuda, mas tudo tem limite (janela de contexto).

**Boas práticas:** dizer o objetivo, o formato esperado, o que evitar e o contexto. Exemplo: "Não crie arquivos ainda" (usado no Prompt 1) evita que o agente se antecipe.

**Analogia:** uma ordem de serviço. Se você não diz tamanho, cor e prazo, cada um entrega o que imagina.

**No projeto-base:** os 10 prompts da oficina são ordens de serviço progressivas, do plano à publicação.

**Erro comum do aluno:** pedidos vagos ("deixa bonito") ou grandões ("faz tudo").

**Pergunta provável:** "Existe prompt perfeito?" **Resposta:** não. Existe o hábito de iterar: pedir, ver, corrigir.

**Para dizer em voz alta:**
1. "Prompt é ordem de serviço: quanto mais claro, melhor o resultado."
2. "Pedi, vi, corrigi. Esse é o ciclo."
3. "Frases como 'não crie arquivos ainda' controlam o ritmo do agente."

### 1.4 Gerar conteúdo x estruturar um projeto

**O que é:** gerar conteúdo é produzir pedaços (um texto, um bloco de código). Estruturar um projeto é organizar arquivos, responsabilidades e fluxo para que tudo funcione junto e possa evoluir.

**Como funciona por dentro:** um projeto tem arquivos com papéis definidos (estrutura, estilo, comportamento) e um ponto de entrada (`index.html`). Sem essa divisão, o código funciona uma vez e não se mantém.

**Analogia:** tijolos x planta. A IA entrega tijolos rápido; a planta organiza a casa.

**No projeto-base:** `index.html` (estrutura), `style.css` (aparência), `script.js` (comportamento). Três arquivos, três responsabilidades.

**Erro comum do aluno:** jogar tudo em um arquivo só e depois não conseguir mexer.

**Pergunta provável:** "Então o que a IA faz sozinha?" **Resposta:** ela propõe a estrutura; você valida se faz sentido.

**Para dizer em voz alta:**
1. "Conteúdo é tijolo; projeto é planta."
2. "Um arquivo para cada responsabilidade."
3. "Organização é o que permite o projeto crescer."

### 1.5 Site estático x aplicação com back-end

**O que é:** o site **estático** é um conjunto de arquivos (HTML, CSS, JS) entregues ao navegador exatamente como estão. A **aplicação com back-end** tem um servidor que processa dados, um banco de dados e regras no lado do servidor.

**Como funciona por dentro:** no estático, o navegador baixa os arquivos e faz todo o trabalho. No back-end, o navegador faz pedidos a um servidor, que consulta o banco e devolve respostas. Sem servidor, não há login, não há dados compartilhados, não há sincronização entre pessoas.

**Analogia:** uma **vitrine** (estático, o que está exposto é o que existe) x uma **loja com estoque e atendentes** (back-end, há um sistema nos bastidores).

**No projeto-base:** o Portal de Trilhas é estático. Progresso e anotações ficam no navegador do aluno, não em um servidor.

**Erro comum do aluno:** prometer "login" ou "ranking" com site estático. Não dá, sem back-end.

**Pergunta provável:** "Dá para fazer um mural colaborativo?" **Resposta:** com back-end, sim; nesta oficina, o que conseguimos é um mural local, visível só para o próprio aluno.

**Para dizer em voz alta:**
1. "Site estático é vitrine: o navegador faz tudo."
2. "Aplicação tem bastidor: servidor e banco."
3. "Nesta oficina ficamos na vitrine, e é muito o que se aprende nela."

### 1.6 Limites, riscos e uso responsável

**O que é:** o conjunto de cuidados no uso pedagógico das ferramentas de IA.

**Como funciona por dentro:** riscos típicos: alucinação (informação inventada), viés, perda de contexto, exposição de dados sensíveis em prompts e dependência excessiva sem entender o resultado.

**Analogia:** cinto de segurança. Não impede a viagem, mas exige atenção.

**No projeto-base:** nunca colar chaves de API ou dados pessoais no projeto nem no prompt; revisar todo texto gerado.

**Erro comum do aluno:** compartilhar chave de API no grupo ou deixá-la dentro do HTML.

**Pergunta provável:** "Posso usar o que a IA gerou direto?" **Resposta:** pode usar como rascunho, mas revise, teste e entenda.

**Para dizer em voz alta:**
1. "IA acelera o começo; a responsabilidade continua sendo sua."
2. "Nada de chave ou senha no projeto e no grupo."
3. "Revise tudo antes de publicar."

---

## Bloco 2: Preparação do projeto (09h20–09h35)

### 2.1 A pasta do projeto

**O que é:** o diretório onde vivem os arquivos do site e, depois, o repositório Git.

**Como funciona por dentro:** o navegador abre o `index.html` e carrega o `style.css` e o `script.js` pelos caminhos declarados. Se o nome ou o caminho do arquivo estiver errado, o estilo ou o comportamento não carregam.

**Analogia:** uma oficina com gavetas rotuladas. Ferramenta no lugar certo, trabalho sem susto.

**No projeto-base:**
```
portal-trilhas/
├── index.html
├── style.css
└── script.js
```

**Erro comum do aluno:** salvar arquivos fora da pasta do projeto ou com nomes diferentes dos referenciados.

**Pergunta provável:** "Posso criar subpastas?" **Resposta:** pode (por exemplo `assets/` para imagens), desde que os caminhos no HTML apontem para elas.

**Para dizer em voz alta:**
1. "A pasta certa é metade do trabalho organizado."
2. "O `index.html` é a porta de entrada do site."
3. "Nome de arquivo errado quebra o estilo e o script."

### 2.2 OpenCode

**O que é:** um agente de código que roda no terminal (e integra com o VS Code). Ele lê e escreve arquivos do projeto e executa comandos, sempre sob seu comando.

**Como funciona por dentro:** o OpenCode se conecta a um provedor de IA (modelo) e usa ferramentas locais para agir na pasta. Ele pode seguir instruções de um arquivo de contexto do projeto. Cada ação que ele propõe pode ser aceita ou recusada por você.

**Analogia:** a bancada de trabalho. É onde o agente põe a mão na massa, na sua frente.

**No projeto-base:** aberto na pasta `portal-trilhas/`, o OpenCode cria e edita os arquivos conforme os prompts.

**Erro comum do aluno:** rodar o OpenCode em outra pasta e não achar os arquivos.

**Pergunta provável:** "Ele mexe em arquivos sem eu ver?" **Resposta:** ele propõe e você aprova. Você continua no controle.

**Para dizer em voz alta:**
1. "O OpenCode é a bancada onde o agente trabalha."
2. "Abra sempre na pasta do projeto."
3. "Você acompanha e aprova cada ação."

### 2.3 Provedores e `/connect`

**O que é:** provedores são serviços que oferecem acesso aos modelos de IA (NVIDIA Build, Google Gemini API, GroqCloud, OpenRouter, entre outros). O `/connect` é o comando do OpenCode para ligar um provedor.

**Como funciona por dentro:** o provedor expõe uma API; o OpenCode autentica com uma **chave de API** e passa a enviar seus pedidos ao modelo. Cada provedor tem catálogo de modelos e limites de uso gratuito.

**Analogia:** tomadas diferentes para o mesmo aparelho. Você escolhe a tomada que tem energia disponível.

**No projeto-base:** você prepara pelo menos um provedor e, se possível, um segundo como contingência.

**Erro comum do aluno:** conta sem crédito, chave inválida ou provedor indisponível.

**Pergunta provável:** "Qual o melhor?" **Resposta:** o que estiver funcionando na sua conta hoje. Tenha sempre um plano B.

**Para dizer em voz alta:**
1. "Pelo menos um provedor ligado; idealmente dois."
2. "A chave é pessoal e não se compartilha."
3. "Se um cair, troque para o outro e siga."

### 2.4 O projeto-base

**O que é:** "Portal de Trilhas de Aprendizagem", o site-modelo que a turma inteira constrói junto.

**Como funciona por dentro:** é um site estático com seções comuns a muitos produtos educacionais (apresentação, trilhas, materiais, portfólio, contato). Serve de molde para a personalização final.

**Analogia:** um molde de bolo. Todos usam a mesma forma; cada um confeita por cima.

**No projeto-base:** construído inteiramente pelos 10 prompts, na frente da turma.

**Erro comum do aluno:** tentar personalizar antes de ter o molde pronto.

**Pergunta provável:** "Meu projeto é diferente, isso serve?" **Resposta:** serve como base. A personalização vem no Bloco 6.

**Para dizer em voz alta:**
1. "Primeiro o molde, depois o sabor."
2. "Um projeto para a turma toda avançar junta."
3. "Todo mundo personaliza no fim, não no começo."

### 2.5 Segurança: chaves de API

**O que é:** a chave de API é a credencial que dá acesso ao provedor. É como uma senha de consumo.

**Como funciona por dentro:** a chave fica na configuração do OpenCode, no seu computador. Ela **nunca** deve ir para o projeto do site, para o repositório público ou para grupo de mensagens.

**Analogia:** a chave de casa. Guardada no seu bolso, não pregada na porta.

**No projeto-base:** nenhuma chave aparece no `index.html`, no `style.css` ou no `script.js`.

**Erro comum do aluno:** colar a chave dentro do código "só para testar" e publicar.

**Pergunta provável:** "Mas o site precisa da chave para funcionar?" **Resposta:** não. O site estático não usa IA nem chave. Quem usa a chave é o OpenCode, na sua máquina.

**Para dizer em voz alta:**
1. "Chave é credencial pessoal, não vai para o projeto."
2. "O site publicado não precisa de chave nenhuma."
3. "Se vazar uma chave, revogue e gere outra."

---

## Bloco 3: Construção guiada (09h35–10h35, com pausa)

### 3.1 HTML

**O que é:** HTML (HyperText Markup Language) é a linguagem de **estrutura** das páginas. Descreve o conteúdo com elementos (tags).

**Como funciona por dentro:** o navegador lê o HTML e monta uma árvore de elementos (o DOM). Cada elemento tem tags de abertura e fechamento (`<section>...</section>`) e pode ter atributos (`class`, `id`, `href`). Tags semânticas (`header`, `nav`, `main`, `section`, `footer`) dizem o que cada parte significa.

**Analogia:** o esqueleto da página. Define onde fica cada parte, sem ainda definir aparência.

**No projeto-base:** o `index.html` com `header`, `nav`, seções de trilhas e recursos e `footer`.

**Erro comum do aluno:** esquecer de fechar uma tag, o que bagunça o resto da página.

**Pergunta provável:** "Por que usar `section` e não só `div`?" **Resposta:** semântica. Ajuda leitores de tela, buscadores e você mesmo a entender o código.

**Para dizer em voz alta:**
1. "HTML é a estrutura: é o esqueleto da página."
2. "Cada elemento diz o que aquela parte é."
3. "Tag aberta e fechada, sempre em pares."

### 3.2 CSS

**O que é:** CSS (Cascading Style Sheets) é a linguagem de **aparência**: cores, tamanhos, espaçamentos, posição.

**Como funciona por dentro:** regras no formato `seletor { propriedade: valor; }`. A "cascata" e a especificidade decidem qual regra vence quando duas afetam o mesmo elemento. O **box model** trata todo elemento como uma caixa (conteúdo, preenchimento, borda, margem).

**Analogia:** a roupa e a pintura da casa. Muda a aparência sem mudar a estrutura.

**No projeto-base:** o `style.css` controla paleta, tipografia e espaçamento do portal.

**Erro comum do aluno:** brigar com a especificidade sem entender por que a regra "não pega".

**Pergunta provável:** "Por que meu estilo não aplica?" **Resposta:** provavelmente há outra regra mais específica vencendo. Abra o inspetor do navegador e veja.

**Para dizer em voz alta:**
1. "CSS é aparência: cor, tamanho, espaço."
2. "Todo elemento é uma caixa, com conteúdo e margem."
3. "Quando o estilo não pega, quase sempre é especificidade."

### 3.3 JavaScript

**O que é:** JavaScript é a linguagem de **comportamento**: reage a cliques, atualiza a tela, salva dados.

**Como funciona por dentro:** o navegador executa o JavaScript. Ele pode ler e alterar o HTML (DOM) e reagir a eventos (clique, digitação, carregamento). É uma linguagem de programação completa, diferente de HTML e CSS. Não confundir com Java.

**Analogia:** o sistema nervoso da página. Sente o que acontece e faz algo.

**No projeto-base:** o `script.js` implementa o progresso e as anotações.

**Erro comum do aluno:** achar que JavaScript é "CSS mais avançado". São coisas diferentes.

**Pergunta provável:** "É difícil?" **Resposta:** o básico é acessível, e nós usamos só o básico aqui.

**Para dizer em voz alta:**
1. "JavaScript é comportamento: a página reage."
2. "Ele conversa com o HTML e responde a cliques."
3. "É linguagem de programação, não é Java."

### 3.4 Os três arquivos do projeto

**O que é:** a divisão mínima de um site estático em três arquivos com papéis separados.

**Como funciona por dentro:** o `index.html` declara no `<head>` o link para o `style.css` e, ao final do `<body>`, o `script.js`. O navegador carrega nessa ordem.

**Analogia:** estrutura, roupa e movimento.

**No projeto-base:** exatamente os três arquivos, cada um com uma responsabilidade.

**Erro comum do aluno:** embutir CSS e JS dentro do HTML e perder a organização.

**Pergunta provável:** "Preciso de mais arquivos?" **Resposta:** para começar, não. Conforme cresce, você separa mais.

**Para dizer em voz alta:**
1. "Três arquivos, três papéis: estrutura, aparência, comportamento."
2. "O HTML chama o CSS e o JS."
3. "Separar é o que permite manter."

### 3.5 Seções e menu de navegação

**O que é:** as seções são os blocos de conteúdo da página (apresentação, trilhas, recursos, portfólio, contato, rodapé). O menu é a lista de links que leva a cada seção.

**Como funciona por dentro:** cada seção recebe um `id`; o menu usa links de **âncora** (`<a href="#trilhas">`) que rolam a página até o elemento com aquele `id`.

**Analogia:** os cômodos da casa e a placa que indica onde fica cada porta.

**No projeto-base:** menu com âncoras para "Sobre", "Trilhas", "Recursos", "Portfólio", "Contato".

**Erro comum do aluno:** criar link para uma âncora com `id` inexistente (o link não vai a lugar nenhum).

**Pergunta provável:** "O menu abre outra página?" **Resposta:** nesta página única, ele rola até a seção. Os `id` fazem essa ligação.

**Para dizer em voz alta:**
1. "Seções são cômodos; o menu é a sinalização."
2. "As âncoras ligam o link ao `id` da seção."
3. "Se o link não navega, o `id` está errado."

### 3.6 Prompts 1, 2, 3, 5 e 6 (como conduzir)

- **Prompt 1 (planejamento, 09h35):** pede o plano sem criar arquivos. Objetivo: mostrar que a IA planeja antes de escrever. Erro comum: aluno sair criando arquivos. Fale: "Primeiro o mapa, depois a obra."
- **Prompt 2 (estrutura inicial, 09h40):** cria `index.html`, `style.css`, `script.js` puros, sem frameworks. Objetivo: fixar a organização. Fale: "Três arquivos, três papéis."
- **Prompt 3 (página inicial, 09h45):** preenche o conteúdo das seções em português. Objetivo: dar corpo ao site. Fale: "Agora o site ganha conteúdo."
- **Prompt 5 (cartões de trilha, 10h15):** cria cartões com título, descrição, duração e botão. Objetivo: componente repetível. Fale: "Um componente que se repete é economia de trabalho."
- **Prompt 6 (recursos, 10h25):** adiciona seção de aulas, minicursos, materiais e portfólio. Objetivo: completar o produto educacional. Fale: "Aqui o site vira ferramenta de estudo."

**Pergunta provável recorrente:** "Posso pular a revisão para adiantar?" **Resposta:** não. Cada prompt depende do resultado do anterior. Pular garante retrabalho.

---

## Bloco 4: Refinamento (09h55–10h55, encadeado)

### 4.1 Layout e box model

**O que é:** layout é a distribuição dos elementos na tela. O box model é o modelo de caixa que o CSS usa para medir cada elemento.

**Como funciona por dentro:** cada elemento ocupa conteúdo + preenchimento (`padding`) + borda (`border`) + margem (`margin`). Ajustar esses valores muda o espaçamento e o equilíbrio visual.

**Analogia:** arrumar os móveis na sala, respeitando o espaço entre eles.

**No projeto-base:** o espaçamento consistente entre seções e cartões.

**Erro comum do aluno:** usar margens aleatórias e criar espaçamento irregular.

**Pergunta provável:** "Qual a diferença entre `margin` e `padding`?" **Resposta:** `padding` é o espaço interno (dentro da borda); `margin` é o espaço externo (fora da borda).

**Para dizer em voz alta:**
1. "Todo elemento é uma caixa com espaço interno e externo."
2. "Espaçamento consistente é o que faz parecer profissional."
3. "Layout é distribuição, não decoração."

### 4.2 Flexbox e grid

**O que é:** dois sistemas de layout do CSS para organizar elementos.

**Como funciona por dentro:** **Flexbox** organiza em uma direção (linha ou coluna) e distribui o espaço. **Grid** organiza em duas dimensões (linhas e colunas). Os dois resolvem alinhamento sem gambiarras.

**Analogia:** flexbox é uma fila bem espaçada; grid é um tabuleiro.

**No projeto-base:** flexbox para os cartões de trilha e o menu; grid para grades de recursos.

**Erro comum do aluno:** tentar posicionar com `float` e `position` antes de dominar flex/grid.

**Pergunta provável:** "Uso qual?" **Resposta:** uma direção, flexbox; duas, grid. Na dúvida, comece por flexbox.

**Para dizer em voz alta:**
1. "Flexbox alinha em uma direção; grid monta o tabuleiro."
2. "Escolher o sistema certo evita gambiarra."
3. "Alinhamento é o que dá a sensação de capricho."

### 4.3 Cores, contraste e acessibilidade

**O que é:** a paleta é o conjunto de cores; o contraste é a diferença entre o texto e o fundo.

**Como funciona por dentro:** contraste se mede por razão de luminância (WCAG: 4.5:1 para texto normal). Paletas coerentes usam poucas cores com variações de tom, não muitas cores diferentes.

**Analogia:** a pintura da casa. Combina, não briga.

**No projeto-base:** uma cor principal, uma neutra de fundo e uma de destaque; texto com contraste suficiente.

**Erro comum do aluno:** texto claro em fundo claro, cansativo de ler.

**Pergunta provável:** "Quantas cores usar?" **Resposta:** poucas. Uma principal, uma de destaque e neutros. Menos é mais.

**Para dizer em voz alta:**
1. "Poucas cores, bem escolhidas."
2. "Contraste é legibilidade, não gosto pessoal."
3. "Se for difícil ler, está errado."

### 4.4 Tipografia

**O que é:** a escolha de fontes, tamanhos, pesos e espaçamento entre linhas.

**Como funciona por dentro:** hierarquia tipográfica usa tamanhos diferentes para título, subtítulo e corpo. Linhas muito longas ou muito juntas cansam a leitura.

**Analogia:** a voz do site. Fala alto no título, normal no corpo.

**No projeto-base:** uma fonte legível, títulos maiores e corpo confortável.

**Erro comum do aluno:** fonte decorativa no corpo do texto.

**Pergunta provável:** "Qual fonte usar?" **Resposta:** uma legível e simples no corpo. Decoração só no título, se necessário.

**Para dizer em voz alta:**
1. "Tipografia é a voz do site."
2. "Fonte legível no corpo, sempre."
3. "Hierarquia: título chama, corpo informa."

### 4.5 Responsividade e media queries

**O que é:** responsividade é o site se adaptar a diferentes larguras de tela. A media query é a regra de CSS que aplica estilos específicos por tamanho.

**Como funciona por dentro:** o `viewport` no HTML diz ao celular para usar a largura real. As media queries, como `@media (max-width: 768px)`, mudam o layout em telas menores.

**Analogia:** roupa elástica. O mesmo conteúdo, ajustado ao corpo.

**No projeto-base:** colunas que viram empilhamento no celular; menu simplificado.

**Erro comum do aluno:** esquecer a meta viewport e ver o site "zoom out" no celular.

**Pergunta provável:** "Preciso testar no celular?" **Resposta:** sim, ou ao menos redimensionar a janela do navegador. É a única forma de saber.

**Para dizer em voz alta:**
1. "Responsivo é o mesmo site caber em qualquer tela."
2. "A media query troca o layout por tamanho."
3. "Bonito é o que continua legível no celular."

### 4.6 Prompt 4 (como conduzir, 09h55)

Pede layout para notebook e celular, com boa legibilidade, espaçamento consistente e navegação simples. Objetivo: transformar o esqueleto em algo usável. Erro comum: refinar antes de ter conteúdo. Fale: "Primeiro legível, depois bonito."

---

## Bloco 5: Recursos interativos simples (10h35–10h55)

### 5.1 JavaScript no navegador (DOM e eventos)

**O que é:** o DOM é a representação da página que o JavaScript pode ler e alterar. Eventos são acontecimentos (clique, digitação) aos quais o código reage.

**Como funciona por dentro:** o script seleciona elementos (`document.querySelector`), escuta eventos (`addEventListener`) e altera conteúdo ou estilo. Tudo acontece no navegador, sem servidor.

**Analogia:** o sistema nervoso reage ao toque: alguém clica, algo acontece.

**No projeto-base:** cliques que marcam uma trilha como concluída e atualizam o progresso.

**Erro comum do aluno:** rodar o script antes do HTML existir e não encontrar o elemento.

**Pergunta provável:** "Onde coloco o script?" **Resposta:** ao final do `<body>`, para o HTML já existir quando ele rodar.

**Para dizer em voz alta:**
1. "O JavaScript lê a página e reage a eventos."
2. "Clicou, algo acontece."
3. "Sem servidor, tudo isso roda no navegador."

### 5.2 `localStorage`

**O que é:** uma memória de chave e valor do navegador, que guarda dados no próprio dispositivo.

**Como funciona por dentro:** `localStorage.setItem("chave", "valor")` grava; `getItem` lê; `removeItem` apaga. Guarda apenas **texto** (strings). Os dados ficam por **origem** (protocolo + domínio + porta) e por navegador. Não há sincronização entre dispositivos nem entre navegadores diferentes.

**Analogia:** uma gaveta no seu navegador. Fecha o navegador, o dado continua; troca de computador, o dado não vai junto.

**No projeto-base:** o progresso e as anotações do aluno ficam nessa gaveta.

**Erro comum do aluno:** esperar ver os próprios dados em outro computador. Não vai.

**Pergunta provável:** "Isso é um banco de dados?" **Resposta:** não. É memória local simples, sem servidor, sem compartilhamento.

**Para dizer em voz alta:**
1. "localStorage é uma gaveta do navegador."
2. "Fica no dispositivo, não na nuvem."
3. "Serve para progresso e anotações, não para dados entre pessoas."

### 5.3 Indicador de progresso

**O que é:** um elemento visual que mostra quanto do conteúdo o aluno concluiu.

**Como funciona por dentro:** o estado (o que foi marcado) é salvo no `localStorage` e relido ao abrir a página, atualizando a barra ou a contagem.

**Analogia:** o marcador de livro. Diz onde você parou.

**No projeto-base:** barra de progresso das trilhas, persistente ao recarregar.

**Erro comum do aluno:** não tratar o caso "nada salvo ainda" e quebrar na primeira visita.

**Pergunta provável:** "Some ao limpar o histórico?" **Resposta:** os dados locais podem ser apagados ao limpar os dados do navegador. É normal.

**Para dizer em voz alta:**
1. "Progresso é o marcador do aluno."
2. "Salvo localmente, ele volta ao reabrir."
3. "Sem backend, é por dispositivo."

### 5.4 Anotações locais

**O que é:** um campo onde o aluno escreve e o texto é salvo no navegador.

**Como funciona por dentro:** o conteúdo do campo é gravado no `localStorage` e recarregado ao abrir a página. Tudo local.

**Analogia:** um post-it colado no seu espelho. Só você vê.

**No projeto-base:** área de anotações por trilha.

**Erro comum do aluno:** usar isso para dados sensíveis. Não use: é local e simples, sem proteção.

**Pergunta provável:** "Outra pessoa vê minhas anotações?" **Resposta:** não, ficam no seu navegador e no seu dispositivo.

**Para dizer em voz alta:**
1. "Anotações ficam no seu navegador, só para você."
2. "É um post-it local."
3. "Não guarde dado sensível aqui."

### 5.5 O que "sem back-end" implica

**O que é:** ausência de servidor, banco de dados e contas de usuário.

**Como funciona por dentro:** tudo roda e é guardado no dispositivo. Resultado: nada é compartilhado, nada sincroniza, nada é autenticado.

**Analogia:** uma casa sem porão e sem cofre. Tudo o que existe está à vista, no andar de cima.

**No projeto-base:** define o limite honesto do que a oficina entrega.

**Erro comum do aluno:** prometer recursos multiusuário.

**Pergunta provável:** "Como ter login?" **Resposta:** precisa de back-end e banco. É expansão futura, não desta oficina.

**Para dizer em voz alta:**
1. "Sem backend, nada é compartilhado."
2. "O limite é claro e é honesto."
3. "Login e banco são o próximo degrau."

### 5.6 Prompts 7 e 8 (como conduzir)

- **Prompt 7 (progresso, 10h40):** implementa progresso com `localStorage`, sem backend. Obstáculo provável: testar em outro navegador e "sumir". Explique a origem dos dados.
- **Prompt 8 (anotações, 10h50):** área de anotações salva localmente. Reforce o limite: local, não compartilhado.

---

## Bloco 6: Personalização (10h55–11h15)

### 6.1 Adaptação ao contexto

**O que é:** trocar textos, títulos e exemplos do projeto-base pelo conteúdo específico de cada aluno.

**Como funciona por dentro:** o molde (estrutura) se mantém; muda o conteúdo. Assim, o aluno não recomeça do zero.

**Analogia:** a mesma receita com o ingrediente da sua cozinha.

**No projeto-base:** o Portal de Trilhas vira o produto educacional de cada participante.

**Erro comum do aluno:** copiar o exemplo sem adaptar e entregar algo genérico.

**Pergunta provável:** "Posso mudar a estrutura?" **Resposta:** pode, mas mude primeiro o conteúdo onde ele já funciona.

**Para dizer em voz alta:**
1. "O molde é o mesmo; o conteúdo é o seu."
2. "Adapte sem recomeçar."
3. "Genérico não engaja."

### 6.2 Identidade visual

**O que é:** a combinação de paleta, tipografia e tom que dá reconhecimento ao projeto.

**Como funciona por dentro:** poucas variáveis de CSS (cor principal, fundo, texto, destaque) controlam quase toda a aparência. Mudando-as, muda a identidade sem quebrar o layout.

**Analogia:** a impressão digital do projeto.

**No projeto-base:** ajuste de paleta e tipografia no Bloco 6.

**Erro comum do aluno:** trocar dez cores e perder o contraste.

**Pergunta provável:** "Preciso de designer?" **Resposta:** ajuda, mas com uma paleta coerente e contraste você já sai bem.

**Para dizer em voz alta:**
1. "Identidade visual é reconhecimento."
2. "Poucas variáveis mudam tudo."
3. "Menos cores, mais coerência."

### 6.3 Prompt 9 (como conduzir, 11h05)

Adapta textos e identidade visual para um produto educacional. Objetivo: tornar o projeto do aluno. Erro comum: perder a organização ao personalizar. Fale: "Agora o site fica com a sua cara."

### 6.4 Próximos passos e expansões futuras

**O que é:** o horizonte de evolução do projeto, deixado explícito.

**Como funciona por dentro:** recursos como login, banco de dados, certificados automáticos, mural multiusuário e progresso compartilhado exigem back-end, banco e autenticação. São o próximo nível.

**Analogia:** degraus. Um de cada vez.

**No projeto-base:** citados como futuro, nunca como entregue.

**Erro comum do aluno:** achar que já tem isso no site estático.

**Pergunta provável:** "Como continuo?" **Resposta:** aprendendo back-end e banco, além de versionamento e publicação que já praticamos.

**Para dizer em voz alta:**
1. "O que ficou de fora é o próximo degrau, dito com honestidade."
2. "Login e banco exigem back-end."
3. "Hoje entregamos a base; amanhã, a expansão."

---

## Bloco 7: Publicação (11h15–11h55)

### 7.1 Git

**O que é:** Git é um sistema de controle de versão **distribuído**. Guarda o histórico do projeto no seu computador.

**Como funciona por dentro:** o repositório é uma pasta versionada. Um **commit** é um retrato do projeto naquele momento, com mensagem e identificador único (hash). Existe uma área de preparação (staging) onde você escolhe o que entra no próximo commit. Há ramificações (branches) e um ponteiro para a versão atual (HEAD). Comandos essenciais: `init`, `status`, `add`, `commit`, `log`, `remote`, `push`.

**Analogia:** a máquina do tempo do projeto. Cada commit é um ponto salvo.

**No projeto-base:** cada aluno versiona a própria pasta do site.

**Erro comum do aluno:** confundir Git (a ferramenta) com GitHub (o serviço).

**Pergunta provável:** "Preciso da internet para usar Git?" **Resposta:** não. O Git funciona localmente. Internet é para enviar ao GitHub.

**Para dizer em voz alta:**
1. "Git é versionamento local: a máquina do tempo."
2. "Cada commit é um ponto salvo com nome."
3. "Git não é GitHub."

### 7.2 GitHub

**O que é:** um serviço na nuvem que hospeda repositórios Git.

**Como funciona por dentro:** o repositório local se conecta a um repositório remoto (o `origin`) no GitHub. O envio (`push`) leva os commits locais para lá.

**Analogia:** uma pasta compartilhada na nuvem, com histórico.

**No projeto-base:** cada aluno cria o próprio repositório e envia o site.

**Erro comum do aluno:** não conseguir entrar na conta ou errar o endereço do remoto.

**Pergunta provável:** "Meu código fica público?" **Resposta:** depende do repositório. Público é visível a todos; privado, não. Para o GitHub Pages, o repositório precisa permitir a publicação.

**Para dizer em voz alta:**
1. "GitHub é o Git na nuvem."
2. "O repositório remoto se chama origin."
3. "Pense antes de deixar público."

### 7.3 Repositório, commit e push

**O que é:** o trio que move o código do computador para a nuvem.

**Como funciona por dentro:** você prepara (`git add`), registra (`git commit`) e envia (`git push`). O histórico local e o remoto se sincronizam pelo `push` (e pelo `pull`, no sentido inverso).

**Analogia:** empacotar, etiquetar e despachar.

**No projeto-base:** a sequência `init` → `add` → `commit` → `remote add origin` → `push`.

**Erro comum do aluno:** commitar tudo sem revisar e enviar arquivos indesejados.

**Pergunta provável:** "Posso desfazer?" **Resposta:** sim, o histórico permite voltar. É para isso que existe o versionamento.

**Para dizer em voz alta:**
1. "Prepara, registra, envia."
2. "Commit com mensagem clara é bom para o futuro."
3. "Revise antes de enviar."

### 7.4 Público x privado e segurança

**O que é:** a decisão de quem pode ver o repositório, e o cuidado com dados sensíveis.

**Como funciona por dentro:** o `.gitignore` evita que certos arquivos sejam rastreados, mas **não** remove o que já foi enviado. Segredos, chaves, arquivos `.env`, bancos e configurações não devem ser versionados.

**Analogia:** não pendure a chave de casa na porta da frente.

**No projeto-base:** antes de publicar, conferir que não há chave, token, `.env`, `auth.json` ou banco SQLite.

**Erro comum do aluno:** confiar só no `.gitignore` e publicar um segredo.

**Pergunta provável:** "Se eu já enviei sem querer, basta apagar?" **Resposta:** apagar o arquivo não basta: ele permanece no histórico. O ideal é nunca enviar; se acontecer, revogue a credencial.

**Para dizer em voz alta:**
1. "Público é público. Revise antes de subir."
2. "O `.gitignore` ajuda, mas não esconde o que já foi enviado."
3. "Vazou, revogou. Não existe arquivo secreto em repositório público."

### 7.5 GitHub Pages

**O que é:** um serviço do GitHub que publica sites estáticos diretamente de um repositório.

**Como funciona por dentro:** nas configurações do repositório (**Settings** → **Pages**), você escolhe **Deploy from a branch**, a branch (por exemplo `main`) e a pasta (`/(root)` ou `/docs`). O GitHub gera uma URL pública (algo como `usuario.github.io/repositorio`) e passa a servir os arquivos estáticos.

**Analogia:** abrir a vitrine. O site passa a ter endereço público.

**No projeto-base:** publicação do `index.html` na raiz do repositório.

**Erro comum do aluno:** escolher a pasta errada ou a branch errada e ver a página em branco.

**Pergunta provável:** "Precisa de servidor?" **Resposta:** não. O GitHub Pages só entrega arquivos estáticos, o que é exatamente o nosso caso.

**Para dizer em voz alta:**
1. "GitHub Pages publica site estático direto do repositório."
2. "Escolha a branch e a pasta certas."
3. "Em instantes você tem um endereço público."

### 7.6 Prompt 10 (como conduzir, 11h10)

Pede revisão geral, correção de inconsistências, simplificação e preparação para publicação estática. Objetivo: deixar o projeto apresentável. Antes de publicar, passe a lista de segurança (Bloco 7.4). Fale: "Seu site está pronto para o mundo, e revisado."

---

## Encerramento (11h55–12h00)

### Síntese e continuidade

**Para dizer em voz alta:**
1. "Vocês não aprenderam a fazer um site: aprenderam o método para fazer o próximo."
2. "Comece pequeno: automatize uma tarefa sua essa semana."
3. "Os materiais ficam disponíveis, e a comunidade está aberta."

**Perguntas prováveis de fecho:** "Por onde continuo?" (back-end e banco), "Isso serve para meu produto?" (sim, é o molde), "Posso mostrar para colegas?" (sim, publique e compartilhe).

---

## Glossário rápido de bolso

| Termo | Definição curta |
|---|---|
| LLM | Modelo que prevê e gera texto/código |
| Alucinação | Informação inventada com aparência de correta |
| Prompt | Instrução em linguagem natural |
| Agente | IA que age em arquivos e comandos, via ferramentas |
| HTML | Estrutura da página |
| CSS | Aparência da página |
| JavaScript | Comportamento da página |
| DOM | Representação da página que o JS manipula |
| Box model | Caixa de conteúdo, preenchimento, borda e margem |
| Flexbox / Grid | Sistemas de layout em uma / duas dimensões |
| Media query | Regra de CSS por tamanho de tela |
| `localStorage` | Memória local chave-valor do navegador |
| Git | Versionamento local |
| GitHub | Hospedagem de repositórios Git na nuvem |
| Commit | Retrato do projeto com mensagem e hash |
| Push | Envia commits locais para o remoto |
| GitHub Pages | Publicação de site estático a partir do repositório |

## Banco de perguntas frequentes da turma

1. **"A IA vai me substituir?"** Não. Ela reduz o custo de começar e eleva o valor de revisar, testar e decidir.
2. **"Preciso saber programar?"** Para começar, não. Para evoluir e manter, sim.
3. **"Por que não usar WordPress?"** É outra ferramenta, válida. Aqui o objetivo é entender a base e o método.
4. **"Dá para ganhar dinheiro com isso?"** Dá, como serviço de criação e manutenção de sites, entre outras frentes.
5. **"Meus dados ficam salvos onde?"** No navegador do seu dispositivo (`localStorage`). Não vão para servidor.
6. **"Como faço login?"** Precisa de back-end e banco. É expansão futura.
7. **"Posso usar para o meu produto educacional?"** Sim, é para isso que existe o projeto-base.
8. **"E se a IA errar?"** Você revisa e corrige. O ciclo é pedir, ver, corrigir.
9. **"Publicar é de graça?"** O GitHub Pages é gratuito para repositórios públicos, com limites de uso.
10. **"Onde guardo minha chave de API?"** Na configuração do OpenCode, na sua máquina. Nunca no projeto nem no repositório.

---

*Material de estudo do ministrante. Fonte secundária de precisão para o deck do Mira-Animator. A profundidade daqui não vai para a tela.*
