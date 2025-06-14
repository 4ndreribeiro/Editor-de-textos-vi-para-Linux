# Guia Completo: O Editor de Textos Vi no Linux
---

O **Vi** é um dos editores de texto mais antigos e poderosos disponíveis em sistemas Unix-like, incluindo o Linux. Embora possa parecer intimidante à primeira vista devido ao seu modo de operação, o Vi é uma ferramenta extremamente eficiente para edição rápida de arquivos, especialmente em servidores remotos onde interfaces gráficas não estão disponíveis. Dominar o Vi é uma habilidade fundamental para qualquer usuário ou administrador de sistema Linux.

## O que é o Vi?
---

O Vi (Visual Instrument) foi criado em 1976 e se tornou o editor padrão em muitos sistemas Unix. Sua principal característica é ser um **editor modal**, o que significa que ele opera em diferentes "modos", e a função das teclas muda dependendo do modo em que você está. Isso o torna muito rápido para manipulação de texto uma vez que os atalhos são aprendidos, pois a maioria das operações é feita sem tirar as mãos do teclado.

O **Vim** (Vi IMproved) é uma versão moderna e aprimorada do Vi, que oferece mais recursos, melhor usabilidade e é o padrão na maioria das distribuições Linux hoje em dia. Embora este guia se concentre nos comandos básicos do Vi, a maioria deles funciona perfeitamente no Vim.

### Por que aprender o Vi/Vim?

* **Ubiquidade:** O Vi está disponível em praticamente todos os sistemas Unix-like, tornando-o indispensável para trabalhar em servidores ou em ambientes mínimos.
* **Eficiência:** Uma vez dominado, permite edição de texto muito rápida sem o uso do mouse.
* **Poderoso:** Capaz de realizar edições complexas com poucos comandos.
* **Recuperação de Emergência:** Essencial para editar arquivos de configuração em um sistema que não está inicializando completamente, onde nenhum outro editor gráfico está disponível.

## Entendendo os Modos do Vi
---

A chave para usar o Vi é entender seus três modos principais:

1.  **Modo de Comando (Normal Mode):**
    * É o modo padrão ao abrir o Vi.
    * Neste modo, as teclas são interpretadas como **comandos** para navegar pelo texto, copiar, colar, deletar e manipular o buffer.
    * **Não insere texto diretamente.**
    * Para sair de qualquer outro modo e voltar para o Modo de Comando, pressione a tecla `Esc`.

2.  **Modo de Inserção (Insert Mode):**
    * Neste modo, o Vi se comporta como um editor de texto comum. As teclas digitadas são inseridas diretamente no arquivo.
    * Você entra neste modo a partir do Modo de Comando usando comandos como `i`, `a`, `o`, etc.
    * Para sair do Modo de Inserção e voltar para o Modo de Comando, pressione a tecla `Esc`.

3.  **Modo de Última Linha (Ex Mode):**
    * Usado para operações de arquivo, pesquisa e configurações.
    * Você entra neste modo a partir do Modo de Comando digitando dois pontos (`:`).
    * Um prompt `:` aparecerá na parte inferior da tela, onde você pode digitar comandos como `w` (write/salvar), `q` (quit/sair), `s` (substituir), etc.
    * Após executar um comando neste modo, o Vi geralmente retorna ao Modo de Comando.

## Como Usar o Vi - Comandos Essenciais
---

### 1. Abrir/Criar um Arquivo

* **Para abrir um arquivo existente ou criar um novo:**
    ```bash
    vi nome_do_arquivo.txt
    ```
* **Para abrir um arquivo em modo somente leitura (para evitar edições acidentais):**
    ```bash
    vi -R nome_do_arquivo.txt
    # ou
    view nome_do_arquivo.txt
    ```

### 2. Navegação (Modo de Comando)

Estes comandos são usados para mover o cursor sem inserir texto.

* `h`: Mover cursor para a **esquerda**
* `j`: Mover cursor para **baixo**
* `k`: Mover cursor para **cima**
* `l`: Mover cursor para a **direita**
* `w`: Pular para o início da **próxima palavra**
* `b`: Pular para o início da **palavra anterior**
* `e`: Pular para o **final** da palavra atual
* `0` (zero): Ir para o **início da linha**
* `^`: Ir para o **primeiro caractere não-branco** da linha
* `$`: Ir para o **final da linha**
* `gg`: Ir para o **início do arquivo**
* `G`: Ir para o **final do arquivo**
* `:[número]`: Ir para a linha especificada (ex: `:50` para a linha 50)
* `Ctrl + f`: Rolar uma tela para baixo (forward)
* `Ctrl + b`: Rolar uma tela para cima (backward)

### 3. Entrar no Modo de Inserção

Use estes comandos a partir do Modo de Comando para começar a digitar texto. Pressione `Esc` para voltar ao Modo de Comando.

* `i`: Inserir texto **no local atual do cursor** (insert)
* `a`: Inserir texto **após o local atual do cursor** (append)
* `o`: Inserir nova linha **abaixo** da linha atual (open new line below)
* `I`: Inserir texto no **início da linha** (início absoluto)
* `A`: Inserir texto no **final da linha**
* `O`: Inserir nova linha **acima** da linha atual

### 4. Edição Básica (Modo de Comando)

* `x`: Deletar o caractere sob o cursor
* `dw`: Deletar a palavra a partir do cursor (delete word)
* `dd`: Deletar a linha inteira (delete line)
    * Você pode usar um número antes dos comandos de deleção (ex: `5dd` para deletar 5 linhas).
* `yy`: Copiar a linha inteira (yank line)
    * Você pode usar um número antes (ex: `3yy` para copiar 3 linhas).
* `yw`: Copiar a palavra a partir do cursor.
* `p`: Colar o conteúdo copiado/deletado **após** o cursor/linha (paste)
* `P`: Colar o conteúdo copiado/deletado **antes** do cursor/linha (Paste)
* `u`: Desfazer a última ação (undo)
* `Ctrl + r`: Refazer a última ação (redo)
* `J`: Juntar a linha atual com a próxima (join)

### 5. Salvar e Sair (Modo de Última Linha)

Digite `:` para entrar no Modo de Última Linha e, em seguida, um dos comandos:

* `:w`: Salvar o arquivo (write)
* `:q`: Sair do Vi (quit) - Só funciona se não houver alterações.
* `:wq`: Salvar e sair (write and quit)
* `ZZ` (Modo de Comando, sem o dois pontos): Atalho rápido para salvar e sair.
* `:q!`: Sair sem salvar as alterações (quit forcefully) - **Cuidado!**
* `:w!`: Salvar o arquivo mesmo que seja somente leitura (se você tiver permissões para isso).
* `:w nome_novo_arquivo.txt`: Salvar o conteúdo atual em um novo arquivo.

### 6. Pesquisa (Modo de Comando/Última Linha)

* `/termo_de_pesquisa`: Pesquisar `termo_de_pesquisa` para frente.
    * `n`: Ir para a próxima ocorrência.
    * `N`: Ir para a ocorrência anterior.
* `?termo_de_pesquisa`: Pesquisar `termo_de_pesquisa` para trás.

### 7. Substituir Texto (Modo de Última Linha)

* `:%s/antigo/novo/g`: Substituir todas as ocorrências de `antigo` por `novo` em todo o arquivo.
    * `%`: Todo o arquivo.
    * `s`: Substituir.
    * `g`: Global (todas as ocorrências na linha).

## Conclusão
---

O editor Vi, e seu sucessor Vim, são ferramentas poderosas e eficientes para edição de texto no Linux. Embora a curva de aprendizado inicial possa ser íngreme devido aos seus modos de operação, o investimento de tempo no aprendizado dos comandos básicos compensa muito em termos de produtividade, especialmente ao trabalhar em ambientes de terminal. Comece praticando os comandos de navegação, inserção e salvamento, e gradualmente explore os recursos mais avançados.
