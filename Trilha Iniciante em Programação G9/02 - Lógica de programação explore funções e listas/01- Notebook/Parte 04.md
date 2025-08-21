### **Arrays (Listas) em JavaScript**

### Lembretes

- Array (Lista)
- Índices
- **`.length`**
- Acesso a elementos
- Documentação JavaScript

### Anotações

Na aula, Mônica e Guilherme discutem como evitar a repetição de números sorteados em um jogo. Para isso, introduzem o conceito de **Array (lista)** em JavaScript, uma estrutura de dados fundamental presente em várias linguagens de programação.

1. **O que é um Array?**
    - Um Array é uma estrutura que armazena múltiplos valores em uma única variável.
    - Sintaxe: **`let lista = [elemento1, elemento2, ...];`** (usando colchetes **`[]`**).
    - Exemplo:
        
        javascript
        
        ```
        let frutas = ["Maçã", "Banana"];
        let numeros = [1, 5, 9];
        ```
        
2. **Acessando Elementos**
    - Cada elemento tem um **índice**, começando em **0**.
        - Exemplo:
            
            javascript
            
            ```
            numeros[0] → retorna 1
            numeros[1] → retorna 5
            ```
            
    - Tentar acessar um índice inexistente (ex: **`lista[90]`**) retorna **`undefined`**.
3. **Tamanho da Lista (`.length`)**
    - O método **`.length`** retorna a quantidade de elementos.
        - Exemplo:
            
            javascript
            
            ```
            numeros.length → retorna 3
            ```
            
    - Para pegar o **último elemento**, usa-se:
        
        javascript
        
        ```
        lista[lista.length - 1]
        ```
        
        (Pois se o tamanho é 3, **`3 - 1 = 2`**, que é o último índice).
        
4. **Aplicação no Projeto**
    - A ideia é criar uma lista para armazenar números já sorteados e evitar repetições.
    - Futuramente, métodos como inserção, remoção e busca podem ser explorados.

<aside>

📌 **RESUMO**:

Arrays são essenciais para organizar e manipular conjuntos de dados. Neste contexto, serão usados para controlar os números sorteados, garantindo que não se repitam. A documentação do JavaScript (MDN) é uma ótima fonte para aprofundamento.

</aside>

---

### **Implementando Lista de Números Sorteados em JavaScript**

### Lembretes

- Arrays (Listas)
- Método `includes()`
- Recursão
- Método `push()`
- Debug com `console.log()`

### Anotações

Na aula, Mônica e Guilherme implementam uma **lista de números já sorteados** para evitar repetições no jogo.

1. **Criação da Lista Vazia**
    - Declarada no início do código (**`let listaDeNumerosSorteados = []`**), pois o JavaScript é executado linha a linha.
    - Uma lista vazia é criada com **`[]`**, assim como strings vazias usam **`""`**.
2. **Modificação da Função `gerarNumeroAleatorio()`**
    - **Passo 1:** Gera um número aleatório e armazena em **`numeroEscolhido`**.
        
        javascript
        
        ```
        let numeroEscolhido = parseInt(Math.random() * 3 + 1);// Números de 1 a 3 para teste
        ```
        
    - **Passo 2:** Verifica se o número já está na lista com **`includes()`**.
        - Se **sim**, chama a função novamente (**recursão**):
            
            javascript
            
            ```
            if (listaDeNumerosSorteados.includes(numeroEscolhido)) {
                return gerarNumeroAleatorio();
            }
            ```
            
        - Se **não**, adiciona o número à lista com **`push()`** e retorna o valor:
            
            javascript
            
            ```
            else {
                listaDeNumerosSorteados.push(numeroEscolhido);
                console.log(listaDeNumerosSorteados);// Debugreturn numeroEscolhido;
            }
            ```
            
3. **Métodos Importantes**
    - **`includes()`**: Verifica se um elemento existe na lista (retorna **`true`** ou **`false`**).
    - **`push()`**: Adiciona um elemento ao final da lista.
    - **`console.log()`**: Usado para visualizar a lista durante o desenvolvimento.
4. **Testes e Problema Encontrado**
    - Ao acertar o número ou iniciar um novo jogo, o Console exibe a lista atualizada.
    - **Erro:** Se todos os números possíveis (1 a 3) forem sorteados, a recursão entra em loop infinito (será resolvido no próximo vídeo).
5. **Observações**
    - **Recursão:** Útil, mas requer cuidado para não sobrecarregar o sistema.
    - **Nomes de Métodos:** Variam entre linguagens (ex: **`push()`** no JavaScript pode ser **`append()`** em Python).

<aside>
📌 **RESUMO**:

A lista **`listaDeNumerosSorteados`** agora evita repetições, usando métodos nativos do JavaScript (**`includes()`** e **`push()`**). O próximo passo será tratar o caso em que todos os números já foram sorteados.

**Detalhes Adicionais Incluídos:**

- Explicação sobre a posição da declaração da lista (linha 1).
- Uso de **`console.log()`** para debug.
- Ajuste no intervalo de números (1 a 3) para facilitar testes.
- Discussão sobre recursão e cuidados com desempenho.
- Comparação com outras linguagens (ex: diferença no nome de métodos).
</aside>

---

### **Solução para Repetição de Números Sorteados e Limpeza de Lista**

### Lembretes

- Limite de números
- Esvaziar lista (`lista = []`)
- Variável dinâmica (`numeroLimite`)
- Recursão e loop infinito
- Sincronização de valores

### Anotações

Mônica e Guilherme resolvem o problema de **loop infinito** quando todos os números possíveis já foram sorteados.

1. **Identificação do Problema**
    - Ao sortear todos os números possíveis (1 a 3), a função entrava em **recursão infinita** (chamando **`gerarNumeroAleatorio()`** repetidamente).
    - **Mensagem de erro:** *"Tamanho máximo de chamadas para **`Math.random()`** excedido"*.
2. **Solução Implementada**
    - **Passo 1:** Verificar o tamanho da lista com **`listaDeNumerosSorteados.length`**.
    - **Passo 2:** Se a lista estiver cheia (todos os números sorteados), **esvaziar a lista**:
        
        javascript
        
        ```
        if (quantidadeDeElementosNaLista == 3) {
            listaDeNumerosSorteados = [];// Limpa a lista}
        ```
        
    - **Passo 3:** Ajustar o multiplicador em **`Math.random()`** para **3** (equivalente ao limite de números).
3. **Melhoria: Variável Dinâmica (`numeroLimite`)**
    - Criada uma variável global para evitar **hardcoding** (valores fixos no código):
        
        javascript
        
        ```
        let numeroLimite = 10;// Define o intervalo de sorteio (1 a 10)
        ```
        
    - Atualização na função:
        
        javascript
        
        ```
        let numeroEscolhido = parseInt(Math.random() * numeroLimite + 1);
        if (quantidadeDeElementosNaLista == numeroLimite) {
            listaDeNumerosSorteados = [];
        }
        ```
        
4. **Testes e Resultados**
    - **Comportamento esperado:**
        - Ao sortear todos os números (ex: 1, 2, 3), a lista é **resetada**.
        - Novo sorteio começa com uma lista vazia.
    - **Exemplo no Console:**
        - Acertou o número 3 → lista é limpa → próximo sorteio adiciona novo número ao índice 0.
5. **Cuidados Importantes**
    - **Sincronização:** Garantir que **`numeroLimite`** seja o mesmo no **`Math.random()`** e na verificação.
    - **Legibilidade:** Usar nomes claros (ex: **`quantidadeDeElementosNaLista`** em vez de valores fixos como **`3`**).

<aside>
📌 **RESUMO**:

A solução combina **verificação de lista cheia** e **limpeza automática**, usando uma variável dinâmica (**`numeroLimite`**) para flexibilidade. Isso evita erros de recursão infinita e mantém o jogo funcional mesmo após todos os números serem sorteados.

---

**Detalhes Adicionais:**

- **Por que esvaziar a lista?**
    - Permite reiniciar o ciclo de sorteios sem repetições imediatas.
- **Debug:**
    - **`console.log(listaDeNumerosSorteados)`** ajuda a monitorar o estado da lista.
- **Aplicação em outros contextos:**
    - Útil para sistemas de sorteio, quizzes ou qualquer lógica que exija exclusividade temporária.
</aside>

---

### **Resolvendo o Problema de Repetição de Números Sorteados em JavaScript**

### Lembretes

- Lista de números sorteados
- Limite máximo de sorteios
- Recursão infinita
- Esvaziamento de array
- Variável dinâmica

### Anotações

Nesta aula, Mônica e Guilherme enfrentam um problema crítico no jogo: quando todos os números possíveis eram sorteados, o programa entrava em **recursão infinita**, gerando um erro relacionado ao limite de chamadas da função **`Math.random()`**.

1. **Identificação do Problema**
    - Ao limitar os números sorteados de 1 a 3, todos eram eventualmente escolhidos (ex: 4, 1, 3, 2).
    - Como o programa não permitia repetições (usando **`listaDeNumerosSorteados`**), não havia mais números disponíveis, causando um loop infinito na função **`gerarNumeroAleatorio()`**.
2. **Solução Implementada**
    - **Passo 1:** Verificar o tamanho da lista com **`listaDeNumerosSorteados.length`**.
    - **Passo 2:** Se a lista atingisse o limite (3 números), ela era **esvaziada**:
        
        javascript
        
        ```
        if (quantidadeDeElementosNaLista == 3) {
            listaDeNumerosSorteados = [];// Limpa a lista}
        ```
        
    - **Passo 3:** Ajustar o multiplicador em **`Math.random()`** para 3 (coerente com o limite de números).
3. **Testes e Comportamento Observado**
    - Ao acertar o último número possível (ex: 3) e clicar em "Novo jogo", a lista era resetada corretamente.
    - O console mostrava a lista sendo esvaziada e um novo número sendo adicionado ao índice 0.
4. **Melhoria: Variável Dinâmica (`numeroLimite`)**
    - Para evitar **hardcoding** (valores fixos), criou-se uma variável global:
        
        javascript
        
        ```
        let numeroLimite = 10;// Define o intervalo de sorteio (1 a 10)
        ```
        
    - Atualização na função **`gerarNumeroAleatorio()`**:
        
        javascript
        
        ```
        let numeroEscolhido = parseInt(Math.random() * numeroLimite + 1);
        if (quantidadeDeElementosNaLista == numeroLimite) {
            listaDeNumerosSorteados = [];
        }
        ```
        
    - **Vantagem:** Facilita ajustes futuros (ex: mudar o limite para 20 sem alterar múltiplos locais do código).
5. **Cuidados e Boas Práticas**
    - **Sincronização:** Garantir que **`numeroLimite`** seja usado consistentemente (no sorteio e na verificação).
    - **Legibilidade:** Nomes descritivos como **`quantidadeDeElementosNaLista`** tornam o código mais compreensível.
    - **Debug:** Uso de **`console.log(listaDeNumerosSorteados)`** para monitorar o estado da lista durante o desenvolvimento.

**Detalhes Adicionais:**

- **Por que esvaziar a lista?**
    - Permite reiniciar o ciclo de sorteios sem repetições imediatas, mantendo a aleatoriedade.
- **Contexto Geral:**
    - Essa lógica é útil em qualquer sistema que exija exclusividade temporária (ex: sorteios, quizzes, geração de IDs únicos).
- **Erro Comum:**
    - Esquecer de sincronizar o valor do limite (ex: usar **`3`** em um lugar e **`numeroLimite`** em outro) pode causar bugs sutis.

**Exemplo Prático:**

Antes da correção:

- Sorteios: 4 → 1 → 3 → 2 → **ERRO** (lista cheia).
    
    Após a correção:
    
- Sorteios: 4 → 1 → 3 → 2 → **Lista esvaziada** → Novo ciclo começa (ex: 5 → ...).

<aside>
📌 **RESUMO**:

A solução combinou **verificação de lista cheia** e **limpeza automática**, usando uma variável dinâmica para flexibilidade. Isso eliminou o erro de recursão infinita e garantiu que o jogo funcionasse corretamente, mesmo após todos os números serem sorteados.

</aside>

---

### **Arrays em JavaScript: Conceitos Básicos e Aplicações**

### Lembretes

- Array (Lista)
- Índices
- Métodos (`push`, `pop`)
- Tipos de dados
- Linguagens que usam arrays

### Anotações

**O que são Arrays?**

Arrays em JavaScript são estruturas de dados que permitem armazenar múltiplos valores em uma única variável. Eles podem conter diferentes tipos de dados, como números, strings, objetos e até outras arrays. Cada valor é associado a um **índice numérico**, começando do **0**.

**Criação e Acesso:**

- Declara-se uma array usando colchetes **`[]`**.
    
    javascript
    
    ```
    let frutas = ["Maçã", "Uva", "Laranja"];
    ```
    
- Os elementos são acessados via índice:
    
    javascript
    
    ```
    console.log(frutas[0]);// "Maçã"
    console.log(frutas[2]);// "Laranja"
    ```
    

**Modificando Arrays:**

- **Adicionar elementos:**
    
    Usa-se o método **`push()`** para inserir no final.
    
    javascript
    
    ```
    frutas.push("Morango");// ["Maçã", "Uva", "Laranja", "Morango"]
    ```
    
- **Remover elementos:**
    
    O método **`pop()`** remove o último elemento.
    
    javascript
    
    ```
    frutas.pop();// Remove "Morango"
    ```
    

**Linguagens que Utilizam Arrays:**

Além do JavaScript, outras linguagens como **Python, Java, C++, C#, Ruby, PHP, Swift, Kotlin e Go** também implementam arrays ou estruturas similares.

**Importância das Arrays:**

- **Organização eficiente** de dados.
- **Facilidade de manipulação** (adição, remoção, acesso).
- **Fundamental para algoritmos** e aplicações dinâmicas.

<aside>
📌 **RESUMO**:

Dominar arrays é essencial para programação, pois permite **armazenar, acessar e modificar dados** de forma estruturada, melhorando a eficiência no desenvolvimento de software.

</aside>