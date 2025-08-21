# **Lógica de programação: explore funções e listas**

### **Lógica de programação: explore funções e listas**

### Lembretes

- JavaScript e interação com a tela
- Aprimoramento do projeto "Número Secreto"
- Lógica de programação aplicada

### Anotações

- **Problema identificado**:
    - No curso anterior, foram usados **`alert`** e **`prompt`**, mas esses recursos não são comuns em sites reais (como e-commerces).
- **Foco principal**:
    - Aprender a usar **JavaScript para interagir com a tela** de forma mais prática e visual.
    - **Reforçar a lógica de programação** com exemplos aplicados.
    - **Publicar o projeto** para compartilhar com outras pessoas.

### **3. Continuidade do Projeto "Número Secreto"**

- O projeto será **mantido**, porém com melhorias:
    - **Novas funcionalidades** (ainda não detalhadas).
    - **Design mais atrativo** (evitando os **`prompt`** e **`alert`**).

<aside>
📌 **RESUMO**:

- **Prática x Teoria**:
    - O curso prioriza a aplicação real do JavaScript, não apenas conceitos básicos.
- **Evolução do Projeto**:
    - O "Número Secreto" servirá como base para explorar **novas técnicas de desenvolvimento front-end**.
</aside>

---

### Introdução à Manipulação de HTML com JavaScript

### Lembretes

- **HTML, CSS e JavaScript**
- **Manipulação dinâmica do DOM**
- **`document.querySelector()`**
- **`innerHTML`**
- **Tags HTML (`<h1>`, `<p>`)**
- **Integração front-end**

### Anotações

### **1. Introdução ao Projeto**

- **Estrutura do Projeto**:
    - **`index.html`**: Estrutura visual da página.
    - **`style.css`**: Estilização dos elementos.
    - **`app.js`**: Lógica de interação (foco principal).
- **Diferença em relação ao curso anterior**:
    - Substituição de **`alert`** e **`prompt`** por elementos HTML dinâmicos.
    - Experiência mais próxima de sites reais (ex.: e-commerces).

---

### **2. Visual do Projeto**

- **Elementos na página**:
    - **Caixa de texto**: Para inserção do número secreto.
    - **Botões**:
        - **"Chutar"** (azul) → Envia o palpite.
        - **"Novo jogo"** (cinza) → Reinicia a partida.
    - **Personagem ilustrado**: Figura com cabelo roxo observando a caixa de texto.
- **Objetivo**:
    - Interação via elementos HTML, sem pop-ups.

---

### **3. Manipulação do HTML com JavaScript**

### **Selecionando Elementos**

- **`document.querySelector()`**:
    - Método para selecionar elementos HTML.
    - **Case-sensitive**: **`querySelector`** (com "S" maiúsculo).
    - Exemplo:
        
        ```
        let titulo = document.querySelector('h1');
        ```
        

### **Modificando Conteúdo**

- **`innerHTML`**:
    - Altera o conteúdo interno de um elemento.
    - Tradução: "dentro do HTML".
    - Exemplo:

        ```
        titulo.innerHTML = 'Jogo do número secreto';
        ```
        

### **Prática Passo a Passo**

1. **Adicionando um Título (`<h1>`)**
    - Seleção:

        ```
        let titulo = document.querySelector('h1');
        ```
        
    - Inserção do texto:

        ```
        titulo.innerHTML = 'Jogo do número secreto';
        ```
        
2. **Adicionando um Parágrafo (`<p>`)**
    - Seleção:

        ```
        let paragrafo = document.querySelector('p');
        ```
        
    - Inserção do texto:

        ```
        paragrafo.innerHTML = 'Escolha um número entre 1 e 10';
        ```
        

---

### **4. Resultado Final**

- **Título**: "Jogo do número secreto" (em **`<h1>`**).
- **Parágrafo**: "Escolha um número entre 1 e 10" (em **`<p>`**).
- **Visual**:
    - Título maior e em destaque.
    - Parágrafo menor, abaixo do título.

---

### **5. Observações Importantes**

- **Por que usar JavaScript para manipular o HTML?**
    - **Dinamismo**: Alterações frequentes são mais fáceis de gerenciar.
    - **Boas práticas**:
        - **HTML**: Elementos estáticos.
        - **JavaScript**: Elementos dinâmicos.
- **Diferença entre linguagens**:
    - **`innerHTML`** e **`querySelector`** são específicos do JavaScript.
    - Outras linguagens têm métodos distintos para manipulação de interface.

<aside>
📌 **RESUMO**:

- **Aprendizado**:
    - Integração entre **HTML** e **JavaScript**.
    - Uso de **seletores** e **modificadores de conteúdo**.

**Dica**: Sempre salve as alterações (**Ctrl + S**) e visualize os resultados no navegador!

</aside>

---

### **Implementando Interatividade com Funções em JavaScript**

### Lembretes

- **Funções em JavaScript** (**`function`**)
- **Atributo `onclick`**
- **`console.log()` para depuração**
- **Boas práticas de nomenclatura**
- **Escopo de função**

### Anotações

### **1. Contexto do Desafio**

- **Objetivo**: Tornar o botão **"Chutar"** interativo, executando uma ação ao ser clicado.
- **Botão "Novo jogo"**:
    - Está desabilitado inicialmente (foco no jogo atual).
- **Ferramentas usadas**:
    - **Console do navegador** (acessado via *Inspecionar > Console*).

### **2. Implementação Básica da Função**

### **Passo 1: Vinculando o Botão ao JavaScript**

- No **HTML**, o botão "Chutar" possui um atributo **`onclick`**:

    ```
    <button onclick="verificarChute()" class="container__botao">Chutar</button>
    ```
    
    - **`onclick`** aciona a função **`verificarChute()`** ao clicar no botão.

### **Passo 2: Criando a Função no JavaScript**

- **Sintaxe de uma função**:

    ```
    function verificarChute() {
    // Corpo da função}
    ```
    
    - **`function`**: Palavra-chave para declarar funções.
    - **`verificarChute`**: Nome descritivo (boas práticas).
    - **`{}`**: Delimitam o escopo (bloco de código executado).

### **Passo 3: Testando a Função**

- **Exemplo inicial**:
 
    ```
    function verificarChute() {
      console.log('O botão foi clicado!');
    }
    ```
    
    - **`console.log()`**: Exibe mensagens no console para depuração.
    - **Resultado**: Ao clicar em "Chutar", a mensagem aparece no console.

### **3. Boas Práticas e Conceitos Fundamentais**

### **Nomenclatura de Funções**

- **Regra**: Nomes devem ser **autoexplicativos** (ex.: **`verificarChute`** em vez de **`v`**).
- **Motivo**: Melhora a legibilidade e manutenção do código.

### **Princípio da Responsabilidade Única**

- **Diretriz**: Uma função deve ter **uma única tarefa** (ex.: verificar o chute).
- **Vantagem**: Código mais organizado e fácil de debugar.

### **Escopo de Função**

- **Definição**: Tudo dentro de **`{}`** pertence à função e só é executado quando ela é chamada.

### **4. Próximos Passos**

- **Expandir a função `verificarChute`**:
    - Capturar o valor digitado na caixa de texto.
    - Comparar com o número secreto.
    - Exibir feedbacks (acerto/erro).

<aside>
📌 **RESUMO**:

- **Integração HTML-JavaScript**:
    - **`onclick`** no HTML chama funções definidas no JavaScript.
- **Depuração**:
    - **`console.log()`** é essencial para verificar se o código está funcionando.
- **Organização**:
    - Funções bem nomeadas e com responsabilidades claras facilitam o trabalho em equipe.

**Dica**: Sempre teste pequenas partes do código (como o **`console.log`**) para garantir que a lógica está correta antes de implementar funcionalidades complexas!

</aside>

---

### Diferenças entre HTML, CSS e JavaScript

### Lembretes

- **HTML**: Estrutura e conteúdo
- **CSS**: Estilo e design
- **JavaScript**: Interatividade e lógica
- **Desenvolvimento web**
- **História e evolução**

### Anotações

### **1. Introdução**

HTML, CSS e JavaScript são as três tecnologias essenciais para construção de páginas e aplicações web. Cada uma tem um papel distinto, mas complementar.

---

### **2. HTML: A Estrutura Básica**

### **O que é?**

- **HyperText Markup Language** (Linguagem de Marcação de Hipertexto).
- Criado por **Tim Berners-Lee em 1991**.
- Funciona como o **"esqueleto"** da página.

### **Função Principal**

- Define a **hierarquia e organização** do conteúdo:
    - Títulos (**`<h1>`**), parágrafos (**`<p>`**), imagens (**`<img>`**), links (**`<a>`**).
- **Exemplo**:

    ```
    <h1>Título Principal</h1><p>Este é um parágrafo.</p>
    ```
    

### **Importância**

- **Semântica**: Melhora acessibilidade e SEO.
- **Base para CSS e JS**.

---

### **3. CSS: O Design e Estilo**

### **O que é?**

- **Cascading Style Sheets** (Folhas de Estilo em Cascata).
- Criado em **1995** por Håkon Wium Lie.
- Funciona como a **"roupa"** da página.

### **Função Principal**

- Controla **aparência visual**:
    - Cores, fontes, espaçamento, layouts responsivos.
- **Exemplo**:

    ```
    p {
      color: blue;
      font-size: 16px;
    }
    ```
    

### **Importância**

- **Separação de preocupações**: Estilo vs. Estrutura.
- **Design responsivo**: Adapta-se a diferentes dispositivos.

---

### **4. JavaScript: A Interatividade**

### **O que é?**

- **Única linguagem de programação** das três.
- Criada por **Brendan Eich em 1995**.
- Funciona como o **"cérebro"** da página.

### **Função Principal**

- Adiciona **comportamentos dinâmicos**:
    - Validação de formulários, animações, atualizações em tempo real.
- **Exemplo**:

    ```
    function iniciarJogo() {
      alert("Bem-vindo ao jogo!");
    }
    ```
    

### **Importância**

- **Experiência do usuário**: Torna sites interativos.
- **Integração com APIs**: Conecta front-end e back-end.

---

### **5. Comparação Resumida**

| **Tecnologia** | **Tipo** | **Função** | **Exemplo** |
| --- | --- | --- | --- |
| **HTML** | Linguagem de marcação | Estrutura conteúdo | **`<p>Texto</p>`** |
| **CSS** | Linguagem de estilo | Controla aparência | **`p { color: red; }`** |
| **JavaScript** | Linguagem de programação | Adiciona interação | **`function validar() { ... }`** |

---

### **6. Por Que Aprender Essas Tecnologias?**

1. **Mercado de Trabalho**:
    - Habilidades essenciais para desenvolvedores web.
2. **Versatilidade**:
    - Permitem criar desde sites simples até aplicações complexas.
3. **Fundamento para Frameworks**:
    - React, Angular e Vue.js dependem delas.

<aside>
📌 **RESUMO**:

- **HTML**: Organiza o conteúdo.
- **CSS**: Deixa tudo bonito e adaptável.
- **JavaScript**: Torna a página viva e interativa.
- **Juntas**, formam a base do desenvolvimento web moderno.

**Dica**: Para se aprofundar, consulte o artigo da Rafa Ballerini sobre o tema! 🚀

</aside>
