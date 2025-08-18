### **Funções com Parâmetros em JavaScript**

### Lembretes

- Funções
- Parâmetros
- **`document.querySelector()`**
- **`innerHTML`**
- Reutilização de código
- Pair Programming
- Boas práticas

### Anotações

### **1. Introdução ao Problema**

A aula começa com a análise de um código JavaScript que manipula elementos HTML (**`h1`** e **`p`**). Inicialmente, o código repete a mesma lógica para cada elemento:

- Seleciona um elemento (**`document.querySelector()`**).
- Armazena em uma variável (**`let titulo`**, **`let paragrafo`**).
- Altera seu conteúdo (**`innerHTML`**).

Apesar de funcionar, essa abordagem se torna repetitiva e pouco eficiente, principalmente em projetos maiores com muitos elementos.

### **2. Identificando Padrões e Melhorando o Código**

Guilherme e Mônica destacam que:

- O código segue um padrão: **selecionar um elemento → modificar seu texto**.
- As únicas diferenças são:
    - A **tag HTML** (**`h1`**, **`p`**).
    - O **texto** a ser inserido.

Isso indica que podemos **generalizar** esse comportamento em uma **função reutilizável**.

### **3. Criando a Função com Parâmetros**

Para evitar repetição, é criada a função:

javascript

```
function exibirTextoNaTela(tag, texto) {
    let campo = document.querySelector(tag);
    campo.innerHTML = texto;
}
```

- **Parâmetros:** **`tag`** (elemento HTML) e **`texto`** (conteúdo a ser exibido).
- **Chamada da função:**
    
    javascript
    
    ```
    exibirTextoNaTela('h1', 'Jogo do número secreto');
    exibirTextoNaTela('p', 'Escolha um número entre 1 e 10');
    ```
    
- **Vantagens:**
    - **Redução de código repetido.**
    - **Facilidade de manutenção** (alterações são feitas em um único lugar).

### **4. Boas Práticas e Pair Programming**

- **Nomenclatura de funções:** Usar **camelCase** com a primeira letra de cada palavra em maiúscula (exceto a primeira).
- **Pontuação:** Sempre usar **`;`** ao final das linhas.
- **Trabalho em dupla (Pair Programming):** Ajuda a identificar detalhes como esquecimento de **`;`** e melhora a qualidade do código.

### **5. Ordem de Execução no JavaScript**

- O JavaScript **interpreta funções antes de executar o código**, então tanto faz declarar a função antes ou depois de chamá-la.
- **Boa prática:** Declarar funções primeiro para melhor organização.

### **6. Testando o Código**

- Ao recarregar a página, os textos continuam sendo exibidos corretamente.
- O botão "Chutar" ainda funciona, mostrando a mensagem no console.

<aside>

📌 **RESUMO**:

A aula reforça a importância de:

- **Evitar repetição de código** usando funções com parâmetros.
- **Seguir boas práticas** para escrever um código mais limpo e eficiente.
- **Trabalhar em equipe** para identificar e corrigir pequenos erros.

**Resultado final:** Um código mais enxuto, legível e fácil de manter! 🚀

</aside>

---

### **Funções com Retorno**

### Lembretes

- Funções com retorno (**`return`**)
- **`Math.random()`**
- **`parseInt()`**
- Variáveis armazenando funções
- Tipos de funções (com/sem parâmetros, com/sem retorno)
- Console.log para depuração

### Anotações

### **1. Introdução à Nova Funcionalidade**

Mônica e Guilherme introduzem uma nova função para **gerar um número aleatório**, complementando as funções já criadas (**`exibirTextoNaTela`** e **`verificarChute`**).

### **2. Criando a Função `gerarNumeroAleatorio`**

- **Declaração da função:**
    
    javascript
    
    ```
    function gerarNumeroAleatorio() {
        return parseInt(Math.random() * 10 + 1);
    }
    ```
    
    - **`Math.random()`**: Gera um número decimal entre 0 (inclusivo) e 1 (exclusivo).
    - **`10 + 1`**: Ajusta o intervalo para 1 a 10.
    - **`parseInt()`**: Converte o resultado em um número inteiro.
    - **`return`**: Retorna o valor gerado para ser usado fora da função.

### **3. Armazenando o Retorno em uma Variável**

- A variável **`numeroSecreto`** recebe o valor retornado pela função:
    
    javascript
    
    ```
    let numeroSecreto = gerarNumeroAleatorio();
    ```
    
- **Importante:** A função **precisa do `return`** para que o valor seja atribuído à variável.

### **4. Tipos de Funções**

Guilherme explica as diferenças entre:

1. **Funções sem parâmetros e sem retorno** (ex: **`verificarChute`**).
2. **Funções com parâmetros e sem retorno** (ex: **`exibirTextoNaTela`**).
3. **Funções com retorno** (ex: **`gerarNumeroAleatorio`**).

### **5. Testando a Função**

- Para verificar o funcionamento, o **`console.log(numeroSecreto)`** foi adicionado à função **`verificarChute`**.
- **Comportamento observado:**
    - O número é gerado **uma única vez** (quando a página é carregada).
    - Clicar no botão "Chutar" **não regenera** o número, apenas exibe o valor já armazenado.
    - Para gerar um novo número, é necessário **recarregar a página**.

### **6. Boas Práticas e Aprendizados**

- **Organização do código:** Funções isolam comportamentos específicos, facilitando a manutenção.
- **Depuração com `console.log`:** Útil para verificar valores em tempo de execução.
- **Atribuição de funções a variáveis:** Demonstra como funções podem ser tratadas como valores.

<aside>
📌 **RESUMO**:

- Funções com retorno são essenciais quando precisamos **obter um resultado** para uso posterior.
- A combinação de **parâmetros** e **retorno** torna as funções versáteis para diferentes cenários.
- O uso de **`Math.random()`** e **`parseInt()`** mostra como funções nativas do JavaScript podem ser integradas em funções personalizadas.
</aside>

---

### **Entrada de Dados e Comparações: Trabalhando com Inputs e Booleanos**

### Lembretes

- **`input`** HTML
- **`.value`**
- Comparação (**`==`**)
- Tipo booleano (**`true`**/**`false`**)
- Depuração com **`console.log`**

### Anotações

### **1. O Campo de Input no HTML**

No arquivo **`index.html`**, temos um campo onde o jogador digita seu palpite:

html

```
<input type="number" min="1" max="10" class="container__input">
```

- **Funcionalidade:** Permite que o usuário digite um número entre 1 e 10.
- **Exemplo:** Se digitar **`5`** e clicar em "Chutar", queremos comparar esse valor com o **`numeroSecreto`**.

### **2. Capturando o Valor do Input**

Na função **`verificarChute()`**, usamos:

javascript

```
let chute = document.querySelector('input').value;
```

- **`document.querySelector('input')`**: Seleciona o campo de input.
- **`.value`**: Pega o valor digitado (ex: **`"5"`**).
- **Importante:** Sem o **`.value`**, pegaríamos o elemento HTML, não o número digitado!

### **3. Comparando Chute e Número Secreto**

Usamos **`==`** para comparar os valores:

javascript

```
console.log(chute == numeroSecreto);
```

- **`==`**: Verifica se os valores são iguais (não confundir com **`=`**, que é para atribuição).
- **Retorno:**
    - **`true`** se forem iguais (acertou).
    - **`false`** se forem diferentes (errou).

### **4. Entendendo o Tipo Booleano**

- **O que é?** Um tipo de dado que só pode ser **`true`** (verdadeiro) ou **`false`** (falso).
- **Exemplo no jogo:**
    - Digitar **`5`** com **`numeroSecreto = 5`** → **`true`**.
    - Digitar **`2`** com **`numeroSecreto = 8`** → **`false`**.
- **Por que aprendemos isso?**
    - Toda comparação em programação retorna um booleano.
    - Esses valores serão essenciais para tomar decisões no jogo (ex: exibir "Acertou!" ou "Errou!").

### **5. Testando na Prática**

- **Passo a passo:**
    1. Recarregue a página (o **`numeroSecreto`** é gerado).
    2. Digite um número no input.
    3. Clique em "Chutar" e verifique o console:
        - Se aparecer **`true`**, você acertou!
        - Se aparecer **`false`**, tente novamente.
- **Dica:** Use **`console.log(numeroSecreto)`** para "trapacear" e descobrir o número secreto durante os testes 😉.

<aside>
📌 **RESUMO**:

- **Aprendemos:**
    - Como pegar valores de inputs com **`.value`**.
    - Como comparar valores e entender booleanos.
    - A importância da depuração com **`console.log`**.
</aside>

---

### **Anatomia de uma função em JavaScript**

### Lembretes

- Função

### Anotações

Vamos destrinchar a **anatomia de uma função em JavaScript** em partes, com um exemplo bem básico. Olha só:

```jsx
function saudacao(nome) {
  return "Olá, " + nome + "!";
}
```

Agora vamos entender **cada parte** dessa função:

---

🔹 **1. Palavra-chave `function`**

É assim que você diz ao JavaScript que está criando uma função.

🔹 **2. Nome da função: `saudacao`**

Esse é o identificador que você usa para "chamar" a função depois.

🔹 **3. Parênteses com parâmetros: `(nome)`**

Esses são os dados que a função vai receber para trabalhar. Neste caso, o parâmetro é `nome`.

🔹 **4. Chaves `{ ... }`**

Dentro dessas chaves fica o **corpo da função**, ou seja, o que ela vai fazer.

🔹 **5. `return`**

É a saída da função. Tudo o que estiver depois do `return` será o valor final que a função entrega.

### 🧠 Lembra disso:

- **Parâmetro** é o **"espaço reservado"** na definição da função — é como uma **caixinha com nome** que vai receber um valor.
- **Argumento** é o **valor real** que você passa quando **chama** a função.

---

Vamos olhar pra esse trecho de novo:

```jsx
function saudacao(nome) {
  return "Olá, " + nome + "!";
}
```

Aqui:

- `nome` → é o **parâmetro** (definido na criação da função)

Agora, quando você faz isso:

```jsx
let nome = prompt('Digite seu nome');
let mensagem = saudacao(nome)
```

Aqui:

- `nome` (a variável com o valor digitado pelo usuário) é o **argumento** que você está passando na chamada da função `saudacao(nome)`.

---

✅ Ou seja:

- **Parâmetro:** `nome` (dentro da função)
- **Argumento:** o valor passado para a função, que veio de `prompt('Digite seu nome')`

<aside>
📌 **RESUMO**:

</aside>

---

### **Tipos de Funções em JavaScript**

### Lembretes

- Funções sem retorno
- Funções com parâmetros
- Arrow functions
- Funções anônimas
- Reutilização de código

### Anotações

### **1. O Que São Funções?**

Funções são blocos de código **reutilizáveis** que executam uma tarefa específica. Elas ajudam a:

- **Organizar** o código.
- **Evitar repetição**.
- **Facilitar a manutenção**.

### **2. Tipos de Funções em JavaScript**

| **Tipo de Função** | **Exemplo** | **Quando Usar** |
| --- | --- | --- |
| **Sem retorno e sem parâmetro** | **`function saudacao() { alert("Olá!"); }`** | Para ações simples que não precisam de entrada ou saída. |
| **Sem retorno e com parâmetro** | **`function cumprimentar(nome) { console.log("Olá, " + nome); }`** | Quando a função precisa receber dados, mas não retorna nada. |
| **Com retorno e sem parâmetro** | **`function gerarNumero() { return Math.random(); }`** | Para gerar valores sem depender de entradas externas. |
| **Com retorno e com parâmetro** | **`function soma(a, b) { return a + b; }`** | Quando a função processa dados e retorna um resultado. |
| **Função anônima** | **`let quadrado = function(x) { return x * x; };`** | Usada quando a função é atribuída a uma variável. |
| **Arrow function** | **`let cubo = x => x * x * x;`** | Forma mais curta e moderna para funções simples. |

### **3. Quando Usar Cada Tipo?**

- **Funções simples** (sem parâmetros/retorno):
    - Exemplo: Mostrar uma mensagem fixa (**`console.log("Bem-vindo!")`**).
- **Funções com parâmetros**:
    - Exemplo: Personalizar uma mensagem (**`cumprimentar("Maria")`**).
- **Funções com retorno**:
    - Exemplo: Calcular um valor (**`let resultado = soma(2, 3);`**).
- **Arrow functions**:
    - Exemplo: Funções curtas em uma linha (**`let dobro = x => x * 2;`**).

### **4. Por Que Isso Importa?**

- **Eficiência:** Evita repetir o mesmo código várias vezes.
- **Legibilidade:** Divide o programa em partes menores e mais compreensíveis.
- **Flexibilidade:** Permite adaptar o código facilmente (ex: mudar só a função em vez de vários lugares).

### **5. Dicas Práticas**

1. **Nomeie funções claramente**:
    - Ruim: **`function x(a, b) { ... }`**
    - Bom: **`function calcularArea(largura, altura) { ... }`**
2. **Use arrow functions para simplificar**:
    - Antes: **`let soma = function(a, b) { return a + b; };`**
    - Depois: **`let soma = (a, b) => a + b;`**
3. **Funções devem ter uma única responsabilidade**:
    - Ruim: Uma função que calcula, imprime e salva no banco de dados.
    - Bom: Funções separadas para cada tarefa.

### 🟡 1. **Sem retorno e sem parâmetro**

```jsx
function saudacao() {
  console.log("Olá, tudo bem?");
}

saudacao(); // Executa a função, mostra mensagem no console
```

✅ Só excuta algo — **não recebe nada e não retorna nada**.

---

### 🟡 2. **Sem retorno e com parâmetro**

```jsx
function cumprimentar(nome) {
  console.log("Olá, " + nome + "!");
}

cumprimentar("Lucas"); // Exibe: Olá, Lucas
```

✅ **Recebe um valor** (parâmetro), **usa**, mas **não devolve nada**.

---

### 🟡 3. **Com retorno e sem parâmetro**

```jsx
function gerarNumeroAleatorio() {
  return Math.random(); // Retorna um número entre 0 e 1
}

let numero = gerarNumeroAleatorio();
console.log(numero);
```

✅ **Não recebe nada**, mas **devolve um valor** (retorno).

---

### 🟡 4. **Com retorno e com parâmetro**

```jsx

function somar(a, b) {
  return a + b;
}

let resultado = somar(3, 4); // resultado = 7
console.log(resultado);
```

 **Recebe valores** e **devolve um resultado**.

---

### 🟡 5. **Função anônima**

```jsx
let saudacao = function() {
  console.log("Olá!");
};

saudacao(); // Executa a função
```

✅ **Sem nome** na definição, geralmente guardada em uma variável.

---

### 🟡 6. **Arrow function**

```jsx
let quadrado = x => x * x;

console.log(quadrado(5)); // 25
```

✅ É uma forma **mais curta e moderna** de escrever funções.

<aside>
📌 **RESUMO**:

"Funções são como ferramentas: cada tipo tem um uso específico, e dominá-las torna seu código mais poderoso e organizado!" 🛠️🚀

</aside>