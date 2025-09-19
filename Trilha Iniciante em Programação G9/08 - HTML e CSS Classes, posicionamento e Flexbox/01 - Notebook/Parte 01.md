### **Utilizando Classes CSS para Estilização Específica**

### Lembretes

- Classe CSS
- Seletor
- Especificidade
- HTML
- Estilização

### Anotações

### **Problema Inicial:**

- Como estilizar uma tag `<strong>` específica sem afetar todas as outras no documento.

### **Solução:**

- Uso de **classes CSS** para aplicar estilos específicos a elementos individuais.

### **Como criar uma classe:**

1. **No HTML:** Adicionar o atributo `class` à tag desejada.
    - Exemplo: `<strong class="titulo-destaque">Texto</strong>`
2. **No CSS:** Usar o seletor de classe (`.`) para estilizar.
    - Exemplo:
        
        ```css
        .titulo-destaque {
            color: #22D4FD;
        }
        ```
        

### **Vantagens das classes:**

- Permitem estilizar elementos específicos sem alterar todos os da mesma tag.
- Oferecem maior controle e organização do código.

### **Nomeação de classes:**

- Use nomes descritivos e intuitivos (ex: `"titulo-destaque"`).
- Seguir padrões de nomenclatura consistentes facilita a manutenção.

### **Observações:**

- A tag `<strong>` por padrão deixa o texto em **negrito**, independente do CSS.
- Classes são "agrupamentos de tipo" que permitem estilizações específicas.

<aside>
📌 **RESUMO**:

Para estilizar um elemento específico (como uma tag `<strong>`) sem afetar outros da mesma tipo, utilizamos **classes CSS**. No HTML, adicionamos o atributo `class` com um nome descritivo à tag. No CSS, usamos o seletor `.` (ponto) seguido do nome da classe para aplicar estilos. Isso permite maior controle e organização, mantendo a estilização restrita ao elemento desejado. 

</aside>

---

### **Seletores CSS e Reset CSS**

### Lembretes

- Seletores CSS
- Reset CSS
- Especificidade
- Herança
- Normalização

### Anotações

### **O que são Seletores CSS?**

- São padrões usados para **selecionar elementos HTML** e aplicar estilos.
- Tipos comuns:
    1. **Seletor de Tag:** `tag { }` (ex: `strong { color: red; }`)
    2. **Seletor de Classe:** `.classe { }` (ex: `.destaque { color: blue; }`)
    3. **Seletor de ID:** `#id { }` (ex: `#menu { background: black; }`)
    4. **Seletor Universal:** `{ }` (afeta todos os elementos)
    5. **Seletor de Atributo:** `[atributo] { }` (ex: `[href] { color: green; }`)
    6. **Combinadores:** Seletores que combinam elementos (ex: `div > p`).

### **Especificidade dos Seletores:**

- Define qual estilo prevalece quando há conflito.
- Ordem de prioridade (da maior para a menor):
    1. `!important` (evite abusar)
    2. Estilos inline (ex: `style="color: red;"`)
    3. IDs (`#id`)
    4. Classes (`.classe`), atributos (`[type]`) e pseudo-classes (`:hover`)
    5. Tags (`div`, `p`) e pseudo-elementos (`::before`)
    6. Seletor universal ()

### **Reset CSS:**

- **O que é:** Uma técnica para **remover estilos padrão** dos navegadores.
- **Por que usar?** Navegadores aplicam estilos padrão (ex: margens em `<body>`, `<h1>`, etc.), o que causa inconsistências entre eles.
- **Como funciona:** Um código CSS que "reseta" esses estilos para um ponto neutro, permitindo maior controle na estilização.
- Exemplo simples de Reset CSS:
    
    ```css
    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
    }
    ```
    
- Alternativas populares:
    - **Normalize.css** (mantém estilos úteis, mas os uniformiza entre navegadores).
    - **Reset CSS** (mais agressivo, remove quase tudo).

### **Dica importante:**

- Use Reset CSS ou Normalize.css no início do arquivo CSS para garantir consistência.

### **Exemplo Prático (Reset CSS Básico):**

```css
/* Reset CSS simplificado */
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

/* A partir daqui, seus estilos personalizados */
body {
  font-family: Arial, sans-serif;
}
```

Isso garante que todos os elementos comecem sem margens/paddings e usem `box-sizing: border-box` para facilitar o dimensionamento.

<aside>
📌 **RESUMO**:

**Seletores CSS** são padrões que target elementos HTML para estilização, sendo os principais: tags, classes, IDs e universais. A **especificidade** determina qual estilo prevalece em conflitos. Já o **Reset CSS** é uma técnica para remover estilos padrão dos navegadores, garantindo consistência no design. 

</aside>

### **Configurações Padrão de CSS para Layout de Página**

### Lembretes

- `height: 100vh`
- `box-sizing: border-box`
- Viewport
- Elemento Pai e Filho
- Layout Responsivo

### Anotações

### **1. Ocupar 100% da Altura da Tela:**

- **Problema:** O elemento `body` não ocupa toda a altura da tela por padrão.
- **Solução:** Usar `height: 100vh` no CSS do `body`.
    - `vh` (viewport height): Unidade que representa a porcentagem da altura da janela do navegador.
    - Exemplo:
        
        ```css
        body {
            height: 100vh;
        }
        ```
        
- **Resultado:** O corpo da página preenche toda a altura visível da tela.

### **2. Controlar o Box Model:**

- **Problema:** Elementos filhos (como imagens ou botões) podem ultrapassar os limites do elemento pai ao adicionar `padding` ou `border`.
- **Solução:** Usar `box-sizing: border-box` no `body` (ou globalmente).
    - **Diferença entre valores:**
        - `content-box` (padrão): Largura/altura do elemento não inclui `padding` ou `border`.
        - `border-box`: Largura/altura do elemento inclui `padding` e `border`, mantendo o conteúdo dentro dos limites do pai.
- **Exemplo:**
    
    ```css
    body {
        box-sizing: border-box;
    }
    ```
    
- **Vantagem:** Evita que elementos filhos "vazem" do container pai.

### **3. Boas Práticas:**

- Sempre definir `height: 100vh` para páginas que devem ocupar toda a tela sem scroll.
- Usar `box-sizing: border-box` globalmente para controle preciso do layout.
- Testar visualmente com ferramentas de inspeção do navegador (ex: DevTools).

<aside>
📌 **RESUMO**:

Para garantir que uma página ocupe 100% da altura da tela e que os elementos internos se mantenham dentro dos limites do container pai, duas propriedades CSS são essenciais:

1. **`height: 100vh`** no `body`: Assegura que a página ocupe toda a altura do viewport.
2. **`box-sizing: border-box`**: Altera o cálculo do box model para incluir `padding` e `border` nas dimensões do elemento, evitando que conteúdos ultrapassem os limites do container.

Essas configurações são padrões recomendados para projetos com layout fixo em uma única tela (sem scroll), como landing pages ou portfólios.

</aside>

---

### **Posicionando Elementos com Flexbox no CSS**

### Lembretes

- Flexbox
- `display: flex`
- `align-items`
- `flex-direction`
- Responsividade

### Anotações

### **1. Problema de Posicionamento**

- **Objetivo:** Colocar texto e imagem lado a lado, centralizados verticalmente.
- **Solução inadequada:** Usar margens fixas (ex: `margin-top: 300px`), pois não se adapta a diferentes telas.
- **Consequência:** Layout quebra em dispositivos com telas muito grandes ou muito pequenas.

### **2. Introdução ao Flexbox**

- **O que é:** Tecnologia CSS para organizar elementos em containers.
- **Vantagem:** Layouts flexíveis e responsivos sem dependência de valores fixos.
- **Documentação:**
    - [MDN Web Docs](https://developer.mozilla.org/pt-BR/docs/Web/CSS/CSS_Flexible_Box_Layout/Basic_Concepts_of_Flexbox) (técnica).
    - [A Complete Guide to Flexbox](https://css-tricks.com/snippets/css/a-guide-to-flexbox/) (visual).

### **3. Aplicando Flexbox**

- **Passo 1:** Definir o elemento pai como container flexível:
    
    ```css
    .apresentacao {
        display: flex;
    }
    ```
    
- **Resultado imediato:** Os elementos filhos (texto e imagem) ficam em linha (padrão `flex-direction: row`).

### **4. Alinhamento Vertical com `align-items`**

- **Propriedade:** Controla o alinhamento vertical dos itens no container.
- **Valores comuns:**
    - `flex-start`: Itens alinhados no topo.
    - `flex-end`: Itens alinhados na base.
    - `center`: Itens centralizados verticalmente.
- **Exemplo:**
    
    ```css
    .apresentacao {
        display: flex;
        align-items: center;/* Centraliza verticalmente */
    }
    ```
    
- **Observação:** O alinhamento é baseado no elemento mais alto (ex: imagem).

### **5. Boas Práticas**

- **Sem acentos em classes:** Usar `apresentacao` em vez de `apresentação` para evitar erros de interpretação.
- **Evitar unidades fixas:** Preferir Flexbox ou unidades relativas (`%`, `vh`, `vw`) para responsividade.
- **Testar em múltiplos dispositivos:** Garantir que o layout funcione em telas variadas.

<aside>
📌 **RESUMO**:

Para posicionar elementos lado a lado e centralizados verticalmente:

1. Use **Flexbox** no elemento pai (**`display: flex`**).
2. Ajuste o alinhamento vertical com **`align-items: center`**.
3. Evite margens/paddings fixos para garantir responsividade.

O Flexbox é ideal para layouts dinâmicos que se adaptam a diferentes tamanhos de tela, substituindo soluções rígidas baseadas em pixels.

</aside>

### Organizando Elementos com Flexbox e Margens no CSS

### Lembretes

- Flexbox
- **`justify-content: space-between`**
- Margens percentuais (**`%`**)
- Elementos pai e filhos
- Responsividade

### Anotações

### **1. Estruturação do HTML**

- **Problema:** Elementos de texto e imagem estavam "grudados" sem espaçamento.
- **Solução:** Agrupar elementos relacionados em uma tag `<section>` separada da imagem:
    
    ```html
    <main class="apresentacao">
      <section>
        <h1>Eleve seu negócio digital a outro nível <strong class="i         tulo-destaque">com um Front-end de qualidade!</strong></h1>
        <p>Olá! Sou Joana Santos, desenvolvedora Front-end com espei         alidade em React, HTML e CSS. Ajudo pequenos negócios e desg         ners a colocarem em prática boas ideias. Vamos conversar?
        </p>
        <a href="https://instagram.com/rafaballerini">Instagram</a>
        <a href="https://github.com/guilhermeonrails">Github</a>
      </section>
        <img src="imagem.png" alt="Foto da Joana Santos programando">
    ```
    
- **Resultado:** Dois elementos filhos no container flexível (a **`<section>`** e a **`<img>`**).

### **2. Distribuição de Espaço com `justify-content`**

- **Propriedade:** Controla o espaçamento horizontal entre elementos filhos.
- **Valor `space-between`:** Distribui o espaço disponível igualmente entre os elementos, alinhando-os nas extremidades.
    
    ```css
    .apresentacao {
        display: flex;
        justify-content: space-between;/* Espaço entre os elementos */}
    ```
    
- **Efeito:** A seção de texto fica à esquerda e a imagem à direita, com espaço entre elas.

### **3. Ajuste de Margens Externas**

- **Problema:** Elementos colados nas bordas da tela.
- **Solução:** Usar margens percentuais para criar espaçamento responsivo:
    
    ```css
    .apresentacao {
        margin: 10%;/* Margem de 10% em todos os lados */display: flex;
        justify-content: space-between;
    }
    ```
    
- **Vantagem:** Percentual adapta-se automaticamente a diferentes tamanhos de tela.

### **4. Alinhamento Vertical**

- **Manter alinhamento centralizado:**
    
    ```css
    .apresentacao {
        align-items: center;/* Centraliza verticalmente */}
    ```
    
- **Observação:** O alinhamento é baseado no elemento mais alto (imagem).

### **5. Boas Práticas**

- **Agrupar elementos semanticamente:** Usar `<section>` para conteúdo relacionado.
- **Evitar valores fixos:** Preferir porcentagens (`%`) para margens/paddings.
- **Testar responsividade:** Ajustar valores percentuais conforme necessário (ex: 8% vs 10%).

<aside>
📌 **RESUMO**:

Para criar um layout com dois blocos (texto e imagem) lado a lado e bem espaçados:

1. Agrupe o conteúdo em **`<section>`** para formar um único bloco lógico.
2. Use **`justify-content: space-between`** no container pai para distribuir o espaço entre os elementos.
3. Adicione **margens percentuais** (ex: `margin: 10%`) para afastar o container das bordas da tela.
4. Mantenha **`align-items: center`** para alinhamento vertical centralizado.

Essa abordagem garante um layout responsivo e visualmente equilibrado, aproximando-se do design do Figma.

</aside>

---

### A Importância da Indentação no Código

### Lembretes

- Indetação
- Hierarquia visual
- Boas práticas
- Legibilidade
- Manutenção de código

### Anotações

### **1. O que é Indentação?**

- **Definição:** Espaçamento aplicado no início das linhas de código para organizar visualmente a estrutura.
- **Objetivo:** Mostrar a relação hierárquica entre elementos (ex: tags aninhadas em HTML).

### **2. Por que Indentar?**

- **Facilita a leitura:** Permite identificar rapidamente a estrutura do código.
- **Ajuda na manutenção:** Simplifica a localização de erros e a compreensão por outros desenvolvedores.
- **Boas práticas:** Embora não seja obrigatória em algumas linguagens, é essencial para código profissional.

### **3. Exemplo Prático (HTML)**

- **Código NÃO indentado:**
    
    ```html
    <main>
    <div class=”titulos”>
    <h1>Título da página</h1>
    </div>
    <div class=”paragrafos”>
    <p>Primeiro parágrafo</p>
    <p>Segundo parágrafo</p>
    </div>
    </main>
    ```
    
    - **Problema:** Dificuldade para visualizar a hierarquia dos elementos.
- **Código indentado:**
    
    ```html
    <main>
        <div class=”titulos”>
            <h1>Título da página</h1>
        </div>
        <div class=”paragrafos”>
            <p>Primeiro parágrafo</p>
            <p>Segundo parágrafo</p>
        </div>
    </main>
    ```
    
    - **Vantagem:** Estrutura clara e fácil de entender.

### **4. Como Indentar?**

- **Ferramentas:**
    - Editores de código (ex: VS Code) fazem indentação automática com a tecla **Tab**.
    - Atalhos como **"Shift + Tab"** revertem a indentação.
- **Padrão comum:** 4 espaços ou 1 tab por nível hierárquico.

### **5. Dica de Documentação**

- Para aprofundar em HTML e boas práticas:
    - [Iniciando com HTML - MDN](https://developer.mozilla.org/pt-BR/docs/Learn/HTML/Introduction_to_HTML/Getting_started)

<aside>
📌 **RESUMO**:

A **indentação** é uma prática fundamental para manter o código organizado e legível. Ela:

1. Define visualmente a hierarquia entre elementos.
2. Facilita a colaboração e a manutenção do código.
3. Deve ser aplicada consistentemente usando espaços ou tabs.

Sempre indente seu código para seguir boas práticas de desenvolvimento!

</aside>

---

### Ajustando Tamanhos de Elementos e Textos com Base no Figma

### Lembretes

- `width`
- `font-size`
- Classes CSS
- Figma
- Hierarquia de elementos

### Anotações

### **1. Definindo a Largura de um Elemento**

- **Problema:** A seção de texto estava muito larga, diferente do design do Figma.
- **Solução:** Usar `width` para limitar a largura do container de conteúdo.
- **Passos:**
    1. Adicionar classe à section: `apresentacao__conteudo`.
    2. No CSS, definir `width: 615px` (valor extraído do Figma).
- **Efeito:** O conteúdo quebra linhas ao atingir o limite de 615px.

### **2. Ajustando o Tamanho da Fonte**

- **Título (`<h1>`):**
    - Classe: `apresentacao__conteudo__titulo`.
    - Propriedade: `font-size: 36px` (valor do Figma).
- **Parágrafo (`<p>`):**
    - Classe: `apresentacao__conteudo__texto`.
    - Propriedade: `font-size: 24px` (valor do Figma).

### **3. Boas Práticas de Nomenclatura**

- **Convenção BEM (Block Element Modifier):**
    - `apresentacao` (bloco pai).
    - `apresentacao__conteudo` (elemento dentro do bloco).
    - `apresentacao__conteudo__titulo` (elemento dentro do conteúdo).
- **Vantagem:** Clareza na hierarquia e facilidade de manutenção.

### **4. Como Extrair Valores do Figma**

- **Largura (width):** Verificar o valor "W" na aba "Design" do Figma.
- **Tamanho de fonte:** Verificar a aba "Text" no Figma.
- **Unidade:** Usar `px` (pixels) para fidelidade ao design.

### **5. Estrutura do Código**

- **HTML:**
    
    ```html
    <main class="apresentacao">
      <section class="apresentacao__conteudo">
        <h1 class="apresentacao__conteudo__titulo">Eleve seu negócio     digital a outro nível <strong class="titulo-destaque">com um     Front-end de qualidade!</strong></h1>
        <p class="apresentacao__conteudo__texto">Olá! Sou Joana          Santos, desenvolvedora Front-end com especialidade em            React, HTML e CSS. Ajudo pequenos negócios e designers           a colocarem em prática boas ideias. Vamos conversar?
        </p>
        <a href="https://instagram.com/rafaballerini">Instagram</a>
        <a href="https://github.com/guilhermeonrails">Github</a>
      </section>
      <img src="imagem.png" alt="Foto da Joana Santos programando">
    ```
    
- **CSS:**
    
    ```css
    .apresentacao__conteudo {
        width: 615px;
    }
    .apresentacao__conteudo__titulo {
        font-size: 36px;
    }
    .apresentacao__conteudo__texto {
        font-size: 24px;
    }
    ```
    

<aside>
📌 **RESUMO**:

Para ajustar elementos e textos conforme o design do Figma:

1. **Extraia valores** de largura (`width`) e tamanho de fonte (`font-size`) do Figma.
2. **Crie classes** com nomenclatura clara (ex: `bloco__elemento`).
3. **Aplique os valores** no CSS usando unidades `px` para precisão.

Isso garante que seu layout e tipografia correspondam ao design original, melhorando a fidelidade visual do projeto.

</aside>

---

### Importando e Aplicando Fontes do Google Fonts no CSS

### Lembretes

- Google Fonts
- `@import`
- `font-family`
- `font-weight`
- Figma

### Anotações

### **1. Identificando Fontes no Figma**

- **Passo 1:** Selecionar o texto no Figma e verificar o nome da fonte na aba "Text" (ex: `Krona One` para título, `Montserrat` para parágrafo).
- **Passo 2:** Anotar o peso da fonte (`font-weight`) na aba "Inspect" (ex: `400` para Regular).

### **2. Importando Fontes do Google Fonts**

- **Acessar o Google Fonts:** [fonts.google.com](https://fonts.google.com/).
- **Buscar a fonte:** Digitar o nome (ex: `Krona One`) e selecionar o estilo correto (ex: `Regular 400`).
- **Selecionar o estilo:** Clicar em "Select [estilo]" (ex: "Select Regular 400").
- **Copiar o código de importação:**
    - Na barra lateral direita, selecionar a opção `@import`.
    - Copiar o código CSS (excluindo a tag `<style>`):
        
        ```css
        @import url('https://fonts.googleapis.com/css2?family=Krona+One&display=swap');
        ```
        
- **Adicionar no CSS:** Colar o `@import` no topo do arquivo `style.css`.

### **3. Aplicando a Fonte aos Elementos**

- **Usar `font-family`:**
    - Copiar o valor da seção "CSS rules to specify families" no Google Fonts (ex: `'Krona One', sans-serif`).
    - Aplicar à classe do elemento:
        
        ```css
        .apresentacao__conteudo__titulo {
            font-family: 'Krona One', sans-serif;
        }
        ```
        

### **4. Dicas Importantes**

- **Múltiplas fontes:** É possível importar várias fontes em um único `@import`:
    
    ```css
    @import url('https://fonts.googleapis.com/css2?family=Krona+One&family=Montserrat&display=swap');
    ```
    
- **Fallback:** Sempre incluir uma fonte genérica (ex: `sans-serif`) como fallback.
- **Peso da fonte:** Verificar se o `font-weight` corresponde ao estilo selecionado (ex: `400` para Regular).

### **5. Estrutura Final do Código**

- **CSS:**
    
    ```css
    @import url('https://fonts.googleapis.com/css2?family=Krona+One&family=Montserrat&display=swap');
    
    .apresentacao__conteudo__titulo {
        font-size: 36px;
        font-family: 'Krona One', sans-serif;
    }
    
    .apresentacao__conteudo__texto {
        font-size: 24px;
        font-family: 'Montserrat', sans-serif;
    }
    ```
    

<aside>
📌 **RESUMO**:

Para usar fontes personalizadas do Google Fonts:

1. **Identifique** a fonte e o peso no Figma.
2. **Importe** a fonte do google fonts via `@import` no topo do CSS.
3. **Aplique** a fonte com `font-family` nos elementos desejados.
4. **Use fallbacks** (ex: `sans-serif`) para garantir compatibilidade.

Isso garante que seu projeto tenha a mesma identidade visual do design do Figma

</aside>

