### Condicionais no Jogo do Número Secreto: Validando Chutes e Exibindo Feedback

### Lembretes

- **`if/else`**
- Comparação (**`==`**, **`>`**, **`<`**)
- **`exibirTextoNaTela()`**
- Fluxo de jogo
- Depuração com valores fixos

### Anotações

### **1. Objetivo da Aula**

Implementar a lógica que:

- Verifica se o jogador **acertou** o número secreto.
- Dá **dicas** ("maior" ou "menor") quando erra.
- Substitui mensagens estáticas por feedback dinâmico.

### **2. Estrutura da Função `verificarChute()`**

```
function verificarChute() {
    let chute = document.querySelector('input').value;

    if (chute == numeroSecreto) {
        exibirTextoNaTela('h1', 'Acertou!');
        exibirTextoNaTela('p', 'Você descobriu o número secreto!');
    } else {
        if (chute > numeroSecreto) {
            exibirTextoNaTela('p', 'O número secreto é menor');
        } else {
            exibirTextoNaTela('p', 'O número secreto é maior');
        }
    }
}
```

### **3. Passo a Passo da Implementação**

1. **Captura do Chute:**
    - **`document.querySelector('input').value`** pega o valor digitado.
2. **Condicional Principal (`if`):**
    - Se **`chute == numeroSecreto`**:
        - Altera o **`<h1>`** para "Acertou!".
        - Atualiza o **`<p>`** para "Você descobriu o número secreto!".
3. **Tratamento de Erro (`else`):**
    - **Se o chute for maior**:
        - Exibe "O número secreto é menor".
    - **Se for menor**:
        - Exibe "O número secreto é maior".

### **4. Testes e Depuração**

- **Usando Número Fixo (`7`):**

    ```
    let numeroSecreto = 7;// Para testes iniciais
    ```
    
    - Garantia de acerto ao digitar **`7`**, facilitando a validação.
- **Voltando ao Número Aleatório:**

    ```
    let numeroSecreto = gerarNumeroAleatorio();// Versão final
    ```
    
    - Testes com chutes reais (ex: **`2`** → "maior", **`8`** → "menor").

### **5. Detalhes Importantes**

- **Hierarquia de Condicionais:**
    - O **`else`** interno (**`if (chute > numeroSecreto)`**) só executa se o primeiro **`if`** for falso.
- **Mensagens Contextuais:**
    - Feedback muda **dinamicamente** conforme o chute.
- **Console vs Interface:**
    - Lembrando que o **`console.log()`** é para desenvolvedores, enquanto **`exibirTextoNaTela()`** é para jogadores.

### **6. Problemas e Soluções**

- **Problema:**
    - Comparação direta (**`==`**) pode falhar se **`chute`** for string (ex: **`"5"`** vs **`5`**).
- **Solução Futura:**
    - Converter **`chute`** para número com **`Number()`** ou **`parseInt()`**.

### **7. Fluxo do Jogo**

1. Jogador digita um número e clica em "Chutar".
2. O sistema:
    - **Acerto:** Parabeniza.
    - **Erro:** Dá dica ("maior/menor").
3. Para jogar novamente, atualiza a página (por enquanto).

### **8. Melhorias Pendentes**

- Adicionar **contador de tentativas**.
- Implementar **reinício automático** (sem F5).
- Validar entrada (ex: números fora do intervalo 1-10).

<aside>

📌 **RESUMO**:

A aula mostrou como usar **`if/else`** para criar **lógica interativa** em jogos. O sistema agora:

✅ Reconhece acertos.

✅ Fornece dicas úteis.

✅ Mantém o jogador engajado.

🚀 **Dica dos Instrutores:**

*"Sempre testem com valores fixos antes de usar lógica complexa. Isso acelera a depuração!"*

</aside>

---

### **Implementando Contador de Tentativas com Template Strings e Operador Ternário**

### Lembretes

- Contador de tentativas
- Template strings
- Operador ternário
- Incremento (**`++`**)
- Pluralização inteligente

### Anotações

### **1. Objetivo da Implementação**

Adicionar um sistema que:

✔ Mostre quantas tentativas foram necessárias para acertar

✔ Adapte automaticamente "tentativa" (singular) ou "tentativas" (plural)

✔ Só incremente o contador em tentativas erradas

### **2. Implementação Passo a Passo**

**a) Variável de Controle**

```
let tentativas = 1;// Começa com 1 pois o primeiro chute já conta
```

**b) Lógica de Pluralização**

Usando operador ternário para escolher entre singular/plural:

```
let palavraTentativa = tentativas > 1 ? 'tentativas' : 'tentativa';
```

**c) Template String Dinâmica**

Mensagem personalizada com número de tentativas:

```
let mensagemTentativas = `Você descobriu o número secreto com ${tentativas} ${palavraTentativa}!`;
```

**d) Incremento nas Tentativas Erradas**


```
} else {
// ... lógica de dicas ...
    tentativas++;// Só incrementa se errar}
```

### **3. Código Completo da Função**

```
function verificarChute() {
    let chute = document.querySelector('input').value;

    if (chute == numeroSecreto) {
        exibirTextoNaTela('h1', 'Acertou!');
        let palavraTentativa = tentativas > 1 ? 'tentativas' : 'tentativa';
        let mensagemTentativas = `Você descobriu o número secreto com ${tentativas} ${palavraTentativa}!`;
        exibirTextoNaTela('p', mensagemTentativas);
    } else {
        if (chute > numeroSecreto) {
            exibirTextoNaTela('p', 'O número secreto é menor');
        } else {
            exibirTextoNaTela('p', 'O número secreto é maior');
        }
        tentativas++;// Incrementa apenas aqui}
}
```

### **4. Testes Realizados**

| **Cenário** | **Comportamento** |
| --- | --- |
| Acerto na 1ª tentativa | Exibe "1 tentativa" (singular) |
| Acerto após 3 tentativas | Exibe "3 tentativas" (plural) |
| Número fixo (para testes) | Usado **`numeroSecreto = 2`** para validar casos específicos |
| Volta ao aleatório | Restaurado **`gerarNumeroAleatorio()`** após testes |

### **5. Detalhes Importantes**

- **Template Strings**: Permitem interpolação de variáveis com **`${var}`**
- **Lógica de Incremento**:
    - O **`tentativas++`** está apenas no **`else`** → não conta o acerto como nova tentativa
- **Tipagem Dinâmica**:
    - JavaScript converte automaticamente números para strings nas templates

### **6. Melhorias Futuras**

- Adicionar limite máximo de tentativas
- Resetar o jogo automaticamente após acerto
- Mostrar histórico de tentativas anteriores

<aside>
📌 **RESUMO**:

O sistema agora não só diz se o chute está correto, mas também:

✅ Mostra o esforço necessário (número de tentativas)

✅ Adapta gramática automaticamente

✅ Mantém contagem precisa (só incrementa nos erros)

**Dica dos Instrutores:**

*"Template strings são poderosas para mensagens dinâmicas. Combinadas com ternários, substituem concatenações complexas!"*

**Exemplo de Saída:**

- "Você descobriu o número secreto com 1 tentativa!"
- "Você descobriu o número secreto com 5 tentativas!"
</aside>

---

### **Melhorando a Usabilidade do Jogo: Limpar Campo e Habilitar Botão**

### Lembretes

- **`limparCampo()`**
- **`string vazia ('')`**
- **`document.querySelector('input')`**
- **`document.getElementById('reiniciar')`**
- **`removeAttribute('disabled')`**
- **`id único (HTML)`**

### Anotações

**1. Limpando o Campo de Chute Após Erro:**

- **Problema Identificado:** Quando o jogador erra o chute (ex: digita "5"), a mensagem indica se o número secreto é maior ou menor, mas o valor digitado permanece no campo, o que pode causar confusão.
- **Solução:** Criar a função **`limparCampo()`** para apagar o conteúdo do campo após cada tentativa.
    - **Passo a Passo:**
        - Declarar a função sem retorno (**`function limparCampo() {}`**).
        - Usar **`document.querySelector('input')`** para selecionar o campo (sem **`.value`**, pois queremos o elemento, não seu valor).
        - Atribuir **`chute.value = ''`** (string vazia) para "limpar" o campo visualmente.
    - **Exemplo do Código:**
  
        ```
        function limparCampo() {
            chute = document.querySelector('input');
            chute.value = '';// Remove o texto digitado}
        ```
        
    - **Observação:** Strings vazias (**`''`**) são usadas para representar ausência de texto.

**2. Habilitando o Botão "Novo Jogo" ao Acertar:**

- **Contexto:** O botão "Novo Jogo" está desabilitado por padrão no HTML (atributo **`disabled`**). Queremos ativá-lo quando o jogador acertar o número.
- **Solução:**
    - **Selecionar o Botão:** Usar **`document.getElementById('reiniciar')`** (o **`id`** é único no HTML).
        - Diferente de **`querySelector`**, que pega o primeiro elemento, o **`getElementById`** busca diretamente pelo **`id`**.
    - **Remover o `disabled`:** Usar **`removeAttribute('disabled')`** para habilitar o botão.
- **Implementação no Código:**

    ```
    if (chute == numeroSecreto) {
    // ... (código de mensagem de acerto)
        document.getElementById('reiniciar').removeAttribute('disabled');
    }
    ```
    
- **Teste:** Ao acertar, o botão deve ficar clicável.

**3. Dicas e Explicações Adicionais:**

- **Por Que Usar `id`?**
    - **`id`**s são únicos e evitam conflitos ao selecionar elementos específicos (ex: diferenciar entre múltiplos botões).
- **Diferença Entre `querySelector` e `getElementById`:**
    - **`querySelector('button')`** pega o primeiro botão da página.
    - **`getElementById('reiniciar')`** acessa apenas o botão com **`id="reiniciar"`**.
- **Próximos Passos:**
    - Implementar a função do botão "Novo Jogo" para reiniciar o jogo (será abordado no próximo vídeo)

<aside>
📌 **RESUMO**:

- A função **`limparCampo()`** melhora a experiência do usuário ao evitar resíduos de tentativas anteriores.
- Habilitar o botão programaticamente (**`removeAttribute`**) prepara o jogo para a próxima funcionalidade (reinício).
- O uso de seletores específicos (**`getElementById`**) garante precisão na manipulação do DOM.
</aside>

---

### **Finalizando o Jogo: Reinício, Mensagens Iniciais e Boas Práticas**

### Lembretes

- **`onclick="reiniciarJogo()"`** (HTML)
- **`reiniciarJogo()`** (função JS)
- **`exibirMensagemInicial()`**
- **`setAttribute('disabled', true)`**
- **`gerarNumeroAleatorio()`** (reutilização)
- **Refatoração** (evitar repetição de código)

### Anotações

### **1. Funcionalidade do Botão "Novo Jogo"**

**Objetivo:**

- Zerar tentativas, sortear novo número e resetar a interface ao clicar no botão.

**Passos Implementados:**

1. **HTML:**
    - Adicionar **`onclick="reiniciarJogo()"`** ao botão no **`index.html`**.

    ```
    <button onclick="reiniciarJogo()" id="reiniciar" disabled>Novo jogo</button>
    ```
    
2. **JavaScript (`app.js`):**
    - Criar a função **`reiniciarJogo()`**:
        - **Resetar o jogo:**

            ```
            function reiniciarJogo() {
                numeroSecreto = gerarNumeroAleatorio();// Novo sorteiolimparCampo();// Limpa o input
                tentativas = 1;// Reinicia contadorexibirMensagemInicial();// Restaura textos iniciais
                document.getElementById('reiniciar').setAttribute('disabled', true);// Desabilita o botão novamente}
            ```
            

### **2. Correção de Problemas Identificados**

**Problema:**

- Mensagens de vitória ("Acertou!") persistem após reinício.
- Código duplicado para exibir mensagens iniciais.

**Soluções:**

- **Refatoração com `exibirMensagemInicial()`:**
    - Isolar a exibição dos textos iniciais em uma função reutilizável:

        ```
        function exibirMensagemInicial() {
            exibirTextoNaTela('h1', 'Jogo do número secreto');
            exibirTextoNaTela('p', 'Escolha um número entre 1 e 10');
        }
        ```
        
    - Chamá-la:
        - No início do jogo (linha 14, fora de funções).
        - Dentro de **`reiniciarJogo()`**.
- **Desabilitar o Botão Automaticamente:**
    - Usar **`setAttribute('disabled', true)`** no fim da função **`reiniciarJogo()`**.

### **3. Explicações Adicionais**

- **Por Que Refatorar?**
    - Evitar repetição de código (ex: mensagens iniciais apareciam em dois lugares).
    - Facilita manutenção (alterações são feitas em um único lugar).
- **Diferença Entre `removeAttribute` e `setAttribute`:**
    - **`removeAttribute('disabled')`**: Remove o atributo (habilita o botão).
    - **`setAttribute('disabled', true)`**: Adiciona/reativa o atributo (desabilita).
- **Fluxo do Jogo Atualizado:**
    1. Acerta o número → Botão "Novo Jogo" é habilitado (**`removeAttribute`**).
    2. Clica em "Novo Jogo" → Reinicia o jogo e desabilita o botão (**`setAttribute`**).

### **4. Testes e Resultados**

- **Cenário de Teste:**
    - Acertar o número → Botão é liberado.
    - Clicar em "Novo Jogo" → Interface volta ao estado inicial (campo vazio, mensagens padrão, botão desabilitado).
- **Observação:**
    - A função **`gerarNumeroAleatorio()`** é reutilizada, garantindo um novo número secreto a cada reinício.

<aside>
📌 **RESUMO**:

- **Botão "Novo Jogo" Funcional:**
    - Reseta o jogo completamente, incluindo sorteio, interface e estado do botão.
- **Código Mais Organizado:**
    - Funções dedicadas (**`exibirMensagemInicial`**, **`reiniciarJogo`**) seguem o princípio de responsabilidade única.

**Dica do Tutor:**

Sempre que possível, isole comportamentos em funções específicas. Isso torna o código mais legível e fácil de ajustar!

</aside>
