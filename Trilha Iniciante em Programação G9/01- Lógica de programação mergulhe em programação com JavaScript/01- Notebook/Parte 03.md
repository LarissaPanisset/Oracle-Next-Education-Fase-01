### Ponto e Vírgula (;) e ASI no JavaScript - Boas Práticas

### Lembretes

- **ASI**: Inserção automática de **`;`**.
- **Bugs sutis**: Erros difíceis de detectar.
- **Padronização**: Consistência em equipe.
- **Minificação**: Remoção de espaços/quebras.
- **Legibilidade**: Código claro e explícito.

### Anotações

### **1. O Que é ASI?**

- **Definição**: Mecanismo de *Automatic Semicolon Insertion* (Inserção Automática de Ponto e Vírgula).
- **Funcionamento**:
    - JavaScript tenta "adivinhar" e inserir **`;`** onde faltam.
    - Exemplo:
        
        javascript
        
        ```
        let x = 1// ASI adiciona ; aquilet y = 2
        ```
        

### **2. Problemas do ASI**

- **Comportamentos inesperados**:
    - Pode inserir **`;`** em lugares errados, causando bugs.
    - Caso clássico:
        
        javascript
        
        ```
        return
          { nome: "João" };// Retorna `undefined`! (ASI adiciona ; após return)
        ```
        

### **3. Quando o ASI Falha?**

- **Situações críticas**:
    - **Declarações `return`**: Quebras de linha após **`return`** são perigosas.
    - **Operações em uma linha**:
        
        javascript
        
        ```
        a = b
        (c + d).print()// Pode ser lido como a = b(c + d).print()
        ```
        

### **4. Boas Práticas**

- **Sempre use `;` manualmente**:
    - Evita ambiguidades.
    - Melhora a legibilidade.
- **Casos onde é essencial**:
    - Minificação de código.
    - Projetos em equipe (padronização).

### **5. Benefícios do Uso Explícito**

- **Código mais seguro**: Sem surpresas do ASI.
- **Facilita colaboração**: Todos seguem o mesmo padrão.

**Analogia**:

> "O ASI é como um corretor automático: às vezes acerta, mas pode estragar seu texto. Melhor digitar os ; você mesmo!"
> 

**Dica Visual**:

javascript

```
// ❌ Arriscado (depende do ASI):
console.log("Olá")
[1, 2].forEach(console.log)

// ✅ Correto (explícito):
console.log("Olá");
[1, 2].forEach(console.log);
```

<aside>

📌 **RESUMO**:

1. O ASI existe, mas **não é confiável** — pode causar bugs difíceis de encontrar.
2. **Sempre use `;`** explicitamente para:
    - Evitar erros em **`return`**, operações em linha e minificação.
    - Manter o código legível e padronizado em equipe.
3. **Regra de ouro**:
    
    *"Prefira ser explícito: ponto e vírgula manual evita problemas automáticos!"*
    

**Exemplo Crítico**:

javascript

```
// SEM ; → Risco de erro:let a = 1
[a, b] = [2, 3]// Pode ser lido como let a = 1[a, b] = ...// COM ; → Seguro:let a = 1;
[a, b] = [2, 3];
```

</aside>

---

### Implementando um Loop com while em JavaScript

### Lembretes

- Conceito de loop (**while**)
- Estrutura do **while**
- Aplicação no jogo: número secreto
- Inicialização da variável **chute**
- Estrutura condicional dentro do loop
- Comparações com operadores
- Problemas com loop infinito
- Importância da indentação (recuo)
- Execução passo a passo do jogo
- Testes com valores maiores e menores

### Anotações

**🧩 Introdução ao problema:**

- Inicialmente, o jogo era jogado manualmente, com papel, o que permitia várias tentativas.
- No computador, estava limitado a **uma única tentativa**. É necessário modificar isso.

**🔁 Conceito de Loop (while):**

- Guilherme apresenta a estrutura de repetição `while`, que executa **enquanto** uma condição for verdadeira.
- Sintaxe:
    
    ```jsx
    javascript
    CopiarEditar
    while (condição) {
        // instruções
    }
    
    ```
    
- Comparável ao `if`, mas com repetição contínua.

**🎮 Aplicação no jogo do número secreto:**

- A lógica do jogo precisa permitir **várias tentativas até acertar** o número secreto.
- Queremos que o código continue pedindo um número **enquanto o chute não for igual ao número secreto**.

**📦 Inicialização da variável `chute`:**

- Antes do `while`, a variável `chute` deve ser criada como vazia:
    
    ```jsx
    javascript
    CopiarEditar
    let chute;
    
    ```
    
- Dentro do `while`, ela receberá o valor do `prompt`:
    
    ```jsx
    javascript
    CopiarEditar
    chute = prompt('Escolha um número entre 1 e 100');
    
    ```
    

**⚙️ Condição no `while`:**

- A verificação é feita com `!=` (diferente), ou seja:
    
    ```jsx
    javascript
    CopiarEditar
    while (chute != numeroSecreto)
    
    ```
    

**⚠️ Cuidado: Loop Infinito:**

- Se apenas repetir o prompt dentro do while, sem outras verificações, o código entra em **loop infinito**.
- A cada execução, o `prompt` é mostrado, mas nunca há interrupção se o número estiver errado, pois não há verificação adicional.

**🔁 Corrigindo com condicionais:**

- A condicional `if` que verifica o valor do chute deve estar **dentro do while**.
- Movemos com `CTRL+X` as linhas do `if` para dentro do `while`.

**🧠 Estrutura final até o momento:**

```jsx

alert('Boas vindas ao jogo do número secreto');
let numeroSecreto = 5;
console.log(numeroSecreto)
let chute;

while (chute != numeroSecreto) {
    chute = prompt('Escolha um número entre 1 e 100');
    if (chute == numeroSecreto) {
        alert(`Isso ai! Você descobriu o número secreto ${numeroSecreto}`);
    } else {
        if (chute > numeroSecreto) {
            alert(`O número secreto é menor que ${chute}`);
        } else {
            alert(`O número secreto é maior que ${chute}`);
        }
    }
}

```

**🔧 Organização do código (indentação):**

- Guilherme reforça a importância da **indentação (recuo)** para garantir a clareza do escopo (`while`, `if`, `else`).
- Identamos o conteúdo do `if` dentro do `while` usando `Shift + {`.

**🧪 Teste de execução no navegador:**

- Começamos testando com valores **acima do número secreto**:
    - Exemplo: digitar 8 → mensagem: "O número secreto é menor que 8"
    - Digitar 7 → "O número secreto é menor que 7"
    - Até chegar em 5 → "Você acertou o número secreto"
- Depois, testamos com valores **abaixo**:
    - Digitar 1 → "O número secreto é maior que 1"
    - Até chegar em 5 novamente.

**🧮 Explicação dos operadores de comparação:**

- Mônica relaciona os operadores com os conceitos escolares:
    - `!=`: diferente
    - `==`: igual
    - `>`: maior
- Em vez de números simples, comparamos **valores armazenados em variáveis**.

**🧹 Considerações finais:**

- O console ainda mostra o número secreto, pois estamos em fase de desenvolvimento.
- Isso será retirado no final, pois foi útil para teste e validação.
- O jogo agora funciona como esperado, permitindo múltiplas tentativas e dando dicas conforme o chute.

<aside>
📌 **RESUMO**: 
Nesta aula, aprendemos a usar a estrutura de repetição `while` para **repetir uma ação até que uma condição seja satisfeita**. Aplicamos esse conceito ao jogo do número secreto, permitindo múltiplas tentativas por parte do usuário. Também revisamos **operadores de comparação**, a importância da **estruturação do código (indentação)** e testamos diferentes cenários para garantir o funcionamento. O jogo agora é funcional, didático e reflete a lógica de programação ensinada no início do curso.

</aside>

---

### Contador de Tentativas e Ajustes no Código do Jogo

### Lembretes

- Ponto e vírgula no JavaScript
- Como contar tentativas?
- Onde declarar a variável `tentativas`?
- Quando incrementar a tentativa?
- `tentativas++` vs `tentativas = tentativas + 1`
- Por que fora do `else`?
- Como exibir o total de tentativas no `alert`?
- O que acontece nos testes práticos?

### Anotações

### 🔧 **Correções iniciais com ponto e vírgula**

Mônica relembra que Guilherme havia pedido para corrigir quando ele esquecesse do **ponto e vírgula**, prática comum e recomendada para evitar ambiguidade no código JavaScript.

**Correções feitas no código:**

- Final da linha com `console.log(numeroSecreto);`
- Após `let chute;`
- E ao final do `alert` com a mensagem do acerto.

🟢 Isso melhora a clareza e previne problemas de execução futura, mesmo que em alguns casos o JS aceite sem.

---

### 🎯 **Adicionando contador de tentativas**

Objetivo: Melhorar a experiência do jogo contabilizando **quantas tentativas foram feitas** até acertar o número secreto.

**Etapas:**

1. **Criar uma variável `tentativas`:**
    - Inserida antes do loop:
        
        ```jsx
        
        let tentativas = 1;
        ```
        
    - Começa com 1, pois o jogo já inicia com a **primeira tentativa**.
2. **Quando incrementar essa variável?**
    - ❌ Não é adequado somar logo após o `prompt`, pois isso adicionaria antes mesmo da tentativa ser válida.
    - ❌ Não é no `if` do acerto, pois só contaria tentativas **quando acertasse**.
    - ❌ Também não é apenas no `else`, pois isso **exclui a tentativa certa**.
    - ✅ Portanto, **a melhor posição** é fora do `else`, **mas dentro do loop**.

---

### ➕ **Incrementando tentativas**

Duas formas de fazer isso:

- **Forma longa:**
    
    ```jsx
    tentativas = tentativas + 1;
    ```
    
- **Forma curta (mais comum e limpa):**
    
    ```jsx
    tentativas++;
    ```
    

🗨️ **Observação didática:** Ambas funcionam exatamente igual. A segunda é preferida por ser mais legível e amplamente usada no dia a dia de programadores.

## 🧠 **Por que usamos `++` para somar 1 em JavaScript?**

---

### 📌 **Conceito:**

O operador `++` é um **incrementador**, usado para **adicionar 1** ao valor atual de uma variável numérica.

---

### 🔍 **Comparação entre formas de incremento:**

| Forma Tradicional | Forma Abreviada (`++`) |
| --- | --- |
| `tentativas = tentativas + 1;` | `tentativas++;` |
| Escreve a operação completa | Incrementa de forma direta |
| Mais detalhado, mas mais extenso | Mais limpo e comum no código |

---

### 🧪 **O que `tentativas++` faz exatamente?**

- Ele **pega o valor atual da variável `tentativas`**
- **Adiciona 1**
- E **atualiza a variável** com o novo valor.

📌 É igual a:

```jsx
tentativas = tentativas + 1;
```

Mas de forma **mais concisa**, usada com frequência por programadores por ser **rápida, limpa e legível**.

---

### 🧠 **Curiosidade:**

- `++` é chamado de **operador de incremento unário**.
- Ele existe também em outras linguagens como C, C++, Java, Python (com outras formas), etc.
- Pode ser usado no **final** (`tentativas++`) ou no **início** (`++tentativas`), com pequenas diferenças que importam em situações específicas — mas **neste caso**, o final funciona perfeitamente.

---

### ✅ **Quando usar `tentativas++`?**

- Sempre que quiser **somar 1 a uma variável** de forma simples e clara.
- Ideal para **contadores**, como:
    - Número de tentativas
    - Quantidade de cliques
    - Itens processados em loops

---

### 📢 **Exibindo o número de tentativas no alerta final**

Quando a pessoa acerta, queremos que a mensagem diga **quantas tentativas foram necessárias**.

**Alerta final modificado:**

```jsx
alert(`Isso ai! Você descobriu o número secreto ${numeroSecreto} com ${tentativas} tentativas`);
```

- Utiliza **template string** com `${}` para exibir valores de variáveis dentro da string.

---

### 👩‍💻 **Teste prático do jogo**

Mônica faz os testes no navegador com os seguintes chutes:

1. Número 1 (incorreto)
2. Número 8 (incorreto)
3. Número 5 (correto)

**Resultado exibido:**

> "Isso ai! Você descobriu o número secreto 5 com 3 tentativas"
> 

🟢 A lógica está funcionando corretamente, somando as duas tentativas incorretas **e** a correta.

---

### ✅ **Código final resumido:**

```jsx
alert('Boas vindas ao jogo do número secreto');
let numeroSecreto = 5;
console.log(numeroSecreto);
let chute;
let tentativas = 1;

while (chute != numeroSecreto) {
    chute = prompt('Escolha um número entre 1 e 100');

    if (chute == numeroSecreto) {
        alert(`Isso ai! Você descobriu o número secreto ${numeroSecreto} com ${tentativas} tentativas`);
    } else {
        if (chute > numeroSecreto) {
            alert(`O número secreto é menor que ${chute}`);
        } else {
            alert(`O número secreto é maior que ${chute}`);
        }
    }

    tentativas++;
}
```

<aside>
📌 **RESUMO**:

- A aula focou em tornar o jogo mais realista e interessante com um **contador de tentativas**.
- Reforçou boas práticas como o uso de **ponto e vírgula** e **template strings**.
- Apresentou de forma clara **onde e como manipular variáveis dentro de um loop**.
- A importância de testar e pensar na **regra de negócio**: "a tentativa certa conta?"
</aside>