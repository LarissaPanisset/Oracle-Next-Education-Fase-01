# HTML e CSS cabeçalho, footer e variáveis

### Atualização de Aplicações no Mundo Real: Evolução do Projeto Front-End

### Lembretes

- Atualização de Software
- Novas Funcionalidades
- Figma (Design)
- Componentes (Header, Footer, Botões)
- Páginas Múltiplas (Home, Sobre mim)

### Anotações

- **Contexto do Mundo Real:**
    - Sistemas e aplicações estão em constante evolução.
    - Atualizações são frequentes, impulsionadas por necessidades de negócio (ex.: Black Friday).
    - O curso simula esse processo de receber um novo design para implementar.
- **Mudanças na Tela "Home" (Principal):**
    - **Cabeçalho (Header):** Agora com os menus de navegação "Home" e "Sobre mim".
    - **Botões:** Redes sociais (GitHub, LinkedIn, Twitch) foram reformulados.
        - Visual: Fundo preto com **borda ciano** (antes era totalmente ciano).
        - Possuem **ícones** à esquerda do texto.
    - **Novo Elemento Textual:** Subtítulo "Acesse minhas redes:" acima dos botões.
    - **Conteúdo:** Texto de apresentação de Joana Santos.
    - **Imagem:** Foto de Joana com efeito de linha circular e estrela em ciano.
    - **Rodapé (Footer):** Barra ciano com texto "Desenvolvido por Alura" (sugestão de personalizar com o próprio nome).
- **Nova Tela: "Sobre mim":**
    - **Header e Footer:** São **idênticos** aos da página Home, garantindo consistência visual.
    - **Conteúdo Principal Diferente:**
        - Título: `<h1>` com o texto "Sobre mim".
        - Parágrafos: Texto ilustrativo "Lorem ipsum" (usado como placeholder até o texto final estar pronto).
        - Imagem: A mesma foto utilizada na Home.
    - A estrutura de dois blocos (texto e imagem) se mantém.
- **Observações Importantes:**
    - **Lorem Ipsum:** Texto placeholder comum em designs para simular o fluxo e a disposição do conteúdo real.
    - **Análise de Estilo:** Desenvolver a percepção de quais tags HTML (`<h1>`, `<p>`) e técnicas de layout (Flexbox) usar a partir do design é uma habilidade que se aprimora com a prática.

<aside>
📌 **RESUMO**:

A evolução de um projeto front-end, introduzindo uma atualização comum no mundo real, o objetivo central é simular o fluxo de trabalho de pegar um design do Figma e traduzi-lo em código, desenvolvendo a habilidade de analisar visualmente um layout para decidir sobre estrutura e estilização.

</aside>

---

### Implementando um Novo Layout: Ajustes de Estilo com Flexbox

### Lembretes

- Flexbox (display: flex, flex-direction, align-items, gap)
- Semântica HTML (<h2>)
- Alinhamento
- Espaçamento (gap)
- Estrutura de Página

### Anotações

- **Estratégia de Desenvolvimento:**
    - Começar por elementos com mudanças mais evidentes (ex.: botões).
    - A adição de um novo subtítulo ("Acesse minhas redes:") exigiu mudanças estruturais.
- **Alterações no HTML ([index.html](https://index.html/)):**
    - Adicionado um elemento de subtítulo `<h2>` dentro da `div.apresentacao__links`, acima dos links existentes.
    - **Motivo:** Usar apenas um `<h1>` por página é uma boa prática para SEO. O `<h2>` é o elemento semântico correto para um subtítulo.
- **Problema de Layout Inicial:**
    - O novo `<h2>` e os links ficaram dispostos em **horizontal** (em linha), alinhados à esquerda e muito próximos.
    - **Causa:** O contêiner (`div.apresentacao__links`) usava `display: flex` com a direção padrão `row` (linha).
- **Soluções no CSS (style.css):**
    - **1. Direção da Coluna:** `flex-direction: column;` alterou o fluxo do contêiner para empilhar os itens verticalmente.
    - **2. Centralização:** `align-items: center;` centralizou os itens no eixo **cruzado**. Como a direção agora é `column`, o eixo cruzado é o **horizontal**, centralizando o conteúdo.
    - **3. Espaçamento:** `gap: 32px;` adicionou um espaço fixo de 32 pixels entre todos os itens dentro do contêiner flex (o `<h2>` e os links), resolvendo o problema de proximidade.
- **Conceito-Chave do Flexbox:**
    - As propriedades `justify-content` e `align-items` mudam seu comportamento dependendo do `flex-direction`.
    - `flex-direction: row` (padrão):
        - `justify-content`: Alinha no eixo **horizontal** (primário).
        - `align-items`: Alinha no eixo **vertical** (cruzado).
    - `flex-direction: column`:
        - `justify-content`: Alinha no eixo **vertical** (primário).
        - `align-items`: Alinha no eixo **horizontal** (cruzado).

<aside>
📌 **RESUMO**:

O processo de atualização começou pela adição de um novo subtítulo (`<h2>`) na seção de links. Isso quebrou o layout existente, que usava Flexbox em linha (`row`). Para corrigir, o contêiner foi reconfigurado com `flex-direction: column` para empilhar os itens verticalmente. `align-items: center` foi então usado para centralizar horizontalmente todo o conteúdo dentro desse contêiner em coluna. Finalmente, `gap: 32px` providenciou o espaçamento visual correto entre os elementos, aproximando o layout do design no Figma. 

</aside>

---

### **Estilizando Subtítulo e Botões: Do Figma ao Código**

### Lembretes

- Estilização CSS
- Classe (class)
- Propriedades de Texto (font-family, font-weight, font-size)
- Border (borda)
- Box Model (width, border-radius, padding)

### Anotações

- **Criação de Classe para o Subtítulo:**
    - Adicionada `class="apresentacao__links__subtitulo"` à tag `<h2>` no HTML.
    - Segue a convenção de nomenclatura BEM (Bloco, Elemento, Modificador) do projeto.
- **Estilização do Subtítulo (CSS):**
    - **Fonte:** `font-family: 'Krona One', sans-serif;` (já importada).
    - **Peso:** `font-weight: 400;` (regular, não negrito).
    - **Tamanho:** `font-size: 24px;`.
    - *Resultado:* Texto estilizado de acordo com o design do Figma.
- **Reestilização dos Botões (CSS - .apresentacao__links__link):**
    - **Fundo:** A propriedade `background-color: #22D4FD;` foi **comentada** (`/* */`) para ser desativada, removendo o preenchimento ciano.
    - **Borda:** Adicionada `border: 2px solid #22D4FD;` para criar uma borda sólida ciano de 2px.
        - Sintaxe: `border: <espessura> <estilo> <cor>;`
    - **Texto:** A `color` foi alterada de `#000000` (preto) para `#F6F6F6` (branco) para contrastar com o fundo preto.
    - **Largura (Width):** Aumentada de `280px` para `378px` para corresponder ao design.
    - **Raio da Borda (Border-radius):** Reduzido de `16px` para `8px`, tornando os cantos menos arredondados.
    - **Outras propriedades** (`padding`, `text-align`, etc.) foram mantidas.
- **Boas Práticas e Dicas:**
    - **Comentar Código:** Usar `/* código */` para desativar temporariamente uma linha instead de deletá-la, permitindo reverter facilmente.
    - **Inspector do Figma:** Usar a aba "Inspect" no Figma para obter valores exatos de cores, tamanhos e estilos.
    - **Documentação:** Consultar recursos como a W3Schools para aprender sobre valores de propriedades (ex.: outros estilos de borda como `dotted` ou `dashed`).

<aside>
📌 **RESUMO**:

O processo focou em refinar a estilização do subtítulo e dos botões para alinhar com o novo design do Figma. Para o subtítulo, uma nova classe CSS foi criada para aplicar a fonte, peso e tamanho corretos. A estilização dos botões foi drasticamente alterada: o fundo colorido foi substituído por uma borda sólida, a cor do texto foi mudada para branco, e as dimensões (largura e raio da borda) foram ajustadas. A prática de comentar código inativo e usar o Figma como fonte de verdade para valores de design foram enfatizadas como partes essenciais do fluxo de trabalho.

</aside>

---

### Comentários em HTML e CSS: Propósito e Boas Práticas

### Lembretes

- Comentários
- Sintaxe (HTML: `<!-- -->`, CSS: `/* */`)
- Organização de Código
- Boas Práticas
- Código Descritivo

### Anotações

- **Propósito dos Comentários:**
    - **Anotar informações:** Adicionar notas importantes sobre a lógica ou funcionalidade de uma seção do código.
    - **Testar código:** "Desativar" temporariamente trechos de código para testar alternativas sem precisar apagá-los.
    - **Descrever funções:** Explicar o propósito de funções complexas ou específicas para facilitar a manutenção futura.
    - **Organizar ideias:** Ajudar a estruturar o pensamento durante o desenvolvimento.
- **Sintaxe por Linguagem:**
    - **HTML:** Usa `<!--` para abrir e `->` para fechar o comentário.
        - Tudo entre esses marcadores, incluindo quebras de linha, é ignorado.
        - Exemplo: `<!-- Isso é um comentário -->`
    - **CSS:** Usa `/*` para abrir e `/` para fechar o comentário.
        - Tudo entre esses marcadores, incluindo quebras de linha, é ignorado.
        - Exemplo: `/* Isso é um comentário */`
- **Boas Práticas (O Que Fazer e O Que Evitar):**
    - **EVITAR:**
        - Excesso de comentários, para não poluir visualmente o código.
        - Comentários muito longos, pois aumentam o tamanho do arquivo.
        - Dejar "restos" de código comentado de testes após finalizar.
    - **FAZER:**
        - Usar comentários para anotar informações **essenciais**.
        - Apagar comentários de teste após seu uso.
        - Priorizar a criação de um **código descritivo** (usando tags semânticas em HTML e nomes significativos para classes em CSS) para que o código se explique sozinho, reduzindo a dependência de comentários.

<aside>
📌 **RESUMO**:

Comentários são ferramentas valiosas para documentar, testar e organizar o código em HTML (`<!-- -->`) e CSS (`/* */`). Seu uso principal é adicionar contexto e desativar código temporariamente. No entanto, a chave para um código limpo e sustentável é usá-los com moderação, focando em anotações essenciais, e priorizar a escrita de um código autoexplicativo através da semântica HTML e da nomenclatura clara de classes CSS. Isso torna o código mais legível e reduz a necessidade de manutenção de comentários extensos.

</aside>

### Inserindo Ícones e Organizando Assets em um Projeto Web

### Lembretes

- Inserção de ícones
- Tag `<img>`
- Pasta `assets`
- Caminhos relativos
- Organização de projeto
- Alinhamento visual

### Anotações

**Atualização dos Links com Base no Figma:**

- Substituição dos links originais (Instagram/Github) pelos do design (Github/LinkedIn/Twitch)
- Importância de seguir o design mas adaptar com redes pessoais
- Atenção aos padrões de URL diferentes para cada rede social

**Processo de Inserção de Ícones:**

1. **Estrutura HTML:**
    - Tag `<img>` inserida dentro da tag `<a>`
    - Posicionada antes do texto do link
    - Manutenção da mesma classe para todos os botões
2. **Organização de Arquivos:**
    - Criação da pasta `assets` para armazenar imagens
    - Atualização dos caminhos no código (`src`)
    - Uso de caminhos relativos (`./assets/nome_arquivo.png`)
3. **Boas Práticas:**
    - Manter assets organizados em pasta dedicada
    - Manter nomenclatura consistente
    - Atualizar todos os caminhos ao mover arquivos

<aside>
📌 **RESUMO**:

A implementação dos ícones seguiu um processo organizado: atualização dos links conforme o design do Figma, criação de uma estrutura de pasta dedicada (assets) para organização dos arquivos de mídia, e inserção adequada das tags `<img>` dentro dos links. O uso de caminhos relativos e a organização em pasta assets são boas práticas essenciais para manter o projeto escalável e bem organizado. 

</aside>

---

### Alinhando Ícones e Texto em Botões com Flexbox

### Lembretes

- Flexbox
- Display: flex
- Justify-content
- Gap
- Alinhamento
- Elementos filhos

### Anotações

**Problema Identificado:**

- Ícones e textos dentro dos botões estavam desalinhados
- Necessidade de alinhar horizontalmente os elementos internos (imagem + texto)

**Solução com Flexbox:**

1. **Display Flex no Container:**
    - Adicionado `display: flex;` na classe `.apresentacao__links__link`
    - Transforma a tag `<a>` em um container flexível
    - Permite controlar a disposição dos elementos internos
2. **Centralização Horizontal:**
    - Adicionado `justify-content: center;`
    - Centraliza os elementos no eixo principal (horizontal por padrão)
    - Distribui o espaço igualmente ao redor dos elementos
3. **Espaçamento entre Elementos:**
    - Adicionado `gap: 16px;`
    - Cria espaço fixo de 16 pixels entre ícone e texto
    - Valor obtido através da inspeção no Figma

**Ordem das Propriedades:**

1. `display: flex` (ativa o flexbox)
2. `justify-content: center` (alinhamento horizontal)
3. `gap: 16px` (espaçamento entre elementos)

**Comportamento do Flexbox:**

- Direção padrão: `row` (horizontal)
- Eixo principal: horizontal (controlado por justify-content)
- Eixo cruzado: vertical (controlado por align-items)

**Resultado Obtido:**

- Ícones e textos perfeitamente centralizados nos botões
- Espaçamento consistente de 16px entre os elementos
- Layout visualmente alinhado com o design do Figma

<aside>
📌 **RESUMO**:

O alinhamento dos ícones e textos dentro dos botões foi resolvido aplicando Flexbox no container principal (tag `<a>`). Através das propriedades `display: flex`, `justify-content: center` e `gap: 16px`, conseguimos centralizar horizontalmente os elementos e criar o espaçamento adequado entre eles. Esta abordagem demonstra a eficácia do Flexbox para resolver problemas de alinhamento e distribuição de elementos dentro de containers, mantendo o código limpo e o layout fiel ao design original. A solução aproveitou a estrutura hierárquica natural do HTML, tratando a tag de link como container flexível para seus elementos filhos.

</aside>

---

### Implementando Efeitos de Interação com CSS Pseudo-classes (:hover)

### Lembretes

- Pseudo-classe :hover
- Efeito de interação
- Background-color
- User experience (UX)
- Feedback visual
- Cursor pointer

### Anotações

**O que é o Efeito Hover:**

- Efeito visual que ocorre quando o usuário passa o mouse sobre um elemento
- Fornece feedback visual de interatividade
- Melhora a experiência do usuário (UX)
- Comum em elementos clicáveis como botões e links

**Implementação do Hover:**

- Sintaxe CSS: `.classe:hover { propriedades: valor; }`
- A pseudo-classe `:hover` é adicionada ao seletor existente
- As propriedades definidas dentro do bloco `:hover` se aplicam apenas durante a interação

**Código Implementado:**

```css
.apresentacao__links__link:hover {
    background-color: #272727;
}
```

**Detalhes Técnicos:**

- Cor escolhida: `#272727` (cinza escuro)
- Contrasta com o fundo preto original da página
- Fornece um efeito sutil de destaque
- Mantém a estética visual do design

**Comportamento do Cursor:**

- Navegadores automaticamente mudam o cursor para "mão" (pointer) em elementos âncora (`<a>`)
- Isso indica naturalmente a interatividade do elemento
- O efeito hover complementa esta indicação com feedback visual

**Considerações de Design:**

- Efeitos hover devem ser sutis mas perceptíveis
- Devem manter a consistência visual com o design original
- O Figma mostrou o estado hover através de exemplos separados
- A cor #272727 foi identificada como a variação de hover no design

<aside>
📌 **RESUMO**:

A implementação do efeito hover nos botões utilizando a pseudo-classe CSS `:hover` adiciona uma camada importante de interatividade e feedback visual à página. Ao passar o mouse sobre os botões, a cor de fundo muda sutilmente para `#272727`, proporcionando uma indicação clara de que o elemento é interativo. Este efeito, combinado com a mudança automática do cursor para o formato de "mão" pelos navegadores, melhora significativamente a experiência do usuário, tornando a interface mais intuitiva e responsiva. A implementação segue as boas práticas de CSS mantendo a estética original do design enquanto adiciona funcionalidade interativa.

</aside>

### Implementação e Estilização do Rodapé (Footer) com CSS

### Lembretes

- Rodapé (footer)
- Padding vs Margin
- Centralização de texto
- Herança de estilos
- Viewport height (vh)
- Box model

### Anotações

**Estrutura HTML do Rodapé:**

- Adição de parágrafo dentro da tag `<footer>`
- Uso de classe "rodape" para estilização
- Texto personalizável ("Desenvolvido por Alura")

**Estilização CSS do Rodapé:**

- **Cores:**
    - `color: #000000;` (texto preto)
    - `background-color: #22D4FD;` (fundo azul)
- **Espaçamento interno:** `padding: 24px;` (distância entre borda e conteúdo)
- **Alinhamento:** `text-align: center;` (centralização horizontal)
- **Tipografia:**
    - `font-family: 'Montserrat', sans-serif;`
    - `font-size: 24px;`
    - `font-weight: 400;`

**Diferença entre Padding e Margin:**

- **Padding:** Espaço interno entre o conteúdo e a borda do elemento
- **Margin:** Espaço externo entre a borda do elemento e outros elementos
- No rodapé, usamos padding para criar área azul ao redor do texto

**Herança de Estilos:**

- O texto herdou inicialmente a cor branca (#F6F6F6) do body
- Foi necessário sobrescrever com `color: #000000;` no rodapé
- Demonstra como o CSS funciona em cascata

**Ajuste de Layout da Página:**

- Remoção de `height: 100vh;` do body
- Motivo: O rodapé ficava fora da área do body
- Solução: Comentar a propriedade para body ocupar apenas espaço necessário
- Ajuste do padding em `.apresentacao` para 8% (melhor distribuição espacial)

**Fluxo de Trabalho:**

1. Adicionar estrutura HTML do rodapé
2. Estilizar cores e alinhamento
3. Ajustar espaçamento com padding
4. Refinar tipografia
5. Ajustar layout geral da página para acomodar o rodapé

<aside>
📌 **RESUMO**:

A implementação do rodapé envolveu a criação da estrutura HTML semântica com `<footer>` e a estilização CSS completa usando a paleta de cores do projeto. A compreensão da diferença entre padding e margin foi crucial para o espaçamento correto, e o ajuste do layout geral da página garantiu que todos os elementos ficassem adequadamente posicionados. A remoção da altura fixa do body permitiu que o rodapé fosse incorporado naturalmente ao fluxo do documento, enquanto os ajustes de padding melhoraram a distribuição espacial geral da página. O resultado é um rodapé visualmente consistente com o design do Figma e funcional.

</aside>

---

### Implementação do Cabeçalho (Header) com Navegação Semântica

### Lembretes

- Tag semântica <header>
- Navegação <nav>
- Estrutura de menu
- Classes CSS
- Links de navegação
- Estilização

### Anotações

**Estrutura HTML do Cabeçalho:**

- Uso da tag semântica `<header>` para o cabeçalho
- Implementação de `<nav>` para área de navegação
- Dois links âncora (`<a>`) para "Home" e "Sobre mim"
- Estrutura hierárquica: header → nav → a

**Sistema de Classes:**

- `class="cabecalho"` para o header principal
- `class="cabecalho__menu"` para a navegação
- `class="cabecalho__menu__link"` para cada link individual
- Padrão de nomenclatura BEM (Bloco, Elemento, Modificador)

**Função do Cabeçalho:**

- Menu de navegação principal da página
- Links para diferentes seções/páginas do site
- No caso: página inicial (Home) e página sobre (Sobre mim)

**Problema Imediato:**

- Cabeçalho não é visível inicialmente no navegador
- Elementos aparecem muito pequenos no canto superior
- Necessidade de estilização CSS para torná-lo visível e alinhado com o design

**Boas Práticas:**

- Uso de tags semânticas para melhor acessibilidade
- Estrutura clara de classes para organização do CSS
- Manutenção da consistência visual com o design do Figma

<aside>
📌 **RESUMO**:

A implementação do cabeçalho envolveu a criação de uma estrutura semântica HTML com `<header>` e `<nav>`, contendo links de navegação para as principais seções do site. O uso de classes seguindo a metodologia BEM proporciona uma base organizada para a estilização CSS que será realizada em seguida. Embora os elementos não sejam visíveis inicialmente devido à falta de estilização, a estrutura está preparada para receber as propriedades de CSS que tornarão o cabeçalho funcional e visualmente alinhado com o design do projeto. 

</aside>

### Estilização e Posicionamento do Cabeçalho com CSS Flexbox

### Lembretes

- Estilização de cabeçalho
- Flexbox para navegação
- Propriedade padding
- Gap entre elementos
- Alinhamento visual
- Design responsivo

### Anotações

**Estilização dos Links de Navegação:**

- **Fonte:** `'Montserrat', sans-serif` (consistente com o design)
- **Tamanho:** `font-size: 24px` (tamanho padrão do projeto)
- **Peso:** `font-weight: 600` (negrito moderado)
- **Cor:** `color: #22D4FD` (azul claro/ciano da paleta)

**Posicionamento do Cabeçalho:**

- **Padding com 4 valores:** `padding: 2% 0% 0% 15%`
    - 2% superior (afastamento do topo)
    - 0% direito (sem margem direita)
    - 0% inferior (sem margem inferior)
    - 15% esquerdo (alinhamento com conteúdo principal)

**Layout Flexbox para o Menu:**

- `display: flex` no container da navegação
- `gap: 80px` (espaçamento entre links "Home" e "Sobre mim")
- Mantém consistência com espaçamento do Figma

**Ajustes de Alinhamento Geral:**

- Redução do padding em `.apresentacao` de 8% para 5%
- Melhor distribuição espacial entre cabeçalho e conteúdo
- Alinhamento visual com o design do projeto

**Boas Práticas Aplicadas:**

- Uso de porcentagens para padding (layout responsivo)
- Manutenção da paleta de cores consistente
- Organização hierárquica das classes CSS
- Alinhamento preciso com valores do Figma

<aside>
📌 **RESUMO**:

A estilização do cabeçalho foi concluída com sucesso utilizando CSS Flexbox para posicionamento e propriedades de tipografia consistentes com o design do projeto. O uso de padding com valores específicos em porcentagem garantiu um layout responsivo, enquanto o gap de 80px entre os links proporcionou o espaçamento visual adequado. O ajuste do padding geral da apresentação para 5% melhorou a distribuição espacial da página, aproximando-se do layout original do Figma. 

</aside>

---

### Criando Navegação entre Páginas e Organizando a Estrutura de Arquivos

### Lembretes

- Estrutura de pastas
- Navegação entre páginas
- Atributo href
- Organização de arquivos
- Links relativos
- Remoção de sublinhado

### Anotações

**Reorganização da Estrutura de Arquivos:**

- Criação da pasta "styles" para armazenar arquivos CSS
- Movimento do arquivo styles.css para dentro da pasta styles
- Atualização do caminho no HTML: `href="./styles/styles.css"`
- Manutenção da pasta "assets" para imagens
- Arquivos HTML permanecem na raiz do projeto

**Criação da Nova Página ([about.html](https://about.html/)):**

- Uso do atalho "!" + Enter para estrutura HTML básica
- Ajuste do idioma: `lang="pt-br"`
- Definição do título da página: `<title>Sobre mim</title>`
- Conteúdo inicial simples: `<h1>Sobre mim</h1>`

**Implementação da Navegação:**

- Adição do atributo `href` nas tags âncora do menu
- `href="index.html"` para link "Home"
- `href="about.html"` para link "Sobre mim"
- Links relativos (sem ./) pois estão na mesma pasta

**Estilização dos Links de Navegação:**

- Remoção do sublinhado padrão: `text-decoration: none;`
- Manutenção da estética limpa do design
- A propriedade foi adicionada à classe `.cabecalho__menu__link`

**Fluxo de Navegação Funcional:**

- Click em "Home" recarrega a página inicial (já está nela)
- Click em "Sobre mim" redireciona para [about.html](https://about.html/)
- Navegação básica entre páginas está implementada

<aside>
📌 **RESUMO**:

A implementação da navegação entre páginas envolveu a reorganização da estrutura de arquivos com a criação de uma pasta dedicada para estilos (styles) e a manutenção da pasta assets para imagens. A nova página [about.html](https://about.html/) foi criada com a estrutura básica HTML e os links de navegação no cabeçalho foram configurados com os atributos href apropriados. A remoção do sublinhado padrão dos links através da propriedade text-decoration: none garantiu a estética limpa do design. Agora a navegação básica entre a página inicial e a página "Sobre mim" está funcional, preparando o terreno para o desenvolvimento completo do conteúdo da segunda página enquanto mantém a consistência estrutural e visual do projeto.

</aside>
