### Controle de Versões no Git: Como Funciona?

### Lembretes

- Snapshots (instantâneos)
- Commits como registros completos
- ID único (hash SHA-1)
- Cadeia de commits
- Histórico de versões

### Anotações

**1. O Modelo de Snapshots do Git**

- Cada **commit** é um **snapshot** (foto instantânea) completo do projeto naquele momento.
    - Diferente de sistemas que armazenam apenas **diferenças entre arquivos**, o Git guarda o **estado total** dos arquivos.
    - Exemplo: Se você alterar 1 linha em um arquivo de 1000 linhas, o Git salva uma nova versão desse arquivo inteiro (de forma otimizada).

**2. Estrutura de um Commit**

✔ **ID único (hash SHA-1):**

- Código alfanumérico (ex: **`a1b2c3d...`**) que identifica o commit de forma imutável.
    
    ✔ **Referência aos commits pais:**
    
- Ligações aos commits anteriores, formando uma **linha do tempo** (cadeia de commits).
    
    ✔ **Metadados:**
    
- Autor, data, mensagem e árvore de arquivos.

**3. Vantagens do Sistema de Snapshots**

✅ **Rastreabilidade precisa:**

- Permite voltar para qualquer versão passada sem depender de diferenças acumuladas.
    
    ✅ **Desempenho:**
    
- Operações como **`checkout`** e **`branch`** são rápidas (o Git acessa snapshots, não recálculos).
    
    ✅ **Consistência:**
    
- Cada commit representa um estado **funcional** do projeto (seguindo boas práticas).

**4. Como o Git Gerencia as Alterações?**

- **Arquivos não modificados:**
    - O Git **não recopia** arquivos inalterados entre commits. Em vez disso, usa **ponteiros** para o snapshot anterior (economizando espaço).
- **Arquivos modificados:**
    - Gera um novo snapshot apenas para as mudanças.

**5. Visualizando o Histórico**

- Comando **`git log`**:
    - Mostra a sequência de commits, seus IDs, autores e mensagens.
    - Exemplo: bash
        
        ```
        commit a1b2c3d (HEAD -> main)
        Author: João Silva <joao@exemplo.com>
        Date:   Seg 10 Jan 2022 14:00:00 -03
            Adicionar sistema de login
        ```
        

**6. Documentação Oficial**

- Para aprofundamento, consulte:
    - [Git Documentation](https://git-scm.com/doc) (seção "Git Internals").

<aside>
📌 **RESUMO**:

O Git é um **sistema distribuído de snapshots** que:

🔹**Preserva a integridade** do código em cada versão.

🔹**Facilita a colaboração** com histórico detalhado e reversível.

🔹**Otimiza armazenamento** ao evitar redundâncias.

</aside>

---

### Colaboração no GitHub: Enviando Commits com Git Push

### Lembretes

- **`git push`**
- Repositório remoto vs. local
- Permissões no GitHub
- Adicionar colaboradores
- Sincronização de código

### Anotações

### **1. Introdução: Do Local para o Remoto**

Rodrigo explica que Gabrielle fez alterações e commits **localmente**, mas essas mudanças ainda não estão no repositório remoto (GitHub). Agora, o objetivo é enviá-las usando **`git push`**.

### **2. Verificando a Conexão com o Repositório Remoto**

- Gabrielle pergunta se precisa reconectar o repositório local ao remoto.
- Rodrigo esclarece que **o comando `git clone` já configura automaticamente** a conexão com o remoto (chamado **`origin`**).
- Para confirmar, executam: bash
    
    ```
    git remote
    ```
    
    - Saída: **`origin`** (nome padrão dado pelo GitHub ao repositório clonado).

### **3. Enviando Commits com `git push`**

- Comando usado: bash
    
    ```
    git push origin main
    ```
    
    - **`origin`**: Apelido do repositório remoto.
    - **`main`**: Branch de destino.
- **Erro de permissão:**
    - O push é bloqueado porque Gabrielle **não tem acesso de escrita** ao repositório de Rodrigo.
    - Repositórios públicos permitem **clone e pull**, mas **push só para colaboradores autorizados**.

### **4. Adicionando Colaboradores no GitHub**

### **Passo a Passo:**

1. Rodrigo acessa **Settings** > **Collaborators** no repositório.
2. Clica em **"Add people"** e insere o username da Gabrielle.
3. Gabrielle recebe um e-mail de convite e **aceita o acesso**.
4. Agora, ela aparece como colaboradora no repositório.

### **Por Que Isso é Importante?**

- No trabalho em equipe, **é necessário conceder permissões** explicitamente.
- O dono do repositório controla quem pode enviar alterações (**`push`**).

### **5. Push Bem-Sucedido**

- Após a permissão ser concedida, Gabrielle executa novamente: bash
    
    ```
    git push origin main
    ```
    
- **Sucesso!** O commit aparece no GitHub:
    - No arquivo **`app.js`**, a mudança é exibida.
    - No histórico de commits, aparece o commit **"alterando limite para 100"** com a foto de Gabrielle.

### **6. Próximo Passo: Sincronizando o Repositório Local**

- Rodrigo destaca que **ele ainda não tem as alterações** no seu computador.
- No próximo vídeo, aprenderão como **baixar atualizações** (**`git pull`**).

**Dica Extra:**

- Use **`git remote -v`** para ver detalhes da conexão remota (URLs de fetch/push).
- Em equipes, **sempre faça `git pull` antes de `git push`** para evitar conflitos.

<aside>
📌 **RESUMO**:

✅ git push envia commits locais para o repositório remoto.
✅ Permissões são necessárias para colaborar em repositórios alheios.
✅ O dono do repositório deve adicionar colaboradores manualmente no GitHub.
✅ Commits só afetam o remoto após o push, e outros devs precisam fazer pull para sincronizar.

</aside>

---

### Adicionando Colaboradores no Commit - Autoria Compartilhada no Git

### Lembretes

- Git
- Commit
- Autoria compartilhada
- Coautores
- Colaboração em equipe
- GitHub

### Anotações

Na aula, foi abordado como incluir múltiplos autores em um commit no Git, uma funcionalidade útil quando um trecho de código é desenvolvido em colaboração (dupla, trio, etc.). Por padrão, o Git registra apenas uma pessoa como autora do commit, mas em projetos em equipe, é importante reconhecer a contribuição de todos os envolvidos em uma alteração específica.

**Como adicionar coautores a um commit:**

1. **Estrutura do Commit:**
    - Após a mensagem do commit (**`git commit -m "mensagem"`**), é necessário pular **duas linhas**.
    - Em seguida, utiliza-se a palavra-chave **`Co-authored-by:`**, seguida do **nome completo** e do **e-mail associado ao GitHub** (entre **`< >`**) de cada colaborador.
    - Cada coautor deve ser listado em uma **linha separada**.
2. **Exemplo Prático:** bash
    
    ```
    git commit -m "Adicionar nova funcionalidade.
    
    Co-authored-by: João Silva <joao@email.com>
    Co-authored-by: Maria Souza <maria@email.com>"
    ```
    
    - Nesse caso, além do autor principal, João e Maria são creditados como coautores.
3. **Documentação do GitHub:**
    - A aula recomenda consultar a documentação oficial do GitHub para entender mais sobre coautoria, incluindo possíveis regras ou convenções adicionais.

<aside>
📌 **RESUMO**:

A inclusão de coautores em commits é uma prática essencial para projetos colaborativos, garantindo que todas as contribuições sejam devidamente registradas e reconhecidas. Essa funcionalidade do Git não apenas melhora a transparência do histórico de alterações, mas também valoriza o trabalho em equipe. O processo é simples: basta seguir a formatação correta (mensagem + linhas vazias + **`Co-authored-by`**) e incluir os dados de cada colaborador. Para cenários mais complexos ou dúvidas adicionais, a documentação do GitHub serve como um recurso complementar valioso.

Essa abordagem reforça a importância da organização e do crédito coletivo no desenvolvimento de software, alinhando-se com boas práticas de versionamento e colaboração.

</aside>

---

### Colaboração em Projetos Open Source no GitHub

### Lembretes

- Open Source
- Código Aberto
- GitHub
- Issues
- Fork
- Pull Request
- Contribuição
- VS Code
- React

### Anotações

### **1. O que são Projetos Open Source?**

- São projetos de software com o **código-fonte disponível publicamente** no GitHub (ou outras plataformas).
- Qualquer pessoa pode **contribuir** com melhorias, correções ou novos recursos.
- Exemplos famosos: **VS Code, React, Linux, TensorFlow**.

### **2. Como Funciona a Colaboração?**

- **Issues (Problemas/Solicitações):**
    - Demandas (bugs, novas funcionalidades) são registradas como **"issues"** no repositório.
    - Contribuidores podem escolher uma issue para resolver.
- **Fork (Cópia do Repositório):**
    - Antes de modificar o código, é necessário fazer um **fork** (cópia do projeto para sua conta no GitHub).
    - Isso permite trabalhar sem afetar o projeto original.
- **Pull Request (Envio das Alterações):**
    - Após resolver a issue, o contribuidor envia um **Pull Request (PR)**.
    - Os mantenedores do projeto **avaliam as mudanças** e decidem se aceitam ou não.
    - Se aprovado, o código é **incorporado ao projeto original**.

### **3. Regras de Contribuição**

- Cada projeto tem suas **próprias diretrizes** (como estilo de código, testes, documentação).
- É essencial **ler o `CONTRIBUTING.md`** (arquivo de orientações) antes de contribuir.

### **4. Exemplos de Grandes Projetos Open Source**

- [**VS Code**](https://github.com/microsoft/vscode) (Editor de código da Microsoft).
- [**React**](https://github.com/facebook/react) (Biblioteca JavaScript do Facebook).

<aside>
📌 **RESUMO**:

Contribuir para projetos **Open Source** é uma ótima maneira de **aprender, ganhar experiência e colaborar com a comunidade**. O processo geralmente envolve:

1. **Identificar uma issue** para resolver.
2. **Fazer um fork** do repositório.
3. **Implementar a solução** e enviar via **Pull Request**.

É fundamental **seguir as regras do projeto** e entender seu fluxo de trabalho. Projetos como **VS Code e React** são exemplos de como o modelo Open Source pode impulsionar inovações de forma colaborativa.

Para quem deseja começar, a Alura oferece um artigo introdutório sobre o tema: [**Open Source - Uma Breve Introdução**](https://link-do-artigo/).

</aside>

---

### Sincronizando Alterações com **`git pull`** - Fluxo de Trabalho Colaborativo

### Lembretes

- **`git pull`**
- Sincronização remoto/local
- Colaboração com Git
- Fluxo de trabalho
- **`git log`**
- VS Code e Git

### Anotações

### **1. O Problema: Alterações Remotas Não Refletidas Localmente**

- Gabrielle enviou alterações para o repositório remoto (GitHub) via **`git push`**.
- No entanto, o repositório **local do Rodrigo** ainda exibia a versão antiga (com limite de número sorteado = 10).
- Isso ocorre porque o Git **não atualiza automaticamente** os repositórios locais quando há mudanças remotas.

### **2. Solução: O Comando `git pull`**

- **Função:** Baixa commits do repositório remoto (**origin**) para o local, sincronizando as alterações.
- **Sintaxe:** bash
    
    ```
    git pull origin main
    ```
    
    - **`origin`**: Nome do repositório remoto.
    - **`main`**: Branch a ser atualizada.
- **Processo:**
    - O Git compara os commits locais e remotos, **baixando as novidades**.
    - Mensagem de confirmação indica o sucesso da operação.

### **3. Verificando as Alterações**

- **`git log`:**
    - Lista o histórico de commits, mostrando o novo commit da Gabrielle.
    - Confirma que a sincronização foi bem-sucedida.
- **Inspeção Visual (VS Code):**
    - Abrindo **`app.js`**, é possível ver a modificação (ex.: limite alterado para um valor maior).

### **4. Fluxo de Trabalho Básico com Git/GitHub**

1. **Monitorar mudanças:** **`git status`**
2. **Adicionar alterações:** **`git add`**
3. **Registrar commit:** **`git commit -m "mensagem"`**
4. **Enviar para o remoto:** **`git push origin main`**
5. **Atualizar localmente:** **`git pull origin main`** (quando outros colaboradores enviam alterações).

### **5. Próximos Passos: Git no VS Code (Interface Gráfica)**

- O VS Code possui **integração nativa com Git**, permitindo executar comandos via interface visual (menos digitação no terminal).
- Isso simplifica operações como commit, push e pull, especialmente para iniciantes.

<aside>
📌 **RESUMO**:

O comando **`git pull`** é essencial para manter o repositório local **sincronizado** com as contribuições de outros desenvolvedores. Ele completa o ciclo colaborativo:

- **`push`** envia alterações para o GitHub.
- **`pull`** traz atualizações do GitHub para sua máquina.

Esse fluxo (**status → add → commit → push → pull**) é a base do trabalho em equipe com Git. Na próxima aula, exploraremos como o **VS Code facilita esse processo** através de ferramentas visuais, reduzindo a dependência do terminal.

**Dica:** Sempre execute **`git pull`** antes de iniciar novas modificações para evitar conflitos!

</aside>

### Resumo dos Comandos Git e Fluxo de Trabalho Colaborativo

### Lembretes

- **`git clone`**
- **`git add`** e **`git commit`**
- **`git status`**
- **`git log`**
- **`git remote`**
- **`git push`**
- **`git pull`**
- Colaboração no GitHub

### Anotações

### **1. Clonando um Repositório (`git clone`)**

- Baixa uma cópia **completa** de um repositório do GitHub para o computador local.
- Exemplo: bash
    
    ```
    git clone <URL-do-repositório>
    ```
    

### **2. Registrando Alterações (`git add` e `git commit`)**

- **`git add`:** Prepara as mudanças para serem salvas (adição ao *staging area*). bash
    
    ```
    git add <arquivo> ou git add .
    ```
    
- **`git commit`:** Cria um *snapshot* das alterações com uma mensagem descritiva. bash
    
    ```
    git commit -m "mensagem explicativa"
    ```
    

### **3. Verificando Mudanças (`git status` e `git log`)**

- **`git status`:** Mostra arquivos modificados, adicionados ou não rastreados.
- **`git log`:** Exibe o histórico de commits com detalhes (autor, data, mensagem).

### **4. Gerenciando Repositórios Remotos (`git remote`)**

- **`git remote -v`:** Lista os repositórios remotos vinculados ao local.

### **5. Sincronizando com o GitHub (`git push` e `git pull`)**

- **`git push`:** Envia commits locais para o repositório remoto.bash
    
    ```
    git push origin main
    ```
    
- **`git pull`:** Atualiza o repositório local com commits do remoto.bash
    
    ```
    git pull origin main
    ```
    

### **6. Colaboração no GitHub**

- **Adicionar colaboradores:** No GitHub, acessar *Settings > Collaborators*.
- **Aceitar convites:** Via e-mail ou notificação no GitHub.

<aside>
📌 **RESUMO**:

Nesta aula, exploramos os **comandos essenciais do Git** para um fluxo de trabalho colaborativo eficiente, desde clonar um repositório até sincronizar alterações entre times. O domínio dessas ferramentas (**`clone`**, **`add`**, **`commit`**, **`push`**, **`pull`**) é fundamental para:

- Manter um histórico organizado de mudanças.
- Evitar conflitos em projetos compartilhados.
- Integrar contribuições de múltiplas pessoas.
</aside>

---

### Utilizando o Git Visualmente no VS Code - Fluxo Simplificado e Conflitos

### Lembretes

- Git no VS Code
- Source Control
- Interface gráfica
- Stage Changes
- Commit visual
- Sync Changes
- Conflitos no Git

### Anotações

### **1. Introdução à Interface Gráfica do Git**

- O VS Code oferece uma **alternativa visual** aos comandos de terminal do Git.
- Acessível pelo ícone **Source Control** (terceiro na barra lateral, com símbolo de ramificação).

### **2. Modificando Arquivos e Visualizando Alterações**

- **Exemplo prático:** Ajustar o jogo para sortear entre **1 e 50** (originalmente 1-100):
    - Alteração em **`app.js`** (**`numeroLimite = 50`**).
    - Atualização do texto em **`index.html`** ("Escolha um número entre 1 e 50").
- O ícone do Git exibe um **indicador azul (2)**, mostrando o número de arquivos modificados.

### **3. Preparando e Realizando Commits**

- **Aba "Changes":** Lista arquivos alterados com opções para:
    - **Abrir arquivo** (visualizar mudanças).
    - **Descartar alterações** (reverter modificações).
    - **Stage Changes (+):** Adiciona ao próximo commit.
- **Commit:**
    - Mensagem digitada na caixa superior (ex.: "Deixando o jogo mais fácil").
    - Botão **Commit** confirma as alterações localmente.

### **4. Sincronizando com o GitHub**

- Após o commit, o botão muda para **"Sync Changes 1"**, indicando um commit não sincronizado.
- Clicar no botão envia as alterações para o repositório remoto (**push**).
- **Confirmação:** Janela pop-up pede confirmação para sincronizar com **`origin/main`**.

### **5. Verificação no GitHub**

- Atualizar a página do repositório no GitHub para confirmar o novo commit.
- Detalhes do commit mostram as alterações em formato visual (diff).

### **6. Vantagens da Interface Gráfica**

- **Facilidade:** Elimina a necessidade de memorizar comandos.
- **Visualização intuitiva:** Destaque de arquivos modificados.
- **Ações rápidas:** Stage, commit e push em poucos cliques.

### **7. Introdução aos Conflitos no Git**

- **Cenário comum:** Duas pessoas alteram a **mesma linha** de um arquivo.
- O Git sinaliza conflitos, exigindo **resolução manual**.

<aside>
📌 **RESUMO**:

A interface gráfica do Git no VS Code **simplifica o versionamento**, tornando-o mais acessível para iniciantes. O fluxo básico torna-se:

1. **Modificar arquivos** → 2. **Stage Changes** → 3. **Commit** → 4. **Sync Changes (push)**.
</aside>

---

### Resolvendo Conflitos no Git - Quando Colaboradores Alteram o Mesmo Código

### Lembretes

- Conflitos no Git
- Merge conflicts
- Resolução de conflitos
- Git pull
- Colaboração em equipe
- VS Code

### Anotações

### **1. Simulando um Conflito**

- **Cenário:** Dois desenvolvedores (Rodrigo e Gabrielle) alteram **a mesma linha** em arquivos diferentes:
    - Gabrielle: Altera limite para **40** e faz push para o GitHub.
    - Rodrigo: Altera localmente para **30** e tenta fazer pull.

### **2. Tentativa de Sincronização**

1. Rodrigo modifica:
    - **`app.js`**: **`numeroLimite = 30`**
    - **`index.html`**: Texto "1 e 30"
2. Faz commit local: "Deixando o jogo mais fácil ainda".
3. Tenta **git pull**:
    - Git detecta que a mesma linha foi alterada remotamente (40) e localmente (30).
    - **Resultado:** Erro de merge conflict (conflito de fusão).

### **3. Como o Git Lidar com Conflitos**

- **Não decide automaticamente:** Git marca o conflito e pede intervenção humana.
- **Arquivos em conflito:** São destacados na aba **Source Control** com ícone de alerta (⚠️).
- **Conteúdo do arquivo conflitante (ex.: `app.js`):** javascript
    
    ```
    <<<<<<< HEAD
    let numeroLimite = 30;// Versão local (Rodrigo)=======
    let numeroLimite = 40;// Versão remota (Gabrielle)>>>>>>> origin/main
    ```
    
    - **`<<<<<<< HEAD`** até **`=======`** mostra a alteração local.
    - **`=======`** até **`>>>>>>> origin/main`** mostra a alteração remota.

### **4. Próximos Passos (Aula Seguinte)**

- **Resolver o conflito:** Escolher qual versão manter (30, 40 ou uma nova).
- **Marcar como resolvido:** Usar o VS Code para "Accept Changes" (aceitar uma das versões).
- **Completar o merge:** Fazer novo commit após a resolução.

<aside>
📌 **RESUMO**:

Conflitos são **naturais** em projetos colaborativos e ocorrem quando:

- Duas alterações modificam a **mesma linha** de código.
- O Git **não pode** decidir qual versão é a "correta".

**Por que isso é importante?**

- Garante que mudanças não sejam perdidas sem consentimento.
- Permite discussão entre a equipe sobre a melhor solução.

**Dica:** Sempre faça **`git pull`** antes de começar a trabalhar para reduzir conflitos!

</aside>

---

### Resolução de Conflitos no Git - Passo a Passo Prático

### Lembretes

- Resolução de conflitos
- Merge conflict
- Git merge
- VS Code
- Colaboração
- Commit de merge

### Anotações

### **1. Identificando o Conflito**

- Após tentar **`git pull`**, o VS Code:
    - Mostra arquivos conflitantes na seção **Merge Changes** (com ícone ⚠️).
    - Destaca as alterações conflitantes no código: javascript
        
        ```
        <<<<<<< HEAD (Current Change)
        let numeroLimite = 30;// Alteração local (Rodrigo)=======
        let numeroLimite = 40;// Alteração remota (Gabrielle)>>>>>>> origin/main
        ```
        
    - Oferece opção **"Resolve in Merge Editor"** (editor visual) ou edição manual.

### **2. Resolvendo o Conflito Manualmente**

- **Processo:**
    1. **Editar o arquivo:** Remover marcadores do Git (**`<<<<<<<`**, **`=======`**, **`>>>>>>>`**) e escolher a versão desejada (ou combinar ambas).
        - Exemplo (após decisão): javascript
            
            ```
            let numeroLimite = 40;// Versão final (Gabrielle)
            ```
            
    2. **Repetir** para todos os arquivos conflitantes (ex.: **`index.html`**).
    3. **Salvar** as alterações.

### **3. Confirmando a Resolução**

- **Adicionar arquivos resolvidos:** Clicar em **Stage Changes (+)** na aba *Source Control*.
- **Criar commit de merge:**
    - Mensagem padrão: **`Merge branch 'main' of [URL]`** (pode ser personalizada).
    - Clicar em **Commit** para registrar a resolução.

### **4. Sincronizando com o Repositório Remoto**

- O botão muda para **"Sync Changes"** (indicando commit local não sincronizado).
- Clicar para enviar as alterações (**push**) para o GitHub.

### **5. Verificação no GitHub**

- O histórico de commits mostra:
    - O commit original da Gabrielle (**`numeroLimite = 40`**).
    - O commit do Rodrigo (**`numeroLimite = 30`**).
    - O **commit de merge** que resolveu o conflito.

**Exemplo de Boa Prática:**

> "Conflitos são oportunidades para revisar o código em equipe e garantir que a solução final seja a melhor possível."
> 

Este processo, embora inicialmente complexo, torna-se intuitivo com a prática e é fundamental para projetos colaborativos!

<aside>
📌 **RESUMO**:

Resolver conflitos é uma **parte essencial** do trabalho colaborativo com Git. O fluxo básico inclui:

1. **Identificar** o conflito (marcações no código).
2. **Editar** os arquivos (escolhendo/combinaando alterações).
3. **Confirmar** a resolução (commit de merge).
4. **Sincronizar** com o repositório remoto (push).

**Por que isso importa?**

- Garante que mudanças não sejam perdidas acidentalmente.
- Permite **discussão em equipe** para decidir a melhor solução.

**Dicas para evitar conflitos:**

- Sempre faça **`git pull`** antes de começar a trabalhar.
- Comunique-se com a equipe sobre alterações em arquivos compartilhados.
</aside>

---

### Resolução de Conflitos no VS Code com Merge Editor - Guia Completo

### Lembretes

- Merge Editor
- Resolução de conflitos
- Git no VS Code
- Incoming vs Current
- Complete Merge
- Fluxo de trabalho colaborativo

### Anotações

### **1. O Que São Conflitos no Git?**

- Ocorrem quando **duas alterações** modificam a **mesma linha** de código em versões diferentes (local e remota).
- Analogia: Como duas pessoas tentando encaixar peças diferentes no mesmo lugar de um quebra-cabeça.

### **2. Acessando o Merge Editor**

- Ao detectar um conflito durante **`git push`**, o VS Code oferece:
    - Botão **"Resolve in Merge Editor"** (canto inferior direito).
    - Aba especial dividida em 3 seções:
        - **Incoming (Remoto):** Alterações do repositório remoto.
        - **Current (Local):** Suas alterações locais.
        - **Result:** Pré-visualização da resolução.

### **3. Opções de Resolução**

- **Para o Campo "Incoming":**
    - **`Accept Incoming`**: Mantém apenas a versão remota.
    - **`Accept Combination Incoming First`**: Combina as alterações (remoto primeiro).
    - **`Ignore`**: Descarta as alterações remotas.
- **Para o Campo "Current":**
    - **`Accept Current`**: Mantém apenas a versão local.
    - **`Accept Combination Current First`**: Combina as alterações (local primeiro).
    - **`Ignore`**: Descarta as alterações locais.

### **4. Fluxo de Resolução**

1. **Selecionar** a opção desejada (ex.: **`Accept Incoming`** se a versão remota for a correta).
2. **Salvar** o arquivo (**`Ctrl + S`**).
3. **Clicar em "Complete Merge"** (canto inferior direito) para confirmar.
4. **Commit e Push:**
    - Fazer commit da resolução (mensagem automática de merge).
    - Sincronizar com **`git push`**.

### **5. Exemplo Prático**

- **Cenário:**
    - Remoto: **`<h1>Título</h1>`**
    - Local: **`<h2>Subtítulo</h2>`**
- **Solução escolhida:** **`Accept Combination Current First`** → Resultado: html
    
    ```
    <h2>Subtítulo</h2><h1>Título</h1>
    ```
    

<aside>
📌 **RESUMO**:

O **Merge Editor** do VS Code é uma ferramenta **poderosa** para resolver conflitos de forma visual e intuitiva. Permite:

- **Comparar lado a lado** as versões em conflito.
- **Testar combinações** antes de confirmar.
- **Evitar erros** com pré-visualização em tempo real.

**Melhores Práticas:**

- Sempre **revise o resultado** antes de completar o merge.
- **Comunique-se com a equipe** para decidir qual versão priorizar.
</aside>

---

### Revertendo Commits no Git - Como Desfazer Alterações de Forma Segura

### Lembretes

- Git revert
- Histórico de commits
- ID do commit
- Desfazer alterações
- git log
- Colaboração

### Anotações

### **1. Contexto e Necessidade de Reverter Commits**

- Em projetos colaborativos, é comum precisar **desfazer alterações** após feedback ou decisões equivocadas.
- **Exemplo prático:** Rodrigo removeu uma imagem do projeto (**`index.html`**) em um commit específico, mas agora precisam restaurar.

### **2. Localizando o Commit a Ser Revertido**

- **Passo 1:** Usar **`git log`** no terminal para ver o histórico completo.
    - Cada commit tem um **ID único** (hash SHA-1) e uma mensagem descritiva.
    - Exemplo: bash
        
        ```
        commit 2ad48c068dc9677fb57efec70620700410f976b0
        Author: Rodrigo <rodrigo@email.com>
        Date:   Mon Oct 10 14:30:00 2023 -0300
            removendo foto
        ```
        
- **Passo 2:** Identificar o commit alvo (copiar seu ID).

### **3. Comando `git revert`**

- **Funcionamento:**
    - Cria um **novo commit** que desfaz as alterações do commit especificado.
    - Não apaga o commit original (mantém o histórico intacto).
- **Sintaxe:** bash
    
    ```
    git revert <ID-do-commit>
    ```
    
    - Exemplo: bash
        
        ```
        git revert 2ad48c068dc9677fb57efec70620700410f976b0
        ```
        
- **Fluxo:**
    1. O Git abre um editor para a mensagem do novo commit (padrão: **`Revert "mensagem-do-commit-original"`**).
    2. Salvar e fechar o editor para confirmar.

### **4. Resultado do Revert**

- **Novo commit no histórico:** bash
    
    ```
    commit 3bf45a1d2e...
    Author: Gabrielle <gabrielle@email.com>
    Date:   Mon Oct 10 15:00:00 2023 -0300
        Revert "removendo foto"
        This reverts commit 2ad48c068dc9677fb57efec70620700410f976b0.
    ```
    
- **Efeito prático:**
    - A imagem removida é restaurada no **`index.html`**.
    - O commit original ainda existe no histórico (para rastreabilidade).

### **5. Sincronizando com o Repositório Remoto**

- Enviar o commit de revert para o GitHub: bash
    
    ```
    git push origin main
    ```
    
- **Verificação:**
    - Acessar o GitHub e confirmar que a imagem foi restaurada.

### **6. Diferença Entre `revert` e Outras Ações**

- **Revert vs. Reset:**
    - **`revert`** é seguro para colaboração (não reescreve histórico).
    - **`reset`** remove commits permanentemente (usado apenas localmente).
- **Quando usar `revert`:**
    - Em branches compartilhadas (ex.: **`main`**).
    - Quando a alteração já foi enviada ao repositório remoto.

**Dica:** Sempre revise o histórico (**`git log --oneline`**) antes de reverter para garantir o commit correto!

**Exemplo de Boa Prática:**

> "O revert é como um botão de desfazer para Git: seguro, rastreável e colaborativo."
> 

Dominar esse comando é crucial para um fluxo de trabalho profissional com versionamento!

<aside>
📌 **RESUMO**:

O **`git revert`** é uma ferramenta **essencial** para:

- **Corrigir erros** sem perder o histórico.
- **Manter a integridade** do projeto em equipe.
- **Recuperar versões anteriores** de forma controlada.

**Por que isso importa?**

- Evita "soluções manuais" propensas a erros.
- Preserva o contexto das mudanças para toda a equipe.
</aside>

---