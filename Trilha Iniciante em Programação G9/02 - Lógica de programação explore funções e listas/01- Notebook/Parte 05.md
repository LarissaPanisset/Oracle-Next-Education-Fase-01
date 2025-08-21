### **Implementando Leitura de Texto com ResponsiveVoice em JavaScript**

### Lembretes

- ResponsiveVoice
- Text-to-Speech (TTS)
- Integração via `<script>`
- Função `speak()`
- Configuração de voz (idioma, velocidade)

### Anotações

**Introdução ao ResponsiveVoice**

- **O que é?**
    
    ResponsiveVoice é uma biblioteca externa que permite converter texto em voz (TTS – *Text-to-Speech*).
    
    - **Não é nativo do JavaScript**: Requer importação via **`<script>`**.
    - **Documentação**: Disponível em *ResponsiveVoice Text To Speech* (sem necessidade de cadastro).

**Como Integrar no Projeto?**

1. **Inclusão do Script**
    
    Adiciona-se o seguinte código no HTML para carregar a biblioteca:

    ```
    <script src="https://code.responsivevoice.org/responsivevoice.js"></script>
    ```
    
2. **Momento de Uso**
    - Sempre que um texto for exibido na tela (para sincronizar escrita e fala).
    - Exemplo: Na função **`exibirTextoNaTela`**, que já manipula a exibição de textos.

**Implementação da Função de Fala**

- **Método `responsiveVoice.speak()`**
    - **Parâmetros**:
        1. **Texto**: O conteúdo a ser falado (vem do parâmetro da função).
        2. **Voz**: Especifica o idioma e gênero (ex: **`'Brazilian Portuguese Female'`**).
        3. **Configurações adicionais**:
            - **`rate`**: Velocidade da fala (ex: **`{ rate: 1.2 }`**).

**Código Adaptado**

```
function exibirTextoNaTela(tag, texto) {
    let campo = document.querySelector(tag);
    campo.innerHTML = texto;
    responsiveVoice.speak(texto, 'Brazilian Portuguese Female', { rate: 1.2 });
}
```

**Testando a Funcionalidade**

- Ao abrir o jogo, o navegador solicita permissão para usar o áudio (*Allow/Deny*).
- **Exemplo de fluxo**:
    1. Mensagem inicial: *"Escolha um número entre 1 e 10"* (falado).
    2. Após chute: Feedback como *"O número secreto é menor"* ou *"Acertou"*.

**Observações Importantes**

- **Sensibilidade a maiúsculas/minúsculas**: O nome correto é **`ResponsiveVoice`** (sem espaço).
- **Personalização**: A documentação oferece outras vozes e configurações.

<aside>

📌 **RESUMO**:

A integração do ResponsiveVoice trouxe acessibilidade e interatividade ao jogo, narrando ações em tempo real. Isso demonstra como bibliotecas externas podem expandir funcionalidades além do JavaScript puro, enriquecendo a experiência do usuário.

</aside>

---

### **Solucionando Problemas com ResponsiveVoice e Alternativa com Web Speech API**

### Lembretes

- Erro no ResponsiveVoice
- Web Speech API
- SpeechSynthesisUtterance
- Voz nativa do navegador
- Configuração de idioma e velocidade

### Anotações

**Problema Encontrado com ResponsiveVoice**

- **Erros comuns**:
    1. *"ResponsiveVoice missing API key"* → Falta de chave de API (pode exigir registro).
    2. *"Selected voice does not exist: Brazilian Portuguese Female"* → Voz não encontrada na biblioteca.
- **Impacto**: O texto não é narrado, mesmo com o código aparentemente correto.

**Solução Proposta: Web Speech API**

- **Vantagens**:
    - **Nativa dos navegadores** (Chrome, Edge, etc.) → Não requer importação de scripts externos.
    - **Sem dependências** → Elimina erros de chaves ou vozes indisponíveis.

**Implementação da Web Speech API**

1. **Remoção do ResponsiveVoice**:
    - Excluir a linha do script no HTML:

        ```
        <!-- Remover esta linha --><script src="https://code.responsivevoice.org/responsivevoice.js"></script>
        ```
        
    - Substituir a função **`responsiveVoice.speak()`** no JavaScript.
2. **Código Adaptado**:

    ```
    function exibirTextoNaTela(tag, texto) {
        let campo = document.querySelector(tag);
        campo.innerHTML = texto;
        if ('speechSynthesis' in window) {// Verifica suporte do navegadorlet utterance = new SpeechSynthesisUtterance(texto);// Cria objeto de fala
            utterance.lang = 'pt-BR';// Define idioma (português Brasil)
            utterance.rate = 1.2;// Ajusta velocidade
            window.speechSynthesis.speak(utterance);// Inicia a fala} else {
            console.log("Navegador não suporta Web Speech API.");
        }
    }
    ```
    

**Detalhes do Código**

- **`SpeechSynthesisUtterance`**: Objeto que representa o texto a ser falado.
- **`utterance.lang`**: Configura o idioma (ex: **`'pt-BR'`** para português brasileiro).
- **`utterance.rate`**: Controla a velocidade (1.0 = normal, 1.2 = 20% mais rápido).
- **Verificação de suporte**: O **`if`** evita erros em navegadores sem a API.

**Diferenças em Relação ao ResponsiveVoice**

- **Voz padrão**: Geralmente masculina (depende do navegador/sistema).
- **Personalização limitada**: Nem todos os navegadores oferecem múltiplas vozes sem configuração adicional.

**Testando a Solução**

- Reinicie o navegador após as alterações.
- A voz deve narrar automaticamente os textos exibidos (ex: *"Escolha um número entre 1 e 10"*).
- Se não funcionar, verifique o console para mensagens de erro (*F12 > Console*).

<aside>
📌 **RESUMO**:

A migração para a **Web Speech API** resolveu os problemas de dependência externa e simplificou o projeto, utilizando recursos nativos do navegador. Embora com menos opções de vozes pré-definidas, a solução é mais estável e adequada para projetos que prioritizam simplicidade e compatibilidade.

</aside>

---

### **Publicando o Jogo na Nuvem com GitHub e Vercel**

### Lembretes

- GitHub
- Repositório
- Vercel
- Deploy
- Hospedagem na nuvem

### Anotações

**Introdução à Publicação do Projeto**

- **Objetivo**: Tornar o jogo acessível a qualquer pessoa via internet, inclusive em dispositivos móveis.
- **Ferramentas utilizadas**:
    - **GitHub**: Para armazenar o código em um repositório na nuvem.
    - **Vercel**: Para hospedar o projeto e gerar um link público.

**Passo a Passo para Publicação**

1. **Preparação no GitHub**
    - **Criação de conta**:
        - Acessar [GitHub](https://github.com/) e fazer cadastro (gratuito, sem necessidade de cartão de crédito).
        - Confirmar e-mail para ativar a conta.
    - **Criar um repositório**:
        - Nomear (ex: **`jogo-do-numero-secreto`**).
        - Ignorar configurações avançadas e clicar em *"Create repository"*.
2. **Upload dos Arquivos**
    - **Método 1**: Arrastar os arquivos (**`index.html`**, **`style.css`**, **`app.js`**, imagens) para a área de upload do GitHub.
    - **Método 2**: Usar a opção *"uploading an existing file"*.
    - **Commit**: Confirmar as alterações com *"Commit Changes"*.
3. **Hospedagem com Vercel**
    - Acessar [Vercel](https://vercel.com/) e fazer login com GitHub.
    - **Importar repositório**:
        - Selecionar **`jogo-do-numero-secreto`**.
        - Opcional: Alterar o nome do projeto (ex: **`jogo`**).
    - **Deploy**: Clicar em *"Deploy"* e aguardar o processo (cerca de 1-2 minutos).
4. **Testes e Link Público**
    - Após o deploy, acessar a prévia do site gerada pela Vercel.
    - **Verificação**:
        - Permitir áudio no navegador (*"Allow"*).
        - Testar o jogo no celular ou computador (ex: chutar números e ouvir feedback).
    - **Compartilhamento**: O link da Vercel (ex: **`jogo.vercel.app`**) pode ser enviado para qualquer pessoa.

**Detalhes Importantes**

- **GitHub**:
    - Nomes de repositório devem ser únicos para cada usuário.
    - Pode-se usar **`repo.new`** para criar repositórios rapidamente.
- **Vercel**:
    - Oferece hospedagem gratuita para projetos pessoais.
    - Atualiza automaticamente o site quando o código no GitHub é modificado.

<aside>
📌 **RESUMO**:

Com o projeto publicado, qualquer pessoa pode acessar o jogo pelo link da Vercel, inclusive em dispositivos móveis. Essa etapa finaliza o ciclo de desenvolvimento, transformando um código local em uma aplicação acessível globalmente.

</aside>

---

### **Referências Essenciais para Programação em JavaScript e Desenvolvimento Web**

### Lembretes

- Lógica de programação
- JavaScript
- HTML/CSS
- Algoritmos
- Documentação técnica

### Anotações

**1. Introdução à Lógica e Programação Prática**

- **"Lógica de Programação: Crie seus primeiros programas usando Javascript e HTML"**
    - Abordagem prática para iniciantes, com exemplos que surgem de necessidades reais.
    - Ideal para quem está começando e prefere aprender fazendo.
- **"Lógica de programação com Portugol" (Joice Mendes e Rafael Muniz)**
    - Foca em algoritmos e estruturas básicas (condicionais, loops, vetores).
    - Inclui 85 exemplos de código, 55 exercícios com gabarito e um projeto prático.

**2. JavaScript e Estruturas de Dados**

- **"Estruturas de Dados e Algoritmos com JavaScript"**
    - Explica estruturas como arrays, listas e árvores com exemplos em JavaScript.
    - Recomendado para quem quer aprofundar em eficiência de código.
- **"Eloquent JavaScript" (3ª edição, 2018)**
    - Cobre desde conceitos básicos até tópicos avançados (como Node.js e programação assíncrona).
    - Disponível em inglês, com exercícios interativos online.
- **"JavaScript: O Guia Definitivo"**
    - Manual completo para dominar JavaScript e APIs do navegador.
    - Indicado para programadores experientes que buscam referência técnica.

**3. Algoritmos e Teoria Avançada**

- **"Algoritmos - Teoria e Prática" (Thomas H. Cormen)**
    - Clássico universitário sobre design e análise de algoritmos.
    - Abrange desde ordenação até algoritmos complexos como grafos.

**4. HTML, CSS e Front-End**

- **"HTML5 e CSS3: Domine a web do futuro"**
    - Ensina a criar páginas modernas com técnicas semânticas e efeitos visuais.
    - Exemplos práticos (menus, layouts responsivos).
- **"Guia Front-End: O caminho das pedras" (Diego Eis)**
    - Discussão sobre ecossistema front-end (tecnologias, mercado, carreira).
    - Não é técnico, mas ajuda a entender o panorama do desenvolvimento web.

**5. Documentação e Recursos Online**

- **MDN Web Docs**
    - Fonte oficial para sintaxe JavaScript, HTML e CSS.
    - Exemplos claros e atualizações sobre padrões web.

**Como Usar Essas Referências?**

- **Iniciantes**: Comece com *"Lógica de Programação"* ou *"Portugol"* antes de JavaScript.
- **Intermediários**: *"Eloquent JavaScript"* e *"HTML5/CSS3"* para projetos práticos.
- **Avançados**: *"Algoritmos - Cormen"* e *"Guia Definitivo de JavaScript"* para aprofundamento.

<aside>
📌 **RESUMO**:

Essas referências cobrem desde os fundamentos até tópicos avançados, atendendo a diferentes níveis de aprendizado. Combinar livros com a **MDN** garante uma base sólida e atualizada para desenvolvimento web.

</aside>
