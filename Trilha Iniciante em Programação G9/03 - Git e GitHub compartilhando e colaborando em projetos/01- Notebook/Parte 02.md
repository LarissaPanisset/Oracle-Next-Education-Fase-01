### Atualizar no GitHub

### Lembretes

- **`git add .`**
- **`git commit -m "..."`**
- **`git push`**

### Anotações

Isso mesmo! **Salvar no VSCode (Ctrl + S) só atualiza o arquivo no seu computador**, mas **não envia para o GitHub**. Para atualizar seu código no GitHub, você precisa **"avisar" o Git** através do terminal.

### **🔄 Passo a Passo para Atualizar no GitHub**

### **1️⃣ Salve no VSCode**

- Edite seu arquivo e aperte **`Ctrl + S`** (isso só salva localmente).

### **2️⃣ Abra o Terminal (Git Bash, PowerShell ou VSCode Terminal)**

- No VSCode: **`Ctrl + '`** (ou clique em **`Terminal`** > **`New Terminal`**).

### **3️⃣ Comandos Mágicos para Enviar ao GitHub**

Digite **um por um**: 

```
git add .# Prepara TODAS as alteraçõesgit commit -m "mensagem explicativa"# Cria uma "versão" das mudançasgit push origin main# Envia para o GitHub
```

### **4️⃣ Verifique no GitHub**

Acesse:

```
https://github.com/LarissaPanisset/JOGO/commits/main
```

Seus arquivos atualizados devem estar lá!

---

### **💡 Dicas Importantes**

- **`git add .`** → Adiciona **todos** os arquivos modificados.
- **`git commit -m "..."`** → Escreva mensagens claras, como:
    - **`"Adicionei menu de pause"`**
    - **`"Corrigi bug na colisão"`**
- **`git push`** → Só funciona se você já tiver feito **`add`** e **`commit`** antes.

---

### **🚨 Se Der Erro**

- **Primeiro `push`?** Use:
    
    ```
    git push --set-upstream origin main
    ```
    
- **Branch errada?** Troque **`main`** pelo nome da sua branch.

---

### **📌 Resumo Visual**

```
VSCode (Ctrl + S) → Terminal → git add → git commit → git push → GitHub 🎉
```

---

### **Atualizar Arquivos Individuais vs. Atualizar TODOS**

### Lembretes

- **`git add .`**
- **`git add .`**

### Anotações

Você pode escolher **atualizar apenas arquivos específicos** (como **`app.js`**, **`index.html`**, **`style.css`**) ou **todos de uma vez**. Vamos às opções:

---

### **🔧 Como Atualizar Arquivos Individuais no GitHub**

### **1️⃣ Selecionando arquivos específicos (recomendado para alterações pontuais):**

```
git add app.js# Adiciona apenas o app.jsgit add index.html style.css# Adiciona HTML e CSS juntosgit commit -m "Atualizei o JS e o CSS"
git push origin main
```

### **2️⃣ Verificando quais arquivos foram modificados (antes de adicionar):**

```
git status
```

- Mostrará quais arquivos foram alterados e ainda não estão no *stage*.

---

### **🚀 Como Atualizar TODOS os Arquivos de Uma Vez**

Se preferir enviar **todas as alterações** (incluindo novos arquivos):

```
git add .# Adiciona TUDO que foi modificadogit commit -m "Atualização geral"
git push origin main
```

---

### **📌 Quando Usar Cada Método?**

| **Situação** | **Comando Recomendado** |
| --- | --- |
| Alterou **apenas 1-2 arquivos** | **`git add arquivo1 arquivo2`** |
| Alterou **muitos arquivos** | **`git add .`** |
| Criou **arquivos novos** | **`git add .`** (para não esquecer nenhum) |

---

### **❓ Exemplo Prático:**

1. Você modificou **`style.css`** e **`index.html`**:
    
    ```
    git add style.css index.html
    git commit -m "Melhorei o layout e a estrutura HTML"
    git push origin main
    ```
    
2. **No GitHub**, os arquivos serão atualizados!

---

### **⚠️ Cuidado!**

- Se usar **`git add .`**, **revise** com **`git status`** para evitar enviar arquivos temporários (como **`node_modules`**).
- Para ignorar arquivos, crie um **`.gitignore`** ([veja como aqui](https://www.toptal.com/developers/gitignore)).

---

### Clonagem de Repositório e Configuração Inicial no VS Code

### Lembretes

- GitHub
- Git clone
- Repositório remoto vs. local
- Chave SSH
- VS Code
- Download ZIP vs. Clonagem
- Acesso público a repositórios

### Anotações

**1. Revisão das Etapas Anteriores:**

- Criamos uma conta no GitHub e instalamos o Git localmente.
- Configuramos um repositório **remoto** (GitHub) e um **local** (computador), conectando-os.
- Geramos e configuramos a **chave SSH** (lembrando que as chaves privada/pública não devem ser compartilhadas).

**2. Continuando o Projeto:**

- O repositório remoto já contém arquivos, e Rodrigo compartilhou o projeto com Gabrielle para colaboração.
- Gabrielle acessou o projeto pelo navegador e agora precisa transferi-lo para seu computador.

**3. Opções para Transferir o Repositório:**

- **Download ZIP:**
    - GitHub compacta os arquivos em um ZIP para download.
    - **Limitação:** Não inclui o histórico de commits ou a estrutura Git completa.
- **Clonar o Repositório (Recomendado):**
    - Mantém todo o histórico e estrutura do Git.
    - Passos realizados:
        1. Clicar em **"Code"** no GitHub e copiar a URL do repositório.
        2. Abrir o terminal no computador (pelo explorador de arquivos).
        3. Executar o comando: bash
            
            ```
            git clone https://github.com/rodrigoalura87/numero-secreto.git
            ```
            
        4. A pasta do projeto é criada localmente com todos os arquivos.

**4. Abrindo o Projeto no VS Code:**

- No VS Code: **File > Open Folder** → Selecionar a pasta clonada ("numero-secreto").
- Isso permite editar os arquivos diretamente no editor.

**5. Acesso Público ao Repositório:**

- Como o repositório está como **público**, qualquer pessoa pode visualizar, clonar ou baixar os arquivos.
- Consegue modificar os arquivos localmente, mas no próxima aula será explicado como enviar alterações de volta ao GitHub (commits e push).

<aside>
📌 **RESUMO**:

Nesta aula, aprendemos a **clonar um repositório do GitHub** para trabalhar localmente, garantindo que todo o histórico e estrutura do Git sejam preservados. Vimos que, embora o **Download ZIP** seja uma opção, a **clonagem via Git** é a melhor prática para projetos colaborativos. Além disso, reforçamos a importância de repositórios públicos (permitindo acesso a outros desenvolvedores) e preparamos o ambiente no VS Code para edição. No próximo vídeo, exploraremos como modificar os arquivos e sincronizar as mudanças com o repositório remoto.

</aside>

---

### Versionamento e Modificação de Projeto no GitHub

### Lembretes

- Git Status
- Git Add
- Git Commit
- Git Log
- Repositório Local vs. Remoto

### Anotações

**1. Introdução e Objetivo da Modificação**

Aumentar a dificuldade do jogo **"Número Secreto"**, alterando o intervalo de números sorteados de **1 a 10** para **1 a 100**.

**2. Alterações nos Arquivos**

- **index.html (Linha 23):**
    - Modificação do texto para refletir o novo intervalo:
        
        ```
        <p class="texto__paragrafo">Escolha um número entre 1 a 100</p>
        ```
        
- **app.js (Linha 2):**
    - Ajuste da variável **`numeroLimite`** para **`100`**:
        
        ```
        let numeroSecreto = parseInt(Math.random() * 100) + 1;
        ```
        

**3. Verificando Alterações com Git Status**

- O comando **`git status`** é utilizado para verificar o estado atual do repositório local.
    - Arquivos modificados aparecem em **vermelho**, indicando que ainda não foram adicionados para commit.
    - O terminal também sugere o comando **`git add`** para preparar as mudanças.

**4. Adicionando Mudanças para Commit**

- Dois métodos para adicionar arquivos:
    - **Arquivo por arquivo:** **`git add nome_do_arquivo`**
    - **Todos de uma vez:** **`git add .`**
- Após o **`git add`**, o **`git status`** mostra os arquivos em **verde**, confirmando que estão prontos para commit.

**5. Realizando o Commit**

- O comando **`git commit -m "mensagem"`** registra as alterações no histórico local.
    - Exemplo:

        ```
        git commit -m "alterando limite para 100"
        ```
        
    - **Importância da mensagem:** Descreve claramente a mudança para futuras referências.

**6. Visualizando o Histórico de Commits**

- O comando **`git log`** exibe o histórico completo de commits, incluindo:
    - **Autor**
    - **Data**
    - **Mensagem do commit**
- Útil para rastrear mudanças e entender a evolução do projeto.

**7. Repositório Local vs. Remoto**

- O commit foi registrado apenas **localmente** (no computador).
- O próximo passo seria **enviar as alterações para o repositório remoto no GitHub** .

<aside>
📌 **RESUMO**:

Nesta aula, aprendemos o fluxo básico de modificação e versionamento de um projeto usando Git:

1. **Modificar** os arquivos conforme necessário.
2. **Verificar** as alterações com **`git status`**.
3. **Preparar** as mudanças com **`git add`**.
4. **Registrar** as alterações com **`git commit -m "mensagem"`**.
5. **Visualizar** o histórico com **`git log`**.

Essas etapas garantem um controle eficiente das versões do projeto, permitindo rastreabilidade e colaboração. O próximo passo seria enviar essas alterações para o GitHub, integrando o trabalho local com o repositório remoto.

</aside>

---

### DesafiosEntendendo as Sinalizações de Arquivos no VSCode com Git

### Lembretes

- Git no VSCode
- Sinalização "M" (Modified)
- Sinalização "U" (Untracked)
- Controle de Versão Visual

### Anotações

**1. Introdução às Sinalizações no VSCode**

- O **Visual Studio Code (VSCode)** exibe **ícones e letras** ao lado dos arquivos quando usamos **Git** para versionamento.
- Essas sinalizações ajudam a identificar rapidamente o **estado** de cada arquivo no repositório.

**2. O Significado da Letra "M" (Modified)**

- **"M"** significa **Modified (Modificado)**.
    - Indica que o arquivo **já existia** no repositório, mas foi alterado.
    - Exemplo: **`index.html`** (modificado, mas ainda não registrado no Git).
    - **O que fazer?**
        - Usar **`git add`** para preparar a mudança.
        - Depois, **`git commit`** para registrar a alteração.

**3. O Significado da Letra "U" (Untracked)**

- **"U"** significa **Untracked (Não Rastreado)**.
    - Indica que o arquivo **é novo** e ainda não foi adicionado ao Git.
    - Exemplo: **`README.md`** (criado recentemente, mas sem commit).
    - **O que fazer?**
        - Usar **`git add`** para começar a rastrear o arquivo.
        - Depois, **`git commit`** para incluí-lo no histórico.

**4. Por Que Essas Sinalizações São Úteis?**

- Permitem **identificar rapidamente** quais arquivos:
    - Foram modificados (**`M`**).
    - São novos e precisam ser adicionados (**`U`**).
- Facilitam o **controle visual** do projeto sem precisar rodar **`git status`** o tempo todo.

**5. Outras Sinalizações Possíveis (Menção)**

- Embora não tenham sido citadas nesta aula, outras sinalizações comuns incluem:
    - **"A" (Added):** Arquivo adicionado, mas ainda não commitado.
    - **"D" (Deleted):** Arquivo excluído, mas a mudança ainda não foi registrada.

<aside>
📌 **RESUMO**:

As sinalizações no VSCode (M e U) são ferramentas visuais essenciais para quem trabalha com Git, pois:
✔ Simplificam o acompanhamento das mudanças.
✔ Ajudam a evitar esquecimentos (como arquivos modificados ou não rastreados).
✔ Integram-se perfeitamente com os comandos Git (add, commit, status).

</aside>

---

### Como Escrever Mensagens de Commit Eficazes

### Lembretes

- Mensagens de commit
- Clareza e objetividade
- Verbo no infinitivo
- Documentação do histórico
- Boas práticas

### Anotações

**1. Importância das Mensagens de Commit**

- As mensagens de commit servem como **documentação do histórico** de alterações no projeto.
- Facilitam o entendimento para **outras pessoas** (equipe) e para **você no futuro**.
- Devem explicar **o quê** foi alterado e **por quê**, sem exigir contexto prévio.

**2. Estrutura Básica**

- **Primeira linha (obrigatória):**
    - Máximo de **72 caracteres**.
    - Deve ser **clara e direta**, resumindo a mudança principal.
- **Corpo (opcional, se necessário):**
    - Separado por uma linha em branco.
    - Explicação mais detalhada, contexto ou justificativa.

**3. Boas Práticas**

✔ **Verbo no infinitivo:**

- Iniciar com verbos como:
    - **`Adicionar`** (novas funcionalidades).
    - **`Corrigir`** (bugs).
    - **`Atualizar`** (dependências ou textos).
- Exemplo: text
    
    ```
    Corrigir cálculo de desconto no carrinho
    ```
    

✔ **Evitar detalhes técnicos complexos:**

- Detalhes de implementação devem ficar no **código** (comentários) ou na **documentação**.
- Exemplo **não recomendado**:
    
    ```
    Ajustar regex para /^[a-z0-9]+$/i no input
    ```
    

✔ **Mensagens autossuficientes:**

- Evitar mensagens vagas como:
    
    ```
    Arrumar bug
    ```
    
- Preferir: text
    
    ```
    Corrigir erro de validação no formulário de login
    ```
    

**4. Exemplo de Commit Bem Estruturado**

```
Adicionar suporte a temas escuros no CSS

- Inclui novas variáveis de cor no arquivo styles.css.
- Modifica os seletores para usar preferência do sistema do usuário.
```

**5. Impacto de Mensagens Ruins**

- Mensagens confusas ou incompletas:
    - Dificultam a **revisão de código**.
    - Aumentam o tempo para **entender mudanças antigas**.
    - Podem causar **erros em merges** ou rollbacks.

<aside>
📌 **RESUMO**:

Escrever **boas mensagens de commit** é uma habilidade essencial para:

✅ **Manter um histórico limpo** e útil.

✅ **Facilitar a colaboração** em equipe.

✅ **Poupar tempo** no futuro (debugging, revisões).

**Regra de Ouro:**

> "Imagine que outra pessoa (ou você daqui a 6 meses) está lendo a mensagem. Ela entenderá o que foi feito e por quê?"
> 
</aside>

---

### O Momento Certo para Fazer um Commit

### Lembretes

- Frequência de commits
- Tarefas específicas
- Código funcional
- Histórico limpo
- Tamanho do commit

### Anotações

**1. Quando Fazer um Commit?**

✅ **Ao concluir uma tarefa específica:**

- Exemplo: "Adicionar validação de e-mail no formulário".
    
    ✅ **Ao corrigir um bug:**
    
- Exemplo: "Corrigir cálculo de frete no checkout".
    
    ✅ **Após uma mudança significativa e estável:**
    
- Exemplo: "Atualizar biblioteca para versão 2.0".

**2. Frequência Ideal**

- **Commits frequentes**, mas não excessivos:
    - Evitar muitos commits pequenos (ex: "Ajustar espaçamento" → "Ajustar margem").
    - Evitar commits grandes (ex: "Atualizar todo o front-end").
- **Equilíbrio:** Agrupar mudanças relacionadas em um único commit.

**3. O Que Nunca Commitar?**

❌ **Código não funcional ou com bugs conhecidos.**

- O histórico deve refletir apenas versões estáveis.
    
    ❌ **Arquivos temporários ou desnecessários** (ex: **`node_modules/`**, **`.env`**).
    

**4. Boas Práticas**

✔ **Commits atômicos:**

- Cada commit deve representar **uma única alteração lógica**.
- Exemplo ruim: "Corrigir bugs e atualizar CSS".
- Exemplo bom:
    - "Corrigir timeout na API de login" (1° commit).
    - "Ajustar responsividade do menu" (2° commit).

✔ **Mensagens claras:**

- Seguir as diretrizes de "Como escrever mensagens de commit".

**5. Impacto de Commits Mal Planejados**

- **Commits grandes:** Dificultam a identificação de bugs e rollbacks.
- **Commits incompletos:** Podem quebrar o código para outros desenvolvedores.

<aside>
📌 **RESUMO**:

**Um commit deve ser:**

🔹**Focado:** Uma mudança por vez.

🔹**Funcional:** Sem bugs conhecidos.

🔹**Bem documentado:** Mensagem clara e descritiva

</aside>
