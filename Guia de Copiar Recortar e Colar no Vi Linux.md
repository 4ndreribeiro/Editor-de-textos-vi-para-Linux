# Guia Completo: Copiar, Recortar e Colar no Vi/Vim no Linux
>O Vi (e seu sucessor, o Vim) é um editor de texto modal que se destaca pela sua eficiência na manipulação de texto. Dominar os comandos de copiar (yank), recortar (delete/cut) e colar (paste) é fundamental para editar documentos de forma rápida e fluente, sem a necessidade de depender do mouse.

Entendendo os Modos do Vi/Vim
Para usar o Vi/Vim de forma eficaz, é fundamental entender seus três modos principais:

Modo de Comando (Normal Mode): O modo padrão. As teclas são interpretadas como comandos para navegação, manipulação e deleção. Para retornar a este modo de qualquer outro, pressione Esc.

Modo de Inserção (Insert Mode): Para digitar texto no arquivo. As teclas digitadas são inseridas diretamente. Você entra a partir do Modo de Comando usando comandos como i, a, o, etc. Retorne ao Modo de Comando com Esc.

Modo de Última Linha (Ex Mode): Para comandos de arquivo (salvar, sair), pesquisa e substituição. Você entra a partir do Modo de Comando digitando :.

## 1. Copiar Texto (Yank - y)
No Vi/Vim, o ato de copiar é chamado de "yank" (puxar/arrancar). O texto copiado é armazenado em um buffer (como uma área de transferência) e pode ser colado posteriormente.

Copiar Caracteres
yl: Copia o caractere sob o cursor (similar a y seguido de l).

y0: Copia do cursor até o início da linha.

y$: Copia do cursor até o final da linha.

yw: Copia a palavra a partir do cursor.

ye: Copia do cursor até o final da palavra atual.

Copiar Linhas
yy: Copia a linha inteira onde o cursor está.

Copiar Múltiplos Itens (Com Números)
Você pode prefixar os comandos de copiar com um número para especificar quantas vezes a ação deve ser repetida.

5yy: Copia as próximas 5 linhas (incluindo a atual).

3yw: Copia as próximas 3 palavras.

2y$: Copia do cursor até o final das próximas 2 linhas (incluindo a atual).

Copiar em Modo Visual (Vim Específico)
No Vim, você pode usar o Modo Visual para selecionar um bloco de texto e depois copiá-lo.

Entrar no Modo Visual:

v: Modo Visual de Caracteres.

V: Modo Visual de Linhas.

Ctrl + v: Modo Visual de Bloco (para seleção retangular).

Selecionar o Texto: Mova o cursor para estender a seleção.

Copiar a Seleção: Pressione y (yank) para copiar o texto selecionado.

Exemplo:

Posicione o cursor no início de um parágrafo.

Pressione v.

Mova o cursor para o final do parágrafo.

Pressione y para copiar todo o parágrafo selecionado.

## 2. Recortar Texto (Delete/Cut - d, x, D)
No Vi/Vim, o ato de recortar é essencialmente uma operação de "deleção" que também armazena o conteúdo deletado no buffer, tornando-o disponível para ser colado.

Recortar Caracteres
x: Recorta (deleta) o caractere sob o cursor.

X: Recorta (deleta) o caractere à esquerda do cursor.

Recortar Palavras e Linhas
dw: Recorta (deleta) a palavra a partir da posição do cursor até o início da próxima palavra.

de: Recorta (deleta) do cursor até o final da palavra atual.

d0: Recorta (deleta) do cursor até o início da linha.

d$: Recorta (deleta) do cursor até o final da linha.

dd: Recorta (deleta) a linha inteira onde o cursor está.

D: Recorta (deleta) do cursor até o final da linha (equivalente a d$).

Recortar Múltiplos Itens (Com Números)
Assim como com y, você pode prefixar os comandos de recortar com um número.

5dd: Recorta (deleta) as próximas 5 linhas (incluindo a atual).

3dw: Recorta (deleta) as próximas 3 palavras.

Recortar em Modo Visual (Vim Específico)
No Vim, após selecionar um bloco de texto no Modo Visual, você pode recortá-lo.

Entrar no Modo Visual: (v, V, ou Ctrl + v).

Selecionar o Texto: Mova o cursor para estender a seleção.

Recortar a Seleção: Pressione d (delete) ou x para recortar o texto selecionado.

## 3. Colar Texto (Paste - p, P)
O comando de colar insere o conteúdo do último texto copiado (yankado) ou recortado (deletado) no documento.

p (paste after): Cola o conteúdo do buffer após o cursor (se for um caractere/palavra) ou abaixo da linha atual (se for uma linha inteira).

Exemplo (caractere/palavra): Cursor em A_B_C. Você copiou "XY". Pressione p. Resulta em A_B_CXY.

Exemplo (linha): Cursor na linha 2. Você copiou a linha 5. Pressione p. A linha copiada será colada após a linha 2 (ou seja, na linha 3).

P (paste before): Cola o conteúdo do buffer antes do cursor (se for um caractere/palavra) ou acima da linha atual (se for uma linha inteira).

Exemplo (caractere/palavra): Cursor em A_B_C. Você copiou "XY". Pressione P. Resulta em A_BXY_C.

Exemplo (linha): Cursor na linha 2. Você copiou a linha 5. Pressione P. A linha copiada será colada antes da linha 2 (ou seja, na linha 1).

Colar Múltiplas Vezes (Com Números)
Você pode prefixar os comandos de colar com um número para colar o conteúdo múltiplas vezes.

5p: Cola o conteúdo do buffer 5 vezes.

Conclusão
Dominar os comandos de copiar (y), recortar (d, x, D) e colar (p, P) no Vi/Vim é um passo essencial para se tornar um editor de texto eficiente no Linux. A prática desses comandos no Modo de Comando, combinada com os movimentos e a capacidade de usar contadores numéricos e o Modo Visual (no Vim), permite uma manipulação de texto incrivelmente rápida e precisa.Guia Completo: Copiar, Recortar e Colar no Vi/Vim no Linux

O Vi (e seu sucessor, o Vim) é um editor de texto modal que se destaca pela sua eficiência na manipulação de texto. Dominar os comandos de copiar (yank), recortar (delete/cut) e colar (paste) é fundamental para editar documentos de forma rápida e fluente, sem a necessidade de depender do mouse.

Entendendo os Modos do Vi/Vim
Para usar o Vi/Vim de forma eficaz, é fundamental entender seus três modos principais:

Modo de Comando (Normal Mode): O modo padrão. As teclas são interpretadas como comandos para navegação, manipulação e deleção. Para retornar a este modo de qualquer outro, pressione Esc.

Modo de Inserção (Insert Mode): Para digitar texto no arquivo. As teclas digitadas são inseridas diretamente. Você entra a partir do Modo de Comando usando comandos como i, a, o, etc. Retorne ao Modo de Comando com Esc.

Modo de Última Linha (Ex Mode): Para comandos de arquivo (salvar, sair), pesquisa e substituição. Você entra a partir do Modo de Comando digitando :.

### 1. Copiar Texto (Yank - y)
No Vi/Vim, o ato de copiar é chamado de "yank" (puxar/arrancar). O texto copiado é armazenado em um buffer (como uma área de transferência) e pode ser colado posteriormente.

Copiar Caracteres
yl: Copia o caractere sob o cursor (similar a y seguido de l).

y0: Copia do cursor até o início da linha.

y$: Copia do cursor até o final da linha.

yw: Copia a palavra a partir do cursor.

ye: Copia do cursor até o final da palavra atual.

Copiar Linhas
yy: Copia a linha inteira onde o cursor está.

Copiar Múltiplos Itens (Com Números)
Você pode prefixar os comandos de copiar com um número para especificar quantas vezes a ação deve ser repetida.

5yy: Copia as próximas 5 linhas (incluindo a atual).

3yw: Copia as próximas 3 palavras.

2y$: Copia do cursor até o final das próximas 2 linhas (incluindo a atual).

Copiar em Modo Visual (Vim Específico)
No Vim, você pode usar o Modo Visual para selecionar um bloco de texto e depois copiá-lo.

Entrar no Modo Visual:

v: Modo Visual de Caracteres.

V: Modo Visual de Linhas.

Ctrl + v: Modo Visual de Bloco (para seleção retangular).

Selecionar o Texto: Mova o cursor para estender a seleção.

Copiar a Seleção: Pressione y (yank) para copiar o texto selecionado.

Exemplo:

Posicione o cursor no início de um parágrafo.

Pressione v.

Mova o cursor para o final do parágrafo.

Pressione y para copiar todo o parágrafo selecionado.

### 2. Recortar Texto (Delete/Cut - d, x, D)
No Vi/Vim, o ato de recortar é essencialmente uma operação de "deleção" que também armazena o conteúdo deletado no buffer, tornando-o disponível para ser colado.

Recortar Caracteres
x: Recorta (deleta) o caractere sob o cursor.

X: Recorta (deleta) o caractere à esquerda do cursor.

Recortar Palavras e Linhas
dw: Recorta (deleta) a palavra a partir da posição do cursor até o início da próxima palavra.

de: Recorta (deleta) do cursor até o final da palavra atual.

d0: Recorta (deleta) do cursor até o início da linha.

d$: Recorta (deleta) do cursor até o final da linha.

dd: Recorta (deleta) a linha inteira onde o cursor está.

D: Recorta (deleta) do cursor até o final da linha (equivalente a d$).

Recortar Múltiplos Itens (Com Números)
Assim como com y, você pode prefixar os comandos de recortar com um número.

5dd: Recorta (deleta) as próximas 5 linhas (incluindo a atual).

3dw: Recorta (deleta) as próximas 3 palavras.

Recortar em Modo Visual (Vim Específico)
No Vim, após selecionar um bloco de texto no Modo Visual, você pode recortá-lo.

Entrar no Modo Visual: (v, V, ou Ctrl + v).

Selecionar o Texto: Mova o cursor para estender a seleção.

Recortar a Seleção: Pressione d (delete) ou x para recortar o texto selecionado.

### 3. Colar Texto (Paste - p, P)
O comando de colar insere o conteúdo do último texto copiado (yankado) ou recortado (deletado) no documento.

p (paste after): Cola o conteúdo do buffer após o cursor (se for um caractere/palavra) ou abaixo da linha atual (se for uma linha inteira).

Exemplo (caractere/palavra): Cursor em A_B_C. Você copiou "XY". Pressione p. Resulta em A_B_CXY.

Exemplo (linha): Cursor na linha 2. Você copiou a linha 5. Pressione p. A linha copiada será colada após a linha 2 (ou seja, na linha 3).

P (paste before): Cola o conteúdo do buffer antes do cursor (se for um caractere/palavra) ou acima da linha atual (se for uma linha inteira).

Exemplo (caractere/palavra): Cursor em A_B_C. Você copiou "XY". Pressione P. Resulta em A_BXY_C.

Exemplo (linha): Cursor na linha 2. Você copiou a linha 5. Pressione P. A linha copiada será colada antes da linha 2 (ou seja, na linha 1).

Colar Múltiplas Vezes (Com Números)
Você pode prefixar os comandos de colar com um número para colar o conteúdo múltiplas vezes.

5p: Cola o conteúdo do buffer 5 vezes.

Conclusão
Dominar os comandos de copiar (y), recortar (d, x, D) e colar (p, P) no Vi/Vim é um passo essencial para se tornar um editor de texto eficiente no Linux. A prática desses comandos no Modo de Comando, combinada com os movimentos e a capacidade de usar contadores numéricos e o Modo Visual (no Vim), permite uma manipulação de texto incrivelmente rápida e precisa.Guia Completo: Copiar, Recortar e Colar no Vi/Vim no Linux

O Vi (e seu sucessor, o Vim) é um editor de texto modal que se destaca pela sua eficiência na manipulação de texto. Dominar os comandos de copiar (yank), recortar (delete/cut) e colar (paste) é fundamental para editar documentos de forma rápida e fluente, sem a necessidade de depender do mouse.

Entendendo os Modos do Vi/Vim
Para usar o Vi/Vim de forma eficaz, é fundamental entender seus três modos principais:

Modo de Comando (Normal Mode): O modo padrão. As teclas são interpretadas como comandos para navegação, manipulação e deleção. Para retornar a este modo de qualquer outro, pressione Esc.

Modo de Inserção (Insert Mode): Para digitar texto no arquivo. As teclas digitadas são inseridas diretamente. Você entra a partir do Modo de Comando usando comandos como i, a, o, etc. Retorne ao Modo de Comando com Esc.

Modo de Última Linha (Ex Mode): Para comandos de arquivo (salvar, sair), pesquisa e substituição. Você entra a partir do Modo de Comando digitando :.

### 1. Copiar Texto (Yank - y)
No Vi/Vim, o ato de copiar é chamado de "yank" (puxar/arrancar). O texto copiado é armazenado em um buffer (como uma área de transferência) e pode ser colado posteriormente.

Copiar Caracteres
yl: Copia o caractere sob o cursor (similar a y seguido de l).

y0: Copia do cursor até o início da linha.

y$: Copia do cursor até o final da linha.

yw: Copia a palavra a partir do cursor.

ye: Copia do cursor até o final da palavra atual.

Copiar Linhas
yy: Copia a linha inteira onde o cursor está.

Copiar Múltiplos Itens (Com Números)
Você pode prefixar os comandos de copiar com um número para especificar quantas vezes a ação deve ser repetida.

5yy: Copia as próximas 5 linhas (incluindo a atual).

3yw: Copia as próximas 3 palavras.

2y$: Copia do cursor até o final das próximas 2 linhas (incluindo a atual).

Copiar em Modo Visual (Vim Específico)
No Vim, você pode usar o Modo Visual para selecionar um bloco de texto e depois copiá-lo.

Entrar no Modo Visual:

v: Modo Visual de Caracteres.

V: Modo Visual de Linhas.

Ctrl + v: Modo Visual de Bloco (para seleção retangular).

Selecionar o Texto: Mova o cursor para estender a seleção.

Copiar a Seleção: Pressione y (yank) para copiar o texto selecionado.

Exemplo:

Posicione o cursor no início de um parágrafo.

Pressione v.

Mova o cursor para o final do parágrafo.

Pressione y para copiar todo o parágrafo selecionado.

### 2. Recortar Texto (Delete/Cut - d, x, D)
No Vi/Vim, o ato de recortar é essencialmente uma operação de "deleção" que também armazena o conteúdo deletado no buffer, tornando-o disponível para ser colado.

Recortar Caracteres
x: Recorta (deleta) o caractere sob o cursor.

X: Recorta (deleta) o caractere à esquerda do cursor.

Recortar Palavras e Linhas
dw: Recorta (deleta) a palavra a partir da posição do cursor até o início da próxima palavra.

de: Recorta (deleta) do cursor até o final da palavra atual.

d0: Recorta (deleta) do cursor até o início da linha.

d$: Recorta (deleta) do cursor até o final da linha.

dd: Recorta (deleta) a linha inteira onde o cursor está.

D: Recorta (deleta) do cursor até o final da linha (equivalente a d$).

Recortar Múltiplos Itens (Com Números)
Assim como com y, você pode prefixar os comandos de recortar com um número.

5dd: Recorta (deleta) as próximas 5 linhas (incluindo a atual).

3dw: Recorta (deleta) as próximas 3 palavras.

Recortar em Modo Visual (Vim Específico)
No Vim, após selecionar um bloco de texto no Modo Visual, você pode recortá-lo.

Entrar no Modo Visual: (v, V, ou Ctrl + v).

Selecionar o Texto: Mova o cursor para estender a seleção.

Recortar a Seleção: Pressione d (delete) ou x para recortar o texto selecionado.

### 3. Colar Texto (Paste - p, P)
O comando de colar insere o conteúdo do último texto copiado (yankado) ou recortado (deletado) no documento.

p (paste after): Cola o conteúdo do buffer após o cursor (se for um caractere/palavra) ou abaixo da linha atual (se for uma linha inteira).

Exemplo (caractere/palavra): Cursor em A_B_C. Você copiou "XY". Pressione p. Resulta em A_B_CXY.

Exemplo (linha): Cursor na linha 2. Você copiou a linha 5. Pressione p. A linha copiada será colada após a linha 2 (ou seja, na linha 3).

P (paste before): Cola o conteúdo do buffer antes do cursor (se for um caractere/palavra) ou acima da linha atual (se for uma linha inteira).

Exemplo (caractere/palavra): Cursor em A_B_C. Você copiou "XY". Pressione P. Resulta em A_BXY_C.

Exemplo (linha): Cursor na linha 2. Você copiou a linha 5. Pressione P. A linha copiada será colada antes da linha 2 (ou seja, na linha 1).

Colar Múltiplas Vezes (Com Números)
Você pode prefixar os comandos de colar com um número para colar o conteúdo múltiplas vezes.

5p: Cola o conteúdo do buffer 5 vezes.

Conclusão
Dominar os comandos de copiar (y), recortar (d, x, D) e colar (p, P) no Vi/Vim é um passo essencial para se tornar um editor de texto eficiente no Linux. A prática desses comandos no Modo de Comando, combinada com os movimentos e a capacidade de usar contadores numéricos e o Modo Visual (no Vim), permite uma manipulação de texto incrivelmente rápida e precisa.