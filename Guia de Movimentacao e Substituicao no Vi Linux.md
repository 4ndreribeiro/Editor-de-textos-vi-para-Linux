# Guia Completo: Movimentação pela Tela e Substituição de Caracteres no Vi/Vim no Linux
---

O **Vi** (e seu sucessor, o **Vim**) é um editor de texto modal extremamente poderoso e eficiente no Linux. Dominar a navegação e a substituição de texto no Vi pode acelerar significativamente seu fluxo de trabalho, especialmente ao lidar com arquivos de configuração ou scripts diretamente no terminal. Este guia explora comandos essenciais para se mover pela tela e realizar substituições precisas.

## Entendendo os Modos do Vi/Vim
---

Antes de mergulhar nos comandos, é crucial relembrar os modos de operação do Vi:

* **Modo de Comando (Normal Mode):** O modo padrão. As teclas são comandos para navegação, manipulação e deleção.
    * Para retornar a este modo de qualquer outro, pressione **`Esc`**.
* **Modo de Inserção (Insert Mode):** Para digitar texto no arquivo.
    * Entre a partir do Modo de Comando com `i`, `a`, `o`, `I`, `A`, `O`.
    * Retorne ao Modo de Comando com **`Esc`**.
* **Modo de Última Linha (Ex Mode):** Para comandos de arquivo (salvar, sair), pesquisa e substituição global.
    * Entre a partir do Modo de Comando digitando **`:`**.

## 1. Movimentação pela Tela (Modo de Comando)
---

A navegação eficiente é a base da produtividade no Vi.

### Movimento Básico do Cursor (Caractere a Caractere)

* **`h`**: Mover cursor para a **esquerda**
* **`j`**: Mover cursor para **baixo**
* **`k`**: Mover cursor para **cima**
* **`l`**: Mover cursor para a **direita**

### Movimento por Palavras

* **`w`**: Pular para o início da **próxima palavra** (word)
* **`b`**: Pular para o início da **palavra anterior** (back)
* **`e`**: Pular para o **final** da palavra atual (end)

### Movimento por Linhas

* **`0` (zero)**: Ir para o **início da linha** (primeiro caractere).
* **`^`**: Ir para o **primeiro caractere não-branco** da linha.
* **`$`**: Ir para o **final da linha**.
* **`gg`**: Ir para o **início do arquivo**.
* **`G`**: Ir para o **final do arquivo**.
* **`:[número]`**: Ir para a linha especificada (ex: `:50` para a linha 50).
    * Para visualizar o número da linha no Vim: `:set nu` (números relativos: `:set rnu`).

### Movimento por Tela/Página

* **`Ctrl + f`**: Rolar uma tela para **baixo** (forward).
* **`Ctrl + b`**: Rolar uma tela para **cima** (backward).
* **`H`**: Mover cursor para o **topo** da tela visível (High).
* **`M`**: Mover cursor para o **meio** da tela visível (Middle).
* **`L`**: Mover cursor para a **base** da tela visível (Low).

## 2. Substituição de Caracteres e Texto
---

O Vi/Vim oferece comandos poderosos para substituir caracteres ou padrões de texto.

### 2.1. Substituição de Caractere Único (Modo de Comando)

* **`r`**: Substituir o caractere sob o cursor por um **único caractere** que você digitar em seguida. Você não entra no Modo de Inserção.
    * Ex: Pressione `r` e depois `X` para trocar o caractere atual por `X`.

* **`R`**: Entrar no Modo de **Substituição (Replace Mode)**. Tudo o que você digitar sobrescreverá o texto existente até que você pressione `Esc`.

### 2.2. Substituição de Texto com Entrada (Modo de Comando para Modo de Inserção)

Estes comandos deletam texto e automaticamente o colocam no Modo de Inserção para você digitar o novo conteúdo.

* **`s`**: Deletar o caractere sob o cursor e entrar no Modo de Inserção.
    * Ex: Pressione `s`, digite `novo_caractere` e `Esc`.
* **`S`**: Deletar a linha inteira e entrar no Modo de Inserção (o mesmo que `dd` seguido de `O`).

### 2.3. Substituição de Padrões (Modo de Última Linha)

Estes são os comandos mais poderosos para substituir texto, especialmente para múltiplas ocorrências ou em várias linhas.

**Sintaxe Básica:** `:[range]s/pattern/replacement/[flags]`

* **`[range]` (Opcional):** Define onde a substituição será aplicada.
    * `:` (vazio): Linha atual.
    * `%`: Todo o arquivo.
    * `start_line,end_line`: De uma linha a outra (ex: `1,10s/.../.../`).
    * `'<' '>'`: Seleção visual (se você tiver feito uma seleção visual).

* **`s`**: O comando de substituição.

* **`pattern`**: O padrão (texto) a ser pesquisado. Pode ser uma expressão regular.

* **`replacement`**: O texto que substituirá o padrão.

* **`[flags]` (Opcional):** Modificadores do comportamento.
    * **`g` (global):** Substitui todas as ocorrências do padrão na linha (não apenas a primeira). **Muito Comum.**
    * **`i` (ignore case):** Ignora maiúsculas/minúsculas durante a pesquisa.
    * **`c` (confirm):** Pede confirmação antes de cada substituição.
    * **`n` (no replace):** Apenas mostra o número de ocorrências, sem fazer a substituição (útil para testar o padrão).

**Exemplos Comuns de Substituição:**

* **Substituir a primeira ocorrência de "antigo" por "novo" na linha atual:**
    ```vim
    :s/antigo/novo/
    ```

* **Substituir todas as ocorrências de "antigo" por "novo" na linha atual:**
    ```vim
    :s/antigo/novo/g
    ```

* **Substituir todas as ocorrências de "antigo" por "novo" em todo o arquivo:**
    ```vim
    :%s/antigo/novo/g
    ```

* **Substituir "TEXTO" por "substituido" em todo o arquivo, ignorando maiúsculas/minúsculas:**
    ```vim
    :%s/texto/substituido/gi
    ```

* **Substituir todas as ocorrências de "funcao_antiga" por "nova_funcao" de forma interativa (pedindo confirmação):**
    ```vim
    :%s/funcao_antiga/nova_funcao/gc
    ```
    (Para cada ocorrência, digite `y` para sim, `n` para não, `a` para tudo, `q` para sair.)

* **Substituir espaços em branco no início da linha por nada (remover indentação):**
    ```vim
    :%s/^\s*//g
    ```

* **Substituir quebras de linha por espaço (juntar linhas):**
    ```vim
    :%s/\n/ /g
    ```
    *Use com cuidado!*

## Conclusão
---

Dominar os comandos de movimentação e substituição no Vi/Vim é um passo fundamental para se tornar um usuário eficiente do Linux. A prática constante desses comandos no Modo de Comando e no Modo de Última Linha o ajudará a editar arquivos de forma rápida e precisa, sem a necessidade de depender do mouse ou de editores gráficos.
