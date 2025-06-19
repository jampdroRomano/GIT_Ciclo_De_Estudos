# Documentação GIT

Este documento serve como um guia rápido para os conceitos e comandos essenciais do Git e GitHub, desde a criação de um repositório até a realização de commits e a manipulação do histórico.

---




## Primeiro passo: Criar um repositório no GitHub

### O que é um repositório?

Um repositório é onde ficam os arquivos e o histórico de um projeto. Pode ser local (no seu computador) ou remoto (como no GitHub). Ele guarda tudo que é feito no projeto: códigos, alterações, versões e histórico.

---




## Trajeto até realizar um commit

1.  **Criar uma pasta para o projeto e navegar até ela:**

    ```bash
    mkdir "C:\Users\Desktop\GITHUB\ProjetoGIT"
    cd "C:\Users\Desktop\GITHUB\ProjetoGIT"
    ```

    *   `mkdir`: Cria uma pasta no caminho especificado.
    *   `cd`: Entra na pasta no caminho especificado.

2.  **Criar um novo arquivo (exemplo):**

    ```bash
    New-Item "TesteVersionamento.txt"
    ```

    *   `New-Item`: Cria um novo arquivo.

3.  **Inicializar um repositório Git local:**

    ```bash
    git init
    ```

    *   Isso cria a pasta `.git` e transforma o diretório em um repositório Git local.

### O que é uma branch?

Uma branch é um caminho separado de desenvolvimento. Serve para testar novas ideias ou fazer alterações sem mexer no código principal. A principal normalmente se chama `master` ou `main`.

4.  **(Opcional) Renomear a branch principal para `master` (se ela veio como `main`):**

    *   Verifique o nome da branch atual:

        ```bash
        git branch
        ```

        *   Se aparecer um asterisco ao lado de `master`, está tudo certo.
        *   Se não for `master`, renomeie a branch atual para `master`:

            ```bash
            git branch -m master
            ```

5.  **Criar uma nova branch:**

    ```bash
    git branch [Nome da branch]
    ```

6.  **Mudar para a nova branch:**

    ```bash
    git checkout [Nome da branch]
    ```

    *   Muda a branch na qual está realizando commits.

7.  **Configurar o GitHub para usar esse branch (no repositório remoto):**

    ```bash
    git remote add origin https://github.com/seunome/nomedorepo.git
    ```

    *   Esse comando vincula seu projeto local com o repositório remoto chamado `origin` (padrão) no GitHub.

8.  **Testar o vínculo do projeto local com o repositório remoto:**

    ```bash
    git remote -v
    ```

9.  **Definir quem está fazendo os commits no projeto:**

    ```bash
    git config --global user.name "Seu Nome"
    git config --global user.email "seuemail@email.com"
    ```

10. **Adicionar todos os arquivos da pasta para serem commitados:**

    ```bash
    git add .
    ```

11. **Fazer o commit dos arquivos adicionados com uma mensagem:**

    ```bash
    git commit -m "Primeiro commit"
    ```

12. **Enviar os commits para o repositório remoto e definir a branch `master` como padrão:**

    ```bash
    git push --set-upstream origin master
    ```

---




## Comandos importantes

### `git status`

Verifica se os arquivos locais foram alterados.

### `git reflog`

Verifica o histórico de commits, até mesmo em commits descartados, resets e checkouts.

### `git reset --hard <id-do-commit>`

Reseta o commit definitivamente para um commit informado (desfazendo o que veio depois) de forma local.

### `git reset --soft <id-do-commit>`

Volta para o commit anterior, mas mantém as mudanças nos arquivos e no staging. Ideal para refazer commits.

### `git push --force origin master`

Força o envio da sua branch `master` local para o repositório remoto no GitHub, substituindo qualquer alteração que tenha sido feita no GitHub depois do último commit. (Sobrescreve o histórico REMOTO).

### `git log`

Mostra os commits do histórico oficial da sua branch, reflete apenas o que foi confirmado no projeto.

### `git checkout <id-do-commit>`

Agora você está temporariamente vendo o projeto como era naquele commit.

### `git checkout master`

Para voltar para o seu branch principal.

### `git merge [nome branch]`

Une informações entre branches, conforme a branch em que você está e a que deseja unir.

### `git pull`

Atualiza os arquivos locais conforme a última versão da sua branch no repositório remoto.

---



