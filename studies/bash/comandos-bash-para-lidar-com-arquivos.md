
# Table of Contents

1.  [Comandos *bash* para lidar com arquivos](#org0686cbe)
    1.  [Renomear um arquivo](#org863f14e)
        1.  [(*commando*) renomear um arquivo, confirmando caso *filename* já exista](#orgfbe1da3)
        2.  [(*commando*) renomear um arquivo, forçosamente, ignorando em caso de overwrite](#orgbde0087)
        3.  [(*comando*) renomear um caso, se e somente se, o novo filename não existir (`no-clobber`)](#orgf8e9f46)
    2.  [Renomear diversos arquivos em *bulk*](#orgd659ad9)
        1.  [(*comando*) renomear arquivos em *bulk*](#org4fdc845)
    3.  [Remover (deletar, excluir) um arquivo](#org4d1b709)
        1.  [(*comando*) remover um arquivo](#orga4016b5)
        2.  [(*comando*) remover diversos arquivos](#orgf463974)
        3.  [(*comando*) remover todos os arquivos com uma extensão específica](#org40b7652)



<a id="org0686cbe"></a>

# Comandos *bash* para lidar com arquivos


<a id="org863f14e"></a>

## Renomear um arquivo

Para renomear um arquivo, usamos o programa `mv` (*move*). Algumas *flags* são interessantes:

-   `-i` pedirá por confirmação, **caso o *novo* `filename` já exista**;
-   `-f`, por outro lado, irá **forçar** *overwrite* sem *prompting*, sem perguntar se é isto mesmo que desejamos fazer;
-   `-n`, *no-clobber* indica que **se o novo `filename` já existe, então não queremos *overwrite*, o `mv` não permitirá**.


<a id="orgfbe1da3"></a>

### (*commando*) renomear um arquivo, confirmando caso *filename* já exista

    mv old-filename.ext new-filename.ext -i


<a id="orgbde0087"></a>

### (*commando*) renomear um arquivo, forçosamente, ignorando em caso de overwrite

    mv old-filename.ext new-filename.ext -f


<a id="orgf8e9f46"></a>

### (*comando*) renomear um caso, se e somente se, o novo filename não existir (`no-clobber`)

    mv old-filename.ext new-filename -n


<a id="orgd659ad9"></a>

## Renomear diversos arquivos em *bulk*

Podemos renomear diversos arquivos em um só comando através de um laço `for`.


<a id="org4fdc845"></a>

### (*comando*) renomear arquivos em *bulk*

O exemplo abaixo usa o operador `*` para ignorar todos os caracteres anteriores à extensão. Dessa forma, estamos *renomeando todos os arquivos `.js` para `.html`.*

    for f in *.js; do mv -- "$f" "${f%.js}.html"; done


<a id="org4d1b709"></a>

## Remover (deletar, excluir) um arquivo

Usamos o comando `rm` (*remove*) para remover arquivos. O comando `rm` recebe um ou mais *filenames* como argumento, e exclui todos eles.
`[IMPORTANTE!]` Arquivos e diretórios removidos com `rm` são **PERMANENTEMENTE EXCLUÍDOS**. Não há *trashbin* para `rm`. **O USO DE `rm` É UMA DECISÃO PERMANENTE**.
Semelhante ao `mv`, algumas *flags* interessantes:

-   `-i`, interativo. Permite confirmação anterior à exclusão;
-   `-f`, forçosamente. Remoção sem confirmação inclusive de arquivos `write-protected`;
-   `-v`, *verbose*. Imprime em tela os nomes dos arquivos removidos;
-   `-r`, recursivo. Somente faz sentido para **diretórios**, excluindo o diretório e todos os seus conteúdos, inclusive outros diretórios (e seus conteúdos!).


<a id="orga4016b5"></a>

### (*comando*) remover um arquivo

    rm filename.ext


<a id="orgf463974"></a>

### (*comando*) remover diversos arquivos

    rm filename-1.ext filename-2.ext filename-3.ext


<a id="org40b7652"></a>

### (*comando*) remover todos os arquivos com uma extensão específica

Podemos usar a *wild-card* `*` para remover todos os arquivos de mesma extensão

    rm *.ext

Acima, removeremos todos os arquivos no diretório atual com extensão `.ext`.

