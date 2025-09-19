### **Introdução ao HTML: Estrutura Básica e Primeiros Passos**

### Lembretes

- HTML
- Linguagem de marcação
- Tags
- Estrutura básica
- VS Code
- Documentação

### Anotações

### **O que é HTML?**

- Significa **Hyper Text Markup Language** (Linguagem de Marcação de Hipertexto).
- **Não é uma linguagem de programação**, e sim de marcação.
- Usado para **estruturar páginas web** e rotular conteúdos (títulos, parágrafos, links, etc.).

### **Estrutura Básica de um Documento HTML**

```html
<!DOCTYPE html>
<html>
<head>
<title>Page Title</title>
</head>
<body>

<h1>My First Heading</h1>
<p>My first paragraph.</p>

</body>
</html>
```

### **Função das Principais Tags**

- `<!DOCTYPE html>`: Define a versão do HTML (HTML5).
- `<html>`: Elemento raiz que envolve todo o documento.
- `<head>`: Contém **meta-informações** (ex.: título, codificação, links para CSS/JS).
- `<title>`: Define o título da aba do navegador.
- `<body>`: Contém o conteúdo visível da página (textos, imagens, links).

### **Dicas Práticas**

- Use o **VS Code** para escrever e editar código.
- Sempre **feche as tags** com `</tag>` (exceto tags auto-fechadas).
- Use **indentação** (Tab) para organizar visualmente o código.
- Salve o arquivo com extensão **.html** e abra no navegador para testar.

### **Documentação Recomendada**

- Site: **W3Schools** (disponível em português).
- URL: `w3s html intro` (pesquisar no Google).

<aside>
📌 **RESUMO**:

HTML é uma **linguagem de marcação** usada para estruturar páginas web. Sua estrutura básica inclui tags como `<!DOCTYPE html>`, `<html>`, `<head>`, `<title>` e `<body>`. A tag `<head>` contém informações não visíveis (como o título da aba), enquanto o `<body>` abriga o conteúdo principal. Para aprender HTML, é essencial praticar e consultar documentações como a W3Schools. Ferramentas como o VS Code facilitam a escrita e organização do código, que deve ser salvo com extensão .html e aberto em um navegador para visualização.

</aside>

---

### **Estruturando o Corpo HTML: Títulos, Parágrafos e Imagens**

### Lembretes

- `<body>`
- `<h1>` a `<h6>`
- `<p>`
- `<img>`
- `src`
- `alt`
- Acessibilidade

### Anotações

### **Tag `<body>`**

- Define o **corpo do documento**.
- Contém **todo o conteúdo visível** da página (títulos, parágrafos, imagens, links, etc.).
- Deve ser colocada **após** a tag `</head>` e **dentro** de `<html>`.

### **Tags de Título (`<h1>` a `<h6>`)**

- Usadas para **cabeçalhos** (títulos e subtítulos).
- `<h1>` é o **maior e mais importante** (usado apenas uma vez por página).
- `<h2>` a `<h6>` são subtítulos, diminuindo de tamanho conforme o número aumenta.
- Exemplo: html
    
    ```html
    <h1>Isso é um título</h1>
    <h2>Isso é um subtítulo</h2>
    ```
    

### **Tag de Parágrafo (`<p>`)**

- Define um **parágrafo de texto**.
- O texto sem tags é exibido, mas **não é semanticamente correto**.
- Exemplo: html
    
    ```
    <p>Isso é um parágrafo</p>
    ```
    

### **Tag de Imagem (`<img>`)**

- **Não possui tag de fechamento**.
- Requer o atributo `src` para especificar o **caminho da imagem**.
- Exemplo: html
    
    ```html
    <img src="html.png">
    ```
    

### **Atributos Importantes para Imagens**

- `src`: Caminho da imagem (ex.: `"html.png"` se estiver na mesma pasta).
- `alt`: **Texto alternativo** para acessibilidade (descreve a imagem para leitores de tela e aparece se a imagem não carregar).
    
    html
    
    ```html
    <img src="html.png" alt="Logo do HTML5">
    ```
    

### **Boas Práticas e Acessibilidade**

- Sempre use **tags semânticas** (`<h1>`, `<p>`, etc.) para melhorar a acessibilidade.
- Leitores de tela dependem dessas tags para navegação.
- Imagens **devem sempre ter o atributo `alt`** para descrever seu conteúdo.

### **Dica de Organização no VS Code**

- Use **indentação (Tab)** para manter o código organizado.
- Salve o arquivo com frequência (`Ctrl + S`).

<aside>
📌 **RESUMO**:

O corpo da página HTML é definido pela tag `<body>`, onde inserimos todo o conteúdo visível, como títulos (`<h1>` a `<h6>`), parágrafos (`<p>`) e imagens (`<img>`). As tags de título devem ser usadas em ordem hierárquica, e parágrafos devem sempre estar envoltos em `<p>`. Para imagens, usamos a tag `<img>` com os atributos `src` (caminho da imagem) e `alt` (texto alternativo para acessibilidade). Essas práticas garantem que a página seja bem estruturada e acessível para todos os usuários, incluindo aqueles que usam leitores de tela. O próximo passo é continuar praticando e explorando mais elementos HTML!

</aside>

---

### **Validando HTML: DOCTYPE, Modo Quirks e Live Server**

### Lembretes

- `<!DOCTYPE html>`
- Modo Quirks
- Modo Standards
- Live Server
- Inspecionar Elementos
- Extensões VS Code

### Anotações

### **Importância do `<!DOCTYPE html>`**

- Define a **versão do HTML** (HTML5) para o navegador.
- Garante que a página seja renderizada no **Modo Standards** (moderno).
- Sem ele, o navegador entra no **Modo Quirks** (compatibilidade com versões antigas).

### **O que é o Modo Quirks?**

- Modo de renderização para **páginas antigas** (era Netscape/Internet Explorer).
- Pode causar **layout inesperado** ou inconsistente.
- Ativado quando falta `<!DOCTYPE html>`.

### **Como Verificar Problemas?**

- Abra **Ferramentas do Desenvolvedor** (Inspecionar → Botão direito).
- Verifique a aba **"Issues"** para alertas como:
    
    `"Page layout may be unexpected due to Quirks Mode"`.
    

### **Solução**

- Sempre inclua `<!DOCTYPE html>` no início do arquivo HTML.
- Exemplo:
    
    ```html
    <!DOCTYPE html>
    <html><!-- resto do código --></html>
    ```
    

### **Live Server (Extensão VS Code)**

- **Atualização automática** da página no navegador ao salvar o código.
- Como instalar:
    1. Acesse **Extensions** (Ctrl+Shift+X).
    2. Busque por **"Live Server"**.
    3. Instale e habilite a extensão.
- Como usar:
    - Clique em **"Go Live"** (barra inferior do VS Code).
    - A página abrirá automaticamente no navegador.

### **Vantagens do Live Server**

- Elimina a necessidade de **atualizar manualmente** a página.
- Ideal para **testes rápidos** durante o desenvolvimento.

### **Dica Importante**

- Use **extensões** para melhorar produtividade (ex.: syntax highlight, emmet).

<aside>
📌 **RESUMO**:

O `<!DOCTYPE html>` é essencial para garantir que a página seja renderizada no **Modo Standards**, evitando problemas de layout do **Modo Quirks** (modo de compatibilidade antigo). Sem essa declaração, o navegador pode exibir alertas e comportamentos inesperados. Para agilizar o desenvolvimento, a extensão **Live Server** no VS Code permite atualizações automáticas da página no navegador sempre que o código é salvo, eliminando a necessidade de atualizações manuais. Essas práticas garantem um fluxo de trabalho mais eficiente e profissional.

</aside>

---

### Extensões Essenciais do VS Code para Produtividade

### Lembretes

- VS Code
- Extensões
- Produtividade
- Autocomplete
- Formatação
- Git
- Ícones

### Anotações

### **O que são extensões?**

- **Plugins** que adicionam funcionalidades ao VS Code.
- **Leves e personalizáveis** – adaptam o editor às necessidades do desenvolvedor.
- Instalação:
    - Pelo VS Code: `Ctrl+Shift+X` → buscar extensão → instalar.
    - Pelo **Marketplace online** do VS Code.

### **Extensões Recomendadas**

1. **ESLint**
    - Encontra e **corrige erros de sintaxe** automaticamente em JavaScript.
    - Personalizável com regras customizadas.
2. **Live Server**
    - **Atualiza a página automaticamente** no navegador ao salvar alterações.
    - Ideal para desenvolvimento front-end.
3. **Visual Studio IntelliCode**
    - **Autocomplete inteligente** com IA – prioriza código mais usado.
    - Suporte a múltiplas linguagens.
4. **GitLens**
    - **Histórico detalhado do Git** – mostra alterações, autores e comparações.
    - Melhora colaboração em equipe.
5. **VS Code Icons**
    - **Ícones para arquivos e pastas** – organiza visualmente o projeto.
    - Facilita identificação de tipos de arquivo.
6. **Beautify**
    - **Formata e indenta** código automaticamente (atalho: `Ctrl+B`).
    - Mantém o código organizado e legível.
7. **IntelliSense for CSS**
    - **Autocomplete para classes CSS** em arquivos HTML.
    - Evita erros de digitação.
8. **BookMarks**
    - **Marca trechos de código** favoritos para navegação rápida.
    - Útil para projetos grandes.
9. **Auto Import**
    - **Importa automaticamente** arquivos externos (ex.: em TypeScript).
    - Economiza tempo e evita esquecimentos.

<aside>
📌 **RESUMO**:

- Use extensões para **automatizar tarefas repetitivas**.
- Personalize o VS Code conforme seu **fluxo de trabalho**.
- Explore o **Marketplace** para descobrir novas ferramentas.
</aside>

---

### Estrutura Básica do HTML: Elementos Fundamentais

### Lembretes

- Estrutura HTML
- `<head>`
- `<body>`
- Metatags
- `<!DOCTYPE>`
- `lang`
- `charset`

### Anotações

### **Elementos da Estrutura Básica**

html

```html
<!DOCTYPE html>
<html lang="pt-br">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
</head>
<body>

</body>
</html>
```

### **Função de Cada Tag**

- `<!DOCTYPE html>`: Define o documento como **HTML5**.
- `<html lang="pt-br">`: Elemento raiz + idioma principal da página.
- `<head>`: Contém **metainformações** (não visíveis no navegador).
- `<meta charset="UTF-8">`: Define a **codificação de caracteres** (acentos, símbolos).
- `<meta name="viewport"...>`: Configura a página para **dispositivos móveis**.
- `<title>`: Título da aba do navegador.
- `<body>`: Contém todo o **conteúdo visível** (textos, imagens, links).

### **Importância das Metatags**

- `charset="UTF-8"`: Garante que caracteres especiais sejam exibidos corretamente.
- `viewport`: Responsividade – adapta o layout a diferentes telas.
- `lang="pt-br"`: Acessibilidade – ajuda leitores de tela e ferramentas de tradução.

### **Dica de Organização**

- Sempre use **indentação** (Tab) para manter o código legível.
- Feche todas as tags que exigem fechamento (ex.: `</html>`, `</head>`).

### **Artigo Recomendado**

- **Série Alura**: "O que é o HTML e suas tags?" (Parte 1: estrutura básica).
- Explica detalhadamente cada elemento e sua função.

<aside>
📌 **RESUMO**:

A estrutura básica do HTML é composta por tags essenciais como `<!DOCTYPE html>`, `<html>`, `<head>` e `<body>`. O `<head>` contém metainformações críticas, como codificação de caracteres (`charset="UTF-8"`) e configurações de viewport para responsividade. Já o `<body>` abriga todo o conteúdo visível da página. Manter essa estrutura organizada e semântica é fundamental para o funcionamento correto da página, além de melhorar a acessibilidade e a experiência do usuário. Para aprofundar, recomenda-se a série de artigos da Alura sobre HTML.

</aside>
### Do Design ao Código: Implementando um Portfólio a partir do Figma

### Lembretes

- Figma
- HTML/CSS
- Desenvolvimento Front-end
- UX/UI Design
- Implementação
- Portfolio
- Fluxo de trabalho

### Anotações

**Divisão de Papéis no Desenvolvimento:**

1. **Designer (UX/UI):** Responsável pela pesquisa, concepção visual e criação do layout (cores, fontes, espaçamento, elementos). Utiliza ferramentas como o **Figma**.
2. **Desenvolvedor Front-end:** Responsável por transformar o layout (design) em código funcional (**HTML, CSS, JavaScript**).

**O Papel do Figma:**

- Ferramenta essencial para colaboração entre design e desenvolvimento.
- Fornece o **layout pronto** e todas as **especificações** detalhadas para a implementação:
    - Cores exatas (valores HEX, RGB, etc.).
    - Fontes, tamanhos e estilos de texto.
    - Espaçamentos (padding, margin).
    - Dimensões (largura "W", altura "H") de elementos.
    - Assets (como imagens, ícones).

**Como Extrair Informações do Figma:**

1. Acesse o projeto via link (requer cadastro).
2. Selecione qualquer elemento na tela.
3. No painel lateral direito, use as abas:
    - **"Design"**: Mostra propriedades visuais do elemento (cor, tamanho, fonte, etc.).
    - **"Inspect" ("Inspecionar")**: Fornece valores prontos para uso em código (como valores CSS). É a aba mais útil para o desenvolvedor.

**Nosso Desafio (Como Desenvolvedores):**

- **Objetivo:** Transformar o design do Figma em uma página web funcional.
- **Tecnologias:** HTML (para a estrutura) + CSS (para a estilização).
- **Conteúdo da Página (Estrutura HTML inicial):**
    - **Bloco Esquerdo:**
        - Um título principal (`<h1>`) com texto em duas cores.
        - Um parágrafo (`<p>`) de subtítulo/apresentação.
        - Dois botões (`<a>` ou `<button>`) para "Instagram" e "Github".
    - **Blobo Direito:**
        - Uma imagem (`<img>`) representando a pessoa desenvolvedora.
- **Observação:** O conteúdo (texto, imagem) pode e deve ser personalizado para o seu próprio portfólio.

**Próximo Passo:**

- Iniciar a codificação da estrutura HTML baseada na análise do layout no Figma.

<aside>
📌 **RESUMO**:

O processo de criação de uma página web é colaborativo, envolvendo um designer (que cria o layout no Figma) e um desenvolvedor front-end (que o implementa em código). O Figma serve como a fonte única da verdade para o design, fornecendo todas as especificações detalhadas (cores, fontes, espaçamentos) através de suas abas "Design" e principalmente "Inspect". O desafio atual é assumir o papel do desenvolvedor: analisar o layout do portfólio no Figma, planejar a estrutura HTML (identificando títulos, parágrafos, botões e imagens) e começar a codificação, utilizando as informações extraídas da ferramenta para garantir fidelidade ao design original. O próximo passo é escrever o código HTML que dará estrutura à página.

</aside>

---

### Estruturando um Documento HTML: Do Figma ao Código Semântico

### Lembretes

- Estrutura HTML
- Emmet
- Tags Semânticas
- Meta Tags
- Viewport
- UTF-8
- Figma

### Anotações

**Inicialização Rápida com Emmet:**

- No VSCode, digitar `!` + `Enter` gera automaticamente a estrutura básica de um documento HTML5.
- Essa estrutura inclui:
    - `<!DOCTYPE html>`
    - `<html lang="en">`
    - `<head>` com meta tags essenciais
    - `<body>`

**Ajustes Importantes na Estrutura Base:**

1. **Idioma:** Alterar `lang="en"` para `lang="pt-br"` para definir o português do Brasil como idioma principal, garantindo correta interpretação de caracteres especiais.
2. **Meta Tag `charset`:** `<meta charset="UTF-8">` é crucial para garantir que todos os caracteres e acentos sejam exibidos corretamente em qualquer navegador.
3. **Meta Tag `viewport`:** `<meta name="viewport" content="width=device-width, initial-scale=1.0">` é essencial para o design responsivo. Ela faz a página se adaptar à largura do dispositivo (celular, tablet, etc.) e define a escala inicial para 1.0.
4. **Título:** Alterar `<title>Document</title>` para um título descritivo da página (ex.: `<title>Portfolio</title>`).

**Estrutura Semântica do Corpo (`<body>`):**

A análise do layout no Figma deve guiar a estrutura semântica do HTML:

- **`<header>`:** Representa o cabeçalho da página (geralmente contém logotipo e menu de navegação).
- **`<main>`:** Representa o conteúdo principal único da página. É onde o conteúdo central do layout do Figma será colocado (títulos, texto, botões, imagem).
- **`<footer>`:** Representa o rodapé da página (geralmente contém informações de contato, links secundários, etc.).

<aside>
📌 **RESUMO**:

A fase inicial de codificação envolve criar a estrutura base do HTML5, facilmente gerada com o atalho do Emmet (`!`). É fundamental fazer ajustes cruciais nessa estrutura, como definir o idioma correto (`pt-br`), garantir a codificação de caracteres (UTF-8) e configurar a viewport para responsividade. A análise do design no Figma deve ser traduzida em uma estrutura semântica dentro da tag `<body>`, utilizando `<header>`, `<main>` e `<footer>` para organizar logicamente o conteúdo. 

</aside>

---

### Implementando a Estrutura HTML do Portfólio com Base no Figma

### Lembretes

- HTML Semântico
- Tag `<strong>`
- Tag `<a>` (âncora)
- Atributo `href`
- Tag `<img>`
- Atributos `src` e `alt`
- Estrutura Básica

### Anotações

**Estratégia de Implementação:**

- Seguir a ordem visual do layout (esquerda para direita, cima para baixo).
- Analisar o Figma para identificar os elementos e sua hierarquia.

**Elementos Implementados dentro de `<main>`:**

1. **Título Principal (`<h1>`):**
    - Copiado diretamente do Figma.
    - Parte do texto foi envolta pela tag `<strong>` para dar ênfase semântica (destaque no conteúdo, não na forma visual ainda).
    - Exemplo: `<h1>Eleve seu negócio digital a outro nível <strong>com um Front-end de qualidade!</strong></h1>`
2. **Parágrafo de Apresentação (`<p>`):**
    - Texto de descrição copiado do Figma.
    - Exemplo: `<p>Olá! Sou Joana Santos... Vamos conversar?</p>`
3. **Links de Ação (Âncoras - `<a>`):**
    - **Semântica:** Usamos a tag `<a>` (âncora) em vez de `<button>` porque a função é **navegar** para outra página (Instagram, GitHub).
    - **Atributo `href`:** Essencial para definir o URL de destino do link.
        - Exemplo: `href="https://instagram.com/rafaballerini"`
    - **Conteúdo:** O texto entre as tags (`Instagram`, `Github`) é o que aparece para o usuário.
    - Visualmente, por padrão, os links aparecem sublinhados e azuis.
4. **Imagem (`<img>`):**
    - **Fonte (`src`):** A imagem foi exportada do Figma e salva na pasta do projeto. O atributo `src` aponta para o nome do arquivo (`imagem.png`).
    - **Texto Alternativo (`alt`):** Descreve a imagem para acessibilidade e caso ela não carregue. Exemplo: `alt="Foto da Joana Santos programando"`.

**Observações Importantes:**

- A **aparência visual** (cores, fontes, posicionamento) ainda não está como o Figma. Isso será resolvido com **CSS**.
- A tag `<strong>` tem significado **semântico** (importância), não visual. O estilo (cor diferente) será aplicado depois.
- Os links (`<a>`) têm o comportamento correto (redirecionam), mas ainda não parecem botões visualmente.
- A imagem foi inserida com sucesso, mas seu tamanho e posição ainda não estão corretos.

<aside>
📌 **RESUMO**:

A implementação do HTML focou em traduzir os elementos visuais do layout do Figma em código semântico. O conteúdo principal (`<main>`) foi preenchido com: um título (`<h1>`) contendo uma parte destacada semanticamente com `<strong>`; um parágrafo de apresentação (`<p>`); dois links de ação (`<a>`) com seus respectivos URLs no atributo `href`; e uma imagem (`<img>`) com `src` e `alt` definidos. É crucial entender que, nesta fase, a página só possui estrutura e conteúdo – a estilização (cores, fontes, posicionamento) que a faz se parecer com o design do Figma será a próxima etapa, a ser realizada com CSS. A escolha das tags (`<a>` em vez de `<button>`, `<strong>`) foi guiada pela semântica correta de cada elemento.

</aside>
### **Introdução ao CSS: Propósito e Importância**

### Lembretes

- CSS
- HTML
- Semântica
- Estilização
- W3Schools
- Folha de Estilo
- Arquivo .css
- Visual
- Design
- Figma

### Anotações

**Problema Inicial:**

- O HTML está pronto e semântico, mas falta a parte visual (cores, formatos, posicionamento).
- A estilização é crucial para a aparência moderna e profissional de um site.

**O que é CSS?**

- **Significado:** Cascading Style Sheets ou Folhas de Estilo em Cascata.
- **Função:** Linguagem de **estilização** (não de programação) que descreve **como os elementos HTML são exibidos**.
- **Controle:** Gerencia cor, tamanho, fonte, posicionamento e outros detalhes visuais.

**Relação HTML + CSS:**

- **HTML:** Estrutura e conteúdo (o "o quê").
- **CSS:** Apresentação e estilo visual (o "como").
- São linguagens separadas e especializadas.

**Por que usar CSS? (Vantagens)**

1. **Separação de preocupações:** Isola a estilização da marcação.
2. **Controle Centralizado:** Um único arquivo `.css` pode controlar o layout de **múltiplas páginas**.
3. **Manutenção:** Alterar o estilo de um site inteiro fica mais fácil, modificando apenas um arquivo.
4. **Histórico:** Resolveu um "pesadelo" de quando a estilização era feita dentro do HTML com tags como `<font>`, que tornavam o código confuso e grande.

**Como Consultar e Aprender?**

- **Documentação:** Fonte confiável e objetiva para consulta (ex: W3Schools).
- **Aprendizado Gradativo:** Não é necessário decorar todas as propriedades de uma vez. Foca-se nas principais.

<aside>
📌 **RESUMO**:

O diálogo introduz o CSS como a linguagem responsável pela estilização visual (cores, layouts, fontes) de uma página web, que trabalha em conjunto com o HTML, responsável pela estrutura e semântica do conteúdo. A principal vantagem do CSS é a separação entre conteúdo e apresentação, permitindo que o estilo seja controlado de forma centralizada em um arquivo externo (`.css`), o que facilita enormemente a manutenção e a uniformidade de um site. O objetivo prático é utilizar o CSS para transformar a estrutura HTML básica em uma página visualmente atraente e alinhada com um projeto de design (Figma). A recomendação é aprender de forma gradual usando documentações como a do W3Schools.

</aside>

---

### **Primeiros Passos com CSS - Criando e Vinculando o Arquivo**

### Lembretes

- `style.css`
- `body`
- `background-color`
- `color`
- `<link>`
- `rel`
- `href`
- Vinculação
- Propriedade CSS
- Valor CSS

### Anotações

**Criação do Arquivo CSS:**

- **Nome do arquivo:** `style.css` (convenção para o arquivo de estilos principal).
- **Estratégia de Desenvolvimento:** Começar por estilos gerais (que afetam toda a página) e depois estilizar elementos específicos. A prioridade foi:
    1. Cor de fundo (`background-color`)
    2. Cor do texto (`color`)

**Estrutura Básica de uma Regra CSS:**

- **Seletor:** Define o elemento HTML a ser estilizado (ex: `body`).
- **Bloco de Declaração:** Delimitado por chaves `{}`.
- **Declaração:** Composta por `propriedade: valor;` dentro do bloco.
    - Ex: `background-color: black;`
    - Ex: `color: white;`
- **Autocompletar:** Editores de código ajudam a encontrar propriedades (ex: ao digitar `background`).

**O Passo Crucial: Vincular o CSS ao HTML:**

- Criar o arquivo CSS **não é suficiente**. É necessário fazer a **vinculação** no HTML.
- A tag `<link>` é usada dentro da seção `<head>` do documento HTML.
- **Atributos da tag `<link>`:**
    - `rel="stylesheet"`: Define o relacionamento do arquivo linkado como uma **folha de estilos**.
    - `href="style.css"`: Define o **caminho** (URL) para o arquivo CSS.

**Sintaxe de Vinculação no HTML:** html

```
<head><meta charset="UTF-8"><title>Portfolio</title><link rel="stylesheet" href="style.css"></head>
```

**Resultado e Próximos Passos:**

- Após a vinculação, o fundo ficou preto e o texto branco.
- **Problema inicial:** O texto "sumiu" porque a cor inicial do texto também era preta. Foi resolvido com `color: white;`.
- **Elementos não estilizados:** Links (`<a>`) mantêm o estilo padrão do navegador (azul e sublinhado), pois precisam ser selecionados e estilizados especificamente mais tarde.

<aside>
📌 **RESUMO**:

O processo de estilização inicia com a criação de um arquivo `style.css`. Nele, as regras CSS são escritas na estrutura `seletor { propriedade: valor; }`. O elemento `body` é um seletor comum para estilos gerais da página. O passo **fundamental e obrigatório** é vincular esse arquivo ao HTML usando a tag `<link>` com os atributos `rel="stylesheet"` e `href="style.css"` dentro do `<head>`. Este vínculo permite que o navegador busque e aplique os estilos definidos. A estratégia de começar por propriedades amplas, como cor de fundo e de texto, estabelece a base visual antes de detalhar elementos individuais, cujos estilos padrão (como os dos links) serão sobrescritos posteriormente.

</aside>