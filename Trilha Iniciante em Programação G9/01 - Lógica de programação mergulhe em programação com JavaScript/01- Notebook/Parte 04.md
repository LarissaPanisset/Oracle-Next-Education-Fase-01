### Operadores Lógicos em JavaScript

### Lembretes

- Operadores lógicos
- **`&&`** (AND)
- **`||`** (OR)
- **`!`** (NOT)
- Comparação (**`==`**, **`!=`**, **`<`**, **`>`**, **`<=`**, **`>=`**)
- Condicionais em JavaScript

### Anotações

### **Introdução**

Em JavaScript, os operadores lógicos são fundamentais para criar estruturas condicionais que permitem ao programa tomar decisões com base em diferentes situações. Eles avaliam expressões e retornam valores booleanos (**`true`** ou **`false`**), possibilitando o controle do fluxo do programa.

---

### **1. Operador AND (`&&`)**

- **Função:** Verifica se **todas** as condições são verdadeiras.
- **Exemplo:**
    
    javascript
    
    ```
    let idade = 25;
    let possuiCarteira = true;
    
    if (idade > 18 && possuiCarteira) {
      console.log("Pode dirigir!");// Executa se AMBAS condições forem verdadeiras} else {
      console.log("Não pode dirigir.");
    }
    ```
    
- **Resultado:**
    - **`true && true`** → **`true`**
    - **`true && false`** → **`false`**

---

### **2. Operador OR (`||`)**

- **Função:** Verifica se **pelo menos uma** das condições é verdadeira.
- **Exemplo:**
    
    javascript
    
    ```
    let temMaça = false;
    let temBanana = true;
    
    if (temMaça || temBanana) {
      console.log("Você tem frutas!");// Executa se UMA ou AMBAS forem verdadeiras} else {
      console.log("Não tem frutas.");
    }
    ```
    
- **Resultado:**
    - **`false || true`** → **`true`**
    - **`false || false`** → **`false`**

---

### **3. Operadores de Comparação**

São usados para comparar valores antes de aplicar operadores lógicos:

| **Operador** | **Nome** | **Exemplo** | **Resultado** |
| --- | --- | --- | --- |
| **`==`** | Igual | **`A == B`** | Verdadeiro se **`A`** for igual a **`B`** |
| **`!=`** | Diferente | **`A != B`** | Verdadeiro se **`A`** **não** for igual a **`B`** |
| **`<`** | Menor que | **`A < B`** | Verdadeiro se **`A`** for menor que **`B`** |
| **`>`** | Maior que | **`A > B`** | Verdadeiro se **`A`** for maior que **`B`** |
| **`<=`** | Menor ou igual | **`A <= B`** | Verdadeiro se **`A`** for menor **ou** igual a **`B`** |
| **`>=`** | Maior ou igual | **`A >= B`** | Verdadeiro se **`A`** for maior **ou** igual a **`B`** |

---

### **4. Operador de Negação (`!`)**

- **Função:** Inverte o valor booleano (**`true`** → **`false`** / **`false`** → **`true`**).
- **Exemplo:**
    
    javascript
    
    ```
    let A = 10;
    let B = 10;
    
    if (!(A == B)) {// NEGA a igualdade
      console.log("A e B são diferentes.");
    } else {
      console.log("A e B são iguais.");// Será executado}
    ```
    

| Operador | Operação | Exemplo |
| --- | --- | --- |
| > | Maior que | (a > b) |
| < | Menor que | (a < b) |
| >= | Maior ou igual a | (a >= b) |
| <= | Menor ou igual a | (a <= b) |
| == | Igual a | (a == b) |
| != | Diferente de | (a !== b) |
| === | Idêntico a | (a === b) |
| !== | Não idêntico a | (a !== b) |
| && | E/and | (a && b) |
| ll | Ou/or | (a ll b) |

<aside>

📌 **RESUMO**:

Os operadores lógicos (**`&&`**, **`||`**, **`!`**) e de comparação são essenciais para criar condições complexas em JavaScript. Eles permitem:

- **Combinação de verificações** (ex: **`if (idade > 18 && temCarteira)`**).
- **Flexibilidade** (ex: **`if (temMaçã || temBanana)`**).
- **Controle preciso** do fluxo do programa.

**Para aprofundar:** Leia o artigo da Rafa Ballerini sobre [Como utilizar operadores de comparação em JavaScript](https://rafaballerini.com.br/).

</aside>

---

### Controle de Fluxo com break e Condicionais em JavaScript

### Lembretes

- **`break`** (interrupção de loop)
- Condicionais (**`if`**, **`else`**)
- Laço **`while`**
- Pluralização condicional
- Refatoração de código

### Anotações

### **1. O Problema: Condicionais Aninhadas**

- **Contexto:** Em um jogo de adivinhação, o código verifica se o **`chute`** é igual ao **`numeroSecreto`** dentro de um laço **`while`**.
- **Preocupação:**
    - Se muitas condições fossem adicionadas dentro do **`if`**, o código ficaria poluído e difícil de manter.
    - Exemplo original:
        
        javascript
        
        ```
        if (chute == numeroSecreto) {
            alert(`Acertou! Número secreto: ${numeroSecreto} em ${tentativas} tentativas.`);
        }
        ```
        

---

### **2. Solução: Usando `break` para Interromper o Loop**

- **Funcionalidade do `break`:**
    - Interrompe imediatamente o laço (**`while`**, **`for`**, etc.).
    - Qualquer código após o **`break`** **não é executado**.
- **Aplicação:**
    
    javascript
    
    ```
    if (chute == numeroSecreto) {
        break;// Sai do loop// alert() aqui NUNCA será executado!}
    ```
    
- **Refatoração:**
    - O **`alert()`** de sucesso foi movido **para fora do `while`**, garantindo que só execute após o loop terminar.

---

### **3. Testando o Fluxo**

- **Cenário 1 (Acerto na 1ª tentativa):**
    - Loop é interrompido (**`break`**).
    - **`alert()`** externo exibe:
        
        text
        
        ```
        "Isso aí! Você descobriu o número secreto 5 com 1 tentativa."
        ```
        
- **Cenário 2 (Acerto após múltiplas tentativas):**
    - Exemplo com 2 tentativas:
        
        text
        
        ```
        "Isso aí! Você descobriu o número secreto 5 com 2 tentativas."
        ```
        

---

### **4. Ajuste de Pluralização**

- **Problema:** A mensagem sempre usava "tentativas", mesmo para 1 tentativa.
- **Solução:** Condicional para singular/plural:
    
    javascript
    
    ```
    if (tentativas > 1) {
        alert(`... ${tentativas} tentativas.`);// Plural} else {
        alert(`... ${tentativas} tentativa.`);// Singular}
    ```
    
- **Resultado:**
    - Concordância gramatical correta em todos os casos.

<aside>
📌 **RESUMO**:

- **Otimização:**
    - **`break`** evita condicionais aninhadas excessivas.
    - Código mais limpo e fácil de depurar.
- **Melhorias Implementadas:**
    1. Controle preciso do fluxo com **`break`**.
    2. Mensagem pós-loop sem repetição de código.
    3. Pluralização dinâmica para melhor experiência do usuário.
</aside>

---

### DesafiosRefatorando Condicionais com Operador Ternário

### Lembretes

- Operador ternário (**`? :`**)
- Refatoração de código
- DRY (Don’t Repeat Yourself)
- Legibilidade
- Variáveis condicionais

### Anotações

### **1. O Problema: Redundância em Condicionais**

- **Contexto:** O código original usava um bloco **`if-else`** para controlar a pluralização da palavra "tentativa(s)" na mensagem de sucesso:
    
    javascript
    
    ```
    if (tentativas > 1) {
        alert(`... ${tentativas} tentativas.`);
    } else {
        alert(`... ${tentativas} tentativa.`);
    }
    ```
    
- **Desvantagens:**
    - Repetição de código (duas mensagens quase idênticas).
    - Dificuldade de manutenção (alterações exigem mudanças em dois lugares).

---

### **2. Solução: Operador Ternário**

- **Funcionamento:**
    - Sintaxe: **`condição ? valor_se_verdadeiro : valor_se_falso`**.
    - Equivalente a um **`if-else`** compacto.
- **Aplicação:**
    
    javascript
    
    ```
    let palavraTentativa = tentativas > 1 ? 'tentativas' : 'tentativa';
    alert(`Isso aí! Você descobriu o número secreto ${numeroSecreto} com ${tentativas} ${palavraTentativa}.`);
    ```
    
- **Vantagens:**
    - **Menos código:** Elimina a duplicação da mensagem.
    - **Mais legível:** Expressa a lógica em uma única linha.
    - **Fácil modificação:** Ajustar a pluralização requer mudar apenas uma string.

---

### **3. Comparação: `if-else` vs. Ternário**

| **Critério** | **`if-else`** | **Operador Ternário** |
| --- | --- | --- |
| **Linhas de código** | 4+ | 2 |
| **Legibilidade** | Explícito, mas verboso | Compacto, ideal para condições simples |
| **Uso Recomendado** | Lógicas complexas ou múltiplos passos | Atribuições condicionais simples |

---

### **4. Testes e Validação**

- **Cenário 1 (Plural):**
    - **`tentativas = 2`** → Saída: **`"3 tentativas"`**.
- **Cenário 2 (Singular):**
    - **`tentativas = 1`** → Saída: **`"1 tentativa"`**.
- **Resultado:**
    - Comportamento idêntico ao código original, mas com menos repetição.

---

### **5. Boas Práticas e Mercado**

- **Por que usar ternários?**
    - **Código mais limpo:** Reduz "ruído" em condições simples.
    - **Convenção do mercado:** Amplamente adotado em JavaScript e outras linguagens.
- **Cuidados:**
    - Evitar ternários aninhados (ex.: **`cond1 ? val1 : cond2 ? val2 : val3`**), pois prejudicam a legibilidade.

<aside>
📌 **RESUMO**:

- **Melhorias Implementadas:**
    1. Substituição de **`if-else`** redundante por operador ternário.
    2. Centralização da lógica de pluralização em uma variável (**`palavraTentativa`**).
    3. Mensagem única, facilitando futuras atualizações.
- **Próximos Passos:**
    - Aplicar ternários em outras condições similares (ex.: mensagens de erro).
    - Explorar outras técnicas de refatoração (ex.: funções reutilizáveis).

**Dica:** Sempre avalie a legibilidade ao escolher entre ternários e **`if-else`**. Opte pelo que torna o código mais claro para sua equipe!

</aside>

---

### Gerando Números Aleatórios em JavaScript

### Lembretes

- **`Math.random()`**
- **`parseInt()`**
- Números pseudoaleatórios
- Intervalo numérico (1 a 10)
- Refatoração para aleatoriedade

### Anotações

### **1. O Problema: Número Secreto Fixo**

- **Contexto:** O jogo atual sempre usa o mesmo **`numeroSecreto`** (ex.: 5), tornando-o previsível.
- **Objetivo:** Gerar um número aleatório entre 1 e 10 a cada execução.

---

### **2. Entendendo `Math.random()`**

- **Funcionamento:**
    - Retorna um número pseudoaleatório entre **0 (inclusivo)** e **1 (exclusivo)**.
    - Exemplos: **`0.581`**, **`0.929`**, **`0.2595555`**.
- **Limitação:**
    - Números decimais são impraticáveis para um jogo de adivinhação.

---

### **3. Ajustando o Intervalo**

1. **Multiplicação por 10:**
    
    javascript
    
    ```
    Math.random() * 10// Gera números entre 0.000... e 9.999...
    ```
    
2. **Extraindo a parte inteira com `parseInt()`:**
    
    javascript
    
    ```
    parseInt(Math.random() * 10)// Resultados: 0 a 9
    ```
    
    - **`parseInt()`** descarta as casas decimais.
3. **Deslocando o intervalo para 1 a 10:**
    
    javascript
    
    ```
    parseInt(Math.random() * 10 + 1)// Resultados: 1 a 10
    ```
    
    - Adicionar **`+1`** evita o 0 e inclui o 10.

---

### **4. Implementação no Jogo**

- **Substituição no código:**
    
    javascript
    
    ```
    // Antigo (número fixo):let numeroSecreto = 5;
    
    // Novo (número aleatório):let numeroSecreto = parseInt(Math.random() * 10 + 1);
    ```
    
- **Teste no Console:**
    - Executar **`parseInt(Math.random() * 10 + 1)`** várias vezes para verificar a aleatoriedade.

---

### **5. Documentação e Boas Práticas**

- **`Math.random()`:**
    - [Documentação MDN](https://developer.mozilla.org/pt-BR/docs/Web/JavaScript/Reference/Global_Objects/Math/random).
- **`parseInt()`:**
    - Converte strings/números em inteiros, descartando decimais.
    - **Cuidado:** Sem o **`+1`**, o intervalo seria 0–9.

<aside>
📌 **RESUMO**:

- **Resultado:**
    - Número secreto agora é **imprevisível**, melhorando a experiência do jogo.
- **Princípios aprendidos:**
    1. Uso de funções nativas (**`Math.random()`**, **`parseInt`**).
    2. Ajuste de intervalos matemáticos.
    3. Importância de testar no console antes de implementar.

**Dica:** Sempre consulte a documentação para explorar recursos adicionais (ex.: **`Math.floor()`** como alternativa a **`parseInt()`**).

</aside>

---

### Implementando Números Aleatórios no Jogo

### Lembretes

- **`Math.random()`**
- **`parseInt()`**
- Intervalo numérico (1-10 → 1-100)
- Refatoração de código
- Ajuste de prompts

### Anotações

### **1. Implementação do Número Aleatório**

- **Código Original (Número Fixo):**
    
    javascript
    
    ```
    let numeroSecreto = 5;// Sem graça!
    ```
    
- **Novo Código (Número Aleatório 1-10):**
    
    javascript
    
    ```
    let numeroSecreto = parseInt(Math.random() * 10 + 1);
    ```
    
    - **Explicação:**
        - **`Math.random() * 10`**: Gera números entre **0.000...** e **9.999...**.
        - **`parseInt()`**: Remove decimais, resultando em **0 a 9**.
        - **`+ 1`**: Desloca o intervalo para **1 a 10**.

---

### **2. Ampliando a Dificuldade (1-100)**

- **Modificação:**
    
    javascript
    
    ```
    let numeroSecreto = parseInt(Math.random() * 100 + 1);// 1 a 100
    ```
    
    - **Lógica:**
        - Multiplicar por **`100`** gera números até **99.999...**.
        - **`+ 1`** garante o intervalo **1 a 100**.
- **Ajuste no `prompt`:**
    
    javascript
    
    ```
    chute = prompt('Escolha um número entre 1 e 100');// Atualizado!
    ```
    
    - **Importância:** Manter a interface alinhada com a lógica do jogo.

---

### **3. Testes e Validação**

- **Cenário 1 (1-10):**
    - Número secreto: **`2`** (exemplo).
    - Jogador acerta após algumas tentativas.
- **Cenário 2 (1-100):**
    - Exemplo de fluxo:
        - Chute: **`50`** → Dica: "Maior".
        - Chute: **`75`** → Dica: "Maior".
        - Chute: **`83`** → Dica: "Menor".
        - Chute: **`78`** → Dica: "Menor".
        - Chute: **`76`** → Dica: "Maior".
        - Chute: **`77`** → Acerto! (6 tentativas).

---

### **4. Lições Aprendidas**

- **Desacoplamento:**
    - Mudanças em **`numeroSecreto`** exigem ajustes em outras partes (ex.: **`prompt`**).
    - **Boas práticas:** Centralizar intervalos em variáveis para facilitar manutenção.
        
        javascript
        
        ```
        const MIN = 1;
        const MAX = 100;
        let numeroSecreto = parseInt(Math.random() * MAX + MIN);
        chute = prompt(`Escolha um número entre ${MIN} e ${MAX}`);
        ```
        
- **Escalabilidade:**
    - Para aumentar o desafio, basta modificar **`MAX`** (ex.: **`1000`**).

<aside>
📌 **RESUMO**:

- **Melhorias Implementadas:**
    1. Número secreto agora é **aleatório** (1-10 → 1-100).
    2. Interface refletiu a mudança (**`prompt`** atualizado).
    3. Jogo mais desafiador e dinâmico.

**Dica:** Use **`Math.floor()`** como alternativa a **`parseInt()`** para arredondar números:

javascript

</aside>