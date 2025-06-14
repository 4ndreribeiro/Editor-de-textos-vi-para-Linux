Guia Completo: Movimentação pela Tela e Início/Fim de Arquivo no Vi/Vim no Linux
O Vi (e seu sucessor, o Vim) é um editor de texto modal amplamente utilizado no ambiente Linux, conhecido por sua eficiência e velocidade. Dominar os comandos de movimentação é fundamental para navegar rapidamente por documentos e scripts, seja para pequenas edições ou para analisar grandes arquivos. Este guia se aprofunda nos comandos de movimentação pela tela, além de atalhos para ir diretamente ao início e ao fim de um arquivo.

Entendendo os Modos do Vi/Vim
Antes de explorar a navegação, é importante lembrar os modos principais do Vi:

Modo de Comando (Normal Mode): O modo padrão ao abrir o Vi. Neste modo, as teclas são interpretadas como comandos para navegar, manipular e deletar texto. Você não digita texto diretamente. Pressione Esc para retornar a este modo de qualquer outro.

Modo de Inserção (Insert Mode): Neste modo, você pode digitar texto no arquivo como em um editor comum. Você entra a partir do Modo de Comando usando comandos como i, a, o, etc. Pressione Esc para voltar ao Modo de Comando.

Modo de Última Linha (Ex Mode): Usado para comandos de arquivo (salvar, sair), pesquisa e configurações. Você entra a partir do Modo de Comando digitando :. Um prompt : aparecerá na parte inferior da tela.

1. Movimentação pela Tela (Modo de Comando)
Estes comandos permitem que você role o conteúdo do arquivo na tela, mas sem mover o cursor para a posição específica. Eles são ideais para "folhear" um documento.

Rolagem de Página
Ctrl + f: Rolar uma tela para baixo (forward).

Ctrl + b: Rolar uma tela para cima (backward).

Rolagem de Meia Página
Ctrl + d: Rolar meia tela para baixo (down half a page).

Ctrl + u: Rolar meia tela para cima (up half a page).

Rolagem por Linhas
Ctrl + e: Rolar uma linha para baixo (extra line down).

Ctrl + y: Rolar uma linha para cima (yank line up).

Posicionamento do Cursor na Tela Visível
Estes comandos movem o cursor para uma posição específica dentro da tela visível atual, sem rolar o conteúdo do arquivo.

H: Mover cursor para o topo da tela visível (High).

M: Mover cursor para o meio da tela visível (Middle).

L: Mover cursor para a base da tela visível (Low).

2. Movimento para Início e Fim do Arquivo (Modo de Comando)
Esses são comandos essenciais para ir rapidamente para as extremidades de um documento.

gg: Mover cursor para o início do arquivo (primeira linha, primeira coluna não-branca).

G: Mover cursor para o final do arquivo (última linha, primeira coluna não-branca).

Movimento para Linhas Específicas
:[número]: Mover cursor para a linha especificada (ex: :50 para a linha 50).

No Vim, você pode exibir os números das linhas com :set nu (números absolutos) ou :set rnu (números relativos).

3. Movimentação Básica do Cursor (Revisão - Modo de Comando)
Embora não sejam de "tela cheia", estes são os movimentos fundamentais.

Caractere a Caractere
h: Mover cursor para a esquerda

j: Mover cursor para baixo

k: Mover cursor para cima

l: Mover cursor para direita

Por Palavras
w: Pular para o início da próxima palavra

b: Pular para o início da palavra anterior

e: Pular para o final da palavra atual

Por Linhas
0 (zero): Ir para o início absoluto da linha (primeiro caractere).

^: Ir para o primeiro caractere não-branco da linha.

$: Ir para o final da linha.

Conclusão
Dominar os comandos de movimentação no Vi/Vim, incluindo a rolagem pela tela e os atalhos para o início e fim do arquivo, é fundamental para ser eficiente ao editar texto no Linux. A prática regular desses comandos no Modo de Comando irá aprimorar sua velocidade e precisão, permitindo que você navegue por documentos de qualquer tamanho com facilidade.