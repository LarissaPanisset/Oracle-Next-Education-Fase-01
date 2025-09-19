### Agrupando e Posicionando Botões com Flexbox no CSS

### Lembretes

- Flexbox
- `display: flex`
- `justify-content: space-between`
- Tag `<div>`
- Agrupamento visual

### Anotações

### **1. Agrupando Elementos com `<div>`**

- **Problema:** Os botões (links) precisam ser tratados como um grupo visual.
- **Solução:** Usar a tag `<div>` para agrupar elementos semanticamente relacionados.
    
    ```html
    <div class="apresentacao__links">
       <a href="...">Instagram</a>
       <a href="...">Github</a>
    </div>
    ```
    
- **Observação:** `<div>` não tem valor semântico; é puramente para agrupamento visual.

### **2. Posicionando com Flexbox**

- **Passo 1:** Adicionar `display: flex` ao container pai (`.apresentacao__links`).
- **Passo 2:** Usar `justify-content: space-between` para distribuir os botões nas extremidades:
    
    ```css
    .apresentacao__links {
        display: flex;
        justify-content: space-between;
    }
    ```
    
- **Resultado:** Os botões ficam alinhados à esquerda e à direita do container.

### **3. Hierarquia de Classes**

- **Convenção BEM:**
    - `apresentacao__links`: Indica que o elemento está dentro do bloco "apresentacao".
    - Mantém a consistência com outras classes (ex: `apresentacao__conteudo`).

### **4. Boas Práticas**

- **Semântica vs. Visual:**
    - Use `<main>` para conteúdo principal.
    - Use `<section>` para agrupar conteúdo temático.
    - Use `<div>` para agrupamentos puramente visuais.
- **Flexbox para alinhamento:** Ideal para distribuir elementos horizontalmente.

### **5. Estrutura do Código**

- **HTML:**
    
    ```html
    <div class="apresentacao__links">
           <a>Instagram</a>
        <a>Github</a>
    </div>
    ```
    
- **CSS:**
    
    ```css
    .apresentacao__links {
        display: flex;
        justify-content: space-between;
    }
    ```
    

<aside>
📌 **RESUMO**:

Para posicionar botões lado a lado com espaçamento entre eles:

1. **Agrupe os botões** em uma `<div>` com uma classe descritiva (ex: `apresentacao__links`).
2. **Aplique Flexbox** no container: `display: flex` e `justify-content: space-between`.
3. **Mantenha a consistência** na nomenclatura das classes seguindo a convenção BEM.

Isso garante um controle preciso sobre o layout dos botões, aproximando-se do design do Figma.

</aside>

---

### Estilizando Botões com CSS para Corresponder ao Design do Figma

### Lembretes

- Estilização de botões
- `background-color`
- `border-radius`
- `padding`
- `font-weight`
- Google Fonts

### Anotações

### **1. Estrutura HTML para Botões**

- **Agrupamento:** Usar `<div>` com classe `apresentacao__links` para agrupar os botões.
- **Classe individual:** Cada botão (`<a>`) recebe a classe `apresentacao__links__link`.
    
    ```html
    <div class="apresentacao__links">
       <a class="apresentacao__links__link" href="...">Instagram</a>    <a class="apresentacao__links__link" href="...">Github</a>
    </div>
    ```
    

### **2. Propriedades de Estilização**

- **Cor de fundo:** `background-color: #22D4FD;` (valor hexadecimal do Figma).
- **Largura:** `width: 280px;` (valor do Figma).
- **Alinhamento de texto:** `text-align: center;` para centralizar o texto.
- **Bordas arredondadas:** `border-radius: 16px;` (valor do Figma).
- **Tamanho da fonte:** `font-size: 24px;` (valor do Figma).
- **Espaçamento interno:** `padding: 21.5px 0;` (21.5px para topo/base, 0 para laterais).
- **Remover sublinhado:** `text-decoration: none;` (padrão de links).
- **Cor do texto:** `color: #000000;` (preto, valor do Figma).

### **3. Tipografia**

- **Fonte:** `font-family: 'Montserrat', sans-serif;` (já importada do Google Fonts).
- **Peso da fonte:** `font-weight: 600;` (SemiBold, valor do Figma).
- **Importar peso adicional:** Atualizar o `@import` do Google Fonts para incluir `wght@400;600`:
    
    ```css
    @import url('https://fonts.googleapis.com/css2?family=Krona+One&family=Montserrat:wght@400;600&display=swap');
    ```
    

### **4. Boas Práticas**

- **Reutilização de classes:** Use a mesma classe para botões com o mesmo estilo.
- **Valores do Figma:** Sempre extraia valores exatos (cores, tamanhos, espaçamentos) do design.
- **Box Model:** Use `padding` para controlar o espaçamento interno entre texto e bordas.

### **5. Código CSS Final**

```css
.apresentacao__links__link {
    background-color: #22D4FD;
    width: 280px;
    text-align: center;
    border-radius: 16px;
    font-size: 24px;
    font-weight: 600;
    padding: 21.5px 0;
    text-decoration: none;
    color: #000000;
    font-family: 'Montserrat', sans-serif;
}
```

<aside>
📌 **RESUMO**:

Para estilizar botões conforme o design do Figma:

1. **Estruture o HTML** com classes descritivas seguindo a convenção BEM.
2. **Aplique propriedades CSS** como `background-color`, `border-radius`, `padding` e `font-weight` com valores extraídos do Figma.
3. **Atualize o import** do Google Fonts para incluir todos os pesos necessários (ex: `400` e `600`).
4. **Use `text-decoration: none`** para remover o sublinhado padrão de links.

Isso garante que os botões tenham aparência profissional e consistente com o design original.

</aside>

### Ajustando Espaçamentos e Alinhamento com Flexbox no CSS

### Lembretes

- Flexbox
- `flex-direction`
- `gap`
- `margin`
- Espaçamento responsivo

### Anotações

### **1. Ajuste de Margens no Container Principal**

- **Problema:** O conteúdo estava muito próximo das bordas, diferente do Figma.
- **Solução:** Aumentar a margem do container principal (`margin: 15%`).
    
    ```css
    .apresentacao {
        margin: 10% 15%;
    ```
    
- **Resultado:** Os elementos ficam mais centralizados na tela.

### **2. Organização Vertical com Flexbox**

- **Problema:** Os elementos textuais (título, parágrafo, botões) estavam muito próximos.
- **Solução:** Usar Flexbox com direção de coluna no container de conteúdo:
    
    ```css
    .apresentacao__conteudo {
      width: 615px;
      display: flex;
      flex-direction: column;/* Empilha os elementos verticalmente */
     }
    ```
    

### **3. Espaçamento Entre Elementos com `gap`**

- **Propriedade `gap`:** Cria espaçamento entre os elementos filhos de um container Flexbox.
- **Valor extraído do Figma:** `40px` entre título, parágrafo e botões.
    
    ```css
    .apresentacao__conteudo {
        gap: 40px;/* Espaçamento vertical entre os elementos */
    }
    ```
    

### **4. Boas Práticas**

- **Evitar valores fixos para margens:** Use porcentagens (`%`) para responsividade.
- **Flexbox para alinhamento vertical:** Ideal para organizar elementos em coluna.
- **Extrair valores do Figma:** Sempre use medidas exatas do design (ex: `40px` para `gap`).

### **5. Estrutura Final do Código**

- **CSS:**
    
    ```css
    .apresentacao {
        margin: 15%;
        display: flex;
        align-items: center;
        justify-content: space-between;
    }
    
    .apresentacao__conteudo {
        width: 615px;
        display: flex;
        flex-direction: column;
        gap: 40px;
    }
    ```
    

<aside>
📌 **RESUMO**:

Para ajustar espaçamentos e alinhamento conforme o Figma:

1. **Ajuste as margens** do container principal usando porcentagens para responsividade.
2. **Use Flexbox com `flex-direction: column`** para organizar elementos verticalmente.
3. **Adicione espaçamento** entre elementos com `gap` (valores extraídos do Figma).

Isso garante que o layout seja fiel ao design e responsivo em diferentes telas.

</aside>

---

### Recursos para Aprofundamento em CSS - Guia de Estudos

### Lembretes

- CSS Avançado
- Flexbox
- Box Model
- Google Fonts
- Responsividade
- BEM
- Reset CSS

### Anotações

### **📚 ARTIGOS (Português)**

1. **Seletores CSS Avançados**
    
    → [Artigo da Alura](https://www.alura.com.br/artigos/css-seletores-avancados)
    
2. **Organizando seu CSS**
    
    → [Artigo da Alura](https://www.alura.com.br/artigos/organizando-css)
    
3. **Padrão BEM**
    
    → [Artigo da Alura](https://www.alura.com.br/artigos/criando-componentes-css-com-padrao-bem)
    
4. **Box Model e Box Sizing**
    
    → [Artigo da Alura](https://www.alura.com.br/artigos/entendendo-box-model-e-box-sizing)
    
5. **Guia de Unidades CSS (vh, rem, em)**
    
    → [Artigo da Alura](https://www.alura.com.br/artigos/guia-de-unidades-no-css)
    
6. **Reset CSS**
    
    → [Artigo da Alura](https://www.alura.com.br/artigos/reset-css)
    
7. **Fontes Customizadas**
    
    → [Artigo da Alura](https://www.alura.com.br/artigos/tailwind-adicionando-fontes-customizadas)
    

---

### **🎓 CURSOS (Português)**

1. **Flexbox e Layouts Responsivos**
    
    → [Curso da Alura](https://www.alura.com.br/curso-online-css-flexbox-layouts-responsivos)
    
2. **Espaçamentos e Dimensões**
    
    → [Curso da Alura](https://www.alura.com.br/curso-online-espacamentos-e-dimensoes)
    
3. **Unidades Relativas (EM e REM)**
    
    → [Curso da Alura](https://www.alura.com.br/curso-online-unidades-relativas-com-em-e-rem)
    

---

### **💬 FÓRUNS (Português)**

1. **Dúvidas sobre Viewport**
    
    → [Fórum da Alura](https://cursos.alura.com.br/forum/duvida-sobre-viewport-em-html-e-css)
    
2. **Box Sizing**
    
    → [Fórum da Alura](https://cursos.alura.com.br/forum/funcao-do-box-sizing-border-box)
    
3. **Estilização de Botões**
    
    → [Fórum da Alura](https://cursos.alura.com.br/forum/duvida-sobre-estilizacao-de-botoes)
    
4. **Remover Linha de Links**
    
    → [Fórum da Alura](https://cursos.alura.com.br/forum/como-remover-linhas-dos-links-dos-botoes)
    

---

### **🌐 TUTORIAIS (Inglês)**

1. **Como Importar Google Fonts no CSS**
    
    → [Tutorial](https://www.w3schools.com/howto/howto_google_fonts.asp)
    
2. **Usando Google Fonts com @font-face**
    
    → [Tutorial](https://developers.google.com/fonts/docs/getting_started)
    

<aside>
📌 **RESUMO**:

Para dominar CSS:

1. Use **artigos** para conceitos específicos (BEM, Box Model).
2. Faça **cursos** para conhecimentos práticos (Flexbox, unidades).
3. Participe de **fóruns** para tirar dúvidas.
4. Consulte **tutoriais** em inglês para expandir conhecimentos.
</aside>