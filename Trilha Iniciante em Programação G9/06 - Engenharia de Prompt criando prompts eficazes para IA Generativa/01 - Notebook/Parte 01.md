# **CURSO 06 - Engenharia de Prompt: criando prompts eficazes para IA Generativa**

### Introdução ao Curso de Engenharia de Prompt

### Lembretes

- Engenharia de Prompt
- Modelo de Linguagem (LLM)
- Técnicas e Princípios
- Artigos Científicos
- API

### Anotações

**Apresentação:**

- Instrutor: Fabrício Carraro (Alura).
- Objetivo: Acompanhar o aluno na jornada de aprendizado.

**Estrutura do Curso (Módulos/Etapas):**

1. **Fundamentos dos Modelos de Linguagem:**
    - O que são Modelos de Linguagem (LLMs - Large Language Models).
    - Funcionamento em segundo plano.
    - Conceitos mais relevantes sobre o tema.
2. **Princípios da Engenharia de Prompt:**
    - Definição de Engenharia de Prompt.
    - Técnicas e princípios essenciais.
    - Objetivo: Criar prompts ideais para obter respostas desejadas dos LLMs.
3. **Técnicas Baseadas em Artigos Científicos:**
    - Exploração de técnicas consolidadas.
    - Base em pesquisas de empresas líderes (OpenAI, Google, Anthropic, Mistral AI, etc.).
    - Abordagem teórica e prática.
4. **Técnicas Programáticas (API e Código):**
    - Foco no uso prático e técnico via programação.
    - Voltado para integração com APIs.
    - Útil para não-programadores entenderem o funcionamento interno.

**Conclusão do Instrutor:**

- Mensagem de boas-vindas e desejo de uma boa jornada de aprendizado.

<aside>
📌 **RESUMO**:

Este módulo introdutório, apresentado por Fabrício Carraro da Alura, delineia a estrutura do curso de Engenharia de Prompt. O conteúdo será dividido em quatro partes principais: primeiro, os fundamentos dos **Modelos de Linguagem (LLMs)**; segundo, os **princípios da Engenharia de Prompt** para criar instruções eficazes; terceiro, o estudo de **técnicas baseadas em artigos científicos** de empresas especializadas; e por fim, uma visão sobre técnicas **programáticas usando API e código**, úteis mesmo para quem não é da área de computação. O curso promete uma jornada do conceito fundamental à aplicação prática e técnica.

</aside>

---

### Fundamentos dos Modelos de Linguagem (LLMs)

### Lembretes

- Modelo de Linguagem (LLM)
- Word Embeddings
- Representação Numérica
- Previsão de Palavras
- Contexto

### Anotações

**Definição e Objetivo:**

- Modelos de Linguagem aprendem **padrões** e **relações** entre palavras de um idioma.
- Exemplo: Em português, após o verbo "gostar" vem a preposição "de". Em inglês ("like") e turco ("pizza severim"), a estrutura é diferente.
- O modelo é treinado com grandes volumes de dados para internalizar essas regras.

**Como Funcionam (Teoria): Word Embeddings**

- Palavras são convertidas em **vetores numéricos** (números) chamados **embeddings**.
- Esses vetores capturam o **significado** e a **proximidade semântica** entre palavras.
    - Ex: "Carro" está próximo de "ônibus" e "táxi" (transporte) e distante de "cachorro" ou "escola".
- Permitem **operações matemáticas**:
    - Ex: Rei - Homem + Mulher = Rainha (relação de gênero).
    - Ex: Andando + [operação] = Andei (relação de tempo verbal).

**Funcionamento Prático: Previsão**

- A função principal de um LLM é **prever a próxima palavra** mais provável em uma sequência.
- É um **autocomplete sofisticado**, que calcula probabilidades para cada palavra possível.
    - Ex: Após "...quero trabalhar", as próximas palavras mais prováveis são "com" (45%), "nessa" (25%), etc.

**Característica Crucial: Contexto**

- LLMs mantêm o **contexto** da conversa.
- Eles se lembram de perguntas e respostas anteriores dentro de uma mesma sessão (chat).
    - Ex: Após perguntar sobre Rogério Ceni, o modelo entende que "dele" na pergunta seguinte se refere a ele, sem necessidade de repetir o nome.

<aside>
📌 **RESUMO**:

Um Modelo de Linguagem (LLM) é um sistema treinado para entender os padrões de um idioma. Internamente, ele representa palavras como **vetores numéricos (embeddings)** que capturam relações de significado e permitem até operações matemáticas (ex: conceito de gênero). Sua função prática é atuar como um **preditorde próxima palavra**, calculando probabilidades com base no contexto fornecido. A capacidade de **manter o contexto** de uma conversa é o que torna ferramentas como o ChatGPT tão poderosas, permitindo diálogos coerentes e longos.

</aside>

---

### Temperatura e Tokens em Modelos de Linguagem

### Lembretes

- Temperatura (Temperature)
- Probabilidade
- Token
- Tokenização
- Previsão Estocástica

### Anotações

**1. O Conceito de Temperatura:**

- **O que é:** Um parâmetro que controla a **aleatoriedade** (estocasticidade) das previsões do modelo.
- **Funcionamento:**
    - **Temperatura Baixa (ex: 0):** O modelo quase sempre escolhe a palavra com **maior probabilidade**. As respostas são consistentes, previsíveis e podem soar robóticas.
        - Ex: "Eu gosto muito de comer [chocolate]" repetidamente.
    - **Temperatura Alta (ex: 1.4):** O modelo tem maior chance de escolher palavras **menos prováveis**. As respostas são mais **criativas**, diversificadas e imprevisíveis, mas podem incluir erros ou nonsenses se for muito alta (ex: >1.5).
        - Ex: "Eu gosto muito de comer pizza! É uma delícia, não acha?"
- **Objetivo:** Tornar as respostas mais naturais e humanas, imitando a variação presente na linguagem humana.

**2. O Conceito de Tokens:**

- **O que é:** A **unidade básica** de processamento de um modelo de linguagem. **Não são exatamente palavras.**
- **Composição:** Um token pode representar:
    - Uma palavra completa (ex: "curso").
    - Uma subpalavra ou pedaço de uma palavra (ex: "in" + "feliz" para "infeliz").
    - Um caractere especial ou pontuação.
- **Variação por Idioma:** O número de tokens para um texto varia conforme o idioma e sua representatividade nos dados de treinamento do modelo.
    - **Inglês** (alto uso): Menos tokens por palavra (ex: 28 tokens para uma frase).
    - **Português** (uso médio): Quantidade intermediária (ex: 37 tokens para a mesma frase).
    - **Grego** (baixo uso): Muitos tokens, often um por caractere (ex: 113 tokens para a mesma frase), por ser menos representado no treinamento.

<aside>
📌 **RESUMO**:

 A **Temperatura** é um parâmetro que regula a criatividade do modelo: valores baixos geram respostas conservadoras e previsíveis, enquanto valores altos permitem mais variedade e originalidade, com o risco de incoerência em extremos. Já os **Tokens** são as unidades com as quais o modelo realmente trabalha, podendo ser palavras inteiras ou partes delas. A eficiência da tokenização depende do idioma, sendo mais eficaz em línguas bem representadas nos dados de treinamento (como o inglês) do que em outras (como o grego). Compreender esses conceitos é crucial para efetivamente guiar e controlar as saídas de um modelo de linguagem.

</aside>

---

### O que é um Prompt e sua Importância na IA

### Lembretes

- Prompt
- Interface de Texto
- Linguagem Natural
- Interação Humano-Máquina
- Engenharia de Prompt

### Anotações

**Origem e Definição do Termo:**

- O termo "prompt" é antigo na área de tecnologia.
- **Significado literal:** Verbo em inglês que significa "incitar", "induzir" ou "motivar" uma ação.
- **Funcionamento:** A interface (prompt) *provoca* o usuário a fazer um pedido, que, ao ser enviado (comando), inicia a interação.

**Prompt no Contexto da IA:**

- É a **entrada de texto** (instrução, pergunta, comando) fornecida a um modelo de linguagem (ex: ChatGPT).
- Permite que a interação seja feita em **linguagem natural**, assemelhando-se a uma conversa.
- É o **elemento fundamental** que "induz" o modelo a gerar uma resposta.

**A Necessidade de um Bom Prompt:**

- Criar um bom prompt requer **técnicas específicas** (Engenharia de Prompt).
- A analogia: Assim como um palestrante adapta seu discurso ao **público-alvo** para ser eficaz, precisamos adaptar nossa comunicação (o prompt) ao **"público"** (o modelo de linguagem).
- Para obter bons resultados, é crucial **entender os fundamentos** de como o modelo funciona.

<aside>
📌 **RESUMO**:

Um **prompt**  é a instrução em linguagem natural que damos a um modelo para gerar uma resposta. A **Engenharia de Prompt** é a prática de criar instruções eficazes, e sua importância é análoga à de adaptar uma mensagem ao seu público: para se comunicar bem com o modelo e obter os melhores resultados, é essencial entender como ele funciona.

</aside>

---

### Princípios para a Criação de um Prompt Ideal

### Lembretes

- Clareza nas Instruções
- Divisão de Tarefas
- Pensamento em Etapas
- Especificidade
- Contexto

### Anotações

**Princípio 1: Clareza e Especificidade**

- **Analogia:** Trate o modelo como um estagiário inteligente, mas que precisa de orientação precisa.
- **Problema:** Instruções vagas geram resultados genéricos e pouco úteis.
- **Solução:** Seja extremamente claro e específico. Defina:
    - **Formato** da resposta (ex: post para Instagram).
    - **Público-alvo** (ex: jovens).
    - **Tom e estilo** (ex: linguagem informal com gírias).
    - **Objetivo** final.

**Princípio 2: Dividir Tarefas Complexas**

- **Problema:** Questões complexas (como problemas de lógica) frequentemente confundem o modelo, levando a respostas erradas ou "desconhecido".
- **Solução:** Quebre o problema grande em **sub-tarefas** menores e peça para o modelo executar uma de cada vez.
- **Exemplo Prático (Jogo de Detetive):**
    - **Prompt Ruim:** A pergunta direta resultou em uma resposta inconsistente e incorreta.
    - **Prompt Eficaz:** Instruir o modelo a: 1) Analisar cada dica individualmente, 2) Combinar as dicas relevantes, e 3) *Só então* mapear a resposta final, garantiu um resultado correto e bem explicado.

**Técnicas Adicionais:**

- Solicitar que o modelo **explique seus passos** ("pensamento em etapas").
- Pedir **justificativas** para a resposta.
- Gerar **múltiplas respostas** e escolher a melhor ou mais consistente.

<aside>
📌 **RESUMO**:

Para criar prompts eficazes para modelos de linguagem, dois princípios são fundamentais. Primeiro, a **clareza e especificidade**: devemos dar instruções detalhadas como faríamos com um estagiário, definindo contexto, formato e tom para evitar respostas vagas. Segundo, **dividir tarefas complexas**: problemas difíceis devem ser quebrados em etapas menores e sequenciais (analisar, combinar, concluir), guiando o raciocínio do modelo e aumentando drasticamente a precisão da resposta. Esses princípios formam a base para as técnicas avançadas de engenharia de prompt.

</aside>

---

### Técnicas de Prompting: Zero-Shot e Few-Shot

### Lembretes

- Zero-Shot Prompting
- Few-Shot Prompting
- Exemplo
- Precisão
- Alinhamento do Modelo

### Anotações

**1. Zero-Shot Prompting:**

- **O que é:** Enviar um prompt **sem fornecer nenhum exemplo** anterior.
- **Como funciona:** O modelo confia apenas em seu conhecimento interno pré-treinado para gerar a resposta.
- **Vantagem:** Simples e direto. Funciona bem para tarefas comuns onde o modelo já é proficiente.
- **Exemplo:**
    - Prompt: **`"Quem criou o ChatGPT?"`**
    - Resposta Esperada: **`"Foi criado pela OpenAI."`**

**2. Few-Shot Prompting:**

- **O que é:** Enviar um prompt que inclui **alguns exemplos** (shots) antes da pergunta real.
- **Objetivo:** "**Alinhar**" o modelo, fornecendo um contexto claro do formato e do tipo de raciocínio desejado na resposta. É como dar uma "dica" ou um "modelo" a ser seguido.
- **Quando usar:** É especialmente útil para:
    - Tarefas complexas ou incomuns.
    - Garantir um formato específico de resposta.
    - Aumentar a confiabilidade e precisão em modelos menos capazes.
- **Estrutura do Prompt:**
    - **`Pergunta: [Exemplo 1]`**
    - **`Resposta: [Resposta do Exemplo 1]`**
    - **`Pergunta: [Exemplo 2]`**
    - **`Resposta: [Resposta do Exemplo 2]`**
    - **`Pergunta: [Sua pergunta real]`**
    - **`Resposta:`**

<aside>
📌 **RESUMO**:

Duas técnicas fundamentais para melhorar as respostas de um modelo de linguagem são o **Zero-Shot** e o **Few-Shot Prompting**. O **Zero-Shot** é fazer uma pergunta diretamente, sem exemplos, e é eficaz para consultas simples. Já o **Few-Shot** envolve fornecer um ou mais exemplos antes da pergunta real, servindo como um guia para que o modelo entenda o formato, o estilo e o tipo de raciocínio esperado na resposta. Esta última técnica é poderosa para aumentar a precisão em tarefas complexas, "alinhando" o modelo com a lógica que se deseja que ele siga. A escolha entre uma e outra depende da complexidade da tarefa e da confiabilidade do modelo que se está usando.

</aside>

---

### Aplicações Práticas do Few-Shot Prompting

### Lembretes

- Few-Shot Prompting
- Generalização
- Análise de Sentimentos
- Tradução
- Padrão de Resposta

### Anotações

**Conceito Revisado: Few-Shot Prompting**

- **Definição:** Técnica que fornece **poucos exemplos** (shots) no prompt para "ensinar" o modelo a realizar uma tarefa específica.
- **Objetivo:** Guiar o modelo a entender o **formato**, o **estilo** e o **tipo de raciocínio** desejado na resposta, alinhando-o com a intenção do usuário.

**Aplicações em Diferentes Áreas:**

**1. Matemática e Lógica:**

- **Exemplo:**
    - **`Pergunta: O Rogério tem 5 bolas... Resposta: Ele tem 11 bolas.`**
    - **`Pergunta: Havia 23 maçãs... Resposta:`**
- **Função:** Os exemplos direcionam o modelo a **quebrar o problema em etapas** e realizar os cálculos sequencialmente, melhorando a precisão.

**2. Análise de Sentimentos:**

- **Exemplo:**
    - **`"Esse filme foi terrível" - Negativo.`**
    - **`"Esse é o meu filme favorito" - Positivo.`**
- **Função:** Os exemplos definem as **categorias** (Positivo/Negativo) e ensinam o modelo a **interpretar a nuance** da linguagem para classificar novos textos automaticamente.

**3. Tradução de Idiomas:**

- **Exemplo:**
    - **`Inglês: Hello... Francês: Bonjour...`**
    - **`Inglês: I am learning... Francês: J'apprends...`**
- **Função:** Os exemplos estabelecem o **par de idiomas** e o **formato** da tradução (**`Inglês: [texto] Francês: [tradução]`**), permitindo que o modelo generalize e traduza novas frases seguindo o mesmo padrão.

**Características Observadas:**

- **Consistência:** O modelo tende a seguir **rigorosamente o padrão** demonstrado nos exemplos (ex: usar ou não pontuação, manter a mesma estrutura).
- **Generalização:** Com poucos exemplos, o modelo é capaz de aplicar a lógica aprendida para **novas instâncias** da mesma tarefa.
- **Flexibilidade:** A técnica é **adaptável** a diversas áreas do conhecimento, desde matemática até processamento de linguagem natural.

<aside>
📌 **RESUMO**:

O **Few-Shot Prompting** é uma técnica versátil e poderosa para orientar modelos de linguagem. Fornecendo alguns exemplos específicos, é possível "ensinar" o modelo a executar tarefas complexas e variadas, como resolver problemas matemáticos, analisar sentimentos ou traduzir idiomas. Os exemplos servem como um **modelo em miniatura**, definindo o padrão de raciocínio e formatação que o modelo deve replicar em suas respostas. Essa técnica é fundamental para extrair o máximo potencial de um LLM, garantindo respostas precisas e alinhadas com o objetivo desejado, mesmo em contextos diferentes.

</aside>

---

### Chain of Thought (CoT): Aprimorando o Few-Shot Prompting

### Lembretes

- Chain of Thought (CoT)
- Few-Shot Prompting
- Raciocínio Passo a Passo
- Resolução de Problemas
- Precisão

### Anotações

**O Problema com o Few-Shot Básico:**

- Fornecer apenas a resposta final **não ensina o processo** de raciocínio ao modelo.
- Isso pode levar a erros em problemas complexos, onde o modelo "chuta" a resposta sem entender a lógica.

**A Solução: Chain of Thought (CoT) Prompting:**

- **O que é:** Uma técnica de few-shot prompting onde os exemplos **incluem o raciocínio passo a passo** que leva à resposta final.
- **Objetivo:** "Ensinar" o modelo a **simular um processo de pensamento**, quebrando um problema complexo em subetapas mais simples antes de dar a resposta.
- **Como funciona:** No prompt, cada exemplo mostra não só a pergunta e a resposta, mas **também a explicação lógica** ("o porquê") que conecta uma à outra.

**Exemplo Prático (Comparação):**

- **Few-Shot Básico (Menos Eficaz):**
    - **`P: O Rogério tem 5 bolas... R: Ele tem 11 bolas.`**
- **Few-Shot com Chain of Thought (Mais Eficaz):**
    - **`P: O Rogério tem 5 bolas... R: Ele inicialmente tinha 5. Comprou 2 caixas de 3 bolas (2*3=6). Portanto, agora tem 5 + 6 = 11 bolas.`**

**Resultado e Origem:**

- **Resultado:** Modelos que recebem exemplos com CoT **reproduzem o mesmo raciocínio** para novas perguntas, resultando em uma precisão muito maior.
- **Origem:** Técnica formalizada em um artigo do **Google Research/DeepMind**. Eles demonstraram que o CoT eleva significativamente o desempenho de LLMs em tarefas que requerem raciocínio lógico, matemático ou comum.

<aside>
📌 **RESUMO**:

- O **Chain of Thought** não é uma técnica nova, mas um **aprimoramento poderoso** do Few-Shot Prompting.
- Ele é extremamente eficaz porque força o modelo a **dedicar capacidade de processamento** para entender a jornada lógica (o "pensar"), e não apenas o destino final (a resposta).
- Essa técnica combina dois princípios fundamentais: **dividir tarefas complexas** e **fornecer clareza** através de exemplos.
</aside>

---

### Aplicação Prática: Few-Shot + Chain of Thought para um Problema Complexo

### Lembretes

- Few-Shot Prompting
- Chain of Thought (CoT)
- Padrão de Resposta
- Automatização
- Aplicação Prática

### Anotações

**Objetivo do Exemplo:**

- Demonstrar o poder combinado do **Few-Shot Prompting** com o **Chain of Thought** para guiar um modelo na resolução de um problema complexo e com regras específicas (cálculo de imposto).

**Estrutura do Prompt (O "Como"):**

1. **Definição Clara da Tarefa:** Explicitar precisamente o que deve ser feito (somar valores >40k, calcular 30%).
2. **Fornecimento de um Exemplo Simples (Few-Shot):**
    - Inclui uma **pergunta-teste** com uma lista pequena de valores.
    - Fornece uma **resposta modelo** que detalha **cada etapa** do raciocínio (Chain of Thought):
        - Contagem de valores elegíveis.
        - Listagem dos valores.
        - Cálculo da soma.
        - Cálculo da porcentagem.
3. **Apresentação do Problema Real:** A mesma pergunta é repetida, mas com a **lista completa de dados reais**.

**Resultado e Eficácia:**

- O modelo **reproduziu perfeitamente** o padrão estabelecido no exemplo.
- Ele seguiu **exatamente a mesma estrutura lógica**: contou (5 valores), listou (R$52k, R$103k...), somou (R$435k) e calculou a porcentagem (30% de R$435k = R$130.500).
- A resposta final foi **correta e formatada** de forma idêntica à do exemplo fornecido.

**Conclusões e Lições Aprendidas:**

1. **Poder da Combinação:** Few-Shot + CoT é extremamente eficaz para **ensinar tarefas complexas** com regras específicas.
2. **Reprodutibilidade:** O modelo é capaz de aprender e **replicar um padrão** de resposta de forma consistente.
3. **Aplicabilidade:** Esta técnica é útil para **automatizar** a geração de relatórios, análises de dados e qualquer tarefa que siga uma estrutura repetitiva.
4. **Limitação Consciente:** LLMs **não são ferramentas de cálculo ideais**. O exemplo serviu para ilustrar a técnica, mas para matemática pesada, planilhas (Excel/Sheets) ou código são mais adequados e confiáveis. A técnica é mais valiosa para **texto, formatação e lógica de negócio**.

<aside>
📌 **RESUMO**:

**O Few-Shot Prompting** (fornecer exemplos) com **Chain of Thought** (exigir um raciocínio passo a passo) pode ser usada para "treinar" um modelo a resolver um problema complexo de forma estruturada e reproduzível. A técnica mostrou-se poderosa para ensinar um padrão específico de resposta, tornando-a ideal para automatizar tarefas que envolvem análise e relatório. No entanto, é crucial entender as limitações dos LLMs e aplicar a técnica em contextos onde seu uso é mais apropriado, como na geração e formatação de texto seguindo uma lógica definida.

</aside>

---

### Least-to-Most Prompting: Dividindo Problemas Complexos

### Lembretes

- Least-to-Most Prompting
- Decomposição de Problemas
- Raciocínio (Reasoning)
- Custo Computacional (Tokens)
- Acuracia

### Anotações

**O Problema:**

- Modelos de linguagem (especialmente os mais antigos) tinham **dificuldade em tarefas de raciocínio lógico** complexo quando a pergunta era feita de uma só vez (Zero-Shot).

**A Solução: Least-to-Most Prompting**

- **O que é:** Técnica desenvolvida pela Google Research que consiste em **decompor automaticamente** um problema complexo em **subproblemas menores e sequenciais**.
- **Como Funciona (Programaticamente):**
    1. O modelo é instruído a **gerar os próprios subproblemas** necessários para resolver a questão principal.
    2. Ele **resolve cada subproblema** individualmente.
    3. Por fim, usa as **respostas dos subproblemas** para chegar à resposta final do problema original.
- **Exemplo (Toboágua):**
    - **Problema Original:** "Quantas vezes Amy pode escorregar em 15 minutos?"
    - **Subproblema Gerado:** "Quanto tempo dura cada viagem (subir + descer)?"
    - **Resposta do Subproblema:** 4 + 1 = 5 minutos.
    - **Resposta Final:** 15 min / 5 min por viagem = **3 vezes**.

**Resultados e Implicações:**

- **Eficácia:** Em modelos como o GPT-3, a técnica elevou a **acuracia em problemas de raciocínio de ~16% para ~99%**.
- **Custo:** A técnica é **mais custosa** (em termos de tokens usados na API), pois requer múltiplas interações ("idas e vindas") com o modelo para gerar e resolver cada subproblema.
- **Contexto:** Todo o histórico da conversa (subproblemas + respostas) é enviado de volta ao modelo para manter o contexto, consumindo mais tokens.

**Conceito Central:**

- O nome "Least-to-Most" (Do Menor para o Maior) captura a essência da técnica: começar com os **componentes mais simples** (subproblemas) para, então, construir a solução para o **problema maior**.

<aside>
📌 **RESUMO**:

O **Least-to-Most Prompting** é uma técnica poderosa para superar as limitações de raciocínio dos LLMs. Ela automatiza o princípio de "dividir tarefas complexas" instruindo o próprio modelo a quebrar um problema grande em subproblemas menores, resolvê-los e depois integrar as soluções. Embora extremamente eficaz para aumentar drasticamente a precisão em lógica e matemática, seu uso vem com um **trade-off de custo**, já que consome significativamente mais tokens devido à necessidade de múltiplas interações para gerar e resolver cada etapa. É uma técnica voltada principalmente para uso **programático via API** em casos onde a precisão é crítica.

</aside>

---

### Chain-of-Verification (CoVe): Verificando Fatos com o Próprio Modelo

### Lembretes

- Chain-of-Verification (CoVe)
- Verificação de Fatos
- Precisão Factual
- Alucinação
- Custo Computacional

### Anotações

**O Problema:**

- Modelos de linguagem podem gerar **informações incorretas** ou "alucinações" (hallucinations), especialmente em questões factuais (ex: datas, locais de nascimento, eventos históricos).

**A Solução: Chain-of-Verification (CoVe)**

- **O que é:** Uma técnica desenvolvida pela Meta que faz o modelo **verificar suas próprias respostas** através de um processo estruturado de 4 etapas.
- **Objetivo:** Reduzir erros factuais e aumentar a confiabilidade das informações geradas.

**As 4 Etapas do CoVe:**

1. **Resposta Inicial:** O modelo gera uma primeira resposta para o prompt (ex: "Cite políticos nascidos em Nova Iorque" → Hillary Clinton, Donald Trump, etc.).
2. **Geração de Perguntas de Verificação:** O modelo **analisa sua própria resposta inicial** e gera perguntas específicas para verificar cada fato listado (ex: "Onde Hillary Clinton nasceu?", "Onde Donald Trump nasceu?").
3. **Execução das Verificações:** O modelo **responde a cada uma das perguntas de verificação** que ele mesmo gerou, consultando seu conhecimento interno.
4. **Resposta Final Verificada:** O modelo **compara as respostas de verificação** com a resposta inicial, **corrige os erros** e produz uma resposta final mais precisa (ex: Remove Hillary Clinton da lista e adiciona outros políticos que realmente nasceram em NY).

**Vantagens e Desvantagens:**

- **Vantagem:** Aumenta significativamente a **precisão factual** das respostas, combatendo a alucinação.
- **Desvantagem (Trade-off):** Assim como o Least-to-Most, é uma técnica **muito custosa**. Requer múltiplas interações (chamadas à API), consumindo muitos tokens e tornando-a **impraticável para uso manual**.
- **Uso Prático:** É uma técnica projetada para ser implementada de forma **programática**, automatizando as 4 etapas via código e API.

<aside>
📌 **RESUMO**:

O **Chain-of-Verification (CoVe)** é uma técnica sofisticada que transforma o modelo em seu próprio **verificador de fatos**. Através de um processo de 4 etapas, ele é forçado a questionar e validar suas respostas iniciais, levando a um resultado final muito mais confiável. Sua principal força é **reduzir drasticamente erros factuais**. No entanto, esse ganho em precisão vem com um alto **custo computacional** (token), tornando-a uma ferramenta voltada para aplicações **automatizadas e programáticas** onde a exatidão das informações é crítica, e não para o uso casual em um chat.

</aside>

---

### Self-Consistency: Melhorando a Precisão com Repetição e Consenso

### Lembretes

- Self-Consistency (Autoconsistência)
- Chain of Thought (CoT)
- Consenso
- Precisão Estatística
- Automação (API)

### Anotações

**O Princípio:**

- **Hipótese Central:** Se um modelo de linguagem é questionado **várias vezes** sobre o mesmo problema, a **resposta mais frequente** (o consenso) tem uma **alta probabilidade de ser a correta**.
- **Base Lógica:** Assume-se que o modelo acerta na maioria das vezes, e os erros são aleatórios e não consistentes.

**Como Funciona na Prática:**

1. **Repetição:** O mesmo prompt (usando Chain of Thought) é enviado para o modelo **múltiplas vezes** (ex: 4, 10 ou 15 vezes).
2. **Coleta de Respostas:** Todas as respostas geradas são coletadas em uma lista.
3. **Análise de Consenso:** Identifica-se qual resposta **aparece com mais frequência** (moda estatística).
4. **Resposta Final:** A resposta de consenso é considerada a **resposta final e mais confiável**.

**Implementação Técnica (Código):**

- A técnica é implementada de forma **programática**, usando um loop (**`for`**) para fazer múltiplas chamadas à **API** do modelo (ex: OpenAI).
- O código extrai a parte numérica da resposta de cada iteração (ex: o valor após **`Resultado:`** ).
- Um parâmetro **`temperature`** > 0 (ex: 1) é usado para garantir **variação** nas respostas entre cada loop.
- No final, o código calcula estatisticamente a resposta mais comum.

**Vantagens e Considerações:**

- **Vantagem:** Aumenta significativamente a **confiabilidade** da resposta para problemas objetivos (ex: matemática, fatos).
- **Custo:** É uma técnica **custosa** (em tokens e tempo), pois requer múltiplas chamadas à API.
- **Aplicabilidade:** Ideal para ser usada de forma **automática em sistemas** onde a precisão é crítica, e não manualmente.
- **Limitação:** O código de exemplo precisa ser robusto para lidar com formatos de resposta inesperados do modelo.

<aside>
📌 **RESUMO**:

A **Self-Consistency** é uma técnica simples porém poderosa que aproveita o poder estatístico do **consenso**. Ao solicitar que o modelo resolva o mesmo problema diversas vezes e escolher a resposta mais frequente, a técnica mitiga erros aleatórios e produz um resultado final muito mais confiável. Ela é a evolução natural do Chain of Thought, adicionando uma camada de verificação estatística. Por ser computacionalmente intensiva e custosa, seu uso é mais indicado em **aplicações automatizadas via API** para tarefas onde a exatidão é não-negotiable, tornando-a uma ferramenta valiosa para desenvolvedores que integram LLMs em sistemas críticos.

</aside>

---

### Aplicando técnicas de Prompt no cotidiano

### Lembretes

- Prompts

### Anotações

---

### **1. Prompt para Organizar Rotina de Estudos na Alura (Chain of Thought + Few-Shot)**

**Técnicas Usadas:** Chain of Thought (para explicar o raciocínio) + Few-Shot (com exemplos de estilo).

**Prompt:**

```
Atue como um consultor especializado em planejamento de estudos e produtividade. Sua tarefa é me ajudar a criar uma rotina semanal de estudos para meus cursos na Alura.

Siga estes passos para construir minha rotina:

1.  **Coletar Informações:** Faça perguntas para entender:
    *   Minhas **áreas de interesse** (ex: Front-end, Data Science, UX).
    *   Meu **objetivo** (ex: aprender do zero, aprofundar conhecimento, preparar-se para entrevista).
    *   Minha **disponibilidade semanal** (quantas horas por dia e quais dias posso estudar).
    *   **Outras atividades** fixas que tenho (trabalho, academia, compromissos).
    *   Meu **estilo de aprendizado preferido** (ex: prefiro mais prática do que teoria, gosto de intercalar com exercícios).

2.  **Propor uma Estrutura:** Com base nas minhas respostas, crie uma rotina semanal detalhada que intercale diferentes modos de estudo, por exemplo:
    *   **Assistir a videoaulas** (conteúdo novo)
    *   **Prática em projetos** (colocar a mão na massa)
    *   **Resolução de exercícios** (fixar o conteúdo)
    *   **Revisão** (rever anotações ou flashcards)

3.  **Fornecer a Rotina:** Apresente a rotina em formato de tabela, com os dias da semana, o tipo de atividade e o tema/tópico a ser estudado. Seja específico e realista com o tempo.

Vamos começar? Por favor, comece me fazendo as perguntas do Passo 1.
```

---

### **2. Prompt para Simular uma Entrevista Técnica (Persona + Few-Shot)**

**Técnicas Usadas:** Persona (definir um papel) + Few-Shot (com exemplo de pergunta/resposta).

**Prompt:**

```
Você será um entrevistador técnico sênior para a vaga de [INSIRA A VAGA AQUI, ex: Desenvolvedor(a) Front-end React]. Sua persona é séria, profissional, mas justa. Você deve conduzir uma entrevista simulada comigo.

**Instruções:**
1.  **Estruture a entrevista em fases:** Comece com perguntas conceituais, depois parta para perguntas técnicas específicas e, por fim, proponha um desafio prático (um pequeno problema de código ou lógica).
2.  **Faça uma pergunta de cada vez.** Espere pela minha resposta antes de prosseguir.
3.  **Após cada uma das minhas respostas,** forneça feedback imediato: diga o que estava correto, aponte erros ou omissões e, se necessário, forneça a resposta ideal.
4.  **Use os seguintes tópicos técnicos como guia:** [LISTE TÓPICOS ESPECÍFICOS, ex: React Hooks (useState, useEffect), Componentização, CSS-in-JS, Gerenciamento de Estado Global, Ciclo de Vida de um Componente].

**Exemplo de como você deve agir:**
*   **Você (Entrevistador):** "Explique, em suas palavras, o que é o Virtual DOM no React e que vantagem ele oferece."
*   **Eu (Candidato):** [Minha resposta]
*   **Você (Entrevistador):** "Sua resposta cobriu o básico. Você acertou ao mencionar a performance, mas esqueceu de citar que o Virtual DOM permite uma reconciliação mais eficiente... A resposta mais completa seria: [forneça a resposta ideal]."

**Quando eu disser "Estou pronto(a)", comece a entrevista com a primeira pergunta.**
```

---

### **3. Prompt para Gerar um Quiz de Revisão (Few-Shot + Formato Específico)**

**Técnicas Usadas:** Few-Shot (com exemplo do formato) + Instrução clara para formatação.

**Prompt:**

```
Você é um assistente pedagógico. Com base no tópico de estudo que eu fornecer, sua tarefa é criar um quiz de 5 perguntas e respostas para me ajudar na revisão e fixação do conteúdo.

**Regras:**
*   As perguntas devem variar entre múltipla escolha (com 4 opções) e verdadeiro/falso.
*   **O formato de saída deve ser exatamente o seguinte para cada pergunta:**
    ```
    Pergunta [Número]:
    [Texto da pergunta]
    a) [Opção A]
    b) [Opção B]
    c) [Opção C]
    d) [Opção D]
    (ou) Verdadeiro ( ) Falso ( ) // use apenas se for V/F

    Resposta: [Letra da resposta correta ou "Verdadeiro"/"Falso"]
    Explicação: [Uma explicação concisa de por que essa é a resposta correta]
    ---
    ```
*   **Após gerar o quiz, espere eu responder.** Só então você deve me dar o feedback, dizendo quantas eu acertei e revisando as que eu errei.

**Exemplo para o tópico "JavaScript - Array.map()":**

Pergunta 1:
Qual é a finalidade principal do método `.map()` em JavaScript?
a) Iterar sobre um array para filtrar elementos específicos.
b) Modificar o array original, adicionando um novo elemento.
c) Criar um novo array com os resultados da aplicação de uma função a cada elemento.
d) Ordenar os elementos de um array em ordem alfabética.

Resposta: c
Explicação: O método `.map()` não modifica o array original; ele cria um novo array populado com os resultados de uma função chamada para cada elemento do array original.
---
**Agora, vamos começar. O tópico é: [INSIRA SEU TÓPICO DE ESTUDO AQUI, ex: "Propriedades CSS Flexbox"]**
```

**Dica para Refinar:** Teste os prompts, veja as respostas e ajuste as instruções para ficarem ainda mais claras. Por exemplo, se o quiz gerar perguntas muito fáceis, adicione ao prompt: "Crie perguntas desafiadoras que vão além da memorização, testando a aplicação prática do conceito."

Bons estudos e boa prática

---

### Engenharia de Prompt - Recap

### Lembretes

- Modelos de Linguagem (LLMs)
- Engenharia de Prompt
- Chain of Thought (CoT)
- Few-Shot / Zero-Shot
- Tokens & Temperatura

### Anotações

**Fundamentos dos Modelos de Linguagem**

- **Funcionamento:** LLMs preveem a próxima palavra (token) com base em probabilidades aprendidas de um vasto conjunto de dados.
- **Word Embeddings:** Palavras são representadas como vetores numéricos que capturam relações de significado e proximidade semântica.
- **Temperatura:** Parâmetro que controla a aleatoriedade das previsões. Baixa = previsível; Alta = criativa (mas possivelmente incoerente).
- **Tokens:** Unidades de processamento (podem ser palavras completas ou pedaços de palavras). O custo de uso de APIs é calculado por token.

**Princípios para um Prompt Ideal**

- **Clareza e Especificidade:** Seja extremamente claro, como se estivesse instruindo um estagiário. Defina formato, tom, público-alvo e objetivo.
- **Dividir Tarefas Complexas:** Quebre problemas grandes em sub-tarefas menores e mais gerenciáveis para guiar o raciocínio do modelo.

**Técnicas Principais de Prompting**

- **Zero-Shot Prompting:** Fazer uma pergunta diretamente, sem exemplos. Ideal para tarefas simples.
- **Few-Shot Prompting:** Fornecer exemplos no prompt para "ensinar" o modelo o formato e estilo desejado da resposta.
- **Chain of Thought (CoT):** A técnica mais poderosa. Incluir no prompt exemplos que mostrem o **raciocínio passo a passo** para chegar à resposta, não apenas a resposta final. Isso aumenta a precisão em tarefas complexas.

**Técnicas Avançadas (Geralmente Programáticas)**

- **Least-to-Most Prompting:** Instruir o modelo a decompor automaticamente um problema complexo em subproblemas, resolvê-los e depois integrar as soluções.
- **Chain-of-Verification (CoVe):** Fazer o modelo verificar **seus próprios fatos** gerando e respondendo perguntas sobre sua resposta inicial.
- **Self-Consistency:** Fazer a **mesma pergunta complexa múltiplas vezes** e escolher a resposta que mais se repete (consenso), aumentando a confiabilidade estatística.

<aside>
📌 **RESUMO**:

Percorremos **conceitos fundamentais** de como os LLMs funcionam (previsão de tokens, embeddings, temperatura) até as **técnicas mais avançadas** de Engenharia de Prompt. O grande segredo para prompts eficazes é a **clareza e a estrutura**. A técnica mais impactante aprendida foi o **Chain of Thought (Few-Shot + CoT)**, que ensina o modelo a raciocinar explicitamente. Técnicas como Self-Consistency e CoVe oferecem ganhos adicionais de precisão para sistemas automatizados via API, mas com um trade-off de custo. Agora você está equipado para se comunicar de forma mais eficaz e obter melhores resultados dos modelos de linguagem, seja no dia a dia ou em aplicações profissionais.

</aside>

---