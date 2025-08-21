### Código parte 01

### Lembretes

- Código Inicial

### Anotações

```jsx
let amigos = [];

function adicionarAmigo() {
     let nome = document.querySelector('input').value.trim();
     if (nome === "") {
     alert("Por favor, digite um nome!");
     } else { amigos.push(nome);
     exibirAmigos();
     } limparCampo();
}

function limparCampo() {
     let nomeInput = document.querySelector('input');
     nomeInput.value = '';
}

function exibirAmigos() {
     let listaAmigos = document.getElementById("listaAmigos");
     listaAmigos.innerHTML = "";
     for (let i = 0; i < amigos.length; i++) {
     listaAmigos.innerHTML += "<li>" + amigos[i] + "</li>"; }
}

function sortearAmigo() {
     if (amigos.length < 3) {
     alert("Adicione pelo menos 3 amigos para sortear!");
     return;
}

let indiceSorteado = Math.floor(Math.random() * amigos.length);
let amigoSorteado = amigos[indiceSorteado];

document.getElementById('resultado').innerHTML =
"<p>O amigo sorteado é: <strong>" + amigoSorteado + "</strong></p>";
}
```

<aside>
📌 **RESUMO**:

O código inicial apresenta alguns problemas: ele permite nomes repetidos, não descarta os nomes já sorteados em novos sorteios e não possui um encerramento, ficando em loop infinito. Seria interessante adicionar um aviso informando quando todos os nomes já tiverem sido sorteados.

</aside>

---

### Código parte 02

### Lembretes

- Código Final

### Anotações

```jsx
// Declaração de arrays (listas) vazias para armazenar dados
let amigos = []; // Array para armazenar todos os nomes dos amigos adicionados
let sorteados = []; // Array para controlar quais amigos já foram sorteados

// Função para adicionar um novo amigo à lista
function adicionarAmigo() {
    // Obtém o valor do campo de input, removendo espaços em branco no início e fim
    let nome = document.querySelector('input').value.trim();
    
    // Verifica se o campo está vazio
    if (nome === "") {
        // Exibe alerta se não houver nome digitado
        alert("Por favor, digite um nome!");
    } else {
        // Verifica se o nome já existe no array 'amigos'
        if (amigos.includes(nome)) {
            // Alerta sobre nome duplicado
            alert("Esse nome já existe na lista, digite outro nome!");
            
            // Limpa o campo de input
            limparCampo();
            
            // Encerra a execução da função
            return;
        } else {
            // Adiciona o novo nome ao final do array 'amigos'
            amigos.push(nome);
            
            // Atualiza a exibição da lista na página
            exibirAmigos();
            
            // Limpa o campo de input para novo preenchimento
            limparCampo();
        }
    }
}

// Função para limpar o campo de input
function limparCampo() {
    // Seleciona o elemento input
    let nomeInput = document.querySelector('input');
    
    // Define o valor do input como string vazia
    nomeInput.value = '';
}

// Função para exibir a lista de amigos na página
function exibirAmigos() {
    // Obtém a referência ao elemento UL onde a lista será exibida
    let listaAmigos = document.getElementById("listaAmigos");
    
    // Limpa o conteúdo atual da lista
    listaAmigos.innerHTML = "";
    
    // Percorre o array 'amigos' usando um loop for
    for (let i = 0; i < amigos.length; i++) {
        // Para cada amigo, adiciona um novo item (<li>) à lista
        listaAmigos.innerHTML += "<li>" + amigos[i] + "</li>";
    }
}

// Função para sortear um amigo aleatoriamente
function sortearAmigo() {
    // Verifica se há pelo menos 3 amigos na lista
    if (amigos.length < 3) {
        // Alerta sobre número insuficiente de amigos
        alert("Adicione pelo menos 3 amigos para sortear!");
        
        // Encerra a execução da função
        return;
    }

    // Verifica se todos os amigos já foram sorteados
    if (sorteados.length === amigos.length) {
        // Exibe mensagem informando que todos já foram sorteados
        document.getElementById('resultado').innerHTML =
            "<p>Todos os nomes já foram sorteados!</p>";
        
        // Encerra a execução da função
        return;
    }

    // Declara variáveis para armazenar o índice e nome do amigo sorteado
    let indiceSorteado;
    let amigoSorteado;
    
    // Loop que continua executando até encontrar um amigo não sorteado
    do {
        // Gera um número aleatório 
        indiceSorteado = Math.floor(Math.random() * amigos.length);
        
        // Obtém o nome do amigo no índice sorteado
        amigoSorteado = amigos[indiceSorteado];
        
    // Continua o loop enquanto o amigo sorteado já estiver na lista de sorteados
    } while (sorteados.includes(amigoSorteado));
    
    // Adiciona o amigo sorteado ao array de sorteados
    sorteados.push(amigoSorteado);
    
    // Exibe o resultado do sorteio na página
    document.getElementById('resultado').innerHTML =
        "<p>O amigo sorteado é: <strong>" + amigoSorteado + "</strong></p>";
}
```

<aside>
📌 **RESUMO**:

**Melhorias Futuras no Código (após concluir o restante do curso):**

- **Aprimorar o design da página**, tornando a interface mais moderna e intuitiva.
- **Adicionar um botão de “Reiniciar”**, permitindo que o sorteio seja refeito do zero sem precisar recarregar a página.
- **Incluir a opção de ocultar o nome sorteado exibido na tela**, evitando que a próxima pessoa veja quem já foi sorteado anteriormente.
- **Aumentar a complexidade do sistema**, permitindo que cada participante adicione até **3 opções de presente** ao inserir o nome.
    - Quando esse participante for sorteado, as 3 opções de presente deverão aparecer junto ao nome sorteado, facilitando a escolha do presenteador.
</aside>

---

### Explicação parte a parte do código

### Lembretes

- Detalhes

### Anotações

**1. Declaração das Variáveis Globais**

```
let amigos = [];
let sorteados = [];
```

- **`let amigos = [];`** - Cria uma lista (array) vazia para armazenar os nomes dos amigos
- **`let sorteados = [];`** - Cria outra lista vazia para guardar os nomes que já foram sorteados
- **`let`** - Palavra que declara uma variável que pode ser alterada depois
- **`[]`** - Representa um array (lista) vazio

**2. Função adicionarAmigo()**

```
function adicionarAmigo() {
```

- **`function`** - Palavra que cria uma função (bloco de código reutilizável)
- **`adicionarAmigo`** - Nome da função

```
let nome = document.querySelector('input').value.trim();
```

- Pega o valor do campo de input, remove espaços extras no início e fim
- **`document.querySelector('input')`** - Encontra o primeiro elemento input na página
- **`.value`** - Pega o valor digitado no input
- **`.trim()`** - Remove espaços em branco do início e fim do texto

```
if (nome === "") {
    alert("Por favor, digite um nome!");
}
```

- Verifica se o nome está vazio
- Se estiver vazio, mostra um alerta para o usuário

```
} else {
    if (amigos.includes(nome)) {
        alert("Esse nome já existe na lista, digite outro nome!");
        limparCampo();
        return;
    } else {
        amigos.push(nome);
        exibirAmigos();
        limparCampo();
    }
}
```

- **`amigos.includes(nome)`** - Verifica se o nome já existe na lista
- **`amigos.push(nome)`** - Adiciona o nome ao final da lista de amigos
- **`return`** - Para a execução da função imediatamente
- **`exibirAmigos()`** - Chama outra função para atualizar a lista na tela
- **`limparCampo()`** - Chama função para limpar o campo de input

**3. Função limparCampo()**

```
function limparCampo() {
    let nomeInput = document.querySelector('input');
    nomeInput.value = '';
}
```

- Encontra o campo de input e define seu valor como string vazia
- Isso limpa o campo depois de adicionar um nome

**4. Função exibirAmigos()**

```
function exibirAmigos() {
    let listaAmigos = document.getElementById("listaAmigos");
    listaAmigos.innerHTML = "";

    for (let i = 0; i < amigos.length; i++) {
        listaAmigos.innerHTML += "<li>" + amigos[i] + "</li>";
    }
}
```

- **`getElementById("listaAmigos")`** - Encontra o elemento HTML com id "listaAmigos"
- **`innerHTML = ""`** - Limpa todo o conteúdo dentro desse elemento
- **`for (let i = 0; i < amigos.length; i++)`** - Loop que repete para cada amigo na lista
- **`innerHTML += "<li>" + amigos[i] + "</li>"`** - Adiciona cada nome como item de lista

**5. Função sortearAmigo()**

```
if (amigos.length < 3) {
    alert("Adicione pelo menos 3 amigos para sortear!");
    return;
}
```

- Verifica se há pelo menos 3 amigos na lista
- Se não tiver, mostra alerta e para a função com **`return`**

```
if (sorteados.length === amigos.length) {
    document.getElementById('resultado').innerHTML =
        "<p>Todos os nomes já foram sorteados!</p>";
    return;
}
```

- Verifica se todos os amigos já foram sorteados
- **`sorteados.length === amigos.length`** - Compara se o número de sorteados é igual ao total de amigos

```
let indiceSorteado;
let amigoSorteado;

do {
    indiceSorteado = Math.floor(Math.random() * amigos.length);
    amigoSorteado = amigos[indiceSorteado];
} while (sorteados.includes(amigoSorteado));
```

- **`do...while`** - Loop que executa pelo menos uma vez e repete enquanto a condição for verdadeira
- **`Math.random()`** - Gera um número aleatório entre 0 e 1
- **`Math.floor()`** - Arredonda o número para baixo (remove decimais)
- **`Math.random() * amigos.length`** - Gera número entre 0 e o total de amigos
- **`sorteados.includes(amigoSorteado)`** - Verifica se o amigo sorteado já foi sorteado antes

```
sorteados.push(amigoSorteado);

document.getElementById('resultado').innerHTML =
    "<p>O amigo sorteado é: <strong>" + amigoSorteado + "</strong></p>";
```

- **`sorteados.push(amigoSorteado)`** - Adiciona o nome sorteado à lista de sorteados
- Atualiza o HTML para mostrar o resultado do sorteio

**Resumo do Fluxo:**

1. Usuário digita nome → clica para adicionar
2. Sistema verifica se é válido e não repetido
3. Adiciona à lista e mostra na tela
4. Quando tiver 3+ nomes, pode sortear
5. Sorteia um nome que ainda não foi sorteado
6. Mostra resultado e guarda que foi sorteado