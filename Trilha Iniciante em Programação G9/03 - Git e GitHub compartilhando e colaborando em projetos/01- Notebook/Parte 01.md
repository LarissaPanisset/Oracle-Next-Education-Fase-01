# **Git e GitHub: compartilhando e colaborando em projetos**

### **Criando um Repositório no GitHub: Organização e Configurações**

### Lembretes

- Repositório no GitHub
- Organização de projetos
- Configuração de tema (claro/escuro)
- Visibilidade (público/privado)
- Nome único para repositório
- Upload de código
- Página inicial do repositório

### Anotações

**1. Introdução à Necessidade de Organização no GitHub:**

- Após criar a conta no GitHub, surge a questão: **como organizar múltiplos projetos** (sejam 2, 10 ou 100)?
- Cada projeto deve ter seu espaço separado, pois possuem arquivos e finalidades distintas.
- **Solução**: Uso de **repositórios** — "pastas virtuais" no GitHub para armazenar códigos de um projeto específico.

**2. Configuração Inicial do GitHub:**

- **Mudança do tema (claro → escuro)**:
    - Acessar **Settings** (no menu do avatar) → **Appearance**.
    - Trocar de *"Sync with system"* para *"Single theme"* e selecionar **"Dark default"**.
    - Opções adicionais: *Dark high contrast* (alto contraste) ou temas para daltonismo (*Protanopia/Deuteranopia/Tritanopia*).
- **Retorno à página inicial**: Clicar no ícone do GitHub (canto superior esquerdo).

**3. Criando um Repositório:**

- **Dois caminhos para criação**:
    1. Botão verde **"Create Repository"** (lateral esquerda).
    2. Ícone **"+"** no menu → *"New Repository"*.
- **Formulário de criação**:
    - **Nome do repositório**: Deve ser **único apenas na sua conta** (ex.: *numero-secreto*).
        - *Observação*: Outros usuários podem ter repositórios com o mesmo nome.
    - **Descrição** (opcional): Breve explicação sobre o projeto.
    - **Visibilidade**:
        - **Público**: Qualquer pessoa com o link pode ver o código (ideal para portfólio).
        - **Privado**: Restrito a você ou colaboradores (para projetos confidenciais).
    - **Outras opções ignoradas por agora**: *README*, *.gitignore*, *license* (serão explicadas depois).
- **Confirmação**: Clicar em **"Create Repository"**.

**4. Página do Repositório Criado:**

- **URL do repositório**: Segue o formato **`github.com/[usuário]/[nome-do-repositório]`** (ex.: **`github.com/rodrigoalura87/numero-secreto`**).
- **Próximo passo**: Fazer o **upload do código** do projeto (que está no computador) para este repositório.
- **Dica do GitHub**: A plataforma exibe um **tutorial básico** com comandos para subir o código (a ser explorado nas próximas aulas).

<aside>

📌 **RESUMO**:

- **Repositórios são a base** para organizar projetos no GitHub, permitindo separação clara entre diferentes códigos.
- **Configurações personalizáveis** (como temas) melhoram a experiência do usuário.
- A escolha entre **público/privado** depende do objetivo do projeto (colaboração aberta ou restrita).
- Na próxima etapa, aprenderemos a **enviar o código local** (do projeto *Número Secreto*) para o repositório recém-criado, utilizando os recursos do GitHub e integração com GIT.
</aside>

---

### **Visibilidade de Repositórios: Públicos vs. Privados**

### Lembretes

- Repositórios públicos
- Repositórios privados
- Colaboradores
- Limitações de contas gratuitas
- Planos pagos
- Controle de acesso

### Anotações

**1. Visibilidade dos Repositórios no GitHub:**

- **Repositórios públicos**:
    - Qualquer pessoa na internet pode **visualizar e acessar** o código.
    - Ideal para projetos **open-source**, portfólios ou compartilhamento aberto.
- **Repositórios privados**:
    - **Restritos** ao dono do repositório e colaboradores **explicitamente adicionados**.
    - Usado para projetos **pessoais, internos ou confidenciais**.

**2. Colaboradores em Repositórios Privados:**

- **Contas gratuitas**:
    - Limite de **até 3 colaboradores** por repositório privado.
    - Para times maiores, é necessário **upgrade para um plano pago** ou tornar o repositório público.
- **Planos pagos**:
    - Permitem **mais colaboradores** e recursos avançados (como *code review* e *actions* privadas).

**3. Quando Escolher Cada Tipo:**

- **Público**:
    - Projetos que **beneficiam a comunidade** (ex.: bibliotecas, tutoriais).
    - Para **mostrar habilidades** em portfólios.
- **Privado**:
    - Projetos **empresariais** ou em desenvolvimento fechado.
    - Códigos com **dados sensíveis** ou não liberados para o público.

**4. Documentação Recomendada:**

- [**Sobre repositórios** - GitHub Docs](https://docs.github.com/pt/repositories)
- [**Definir a visibilidade do repositório** - GitHub Docs](https://docs.github.com/pt/repositories/managing-your-repositorys-settings-and-features/managing-repository-settings/setting-repository-visibility)

<aside>
📌 **RESUMO**:

- A escolha entre **público e privado** impacta **quem pode ver e contribuir** com seu projeto.
- Contas gratuitas têm **limitações em colaboradores privados**, mas são ideais para uso pessoal ou pequenos times.
- Para **projetos profissionais ou grandes equipes**, considere planos pagos para **maior flexibilidade**.
</aside>

---

### **Integrando um Projeto Local com o GitHub: Instalação e Configuração do Git**

### Lembretes

- Git vs. GitHub
- Terminal integrado (VS Code)
- Comandos Git (**`git init`**, **`git remote`**, **`git push`**)
- Instalação do Git
- Variáveis de ambiente (Windows)
- Configuração de repositório local

### Anotações

### **1. Introdução à Conexão entre Projeto Local e GitHub**

- **Problema**: O projeto *Número Secreto* está no **VS Code (local)**, mas o repositório foi criado no **GitHub (remoto)**.
- **Solução**: Criar uma **ligação** entre eles usando **Git** (ferramenta de versionamento).
- **Passo inicial**: Executar comandos Git no **terminal integrado do VS Code** (**`Ctrl + Shift + '`**).

### **2. Diferença entre Git e GitHub**

- **Git**:
    - Ferramenta de **controle de versão local**.
    - Rastreia alterações, cria históricos e permite commits.
- **GitHub**:
    - Plataforma de **hospedagem remota** de repositórios Git.
    - Facilita colaboração e compartilhamento de código.

### **3. Comandos do GitHub para Upload**

O GitHub sugere **dois fluxos** após criar um repositório:

### **A) Para um projeto novo (sem arquivos locais):**

bash

```
echo "# numero-secreto" >> README.md# Cria um READMEgit init# Inicializa um repositório Git localgit add README.md# Adiciona o README ao "stage"git commit -m "first commit"# Registra as alteraçõesgit branch -M main# Renomeia a branch para "main"git remote add origin [URL-do-repositório]# Conecta ao repositório remotogit push -u origin main# Envia os arquivos para o GitHub
```

### **B) Para um projeto existente (com arquivos locais):**

bash

```
git remote add origin [URL-do-repositório]# Conecta ao repositório remotogit branch -M main# Garante que a branch se chama "main"git push -u origin main# Envia os arquivos para o GitHub
```

- **No nosso caso**: Usaremos o **segundo fluxo**, pois o projeto já existe.

### **4. Erro na Execução do `git init`**

- **Problema**: O terminal não reconhece o comando **`git`**.
- **Causa**: O **Git não está instalado** no computador.
- **Solução**:
    1. Baixar o Git do [site oficial](https://git-scm.com/) (versão para Windows 64-bit).
    2. Instalar com **configurações padrão**.
    3. Verificar se o caminho do Git foi adicionado às **variáveis de ambiente** do Windows:
        - Acessar: **`Painel de Controle > Sistema > Configurações avançadas > Variáveis de Ambiente`**.
        - Editar a variável **Path** e adicionar: **`C:\Program Files\Git\cmd\`**.
    4. **Reiniciar o VS Code** para o terminal reconhecer o Git.

### **5. Configuração Final e Próximos Passos**

- Após a instalação, o comando **`git init`** funciona:

    ```
    Initialized empty Git repository in C:/Users/[usuário]/Desktop/numero-secreto/.git/
    ```
    
- **Próximos passos**:
    - Usar **`git remote add origin [URL]`** para vincular ao repositório remoto.
    - Enviar os arquivos com **`git push -u origin main`**.

<aside>
📌 **RESUMO**:

- **Git é essencial** para versionar projetos locais antes de enviá-los ao GitHub.
- A instalação requer atenção às **variáveis de ambiente** no Windows.
- O VS Code facilita o processo com seu **terminal integrado**.
- Na próxima aula, exploraremos como **enviar efetivamente o código** para o GitHub usando **`git add`**, **`git commit`** e **`git push`**.

**Dica dos Instrutores**:

> "Sempre reinicie o VS Code após instalar o Git para evitar erros no terminal."
> 
</aside>

---

### **Entendendo o Comando `git init`: Inicialização de Repositórios Git**

### Lembretes

- **`git init`**
- Repositório local
- Controle de versão
- Diretório do projeto
- Reinicialização
- **`git status`**

### Anotações

### **1. O Que é o Comando `git init`?**

- **Finalidade**: Transforma um diretório comum (pasta de projeto) em um **repositório Git**.
- **Funcionamento**:
    - Cria uma subpasta oculta **`.git/`** no diretório atual.
    - Habilita o **rastreamento de alterações** (versionamento) no projeto.
- **Uso único**: Deve ser executado **apenas uma vez** por projeto.

### **2. Como Executar `git init`?**

- **Passo a passo**:
    1. Abra o terminal do **VS Code** (ou outro) no diretório do projeto.
    2. Execute:
 
        ```
        git init
        ```
        
    3. Saída esperada:

        ```
        Initialized empty Git repository in [caminho-do-projeto]/.git/
        ```
        
- **Atenção**:
    - O comando **deve ser executado na pasta raiz do projeto** (não em subpastas ou diretórios aleatórios).
    - Exemplo correto:
 
        ```
        ~/Projetos/meu-projeto$ git init
        ```
        

### **3. Cuidados e Erros Comuns**

- **Reinicialização acidental**:
    - Se executar **`git init`** em um repositório **já existente**, o Git exibirá:

        ```
        Reinitialized existing Git repository in [caminho]/.git/
        ```
        
    - **Não apaga o histórico**, mas é desnecessário.
- **Como evitar**:
    - Verifique se o diretório já é um repositório Git com:

        ```
        git status
        ```
        
    - Se a saída for:

        ```
        fatal: not a git repository (or any of the parent directories): .git
        ```
        
        → O diretório **pode** ser inicializado.
        

### **4. Por Que Usar `git init`?**

- **Benefícios**:
    - Permite **commits**, **branches** e **histórico de versões**.
    - Pré-requisito para integrar com **GitHub** (via **`git remote add`**).
- **Fluxo típico**:

    ```
    git init → git add → git commit → git remote add → git push
    ```
    

<aside>
📌 **RESUMO**:

- **`git init`** é o **primeiro passo** para versionar um projeto com Git.
- **Sempre execute na pasta raiz do projeto** e **apenas uma vez**.
- Use **`git status`** para verificar se o diretório já é um repositório Git.
- Após a inicialização, o projeto está pronto para **rastreamento de alterações** e **integração com plataformas remotas** (GitHub, GitLab, etc.).
</aside>

---

### **Sincronizando Repositórios Locais e Remotos: Configuração Completa**

### Lembretes

- **`git remote add`**
- Chave SSH
- **`git push`**
- Autenticação no GitHub
- Configuração de usuário (**`git config`**)
- Protocolo SSH vs HTTPS

### Anotações

### **1. Estabelecendo a Conexão Local-Remoto**

- **Repositório local** (computador) e **remoto** (GitHub) são independentes inicialmente.
- **Fluxo de comandos para vincular**:
    1. **`git add .`** → Adiciona **todos** os arquivos ao *stage*.
    2. **`git commit -m "mensagem"`** → Cria um *snapshot* das alterações.
    3. **`git branch -M main`** → Garante que a branch principal se chama **`main`**.
    4. **`git remote add origin [URL]`** → Vincula ao repositório remoto (**usar URL SSH**).
    5. **`git push -u origin main`** → Envia os arquivos para o GitHub.

### **2. Configuração Inicial do Git**

- **Erro comum**: *Author identity unknown*.
    - **Solução**: Definir identidade globalmente:

        ```
        git config --global user.email "seu@email.com"
        git config --global user.name "Seu Nome"
        ```
        
    - **Observação**: Use o mesmo e-mail cadastrado no GitHub.

### **3. Autenticação com Chave SSH**

- **Problema**: **`Permission denied (publickey)`** ao executar **`git push`**.
- **Solução**: Gerar e registrar chave SSH no GitHub:
    1. **Gerar chave**:
 
        ```
        ssh-keygen -t ed25519 -C "seu@email.com"
        ```
        
        - Pressione **`Enter`** para usar o local padrão (**`~/.ssh/`**).
        - Deixe a *passphrase* vazia (a menos que queira segurança extra).
    2. **Copiar chave pública**:
        - Acesse **`~/.ssh/id_ed25519.pub`** (abra com Bloco de Notas).
    3. **Adicionar ao GitHub**:
        - Settings → **SSH and GPG keys** → **New SSH key**.
        - Cole a chave pública e salve.

### **4. Escolha do Protocolo (SSH vs HTTPS)**

- **SSH** (recomendado):
    - Mais seguro (autenticação por chaves).
    - URL: **`git@github.com:usuário/repositório.git`**.
- **HTTPS**:
    - Requer login/senha ou token de acesso.
    - URL: **`https://github.com/usuário/repositório.git`**.

### **5. Finalizando o Upload**

- Após configurar a chave SSH, execute novamente:

    ```
    git push -u origin main
    ```
    
- **Saída esperada**:

    ```
    [new branch] main -> main
    ```
    
- **Verificação**: Atualize a página do repositório no GitHub → arquivos devem aparecer.

<aside>
📌 **RESUMO**:

- A conexão entre repositórios exige **configuração de usuário** e **autenticação via SSH**.
- O protocolo SSH **elimina a necessidade de digitar credenciais** repetidamente.
- Após o primeiro **`git push`**, os próximos commits exigem apenas:

    ```
    git add . → git commit -m "mensagem" → git push
    ```
    
</aside>

---

### Gerenciando Conexões com Repositórios Remotos: O Comando git remote

### Lembretes

- **`git remote add`**
- **`git remote -v`**
- **`git remote remove`**
- **`git remote set-url`**
- **`git remote rename`**
- Repositório remoto
- Colaboração

### Anotações

### **1. Introdução ao `git remote`**

- **Função**: Gerencia a conexão entre repositórios **locais** e **remotos** (ex: GitHub).
- **Caso de uso típico**: Vincular um projeto local a um repositório no GitHub para sincronizar alterações.

---

### **2. Comandos Principais**

### **A) Adicionar um Repositório Remoto**

- **Sintaxe**: 
    
    ```
    git remote add <apelido> <URL>
    ```
    
- **Exemplo**:
    
    ```
    git remote add origin git@github.com:usuario/repositorio.git
    ```
    
- **Observações**:
    - **`origin`** é o apelido padrão para o repositório principal.
    - Use URLs **SSH** (recomendado) ou **HTTPS**.

### **B) Listar Repositórios Remotos**

- **Sintaxe**:
    
    ```
    git remote -v
    ```
    
- **Saída**:
    
    ```
    origin  git@github.com:usuario/repositorio.git (fetch)
    origin  git@github.com:usuario/repositorio.git (push)
    ```
    
- **Finalidade**: Verificar URLs configuradas para **`fetch`** (baixar) e **`push`** (enviar).

### **C) Remover um Repositório Remoto**

- **Sintaxe**:
    
    ```
    git remote remove <apelido>
    ```
    
- **Exemplo**:
    
    ```
    git remote remove origin
    ```
    
- **Uso**: Quando um repositório remoto não é mais necessário.

### **D) Alterar a URL de um Repositório Remoto**

- **Sintaxe**:
    
    ```
    git remote set-url <apelido> <nova_URL>
    ```
    
- **Exemplo**:
    
    ```
    git remote set-url origin git@github.com:usuario/novo-repositorio.git
    ```
    
- **Cenários**:
    - Migração para outro servidor.
    - Troca de protocolo (SSH ↔ HTTPS).

### **E) Renomear um Repositório Remoto**

- **Sintaxe**: 
    
    ```
    git remote rename <apelido_atual> <novo_apelido>
    ```
    
- **Exemplo**: 
    
    ```
    git remote rename origin upstream
    ```
    
- **Aplicação**: Útil em fluxos com múltiplos remotos (ex: **`origin`** para seu fork, **`upstream`** para o projeto original).

---

### **3. Exemplo Completo de Fluxo**

1. **Adicionar um remoto**:
    
    ```
    git remote add origin git@github.com:usuario/projeto.git
    ```
    
2. **Verificar**:
    
    ```
    git remote -v
    ```
    
3. **Alterar URL (se necessário)**:
    
    ```
    git remote set-url origin git@github.com:usuario/projeto-novo.git
    ```
    
4. **Renomear**:
    
    ```
    git remote rename origin meu-repositorio
    ```
    
5. **Remover**:
    
    ```
    git remote remove meu-repositorio
    ```
    

---

### **4. Boas Práticas**

- **Padronize apelidos**: Use **`origin`** para seu repositório principal e **`upstream`** para projetos externos.
- **Prefira SSH**: Mais seguro e evita digitar credenciais.
- **Verifique sempre**: Use **`git remote -v`** antes de operações críticas.

<aside>
📌 **RESUMO**:

- O **`git remote`** é **essencial** para colaboração e sincronização com repositórios remotos.
- Dominar seus subcomandos (**`add`**, **`remove`**, **`set-url`**, **`rename`**) otimiza fluxos de trabalho.
- **Sempre confira as URLs** com **`git remote -v`** para evitar erros.
</aside>
