# Guia Completo: Apagar Caracteres e Linhas, Desfazer e Refazer Comandos no Vi/Vim no Linux
O Vi (e seu sucessor, o Vim) é um editor de texto modal que oferece comandos extremamente eficientes para manipulação de texto. Apagar conteúdo de forma rápida e ter a capacidade de desfazer e refazer alterações são funcionalidades essenciais para qualquer usuário que trabalha com o Vi/Vim no Linux.

Entendendo os Modos do Vi/Vim
Para usar o Vi/Vim de forma eficaz, é fundamental entender seus três modos principais:

Modo de Comando (Normal Mode): O modo padrão. As teclas são interpretadas como comandos para navegação, manipulação e deleção. Para retornar a este modo de qualquer outro, pressione Esc.

Modo de Inserção (Insert Mode): Para digitar texto no arquivo. As teclas digitadas são inseridas diretamente. Você entra a partir do Modo de Comando usando comandos como i, a, o, etc. Retorne ao Modo de Comando com Esc.

Modo de Última Linha (Ex Mode): Para comandos de arquivo (salvar, sair), pesquisa e substituição. Você entra a partir do Modo de Comando digitando :.

1. Apagar Caracteres e Texto (Modo de Comando)
Estes comandos permitem deletar caracteres ou blocos de texto rapidamente. O conteúdo deletado é salvo em um buffer (como um "clipboard") e pode ser colado com p ou P.

Apagar Caractere por Caractere
x: Deleta o caractere sob o cursor e o cursor permanece na posição.

Exemplo: Se o cursor está em C em AB_C_DE, pressione x. Resulta em AB_DE.

X: Deleta o caractere à esquerda do cursor.

Exemplo: Se o cursor está em C em AB_C_DE, pressione X. Resulta em A_C_DE.

Apagar Palavras e Linhas
dw: Deleta a palavra a partir da posição do cursor até o início da próxima palavra.

Exemplo: Se o cursor está em E em Hello _W_orld, pressione dw. Resulta em Hello_orld.

de: Deleta a palavra a partir da posição do cursor até o final da palavra atual.

Exemplo: Se o cursor está em o em Hell_o_ World, pressione de. Resulta em Hell World.

d0: Deleta do cursor até o início da linha.

d$: Deleta do cursor até o final da linha.

dd: Deleta a linha inteira onde o cursor está.

Exemplo: Pressione dd para remover a linha atual.

D: Deleta do cursor até o final da linha (equivalente a d$).

Apagar Múltiplos Itens (Com Números)
Você pode prefixar a maioria dos comandos de deleção com um número para repetir a ação.

5x: Deleta os próximos 5 caracteres a partir do cursor.

3dw: Deleta as próximas 3 palavras.

4dd: Deleta 4 linhas inteiras a partir da linha atual.

2. Desfazer e Refazer Comandos (Modo de Comando)
A capacidade de desfazer e refazer ações é crucial para a edição de texto, permitindo corrigir erros ou reverter para estados anteriores.

Desfazer (Undo)
u: Desfaz a última alteração (undo).

Exemplo: Você apagou uma linha com dd. Pressione u para trazê-la de volta.

U: Desfaz todas as alterações na linha atual desde que o cursor foi posicionado nela. (Cuidado: este comando é menos comum e pode ter um comportamento diferente em certas versões do Vi/Vim).

Refazer (Redo)
Ctrl + r: Refaz a última ação desfeita (redo).

Exemplo: Você apagou uma linha, desfez com u, mas decidiu apagar novamente. Pressione Ctrl + r.

3. Apagar em Modo Visual (Vim Específico)
No Vim, você pode usar o Modo Visual para selecionar um bloco de texto e depois apagar a seleção.

Entrar no Modo Visual:

v: Modo Visual de Caracteres (seleciona caractere por caractere).

V: Modo Visual de Linhas (seleciona linhas inteiras).

Ctrl + v: Modo Visual de Bloco (seleciona um bloco retangular de texto).

Selecionar o Texto: Mova o cursor para estender a seleção.

Apagar a Seleção: Pressione d (delete) ou x para apagar o texto selecionado.

Exemplo:

Posicione o cursor no início de um parágrafo.

Pressione v.

Mova o cursor para o final do parágrafo.

Pressione d para apagar todo o parágrafo selecionado.

Conclusão
Dominar os comandos de deleção (x, X, dw, dd, d$, D) e as funcionalidades de desfazer (u) e refazer (Ctrl + r) no Vi/Vim é fundamental para uma edição de texto eficiente e sem frustrações no Linux. A prática desses comandos no Modo de Comando irá aprimorar sua velocidade e precisão, permitindo que você manipule documentos com confiança.