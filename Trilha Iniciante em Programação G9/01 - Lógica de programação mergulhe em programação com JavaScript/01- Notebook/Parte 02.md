### **Melhorando o Jogo do Número Secreto: Condicionais, Comentários e Debug**

### Lembretes

- **`//`: Comentário (ignorado pelo JavaScript).**
- **`else`: "Se não" (complemento do `if`).**
- **`console.log()`: Debug (não aparece para o usuário final).**
- **Fluxo linear: Ordem de execução do código.**
- **Feedback: `alert()` para interação com usuário.**

### Anotações

### **1. Comentários no Código**

- **Para que servem**:
    - Explicar o código para outros desenvolvedores (ou para você no futuro).
    - Desativar temporariamente partes do código sem apagá-las.
- **Sintaxe**:
    
    ```
    // Comentário de uma linha/* Comentário de
       múltiplas linhas */
    ```
    
- **Exemplo no jogo**:
    
    ```
    // Se chute for igual ao número secretoif (chute == numeroSecreto) {
    // Código aqui}
    ```
    

### **2. Condicional `else` (Se não)**

- **Complementa o `if`**: Executa código quando a condição é falsa.
- **Sintaxe**:
    
    ```
    if (condição) {
    // Código se VERDADEIRO} else {
    // Código se FALSO}
    ```
    
- **Exemplo prático**:

    ```
    if (chute == numeroSecreto) {
      alert('Acertou!');
    } else {
      alert('Errou :(');
    }
    ```
    

### **3. Debug com `console.log()`**

- **Função**: Mostra valores no console do navegador (F12 > Console).
- **Diferença crucial**:
    - **`console.log('texto')`** → Exibe o texto literal.
    - **`console.log(variavel)`** → Exibe o valor da variável.
- **Uso no jogo**:
    
    ```
    let numeroSecreto = 5;
    console.log(numeroSecreto);// Exibe 5 (sem aspas!)
    ```

### **4. Fluxo de Execução**

- **O JavaScript roda linha por linha**, na ordem escrita:
    1. Define **`numeroSecreto = 5`**.
    2. Mostra **`numeroSecreto`** no console.
    3. Só depois pede o **`chute`** via **`prompt()`**.

### **5. Melhorando a Experiência do Usuário**

- **Problema identificado**:
    - **`console.log()`** é visível apenas no console (ferramenta de devs).
- **Solução**:
    - Usar **`alert()`** para feedback direto ao usuário.
    - Manter **`console.log()`** apenas para debug (ex.: ver o número secreto).

<aside>

📌 **RESUMO**:

**O que aprendemos?**

1. **Comentários** documentam o código sem afetar a execução.
2. **`else`** permite criar lógicas para casos de erro.
3. **`console.log()`** é uma ferramenta poderosa para debug.
4. **Ordem de execução** importa: o JavaScript roda de cima para baixo.

**Dica Profissional:**
Sempre use console.log() para verificar valores durante o desenvolvimento, mas remova ou comente essas linhas no código final! 🔍

</aside>

---

### **Tornando o Código Dinâmico com Template Strings**

### Lembretes

- **Template Strings: ``Texto ${variavel}``.**
- **DRY: Princípio de não repetição.**
- **Crases (```): Delimitadores de template strings.**
- **${ }: Interpolação de variáveis.**
- **Manutenção: Facilidade de atualizar o código.**

### Anotações

### **1. O Problema do Código Estático**

- **Situação inicial**:

    ```
    alert('Isso ai! Você descobriu o número secreto 5');
    ```
    
    - Mensagem travada no número 5, mesmo após mudar **`numeroSecreto = 4`**.
- **Consequência**:
    - Necessidade de alterar manualmente o valor em múltiplos lugares.
    - Violação do princípio **DRY** (Don't Repeat Yourself).

### **2. Solução: Template Strings**

- **O que são**:
    - Strings que permitem incorporar variáveis e expressões diretamente.
- **Sintaxe**:
    
    ```
    `Texto ${variavel} mais texto`
    ```
    
    - Usam **crases** (**```**) em vez de aspas.
    - Variáveis são inseridas com **`${ }`**.
- **Exemplo no jogo**:
    
    ```
    alert(`Isso ai! Você descobriu o número secreto ${numeroSecreto}`);
    ```
    
    - Agora, se **`numeroSecreto`** mudar para 4 ou 8, a mensagem se atualiza automaticamente.

### **3. Benefícios das Template Strings**

| **Vantagem** | **Exemplo** |
| --- | --- |
| **Dinamismo** | Mensagem sempre reflete o valor atual. |
| **Legibilidade** | Código mais claro e fácil de manter. |
| **Flexibilidade** | Permite combinar textos, variáveis e cálculos. |

### **4. Fluxo de Atualização**

1. Altere **`numeroSecreto`** no código:

    ```
    let numeroSecreto = 8;// Ou qualquer outro número
    ```
    
2. A mensagem no **`alert()`** se ajusta automaticamente graças ao **`${numeroSecreto}`**.

<aside>
📌 **RESUMO**:

**O que aprendemos?**

1. **Template strings** eliminam a necessidade de concatenação manual.
2. **Código dinâmico** se adapta a mudanças sem esforço extra.
3. **Boas práticas**:
    - Use **```** e **`${ }`** para textos com variáveis.
    - Evite valores fixos quando eles podem ser referenciados.

**Dica Profissional:**

Template strings também permitem quebras de linha naturais no código:

```
alert(`Você acertou!
O número secreto era ${numeroSecreto}.
Parabéns!`);
```

</aside>

---

### **Como Configurar Atualização Automática no VS Code com Live Server**

### Lembretes

- **Live Server**: Extensão para atualização automática.
- **localhost:5500**: Endereço do servidor local.
- **Open with Live Server**: Comando para iniciar.
- **Monitoramento**: O Live Server "observa" mudanças nos arquivos.

### Anotações

### **1. O Problema: Atualização Manual Constante**

- **Situação anterior**:
    - Cada alteração no código exigia F5 no navegador.
    - Fácil esquecer de atualizar, causando confusão durante testes.

### **2. Solução: Extensão Live Server**

- **O que faz**:
    - Cria um servidor local que atualiza automaticamente o navegador quando o código é alterado.
- **Benefícios**:
    - Não precisa recarregar manualmente.
    - Visualização instantânea das mudanças.

### **3. Passo a Passo de Instalação**

1. Abra o VS Code → Ctrl+Shift+X (Extensões).
2. Busque por "Live Server" (Ritwick Dey).
3. Clique em "Install".

### **4. Como Usar**

- **Método 1**:
    1. Clique com botão direito em **`index.html`**.
    2. Selecione "Open with Live Server".
- **Método 2**:
    - Clique no ícone "Go Live" no canto inferior direito do VS Code.

### **5. Como Funciona**

- Injeta um script no HTML:
    
    ```
    <!-- Code injected by live server -->
    ```
    
    - Esse script monitora mudanças nos arquivos e recarrega a página.
- **URL do servidor local**:
    
    **`127.0.0.1:5500`** ou **`localhost:5500`**.
    

### **6. Teste Prático**

1. Altere **`numeroSecreto`** no código (ex.: para 9).
2. Salve o arquivo (Ctrl+S).
3. **Observe**: O navegador atualiza sozinho!

### **7. Dicas Profissionais**

- **Erro comum**:
    - Mensagem "favicon.ico not found" no console → Pode ser ignorada.
- **Melhor visualização**:
    - Use a URL **`localhost:5500`** em vez do caminho de arquivos.

<aside>
📌 **RESUMO**:

**Por que isso é importante?**

1. **Economiza tempo**: Elimina recarregamentos manuais.
2. **Facilita debugging**: Mudanças são refletidas instantaneamente.
3. **Padrão profissional**: Ferramenta essencial no fluxo de desenvolvimento.
</aside>

---

### Guia Completo sobre console.log() - O Seu Melhor Amigo no Debugging

### Lembretes

- 

### Anotações

### **O que é console.log()?**

É uma ferramenta de debugging que imprime mensagens no **console do navegador** (acessível com F12 > Console). Pense nela como um "raio-X" do seu código, revelando informações internas durante o desenvolvimento.

---

### **Por que usar?**

1. **Verificar valores** de variáveis em tempo real.
2. **Rastrear o fluxo** do programa (qual parte está sendo executada).
3. **Identificar erros** lógicos (ex.: por que uma condição não está funcionando?).

---

### **Como usar no Jogo do Número Secreto**

```
alert('Boas vindas ao jogo do número secreto');

// Adicione um console.log para verificar o valor de "chute" após a entrada do usuário
let chute = prompt('Escolha um número entre 1 e 10');
console.log('Valor do chute:', chute);

let numeroSecreto = 4;

// Adicione um console.log para verificar a comparação entre "chute" e "numeroSecreto"
console.log('Resultado da comparação:', chute == numeroSecreto);

if (chute == numeroSecreto) {
    alert('Acertou');
} else {
    // Adicione um console.log para verificar o valor de "numeroSecreto" quando o jogador erra
    console.log('Valor do número secreto:', numeroSecreto);
    alert('O número secreto era ' + numeroSecreto);
}
```

---

### **Quando usar?**

| **Momento** | **Exemplo de Uso** | **Finalidade** |
| --- | --- | --- |
| Após entrada do usuário | **`console.log('Chute:', chute);`** | Verificar se o valor foi capturado certo. |
| Antes de condições | **`console.log('Comparação:', a == b);`** | Checar por que um **`if`** não está executando. |
| Em loops | **`console.log('Iteração:', i);`** | Contar quantas vezes um loop rodou. |

### **Boas Práticas**

1. **Mensagens claras**:
    
    Ruim: **`console.log(x);`**
    
    Bom: **`console.log('Valor do chute:', chute);`**
    
2. **Remova em produção**:
    - Console.logs podem vazar informações sensíveis.
    - Use ferramentas como **Babel** ou **Webpack** para remoção automática.
3. **Níveis alternativos**:
    - **`console.warn()`** para avisos.
    - **`console.error()`** para erros críticos.
    
    ### **Exemplo Avançado**
    
    ```
    // Debug detalhado com template string
    console.log(`
      [DEBUG]
      Chute: ${chute}
      Número Secreto: ${numeroSecreto}
      Resultado: ${chute == numeroSecreto ? 'ACERTOU' : 'ERROU'}
    `);
    ```
    
    ---
    
    ### **Por que isso é importante?**
    
    - **Economiza tempo**: Encontre erros em segundos.
    - **Entenda o fluxo**: Veja passo a passo como seu código é executado.
    - **Melhore o código**: Identifique valores inesperados (ex.: **`undefined`** ou **`NaN`**).
    
    ---
    
    **Dica do Instrutor:**
    
    > "Use console.log() como um diário de desenvolvimento. Quando algo der errado, você terá um histórico do que aconteceu antes do erro!"
    >
