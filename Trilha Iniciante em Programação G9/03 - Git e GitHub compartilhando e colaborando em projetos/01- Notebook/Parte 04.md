### Como Apagar Commits do Histórico com Git Reset

### Lembretes

- **`git reset --hard`**
- Remover commits do histórico
- ID do commit
- Diferença entre **`revert`** e **`reset`**
- Commits locais vs. remotos

### Anotações

### **1. Contexto: Quando Apagar um Commit?**

- Situações em que **não basta reverter** (criar um novo commit desfazendo alterações), mas sim **apagar completamente** um commit do histórico:
    - **Funcionalidade cancelada:** Commits de uma tarefa que foi descartada.
    - **Duplicação de tarefas:** Outra pessoa fez a mesma alteração e subiu antes.

### **2. Simulando um Commit para Remoção**

- **Modificação no código:** Removeram o título **`<h1>`** do **`index.html`**.
- **Commit local:** Fizeram um commit (**`"Remove título"`**), mas **não sincronizaram** com o GitHub.

### **3. Comando `git reset --hard`**

- **Objetivo:** Apagar um commit **local** do histórico.
- **Passo a Passo:**
    1. Usar **`git log`** para encontrar o **ID do commit** a ser removido.
    2. **Erro comum:** Passar o ID do commit **errado** (deve-se passar o ID do commit **anterior** ao que queremos apagar).
        - Exemplo:
            
            ```
            git reset --hard 7f69ff8220e093d2c8ad234ceec109a6e794e5f6# ID do commit ANTERIOR
            ```
            
    3. **Efeito:**
        - O commit some do histórico (**`git log`**).
        - As alterações são **desfeitas** no código (o **`<h1>`** volta a aparecer).

### **4. Diferença Entre `git revert` e `git reset`**

| **`git revert`** | **`git reset --hard`** |
| --- | --- |
| Cria um **novo commit** desfazendo alterações. | **Apaga o commit** do histórico. |
| Mantém o rastreamento da mudança. | Remove o commit **definitivamente**. |
| Seguro para commits **já sincronizados**. | **Só deve ser usado localmente** (antes do **`push`**). |

### **5. Cuidados ao Usar `git reset`**

- **Nunca usar em commits já enviados ao GitHub** (pode causar conflitos para outros colaboradores).
- **Alternativa para commits remotos:** Usar **`git revert`** ou comunicação clara com a equipe.

**Nota:** Essa aula reforça a importância de **trabalhar com branches** para evitar a necessidade de apagar commits compartilhados. Em time, alinhamento é essencial!

<aside>
📌 **RESUMO**:

O **`git reset --hard`** é uma ferramenta poderosa para **excluir commits locais** que não devem mais existir no histórico. No entanto:

- **Use com cautela:** Só aplique em commits **não sincronizados** com o repositório remoto.
- **Prefira `git revert` para commits públicos:** Mantém a integridade do histórico colaborativo.

**Dica:** Sempre verifique o **`git log`** antes de usar **`reset`** para garantir que está apagando o commit correto!

</aside>

---

### **Entendendo o `git reset` em Profundidade**

### Lembretes

- **`git reset`**
- **`-soft`**, **`-mixed`**, **`-hard`**, **`-merge`**, **`-keep`**
- HEAD, ORIG_HEAD
- Índice vs. Árvore de Trabalho
- Desfazer commits vs. Modificar histórico

### Anotações

### **1. O Que é o `git reset`?**

O **`git reset`** é um comando versátil que permite:

- **Redefinir o HEAD** para um commit específico (**`<tree-ish>`**).
- **Modificar o índice (staging area)** e/ou a **árvore de trabalho** (dependendo do modo usado).
- **Desfazer ações** como **`git add`** ou commits indesejados.

### **2. Formas Básicas de Uso**

- **Resetando arquivos específicos:**
    
    ```
    git reset <pathspec># Equivalente a `git restore --staged <pathspec>`
    ```
    
    - Remove arquivos do índice (staging), mas mantém alterações na árvore de trabalho.
    - Útil para desfazer um **`git add`** acidental.
- **Reset interativo (`p`):**
    
    ```
    git reset -p# Seleciona partes (hunks) para remover do índice
    ```
    
    - Oposto de **`git add -p`**.
- **Resetando o branch inteiro:**
    
    ```
    git reset [<modo>] [<commit>]
    ```
    
    - Redefine o HEAD para **`<commit>`** e atualiza índice/árvore de trabalho conforme o **`<modo>`**.

### **3. Modos Principais do `git reset`**

| **Modo** | **Índice** | **Árvore de Trabalho** | **Uso Típico** |
| --- | --- | --- | --- |
| **`--soft`** | **Não altera** | **Não altera** | Alterar mensagem de commit ou reorganizar commits. |
| **`--mixed`** | **Redefine** | **Não altera** (padrão) | Desfazer **`git add`** ou preparar novos commits. |
| **`--hard`** | **Redefine** | **Redefine** | Descarta todas as alterações locais (*cuidado!*). |
| **`--merge`** | **Redefine** | **Atualiza se seguro** | Abortar uma mesclagem conflitosa. |
| **`--keep`** | **Redefine** | **Preserva alterações** | Remover commits locais sem perder trabalho. |

### **4. Exemplos Práticos**

- **Desfazer um `git add`:**
    
    ```
    git reset arquivo.txt# Remove do índice, mantém alterações no diretório
    ```
    
- **Corrigir um commit (mensagem/arquivos esquecidos):**
    
    ```
    git reset --soft HEAD^# Remove o último commit, mantém alterações no índicegit commit -m "Nova mensagem"# Recomenda com os arquivos corrigidos
    ```
    
- **Descartar commits locais não enviados:**
    
    ```
    git reset --hard HEAD~3# Apaga os últimos 3 commits *e* alterações locais
    ```
    
- **Salvar trabalho em progresso antes de trocar de branch:**
    
    ```
    git commit -am "Snapshot WIP"# Commit temporáriogit switch outro-branch
    git switch feature
    git reset --soft HEAD^# Volta ao estado anterior, mantendo alterações
    ```
    

### **5. Cenários Avançados**

- **Dividir um commit em partes menores:**
    1. **`git reset -N HEAD^`** (remove o commit, mantém alterações).
    2. Use **`git add -p`** para selecionar mudanças gradualmente.
    3. Faça commits separados com **`git commit -c HEAD@{1}`**.
- **Abortar uma mesclagem conflituosa:**
    
    ```
    git reset --merge ORIG_HEAD
    ```
    

### **6. Cuidados Importantes**

- **`-hard` é destrutivo:** Perde alterações não commitadas permanentemente.
- **Evite reset em commits públicos:** Pode causar problemas para outros colaboradores.
- **Use `ORIG_HEAD` para recuperação:** Armazena o estado anterior do HEAD após operações críticas.

**Nota:** Este comando é central no fluxo de trabalho do Git. Dominá-lo permite corrigir erros, reorganizar commits e manter um histórico limpo — mas sempre com atenção ao contexto colaborativo!

<aside>
📌 **RESUMO**:

O **`git reset`** é uma ferramenta **poderosa** para gerenciar o histórico e o estado do repositório, mas exige **cautela**. Escolha o modo adequado:

- **`-soft`/`-mixed`:** Para ajustes "seguros" (ex: corrigir commits).
- **`-hard`:** Apenas para descartar alterações locais indesejadas.
- **`-merge`/`-keep`:** Para situações específicas (conflitos ou preservação de trabalho).

**Dica:** Sempre verifique **`git status`** e **`git log`** antes de usar **`reset`** para evitar perdas acidentais. Em equipe, prefira **`git revert`** para commits já compartilhados.

</aside>

---

### Como Corrigir Commits com git commit --amend

### Lembretes

- **`git commit --amend`**
- Corrigir mensagens de commit
- Adicionar arquivos esquecidos
- Modificar commits locais
- Histórico limpo

### Anotações

### **1. Contexto: Por Que Alterar um Commit?**

Situações comuns onde é necessário **modificar um commit existente** em vez de criar um novo:

- **Mensagem incorreta:** Exemplo: "Trocando texto do botão para *avidinhar*" (erro de digitação).
- **Arquivos esquecidos:** Quando você faz um commit, mas esquece de incluir um arquivo modificado.

### **2. Comando `git commit --amend`**

- **Funcionalidade:**
    - Permite **alterar o último commit** (mensagem ou conteúdo) sem criar um novo.
    - Ideal para correções rápidas em commits **ainda não sincronizados** com o repositório remoto.
- **Sintaxe para corrigir mensagem:**
    
    ```
    git commit --amend -m "Nova mensagem correta"
    ```
    
    - Exemplo:
        
        ```
        git commit --amend -m "Trocando botão para adivinhar"
        ```
        
- **Sintaxe para adicionar arquivos esquecidos:**
    1. Adicione o arquivo esquecido ao índice:
        
        ```
        git add arquivo-esquecido.html
        ```
        
    2. Use **`-amend`** para incluí-lo no último commit:
        
        ```
        git commit --amend --no-edit# Mantém a mensagem original
        ```
        

### **3. Passo a Passo na Aula**

1. **Identificação do problema:**
    - Commit com mensagem errada ("avidinhar" em vez de "adivinhar").
2. **Uso do `-amend`:**
    - Comando executado:
        
        ```
        git commit --amend -m "Trocando botão para adivinhar"
        ```
        
3. **Verificação:**
    - **`git log`** confirmou que o commit foi **alterado** (não criou um novo).

### **4. Observações Importantes**

- **Apenas para commits locais:** Não usar em commits já enviados ao GitHub (pode causar conflitos).
- **Altera o hash do commit:** O commit original é substituído por um novo com o mesmo conteúdo (mas hash diferente).
- **Cuidado com `-hard`:** Se combinado com **`reset --hard`**, pode perder alterações não commitadas.

### **5. Casos de Uso Adicionais**

- **Corrigir autores:**
    
    ```
    git commit --amend --author="Nome <email@exemplo.com>"
    ```
    
- **Alterar data do commit:**
    
    ```
    git commit --amend --date="2023-10-01T12:00:00"
    ```
    

**Nota:** Esta aula reforça a importância de revisar commits antes do **`push`**. Um histórico bem documentado facilita a manutenção e colaboração no projeto.

<aside>
📌 **RESUMO**:

O **`git commit --amend`** é uma ferramenta **essencial** para manter um histórico limpo e preciso:

- **Vantagens:**
    - Elimina a necessidade de múltiplos commits para correções simples.
    - Preserva a organização do projeto sem poluir o log.
- **Recomendações:**
    - Use apenas para commits **locais** (não sincronizados).
    - Combine com **`git add`** para incluir arquivos esquecidos.
    - Evite em colaboração simultânea (prefira **`git revert`** para commits remotos).

**Dica:** Para commits mais complexos, considere usar **`git rebase -i`** (interativo), que veremos em aulas futuras!

</aside>

---

### Responsabilidade ao Alterar o Histórico de Commits

### Lembretes

- Histórico de commits
- Commits locais vs. remotos
- Colaboração em equipe
- Integridade do projeto
- Boas práticas

### Anotações

### **1. Introdução ao Problema**

Modificar o histórico de commits no Git é uma funcionalidade poderosa, mas que exige **cautela**. Enquanto comandos como **`git commit --amend`**, **`git reset`** e **`git rebase`** são úteis para ajustes locais, seu uso inadequado pode causar problemas significativos em projetos colaborativos.

### **2. Quando é Seguro Alterar o Histórico?**

- **Apenas para commits locais:** Commits que ainda não foram enviados ao repositório remoto (GitHub, GitLab, etc.) podem ser modificados sem grandes riscos.
- **Exemplos de uso seguro:**
    - Corrigir mensagens de commit mal escritas.
    - Adicionar arquivos esquecidos ao último commit.
    - Reorganizar commits antes de compartilhá-los.

### **3. Riscos de Modificar Commits Públicos**

- **Problemas de sincronização:** Se outras pessoas já basearam seu trabalho em um commit que você alterou, isso pode causar conflitos complexos.
- **Quebra do fluxo de colaboração:**
    - Outros desenvolvedores podem ter feito **`pull`** do commit original.
    - Alterações forçadas (**`git push --force`**) podem sobrescrever o trabalho alheio.
- **Histórico confuso:** Múltiplas versões do mesmo commit podem dificultar o rastreamento de bugs.

### **4. Boas Práticas para Trabalho em Equipe**

1. **Evite `-amend` e `reset` em commits compartilhados:**
    - Prefira **`git revert`** para desfazer alterações publicadas.
2. **Comunique alterações:**
    - Se for necessário modificar um commit remoto, avise a equipe.
3. **Use branches para experimentos:**
    - Teste alterações em branches temporários antes de mesclá-las ao **`main`**.
4. **Documente decisões:**
    - Mensagens de commit claras reduzem a necessidade de modificações posteriores.

### **5. Casos de Exceção**

- **Repositórios pessoais:** Se você trabalha sozinho, pode modificar o histórico com mais liberdade.
- **Limpeza de dados sensíveis:** Às vezes, é necessário remover informações confidenciais acidentalmente commitadas (usando **`git filter-branch`** ou **`BFG Repo-Cleaner`**).

**Nota:** Lembre-se de que o Git é uma ferramenta colaborativa. Preservar a integridade do histórico é tão importante quanto escrever código funcional!

<aside>
📌 **RESUMO**:

Alterar o histórico de commits é como editar o passado: pode ser útil, mas traz consequências.

- **Principais lições:**
    - **Local = Livre:** Commits não compartilhados podem ser ajustados sem medo.
    - **Remoto = Sagrado:** Evite modificar commits públicos para manter a harmonia da equipe.
    - **Clareza é chave:** Um histórico bem documentado reduz a necessidade de correções.

**Dica final:** Quando em dúvida, use **`git revert`** para desfazer alterações publicamente, mantendo o histórico transparente para todos.

</aside>

---

### **Como Criar uma Documentação Eficaz com README.md no GitHub**

### Lembretes

- README.md
- Documentação de projetos
- Markdown e HTML
- Boas práticas de documentação
- Exclusão de arquivos sensíveis

### Anotações

### **1. A Importância da Documentação**

- **Código sem documentação** é difícil de entender para novos colaboradores ou usuários.
- O **README.md** é o cartão de visita do projeto no GitHub, exibido automaticamente na página inicial do repositório.

### **2. O Que é um README.md?**

- **Finalidade:** Explicar o projeto, tecnologias usadas, como contribuir e outras informações relevantes.
- **Formato:**
    - Escrito em **Markdown** (linguagem simples de formatação) ou **HTML** para estruturas mais complexas.
    - Nomeado como **`README.md`** (obrigatoriamente em maiúsculas).

### **3. Criando o README.md**

- **Pelo GitHub:**
    1. Clicar em **"Add a README"** na página do repositório.
    2. Usar o editor integrado (com opções de **Preview** para visualização em tempo real).
    3. Fazer commit diretamente pela interface.
- **Pelo VS Code:**
    - Criar um arquivo **`README.md`** na raiz do projeto e formatá-lo localmente antes do **`push`**.

### **4. Estrutura Básica do README**

Exemplo usado na aula:

```
# Jogo do número secreto

## 💡 Sobre
Projeto utilizado nos cursos de lógica de programação da Alura.

## 🛠 Tecnologias
<div><img src="https://img.shields.io/badge/HTML5-E34F26?style=for-the-badge&logo=html5&logoColor=white"><img src="https://img.shields.io/badge/CSS3-1572B6?style=for-the-badge&logo=css3&logoColor=white"><img src="https://img.shields.io/badge/JavaScript-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black"></div>## 👥 Time
- [Gabrielle Ribeiro](link-do-github)
- [Rodrigo Caneppele](link-do-github)
```

### **5. Formatação Avançada**

- **Markdown:**
    - Títulos (**`#`**, **`##`**), listas (), links (**`[texto](url)`**), imagens (**`![alt](url)`**).
- **HTML:**
    - Permite tabelas, divs, badges personalizados (como os do exemplo).
- **Ferramentas úteis:**
    - [Shields.io](https://shields.io/) para badges de tecnologias.

### **6. Cuidados com Arquivos Sensíveis**

- **O que não deve ser commitado:**
    - Arquivos de configuração com senhas (**`.env`**).
    - Cache de dependências (**`node_modules/`**).
    - Arquivos gerados automaticamente (**`.log`**, **`.tmp`**).
- **Solução:** Usar o **`.gitignore`** para listar arquivos/pastas a serem ignorados (tópico da próxima aula).

**Nota:** A documentação é tão importante quanto o código! Um projeto bem documentado economiza horas de dúvidas e retrabalho. Na próxima aula, aprenderemos a usar **`.gitignore`** para proteger arquivos sensíveis.

<aside>
📌 **RESUMO**:

Um **README.md bem estruturado** é essencial para:

- **Facilitar a colaboração:** Novos membros entendem o projeto rapidamente.
- **Atrair contribuidores:** Projetos open-source com documentação clara são mais acessíveis.
- **Manter organização:** Documentação integrada ao repositório evita perda de contexto.

**Dicas para um README eficaz:**

1. Seja conciso, mas cubra: **objetivo**, **tecnologias**, **como executar** e **como contribuir**.
2. Use **badges** para destacar tecnologias e status do projeto.
3. Inclua **exemplos de uso** ou screenshots para projetos visuais.
</aside>

---

### Como Ignorar Arquivos no Git com .gitignore

### Lembretes

- **`.gitignore`**
- Arquivos temporários
- Segurança de dados
- gitignore.io
- Boas práticas

### Anotações

### **1. O Problema dos Arquivos Indesejados**

Situações onde **não queremos enviar certos arquivos** para o repositório remoto:

- **Arquivos temporários** (ex: **`temp/teste.txt`**).
- **Dados sensíveis** (senhas em **`.env`**).
- **Arquivos gerados automaticamente** (logs, cache).

### **2. Solução: O Arquivo `.gitignore`**

- **Finalidade:** Listar arquivos/pastas que o Git deve ignorar.
- **Localização:** Na raiz do projeto (mesmo nível da pasta **`.git`**).
- **Sintaxe básica:**
    
    ```
    # Ignorar pasta específica
    temp/
    
    # Ignorar todos os arquivos .log
    *.log
    
    # Ignorar arquivo específico
    config.env
    ```
    

### **3. Passo a Passo na Aula**

1. **Criação do `.gitignore`:**
    - Nome exato: **`.gitignore`** (com ponto no início).
    - Adicionada a linha **`temp/`** para ignorar a pasta temporária.
2. **Teste prático:**
    - Criaram uma pasta **`temp/`** com **`teste.txt`**.
    - Modificaram **`index.html`** (trocando "Adivinhe" por "Descubra").
    - Commit incluindo apenas **`index.html`** e **`.gitignore`** – a pasta **`temp/`** foi **ignorada com sucesso**.

### **4. Ferramentas para Gerar `.gitignore`**

- **gitignore.io:**
    - Gera templates prontos para linguagens/frameworks (Java, Python, Django, etc.).
    - Exemplo para Java:
        
        ```
        *.class
        *.log
        *.jar
        ```
        
- **Por que usar?**
    - Evita esquecer arquivos comuns a serem ignorados.
    - Padroniza entre projetos da mesma stack.

### **5. Cuidados Importantes**

- **Arquivos já rastreados:** Se um arquivo já foi commitado, adicioná-lo ao **`.gitignore`** **não o remove** do histórico. Use:
    
    ```
    git rm --cached arquivo.txt
    ```
    
- **Dados sensíveis:** Nunca commit arquivos como **`.env`**. Se ocorrer, reveja as credenciais!

<aside>
📌 **RESUMO**:

O **`.gitignore`** é **essencial** para:

✅ **Manter o repositório limpo** – sem lixo ou arquivos desnecessários.

✅ **Proteger informações sensíveis** – evita vazamento de dados.

✅ **Otimizar colaboração** – todos usam os mesmos padrões.

**Dicas de ouro:**

1. **Crie o `.gitignore` no início do projeto** para evitar commits acidentais.
2. **Use templates do gitignore.io** para sua linguagem/framework.
3. **Revise antes de commits** com **`git status`** para confirmar o que será enviado.
</aside>

---

### Como Compartilhar Trechos de Código com o GitHub Gist

### Lembretes

- GitHub Gist
- Compartilhamento de código
- Gists públicos vs. secretos
- Formatação de código
- Colaboração rápida

### Anotações

### **1. Introdução ao GitHub Gist**

Como compartilhar **trechos específicos de código** sem criar um repositório completo:

- **Problema:** Compartilhar apenas partes relevantes (ex: uma biblioteca ou função).
- **Solução:** Usar o **GitHub Gist**, uma ferramenta para snippets de código.

### **2. Criando um Gist**

- **Acesso:**
    - Clicar em "+" no canto superior direito do GitHub > "New Gist".
- **Campos do formulário:**
    1. **Descrição:** Explicação do propósito do código (ex: "Código de leitura de tela").
    2. **Nome do arquivo:** Definir um nome (ex: **`index.html`**).
    3. **Conteúdo:** Colar o trecho de código (ex: tag **`<script>`**).
    4. **Adicionar múltiplos arquivos:** Botão "Add file" para incluir outros snippets (ex: **`app.js`**).

### **3. Configurações de Visibilidade**

- **Público:** Qualquer pessoa pode acessar (aparece no perfil).
- **Secreto:** Apenas quem tem o link pode ver (não listado publicamente).

### **4. Exemplo Prático**

- **Código compartilhado:**
    - **`index.html`**: Inclusão da biblioteca ResponsiveVoice.js:

        ```
        <script src="https://code.responsivevoice.org/responsivevoice.js"></script>
        ```
        
    - **`app.js`**: Configuração da voz:

        ```
        responsiveVoice.speak(texto, 'Brazilian Portuguese Female', {rate:1.2});
        ```
        
- **URL gerada:** Pode ser compartilhada diretamente (ex: **`gist.github.com/username/ID`**).

### **5. Vantagens do Gist**

- **Rapidez:** Sem necessidade de criar repositórios ou commits.
- **Formatação:** Destaque de sintaxe para várias linguagens.
- **Colaboração:** Permite comentários e forks (como um repositório miniaturizado).

### **6. Casos de Uso Comuns**

- Compartilhar soluções em fóruns (ex: Stack Overflow).
- Enviar exemplos de código para colegas.
- Documentar snippets úteis (ex: configurações de API).

**Nota:** Gists são parte do seu portfólio GitHub – mantenha-os organizados! 

<aside>
📌 **RESUMO**:

O **GitHub Gist** é a ferramenta ideal para:

✅ **Compartilhamento ágil** de trechos de código.

✅ **Documentação técnica** de funções ou bibliotecas.

✅ **Colaboração pontual** sem overhead de repositórios.

**Dicas de uso:**

1. Use **Gists públicos** para conteúdos educativos ou open source.
2. **Gists secretos** são ideais para dados sensíveis (mas evite credenciais!).
3. Inclua **descrições claras** para facilitar o entendimento.
</aside>

---

### Introdução a Branches e Merges no Git

### Lembretes

- Branches (ramificações)
- Merge (mesclagem)
- Fluxo de trabalho
- Controle de versão
- Git avançado

### Anotações

### **1. O Que São Branches?**

- **Definição:**
    - Branches são **ramificações** independentes no histórico do Git.
    - Permitem trabalhar em **diferentes versões** do projeto simultaneamente.
- **Analogia:**
    - Imagine um livro com **rascunhos paralelos** (ex: capítulo 1 v1, capítulo 1 v2).

### **2. Por Que Usar Branches?**

- **Isolar features:** Desenvolver funcionalidades sem afetar a versão principal (**`main`**).
- **Testar ideias:** Experimentar mudanças sem risco.
- **Colaboração:** Múltiplos devs podem trabalhar em branches separadas.

### **3. O Que é Merge?**

- **Definição:**
    - Processo de **unir** o conteúdo de uma branch com outra (ex: **`feature/login`** → **`main`**).
- **Tipos comuns:**
    - **Fast-forward:** Quando não há conflitos.
    - **Merge commit:** Quando há alterações concorrentes.

### **4. Fluxo Básico com Branches**

1. Criar branch:
    
    ```
    git branch nova-feature
    ```
    
2. Trocar para a branch:
    
    ```
    git switch nova-feature
    ```
    
3. Fazer commits na branch.
4. Mesclar com **`main`**:
    
    ```
    git switch main
    git merge nova-feature
    ```
    

### **5. Quando Aprender Mais?**

- **Curso recomendado:**
    - *Git e GitHub: dominando controle de versão de código* (Alura).
- **Pré-requisitos:**
    - Conhecimento básico de Git (commits, repositórios, GitHub).

<aside>
📌 **RESUMO**:

Branches e merges são **essenciais** para:

✅ **Trabalho em equipe** eficiente.

✅ **Gerenciamento complexo** de versões.

✅ **Experimentos seguros** sem quebrar o código principal.

**Dica:** Domine os conceitos básicos do Git antes de avançar para branches!

</aside>

---

### Recapitulação: Domínio do Fluxo de Trabalho com Git e GitHub

### Lembretes

- Fluxo de trabalho colaborativo
- Comandos essenciais do Git
- Resolução de conflitos
- Documentação (README.md)
- GitHub Gist

### Anotações

### **1. Introdução ao Git e GitHub**

- **Objetivo inicial:** Compartilhar o projeto *Jogo do Número Secreto*.
- **GitHub:** Plataforma para hospedar repositórios e colaborar em equipe.
- **Primeiros passos:**
    - Criação de conta no GitHub.
    - Configuração de um repositório remoto.

### **2. Comandos Fundamentais**

| **Comando** | **Função** | **Uso no Curso** |
| --- | --- | --- |
| **`git status`** | Verifica o estado dos arquivos. | Identificar alterações não rastreadas. |
| **`git add`** | Adiciona arquivos ao índice (staging). | Preparar mudanças para commit. |
| **`git commit`** | Registra alterações no histórico. | Salvar versões com mensagens descritivas. |
| **`git push`** | Envia commits locais para o repositório remoto. | Sincronizar com o GitHub. |
| **`git pull`** | Atualiza o repositório local com alterações remotas. | Evitar desatualizações. |

### **3. Trabalho Colaborativo**

- **Conflitos:** Ocorrem quando duas pessoas editam a mesma linha de código.
    - **Solução:** Usar ferramentas de merge (ex: VS Code) para resolver manualmente.
- **Boa prática:** Sempre fazer **`git pull`** antes de começar a trabalhar.

### **4. Gerenciamento do Histórico**

- **`git revert`:** Desfaz um commit criando um novo (seguro para commits públicos).
- **`git reset`:** Apaga commits locais (*cuidado:* não usar em commits compartilhados).
- **`git commit --amend`:** Corrige mensagens ou adiciona arquivos ao último commit.

### **5. Documentação e Organização**

- **README.md:**
    - Arquivo de apresentação do projeto.
    - Inclui: descrição, tecnologias, equipe.
- **.gitignore:**
    - Lista arquivos/pastas a serem ignorados (ex: **`node_modules/`**, **`.env`**).

### **6. Compartilhamento de Trechos**

- **GitHub Gist:**
    - Para snippets de código isolados.
    - Exemplo: Compartilhar uma função específica sem criar um repositório.

<aside>
📌 **RESUMO**:

Este curso equipou você com as habilidades essenciais para:

✅ **Colaborar eficientemente** usando Git/GitHub.

✅ **Manter um histórico organizado** com commits claros.

✅ **Documentar projetos** profissionalmente.

✅ **Resolver conflitos** e gerenciar versões.

"O Git/GitHub são ferramentas indispensáveis no desenvolvimento moderno. Continue explorando e aprofundando seu conhecimento – seu futuro eu agradecerá!" 🚀

</aside>

---

### Recursos Essenciais para Dominar Git, GitHub e Boas Práticas

### Lembretes

- Referências

### Anotações

### **1. Livros Recomendados**

- **"Controlando versões com Git e GitHub"** (Alexandre Aquiles & Rodrigo Ferreira):
    - Aborda desde comandos básicos até branches, tags e resolução de conflitos.
    - Inclui práticas para hospedar repositórios no GitHub.
- **"Introducing GitHub" (O’Reilly)** (em inglês):
    - Focado em iniciantes, com exemplos de colaboração em projetos.
    - Ideal para não desenvolvedores (PMs, designers) que usam GitHub.
- **"Learning Git" (O’Reilly)** (em inglês):
    - Ensino visual com analogias e exercícios práticos.
    - Perfeito para estudantes e juniores.

### **2. Documentações Oficiais**

- **Documentação do Git:**
    - Referência completa de comandos e fluxos de trabalho.
    - Acesse: [git-scm.com](https://git-scm.com/).
- **Conventional Commits:**
    - Padronização de mensagens de commit (ex: **`feat:`**, **`fix:`**).
    - Alinhado com Semantic Versioning (SemVer).
    - Link: [conventionalcommits.org](https://www.conventionalcommits.org/).

### **3. Ferramentas Úteis**

- **Gerador de .gitignore:**
    - Cria templates para ignorar arquivos específicos da sua stack.
    - Disponível em: [gitignore.io](https://www.toptal.com/developers/gitignore).
- **Guia Markdown:**
    - Sintaxe para formatar READMEs e documentação.
    - Referência: [Markdown Guide](https://www.markdownguide.org/).

### **4. Artigos Complementares**

- **"Markdown: como trabalhar com essa linguagem de markup?":**
    - Explica aplicações práticas do Markdown em projetos tech.

<aside>
📌 **RESUMO**:

Estes recursos ajudam a:

✅ **Aprofundar conceitos** além do básico.

✅ **Padronizar práticas** (como commits e documentação).

✅ **Resolver problemas** com referências confiáveis.

**Dica:** Comece pela documentação oficial e depois explore os livros para casos de uso realistas!

</aside>
