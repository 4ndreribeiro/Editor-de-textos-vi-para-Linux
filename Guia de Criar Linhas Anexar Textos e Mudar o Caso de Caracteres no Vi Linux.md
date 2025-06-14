# Guia Completo: Criar Linhas, Anexar Textos e Mudar o Caso de Caracteres no Vi/Vim no Linux
> O Vi (e seu sucessor, o Vim) é um editor de texto modal que oferece uma vasta gama de comandos para manipulação eficiente de texto. Dominar a criação de novas linhas, anexar texto em diferentes posições e alterar o caso dos caracteres são habilidades essenciais para qualquer usuário do Linux que trabalha com o Vi/Vim.

## Entendendo os Modos do Vi/Vim
Para usar o Vi/Vim de forma eficaz, é fundamental entender seus três modos principais:

>>Modo de Comando (Normal Mode): O modo padrão. As teclas são interpretadas como comandos para navegação, manipulação e deleção. Para retornar a este modo de qualquer outro, pressione Esc.

>>Modo de Inserção (Insert Mode): Para digitar texto no arquivo. As teclas digitadas são inseridas diretamente. Você entra a partir do Modo de Comando usando comandos como i, a, o, etc. Retorne ao Modo de Comando com Esc.

Modo de Última Linha (Ex Mode): Para comandos de arquivo (salvar, sair), pesquisa e substituição. Você entra a partir do Modo de Comando digitando :.

## 1. Criar Novas Linhas (Modo de Comando)
Estes comandos permitem criar uma nova linha e, automaticamente, colocá-lo no Modo de Inserção, pronto para você digitar.

o (open below): Cria uma nova linha abaixo da linha atual e entra no Modo de Inserção.

Exemplo: Coloque o cursor em qualquer lugar da linha 5. Pressione o. Uma nova linha será criada entre a linha 5 e 6, e você estará pronto para digitar nela.

O (open above): Cria uma nova linha acima da linha atual e entra no Modo de Inserção.

Exemplo: Coloque o cursor em qualquer lugar da linha 5. Pressione O. Uma nova linha será criada entre a linha 4 e 5, e você estará pronto para digitar nela.

## 2. Anexar Textos (Modo de Comando)
Estes comandos são usados para entrar no Modo de Inserção em posições específicas em relação ao cursor ou à linha.

a (append): Anexa texto após o caractere onde o cursor está posicionado e entra no Modo de Inserção.

Exemplo: Se o cursor está em C em AB_C_DE, pressione a. O cursor se moverá para C e você poderá digitar FG para obter ABCFGDE.

A (append to end of line): Anexa texto no final da linha (após o último caractere da linha) e entra no Modo de Inserção.

Exemplo: Se o cursor está em C em ABCDE, pressione A. O cursor se moverá para o final da linha (após E) e você poderá digitar FG para obter ABCDEFG.

i (insert): Insere texto no local atual do cursor e entra no Modo de Inserção.

Exemplo: Se o cursor está em C em AB_C_DE, pressione i. O cursor permanece em C e você poderá digitar FG para obter ABFGCDE.

I (insert at start of line): Insere texto no início da linha (antes do primeiro caractere não-branco) e entra no Modo de Inserção.

Exemplo: Se a linha é    ABCDE, pressione I. O cursor irá para A e você poderá digitar 123 para obter    123ABCDE.

## 3. Mudar o Caso dos Caracteres (Modo de Comando)
Estes comandos permitem alterar o caso (maiúsculas/minúsculas) de caracteres, palavras ou seleções.

Inverter o Caso (Toggle Case)
~ (tilde): Inverte o caso do caractere sob o cursor e avança o cursor para o próximo caractere.

Exemplo: Se o cursor está em a em aBc, pressione ~. Resulta em Abc. Pressione novamente para aBc.

Com um número prefixado, inverte o caso de N caracteres. Ex: 3~ inverte o caso dos próximos 3 caracteres.

Mudar para Minúsculas (Lowercase)
gu (go to lowercase): Converte texto para minúsculas.

guw: Converte a palavra sob o cursor ou a próxima para minúsculas.

Exemplo: Se o cursor está em H em Hello World, pressione guw. Resulta em hello World.

gue: Converte para minúsculas até o final da palavra atual.

gu$: Converte para minúsculas do cursor até o final da linha.

guu: Converte a linha inteira para minúsculas.

guG: Converte para minúsculas do cursor até o final do arquivo.

gU (seguido de movimento): Converte para maiúsculas (veja abaixo).

Mudar para Maiúsculas (Uppercase)
gU (go to uppercase): Converte texto para maiúsculas.

gUw: Converte a palavra sob o cursor ou a próxima para maiúsculas.

Exemplo: Se o cursor está em h em hello world, pressione gUw. Resulta em HELLO world.

gUe: Converte para maiúsculas até o final da palavra atual.

gU$: Converte para maiúsculas do cursor até o final da linha.

gUU: Converte a linha inteira para maiúsculas.

gUG: Converte para maiúsculas do cursor até o final do arquivo.

Mudar o Caso em Modo Visual (Vim Específico)
No Vim, você pode usar o Modo Visual para selecionar um bloco de texto e então aplicar a mudança de caso.

Entrar no Modo Visual:

v: Modo Visual de Caracteres.

V: Modo Visual de Linhas.

Ctrl + v: Modo Visual de Bloco (no Vim).

Selecionar o Texto: Mova o cursor para selecionar o texto desejado.

Aplicar a Mudança de Caso:

u: Converte a seleção para minúsculas.

U: Converte a seleção para maiúsculas.

~: Inverte o caso da seleção.

Exemplo:

Posicione o cursor no início de um texto.

Pressione V para selecionar a linha inteira (Modo Visual de Linhas).

Mova o cursor para baixo para selecionar várias linhas.

Pressione U para converter todas as linhas selecionadas para maiúsculas.

>Conclusão
Dominar os comandos de criação de linhas (o, O), anexar texto (a, A, i, I) e manipular o caso dos caracteres (~, gu, gU, e os comandos de modo visual u, U) no Vi/Vim é essencial para uma edição de texto eficiente e rápida no Linux. A prática regular desses comandos permite que você trabalhe com flexibilidade e precisão, aproveitando ao máximo o poder deste editor clássico.