# **Lógica de programação: mergulhe em programação com JavaScript**

### **Lógica de Programação: A Base para Resolver Problemas com Código**

Lembretes

- **Lógica de programação: Pensamento estruturado para resolver problemas.**
- **Algoritmo: Sequência de passos para um objetivo.**
- **Fluxograma: Representação visual de um algoritmo.**
- **Pseudocódigo: "Rascunho" de código em linguagem natural.**
- **Pensamento computacional: Abordagem lógica para dividir problemas.**

### Anotações

### **1. Definição de Lógica de Programação**

É a **organização estruturada de pensamentos** para resolver problemas por meio de instruções que um computador pode executar.

- **Antes do código**: Envolve planejar soluções em etapas claras (algoritmos).
- **Analogia do sanduíche**:
    - *Exemplo*: "Montar um sanduíche" requer uma sequência lógica (passo a passo).
    - Se você trocar a ordem (ex.: colocar alface antes do pão), o resultado falha.

### **2. O que é um Algoritmo?**

Uma **sequência ordenada de passos** para atingir um objetivo.

- **Exemplo cotidiano**:
    - *Calçar um sapato*:
        1. Pegar as meias.
        2. Vestir uma meia em cada pé.
        3. Colocar os sapatos.
        4. Amarrar os cadarços.
- Na programação, algoritmos viram **código** (ex.: **`if`**, **`for`**, funções).

### **3. Fluxo do Raciocínio Lógico**

1. **Entender o problema**: Qual é o objetivo?
2. **Planejar a solução**: Dividir em etapas (algoritmo).
3. **Escrever os passos**: Em pseudocódigo ou fluxograma.
4. **Transformar em código**: Usar linguagem de programação.
5. **Testar e ajustar**: Verificar se funciona e corrigir erros.

### **4. Por que Aprender Lógica de Programação?**

- **Base para tudo**: Desenvolvimento web, apps, jogos, IA, automação.
- **Desenvolve pensamento estruturado**:
    - Ajuda a **resolver problemas** não só na programação, mas na vida.
- **Facilita aprender linguagens**:
    - A lógica é universal; a sintaxe (como escrever) muda, mas o raciocínio não.

### **5. Exemplo Prático: "Fazer Café"**

- **Algoritmo**:
    1. Pegar a cafeteira.
    2. Colocar água no reservatório.
    3. Adicionar pó de café.
    4. Ligar a cafeteira.
    5. Esperar o café ficar pronto.
- Se um passo for pulado (ex.: esquecer a água), o café não sai.

<aside>

📌 **RESUMO**:

**Lógica de programação é:**

1. **Organizar ideias** em etapas claras (algoritmos).
2. **Traduzir** essas etapas para uma linguagem que o computador entenda.
3. **Aplicável** em qualquer área da tecnologia (e além).

**Por que importa?**

- Sem lógica, o código vira uma "receita de bolo sem ordem" — não funciona.
- Dominá-la é como aprender a **pensar antes de falar** (ou programar!).

**Dica final:**

Pratique criando algoritmos para tarefas do dia a dia (ex.: lavar louça, fazer café). Isso treina seu cérebro para o raciocínio lógico!

</aside>

---

### **Linguagens de Programação: A Ponte Entre Humanos e Computadores**

### Lembretes

- **Binário: Linguagem da máquina (0s e 1s).**
- **Sintaxe: "Gramática" do código.**
- **Interpretador vs. Compilador: Formas de executar código.**
- **Bugs: Erros no programa.**
- **JavaScript: Linguagem deste curso (vantagens).**

### Anotações

### **1. Por que Precisamos de Linguagens de Programação?**

- **Computadores só entendem binário (0s e 1s)**, mas humanos não pensam dessa forma.
- **Linguagens de programação são tradutoras**:
    - Convertem comandos escritos por nós (em sintaxe quase humana) em instruções que a máquina executa.
    - *Exemplo*: **`console.log("Olá, mundo!")`** → Traduzido para binário → Exibe a mensagem na tela.

### **2. Como Funciona uma Linguagem de Programação?**

- **Você escreve código** usando regras específicas (sintaxe).
- **O computador processa** esse código por meio de:
    - **Interpretadores** (executam linha por linha, como JavaScript).
    - **Compiladores** (transformam todo o código em binário de uma vez, como C++).
- **Analogia**:
    - Linguagem humana → Português/Inglês.
    - Linguagem de programação → JavaScript/Python.
    - Binário → "Idioma" da máquina.

### **3. Características das Linguagens**

- **Palavras-chave**: Comandos pré-definidos (ex.: **`if`**, **`for`**).
- **Sintaxe**: Regras de escrita (ex.: ponto e vírgula no JavaScript).
- **Flexibilidade**: Algumas são mais fáceis (Python), outras mais rigorosas (Java).
- **Criatividade**: Até emojis podem virar código (Emojicode), mas não são usadas profissionalmente.

### **4. Errar é Parte do Processo**

- **Bugs são normais**: Mensagens de erro ajudam a corrigir falhas.
- **Pesquisa constante**:
    - Programadores passam mais tempo lendo documentação e soluções (Stack Overflow) do que escrevendo código.
- **Filosofia**: Programar é **resolver problemas**, não decorar comandos.

### **5. Por que JavaScript no Curso?**

✔ **Popularidade**: Usada em 98% dos sites (front-end e back-end com Node.js).

✔ **Acesso fácil**: Roda no navegador sem instalação complexa.

✔ **Feedback imediato**: Veja resultados alterando uma linha de código.

✔ **Porta de entrada**: Ideal para lógica de programação e desenvolvimento web.

<aside>
📌 **RESUMO**:

1. Linguagens de programação **traduzem** comandos humanos para binário.
2. Cada linguagem tem **regras próprias** (sintaxe) e usos específicos.
3. **Erros são oportunidades de aprendizado** — pesquisar soluções é essencial.
4. **JavaScript** foi escolhida por ser:
    - **Acessível** (navegador).
    - **Versátil** (web, apps, servidores).
    - **Ideal para iniciantes**.

**Reflexão:**

Aprender uma linguagem de programação é como aprender a cozinhar:

- Você segue "receitas" (algoritmos).
- Comete erros (queimou o arroz?).
- Melhora com prática e ajustes.
</aside>

---

### **Criando um Jogo de Adivinhação em JavaScript: Primeiros Passos**

### Lembretes

- **VS Code: Editor de código recomendado.**
- **`alert()`: Função para exibir mensagens.**
- **Sintaxe: Regras de escrita do código (aspas, `;`).**
- **Número secreto: Lógica central do jogo.**
- **Fluxo de trabalho: Salvar → Atualizar navegador.**

### Anotações

### **1. Configuração do Ambiente**

- **Ferramenta usada**: Visual Studio Code (VS Code), editor popular para programação.
- **Arquivos do projeto**:
    - **`app.js`** (código JavaScript principal).
    - **`index.html`** (estrutura da página web).
    - **`style.css`** (estilos visuais).
    - **`img/`** (imagens do jogo).
- **HTML/CSS não são o foco**: O curso prioriza JavaScript (lógica de programação).

### **2. Entendendo o Jogo**

- **Objetivo**: Criar um jogo onde o computador escolhe um número secreto (1–100), e o jogador tenta adivinhar com dicas ("maior" ou "menor").
- **Exemplo humano**:
    - Guilherme adivinhou o número 29 após tentativas (42 → 20 → 30 → 29).

### **3. Primeiro Código: Exibindo uma Mensagem**

- **Função `alert()`**: Mostra uma caixa de diálogo no navegador.
    - Sintaxe:
        
        javascript
        
        ```
        alert('Mensagem aqui');
        ```
        
    - **Regras**:
        - Usar **aspas** (simples **`' '`** ou duplas **`" "`**), mas manter consistência.
        - Ponto e vírgula (**`;`**) no final (boa prática em JavaScript).
- **Passo a passo**:
    1. Abrir **`app.js`** no VS Code.
    2. Escrever:
        
        javascript
        
        ```
        alert('Boas-vindas ao jogo do Número Secreto');
        ```
        
    3. Salvar (**`Ctrl + S`**).
    4. Atualizar navegador (**`F5`**) para ver a mensagem.

### **4. Dicas Importantes**

- **Salvar sempre**: Alterações no código só surtem efeito após salvar (**`Ctrl + S`**).
- **Padronização**:
    - Escolha um tipo de aspas e use em todo o projeto (ex.: aspas simples).
    - Ponto e vírgula evita erros em certos casos.
- **Erros comuns**:
    - Esquecer aspas ou parênteses.
    - Não atualizar o navegador após mudanças.

<aside>
📌 **RESUMO**:

**O que aprendemos hoje?**

1. **Configuramos o projeto** no VS Code (foco em **`app.js`**).
2. **Criamos a primeira interação** com **`alert()`** para dar boas-vindas.
3. **Entendemos a lógica do jogo**:
    - Computador escolhe um número → jogador adivinha com dicas.

**Dica prática:**

- Teste outros textos no **`alert()`** (ex.: **`'Digite um número entre 1 e 100'`**) para ver as mudanças em tempo real!
</aside>

---

### **Armazenando Dados e Capturando Entradas no Jogo do Número Secreto**

### Lembretes

- **`let`: Palavra-chave para criar variáveis.**
- **camelCase: Convenção de nomeação (ex.: `numeroSecreto`).**
- **`prompt()`: Função para entrada de dados.**
- **Bug: Comportamento inesperado no código.**
- **Tipos de dados: Número vs. string.**

### Anotações

### **1. O Conceito de Variáveis**

- **O que são?** Espaços na memória para armazenar dados (como o número secreto).
- **Por que usar?** Para que o computador "lembre" de valores durante a execução do programa.
- **Exemplo humano**:
    - Mônica memorizou o número 29 → Na programação, usamos variáveis para esse fim.

### **2. Criando Variáveis em JavaScript**

- **Sintaxe**:
    
    javascript
    
    ```
    let nomeDaVariavel = valor;
    ```
    
- **Regras**:
    - Nomes sem acentos e em **camelCase** (ex.: **`numeroSecreto`**).
    - Nomes descritivos (evitar **`x`**, **`a`**).
- **Exemplo no jogo**:
    
    javascript
    
    ```
    let numeroSecreto = 29;// Armazena o número a ser adivinhado
    ```
    

### **3. Tipos de Dados**

- **Números**: Sem aspas (ex.: **`5`**, **`29`**).
- **Texto (strings)**: Com aspas (ex.: **`'Olá'`**).
- **Diferença crucial**:
    - **`29`** (número) → Pode ser usado em cálculos.
    - **`'29'`** (texto) → Não pode ser somado diretamente.

### **4. Interação com o Usuário**

- **`prompt()`**: Abre uma caixa para entrada de dados.
    
    javascript
    
    ```
    prompt('Escolha um número entre 1 e 30');// Captura o chute do jogador
    ```
    
- **Problema identificado**:
    - O jogo não valida o chute → Sempre exibe "Você acertou!" (bug).

### **5. Testando e Debugando**

- **Importância de testar erros**:
    - Exemplo: Mudar **`numeroSecreto`** para **`5`** e chutar **`4`** → Mensagem incorreta.
- **Próximo passo**:
    - Comparar o chute do usuário com **`numeroSecreto`** (usando condicionais).

<aside>
📌 **RESUMO**:

**O que aprendemos hoje?**

1. **Variáveis** armazenam informações temporárias (como **`numeroSecreto`**).
2. **`prompt()`** captura entradas do usuário, mas não as valida ainda.
3. **Testar cenários** (como chutes errados) revela bugs a serem corrigidos.

**Dica prática:**

- Troque o valor de **`numeroSecreto`** e teste diferentes chutes para entender o fluxo do programa!
</aside>

---

### **Comparando Chutes com Condicionais em JavaScript**

### Lembretes

- **`if`: Estrutura condicional**
- **`==`: Operador de comparação**
- **`console.log()`: Debugging**
- **Variável `chute`: Armazena entrada do usuário**
- **Fluxo condicional: Execução baseada em condições**

### Anotações

## **Ideias Centrais (Lado Direito)**

### **1. O Problema Identificado**

- O jogo atual sempre exibe "Você acertou!", mesmo com chutes errados
- **Exemplo**: Chutando 4 quando o número secreto é 5 ainda mostra vitória

### **2. Solução: Condicionais com `if`**

- **Sintaxe básica**:
    
    javascript
    
    ```
    if (condição) {
    // código executado se a condição for verdadeira}
    ```
    
- **Comparação com `==`**:
    - Diferente de **`=`** (atribuição)
    - Verifica igualdade de valor

### **3. Armazenando o Chute**

- Criamos uma variável para guardar a entrada do usuário:
    
    javascript
    
    ```
    let chute = prompt('Escolha um número entre 1 e 10');
    ```
    

### **4. Implementando a Verificação**

- Código completo:
    
    javascript
    
    ```
    let numeroSecreto = 5;
    let chute = prompt('Escolha um número entre 1 e 10');
    
    if (chute == numeroSecreto) {
      console.log("Isso aí! Você descobriu o número secreto (5)");
    }
    ```
    

### **5. Debugando com Console**

- **`console.log()`**:
    - Ferramenta essencial para desenvolvimento
    - Exibe mensagens apenas no console do navegador
    - Acessível via Inspecionar → Console

### **6. Testando os Cenários**

- **Acerto (chute = 5)**:
    - Mensagem aparece no console
- **Erro (chute = 3)**:
    - Nada acontece (precisamos implementar o **`else`**)

<aside>
📌 **RESUMO**:

**O que aprendemos hoje?**

1. Como usar **condicionais** para tomar decisões no código
2. A diferença crucial entre **`=`** (atribuição) e **`==`** (comparação)
3. A importância do **console** para debuggar aplicações
4. Como armazenar entradas do usuário em **variáveis**

**Dica prática:**

Experimente modificar a condição para:

javascript

```
if (chute > numeroSecreto) {
  console.log("O número secreto é menor!");
}
```

---

**Para Reflexão:**

"Programação é 10% escrever código e 90% entender por que não está funcionando."

- Neste caso, usamos **`console.log()`** para nos ajudar nesse processo de entendimento!
</aside>

---

### **Sintaxe, Variáveis e Estruturas de Decisão em JavaScript**

Lembretes

- **Sintaxe: Regras de escrita do código.**
- **`let`: Declara variáveis.**
- **`alert()`/`prompt()`: Interação com usuário.**
- **`if/else`: Tomada de decisão.**
- **Operadores: `===`, `>`, `<`, etc.**

### Anotações

### **1. Sintaxe: As Regras do JavaScript**

- **Definição**: Conjunto de regras que definem como escrever código válido.
- **Importância**:
    - Ordem dos comandos, símbolos e pontuação são cruciais.
    - Erros comuns: esquecer **`}`**, **`;`** ou trocar aspas (**`'`** por **`"`**).
- **Analogia**:
    
    *"Em português, 'Eu pão como' é entendível, mas incorreto. Em código, o computador não entende sintaxe errada."*
    

### **2. Variáveis: "Baús" de Informação**

- **Função**: Armazenar dados para uso posterior.
- **Sintaxe**:
    
    javascript
    
    ```
    let nomeDaVariavel = valor;
    ```
    
- **Exemplos**:
    
    javascript
    
    ```
    let nome = "Ana";// String (texto)
    let idade = 25;// Número
    let saldo = 1000.50;// Número decimal
    ```
    
- **Boas Práticas**:
    - Nomes descritivos (**`nomeUsuario`** em vez de **`x`**).
    - **`camelCase`** para nomes compostos.

### **3. Funções Básicas de Entrada/Saída**

| **Função** | **Uso** | **Exemplo** |
| --- | --- | --- |
| **`alert()`** | Exibe mensagem ao usuário | **`alert("Bem-vindo!")`** |
| **`prompt()`** | Captura entrada do usuário | **`let nome = prompt("Seu nome?")`** |

### **4. Estruturas de Decisão (`if/else`)**

- **Lógica**: Executar ações diferentes com base em condições.
- **Sintaxe**:
    
    javascript
    
    ```
    if (condição) {
    // Código se verdadeiro} else {
    // Código se falso}
    ```
    
- **Operadores de Comparação**:
    
    
    | **Operador** | **Significado** | **Exemplo** |
    | --- | --- | --- |
    | **`===`** | Igualdade estrita (valor e tipo) | **`idade === 25`** |
    | **`!==`** | Diferente | **`nome !== "Ana"`** |
    | **`>`** | Maior que | **`saldo > 1000`** |
    | **`<`** | Menor que | **`temperatura < 30`** |
    | **`>=`** | Maior ou igual | **`idade >= 18`** |
    | **`<=`** | Menor ou igual | **`altura <= 1.90`** |
- **Exemplo Prático**:
    
    javascript
    
    ```
    let temPao = prompt("Tem pão? (sim/não)");
    if (temPao === "sim") {
      alert("Faça um sanduíche!");
    } else {
      alert("Coma miojo.");
    }
    ```
    

<aside>
📌 **RESUMO**:

**Principais Conceitos:**

1. **Sintaxe** é a base: um erro de pontuação quebra o código.
2. **Variáveis** armazenam dados para reutilização.
3. **`if/else`** permite criar lógicas condicionais.

**Dica de Prática:**

Experimente modificar este código no VS Code:

javascript

</aside>