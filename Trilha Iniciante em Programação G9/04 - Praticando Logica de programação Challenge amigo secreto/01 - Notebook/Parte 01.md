# **Praticando Logica de programação: Challenge amigo secreto**

### A Importância dos Conceitos Fundamentais na Programação

Lembretes

- Lógica de Programação
- Variáveis
- Condicionais
- Funções
- Listas
- Loops
- Base Sólida

### Anotações

- **Objetivo do Desafio:** Praticar os conceitos mais importantes que formam a base de TODA linguagem de programação.
- **Para que servem esses conceitos?**
    - **Variáveis:** Guardar informações que podem variar (dados dinâmicos).
    - **Condicionais (if/else):** Dar "inteligência" ao programa, fazendo-o tomar decisões.
    - **Funções:** Organizar o código em blocos específicos, tornando-o reutilizável e mais fácil de consertar.
    - **Listas (Arrays):** Trabalhar com grandes conjuntos de dados de uma vez.
    - **Loops (For):** Automatizar tarefas repetitivas de forma eficiente, percorrendo listas.
- **Resultado Final:** Quem domina esses conceitos consegue:
    - Criar programas que manipulam dados de forma eficaz.
    - Aprender qualquer nova linguagem com muito mais facilidade.
    - Adaptar-se a diferentes tecnologias.

<aside>
📌 **RESUMO**:

Os conceitos básicos de programação (variáveis, condicionais, funções, listas e loops) são os pilares de tudo. Eles não são apenas "coisas para decorar", mas ferramentas práticas para construir a lógica por trás de qualquer software. Dominá-los é o primeiro e mais importante passo para se tornar um bom programador, pois essa base sólida permite aprender qualquer linguagem nova no futuro. Este desafio é uma oportunidade prática para consolidar esse conhecimento fundamental.

</aside>

---

### Preparação do Ambiente e Foco na Lógica de Programação

### Lembretes

- Lógica de Programação
- JavaScript
- HTML/CSS
- Concentração
- Prática
- Raciocínio Lógico

### Anotações

- **Ambiente Preparado:**
    - O HTML e o CSS do projeto já estão prontos.
    - Objetivo: Eliminar a distração com design e estrutura visual.
- **Foco Total:**
    - A atenção deve estar 100% na escrita do código JavaScript.
    - A missão é pura e simplesmente **construir a lógica** que faz o programa funcionar.
- **Conceitos-Chave em Prática:**
    - O desafio é uma oportunidade para exercitar e consolidar o uso de:
        - **Variáveis** (armazenar dados)
        - **Condicionais** (**`if/else`** para tomada de decisão)
        - **Funções** (organizar e modularizar o código)
        - **Arrays (Listas)** (trabalhar com conjuntos de dados)
        - **Loops** (repetir tarefas de forma eficiente)
- **Objetivo Final:**
    - Melhorar o **raciocínio lógico** e a capacidade de **resolver problemas** computacionais.
    - Aprender a pensar como um programador, que é a habilidade mais fundamental.

<aside>
📌 **RESUMO**:

A atividade foi estrategicamente planejada para isolar e treinar a competência mais crucial para um desenvolvedor: a lógica de programação. Ao remover a complexidade de lidar com HTML e CSS, o foco se volta integralmente para o JavaScript, onde os conceitos fundamentais (variáveis, condicionais, funções, listas e loops) são postos em prática para resolver um problema específico. Essa abordagem permite que o aprendizado seja direcionado para o desenvolvimento do raciocínio lógico, que é a base para aprender qualquer tecnologia no futuro.

</aside>

---

### Sobre o Desafío

### Lembretes

- Amigo Secreto
- Sorteio Aleatório
- Validação
- Array
- DOM
- Event Listener
- Lógica de Programação

### Anotações

Neste desafio, você desenvolverá uma aplicação que permita aos usuários inserir nomes de amigos em uma lista para, em seguida, realizar um sorteio aleatório e determinar quem é o "amigo secreto".

O usuário deverá adicionar nomes por meio de um campo de texto e de um botão "Adicionar".

Os nomes inseridos serão exibidos em uma lista visível na página, e ao finalizar, um botão "Sortear Amigo" selecionará um dos nomes de forma aleatória, exibindo o resultado na tela.

---

## Funcionalidades:

- **Adicionar nomes**: Os usuários escreverão o nome de um amigo em um campo de texto e o adicionarão a uma lista visível ao clicar em "Adicionar".
- **Validar entrada**: Se o campo de texto estiver vazio, o programa exibirá um alerta solicitando um nome válido.
- **Visualizar a lista**: Os nomes inseridos aparecerão em uma lista abaixo do campo de entrada.
- **Sorteio aleatório**: Ao clicar no botão "Sortear Amigo", um nome da lista será selecionado aleatoriamente e exibido na página.

---

### Tarefas

### Lembretes

- 

### Anotações

- **Crie um array para armazenar os nomes**

Inicie declarando uma variável do tipo array, que armazenará os nomes dos amigos inseridos.

Exemplo:

```jsx
let amigos = []

```

**Para saber mais sobre arrays, você pode revisar a seguinte documentação:**

[Documentação sobre Array - MDN](https://developer.mozilla.org/pt-BR/docs/Web/JavaScript/Reference/Global_Objects/Array)

- **Implemente uma função para adicionar amigos**
    
    Desenvolva uma função que permita ao usuário inserir um nome no campo de texto e adicioná-lo à lista de amigos criada anteriormente.
    
    **Tarefas específicas:**
    
    - Capturar o valor do campo de entrada: Utilize document.getElementById ou document.querySelector para obter o texto inserido pelo usuário.
    - Validar a entrada: Implemente uma validação para garantir que o campo não esteja vazio.
    - Se estiver vazio, exiba um alerta com a mensagem de erro: "Por favor, insira um nome."
    - Atualizar o array de amigos: Se o valor for válido, adicione-o ao array que armazena os nomes dos amigos usando o método .push().
    - Limpar o campo de entrada: Após adicionar o nome, redefina o campo de texto para uma string vazia.

- **Implementa uma função para atualizar a lista de amigos**
    
    Crie uma função que percorra o `array` amigos e adicione cada nome como um elemento `<li>` dentro de uma lista HTML. Use `innerHTML` para limpar a lista antes de adicionar novos elementos.
    
    ## Tarefas específicas:
    
    - Obter o elemento da lista: Utilize `document.getElementById()` ou `document.querySelector()` para selecionar a lista onde os amigos serão exibidos.
    - Limpar a lista existente: Defina `lista.innerHTML = ""` para garantir que não haja **duplicados** ao atualizar.
    - Percorrer o array: Use um loop for para percorrer o array `amigos` e criar elementos de lista (`<li>`) para cada nome.
    - Adicionar elementos à lista: Para cada amigo, crie um novo elemento de lista.
    
- **Implementa uma função para sortear os amigos**
    
    Escreva uma função que selecione aleatoriamente um dos nomes armazenados no array `amigos`.
    
    Use `Math.random()` e `Math.floor()` para obter um índice aleatório.
    
    ## Tarefas específicas:
    
    - Validar que há amigos disponíveis: Antes de sortear, verificar se o array `amigos` não está vazio.
    - Gerar um índice aleatório: Usar `Math.random()` e `Math.floor()` para selecionar um índice aleatório do *array*.
    - Obter o nome sorteado: Utilizar o índice aleatório para acessar o nome correspondente no *array*.
    - Mostrar o resultado: Atualizar o conteúdo do elemento de resultado usando `document.getElementById()` e `innerHTML` para exibir o amigo sorteado.

---

### A Importância do [README.md](http://readme.md/) em um Projeto

### Lembretes

- README
- Documentação
- Markdown
- Instalação
- Processo Seletivo
- Boas Práticas

### Anotações

**O que é o README?**

- Um arquivo de texto (extensão **`.md`** = Markdown) que serve como a página inicial e o manual de um projeto.
- É o **primeiro ponto de contato** para qualquer pessoa que acesse o seu código.

**Por que é tão importante?**

- **Comunicação Clara:** Explica o propósito, a estrutura e o funcionamento do projeto de forma direta.
- **Facilita a Colaboração:** Permite que outros desenvolvedores entendam e usem o seu código rapidamente, sem precisar te perguntar.
- **Destaque em Processos Seletivos:** Em vagas de emprego, um README bem feito é a sua chance de impressionar recrutadores e demonstrar profissionalismo antes mesmo de eles olharem o código.
- **Guia de Uso:** Funciona como um manual de instruções para instalar, configurar e executar a aplicação.

**O que um BOM README deve conter?**

1. **Título e Descrição:** O que o projeto faz?
2. **Funcionalidades:** O que o projeto entrega? (ex: "Adicionar nomes", "Sortear aleatoriamente")
3. **Tecnologias Usadas:** Linguagens, frameworks e bibliotecas.
4. **Como Instalar e Executar:** Um guia passo a passo das dependências e dos comandos para rodar o projeto.
5. **Possíveis Problemas e Soluções:** Antecipação de erros comuns e como resolvê-los.

<aside>
📌 **RESUMO**:

O README.md é muito mais que um simples arquivo; é a **porta de entrada** e a **vitrine** do seu projeto. Ele é uma ferramenta essencial de comunicação e documentação que demonstra organização, profissionalismo e empatia com quem for utilizar o seu trabalho. Um README bem estruturado, com informações claras sobre instalação, uso e propósito, não só facilita a vida de outros desenvolvedores como também é um diferencial crucial em processos seletivos, mostrando sua capacidade de apresentar e entregar um projeto completo e de qualidade. Investir tempo em um bom README é investir no sucesso do seu projeto.

</aside>