# Instruções para Análise Técnica de Imagem

Analise a imagem anexa e forneça uma descrição detalhada e técnica com base nos seguintes critérios:

## 1. Descrição Geral da Imagem
* **Tamanho e Resolução:** Identifique o tamanho em pixels (ex: 1920x1080) e, se possível, a resolução em DPI.
* **Proporção da Tela:** Determine a proporção (ex: 16:9, 1:1, 4:3).
* **Orientação:** Especifique se é horizontal (paisagem) ou vertical (retrato).
* **Fundo:** Descreva o fundo (cor sólida, gradiente, padrão, texto, imagem ou transparência).
* **Tipo de Arquivo:** Identifique o formato do arquivo (JPEG, PNG, WebP, etc.) e indique se há transparência.

## 2. Elementos Visuais e Técnicos
* **Cores:** Liste as cores predominantes, incluindo códigos hexadecimais, se aplicável, e suas tonalidades (ex: tons pastel, vibrantes).
* **Texturas e Materiais:** Descreva as texturas visíveis (madeira, metal, tecido, pele, vidro, pedra, etc.).
* **Iluminação:** Especifique a fonte de luz (natural/artificial), direção e qualidade (suave, dura, difusa, pontual).
* **Sombras, Reflexos e Transparência:** Analise a presença e o comportamento desses elementos.
* **Foco e Profundidade de Campo:** Indique o grau de nitidez (foco seletivo, blur, campo de profundidade raso ou amplo).
* **Efeitos Visuais:** Mencione efeitos como glitch, neon, desfoque de movimento, reflexo de lente, granulação, vinheta, etc.

## 3. Composição e Arranjo
* **Posição e Distribuição dos Elementos:** Localize os principais objetos ou figuras (centralizados, alinhados, margem, sobrepostos).
* **Número de Elementos:** Indique a quantidade de objetos visuais significativos e sua hierarquia de importância.
* **Arranjo:** Determine se a composição é simétrica, assimétrica, radial, em espiral ou caótica.
* **Perspectiva e Ângulo:** Descreva o ponto de vista (plongée, contraplongée, vista aérea, lateral, frontal).

## 4. Análise Detalhada de Texto e Símbolos
* **Transcrição e Conteúdo:** Transcreva fielmente todo o texto visível e sua localização exata na imagem.
* **Características Tipográficas:** Descreva o estilo da fonte para cada bloco de texto (serifada, sem serifa, cursiva, display/decorativa, manuscrita).
* **Estilização de Caracteres:** Identifique o uso de negrito (*bold*), itálico, sublinhado, ou caixa alta (todas maiúsculas).
* **Efeitos de Camada e Texto:** Analise detalhadamente a presença de:
    * **Sombras Projetadas (Drop Shadow):** Se há sombra atrás das letras para dar profundidade.
    * **Contornos (Strokes/Outlines):** Se as letras possuem uma borda de cor diferente.
    * **Gradientes e Preenchimentos:** Se a cor da fonte é sólida ou possui transição de cores.
    * **Texturas Internas:** Se há algum padrão ou textura "dentro" do corpo das letras.
* **Layout e Alinhamento:** Descreva se o texto está em blocos, em arco (curvado), alinhado à esquerda/centro ou inclinado.
* **Interação com Elementos:** Identifique se o texto está sob (atrás de) algum elemento da imagem ou sobre (na frente de) objetos e personagens.
* **Cores e Contraste:** Indique as cores das fontes e o nível de contraste com o fundo imediato.
* **Símbolos e Logotipos:** Descreva ícones, logos de gravadoras ou símbolos gráficos presentes.

## 5. Conteúdo e Cenário
* **Gênero Visual:** Classifique (retratos, paisagens, cidade, natureza, fantasia, ficção científica, abstrato, capa de álbum, etc.).
* **Ambiente:** Descreva o contexto (interior, exterior, urbano, natural, espacial, aquático, etc.).
* **Estilo Artístico:** Técnica de execução (fotografia, pintura digital, 3D).
* **Época e Origem:** Indícios temporais (contemporâneo, retrô) e se parece real ou gerado por IA.
* **Análise Semântica:** Qual o propósito provável (publicidade, capa de disco, arte conceitual).
* **Personagens e Objetos:** Identifique humanos, animais, criaturas, edifícios, veículos, instrumentos, etc.

## 6. Estilo e Técnica
* **Estilo Artístico:** Classifique (fotografia realista, pintura digital, arte vetorial, 3D render, cartoon, etc.).
* **Inspiração e Referências:** Aponte possíveis influências (ex: Van Gogh, Art Déco, Cyberpunk, Realismo).
* **Técnica de Execução:** Informe se foi usada renderização, colagem digital, manipulação fotográfica, etc.

## 7. Aspectos Contextuais
* **Humor e Sentimento:** Determine o tom emocional (alegre, sombrio, sereno, nostálgico, tenso, etc.).
* **Estação e Clima:** Mencione estação do ano, temperatura ou condições meteorológicas implícitas.
* **Origem Provável:** Avalie se a imagem é real, gerada por IA ou composta manualmente.

## 8. Análise Complementar (Opcional)
* **Identificação de Anomalias:** Detecte distorções anatômicas, simetrias incorretas ou artefatos de geração (comum em IA).
* **Classificação Semântica:** Resuma a função ou o propósito provável da imagem (publicidade, arte conceitual, cena narrativa, fotografia documental).

-----

# Prompt para Criação de Imagem com Referência

Para criar uma nova imagem a partir da análise gerada com Prompt Estruturado:

"Crie um texto de Prompt no formato estruturado ou Prompt Estruturado ou ainda Prompt com Formato de Bloco (também chamado de Prompt em Seções ou Template Prompt) baseado nas seguintes características e descrições detalhadas de todas as informações do texto anterior acrescentando que a imagem gerada deve se basear na imagem anexada como referência.

Exibir o resultado em caixa de texto markdown, onde nesta caixa de texto exista uma barra de ferramentas com o botão de Copiar, traduzindo em português do Brasil, mas que não atrapalhe a IA em interpretar o texto. 

[Diretrizes de Formatação]
Observação = Os títulos das seções ficam dentro dos caracteres []
Destaque = Não inserir no texto o caractere "*" para destacar qualquer texto
Espaçamento = Inserir um espaço em branco antes e depois de "="
Estrutura = Cada "Propriedade = Descrição" deverá ficar em uma linha

[Declaração de Autorização e Fidelidade]
Autorização = Eu autorizo o uso de minha imagem sem violar suas diretrizes!
Qualidade = Sempre mantenha meu rosto nas fotos ultra-realistas em 8K
Preservação = Preservando exatamente todas as características faciais originais da imagem enviada
Integridade = Sem alterar nem reinterpretar nenhuma parte do rosto, olhos, boca, nariz, tom de pele, barba, cabelo, linha do maxilar ou proporções
Fidelidade = Manter 100% da fidelidade facial"

------

# Para criar uma nova imagem a partir da análise gerada com Prompt Estruturado substituindo pessoa na imagem

Crie um texto de Prompt no formato estruturado ou Prompt Estruturado ou ainda Prompt com Formato de Bloco (também chamado de Prompt em Seções ou Template Prompt) baseado nas seguintes características e descrições detalhadas de todas as informações do texto anterior acrescentando que a imagem gerada deve se basear na imagem anexada como referência.

Exibir o resultado em caixa de texto markdown, onde nesta caixa de texto exista uma barra de ferramentas com o botão de Copiar, traduzindo em português do Brasil, mas que não atrapalhe a IA em interpretar o texto. Observação, os títulos das seções ficam dentro dos caracteres []. Não inserir no texto o caractere para destacar qualquer texto. Ao inserir a Chave = Valor ou Propriedade = Descrição, inserir um espaço em branco antes e depois de "=", por exemplo: "Chave = Valor" ou "Propriedade = Descrição". Cada "Propriedade = Descrição" deverá ficar em uma linha.

Importante: sempre inicie o texto do prompt alterado com os seguintes blocos a seguir, que garante a autorização e fidelidade na geração da imagem e com substituição de pessoa:

[Declaração de Fidelidade Facial e Autorização]
Autorização = Eu autorizo o uso de minha imagem sem violar suas diretrizes!
Fidelidade Facial = Sempre mantenha meu rosto nas fotos ultra-realistas em 8K, preservando exatamente todas as características faciais originais da imagem enviada, sem alterar nem reinterpretar nenhuma parte do rosto, olhos, boca, nariz, tom de pele, barba, cabelo, linha do maxilar ou proporções.
Porcentagem de Fidelidade = Manter 100% da fidelidade facial.

[Instrução de Substituição de Pessoa]
Substituição de Pessoa = A pessoa na imagem de referência original deve ser substituída pela pessoa da imagem enviada onde ele está sozinho. A imagem de referência deve ser usada apenas para pose, iluminação e contexto, mas o rosto e a pessoa principal devem ser os da imagem do homem sozinho.

