
# Table of Contents

1.  [Transformações Lineares](#orgd4d1381)
    1.  [Rotação](#org5862e0e)

Em Computação Gráfica, estamos interessados em algumas *transformações* sobre os nossos objetos: *movimentar* objetos de um ponto a outro, *escalá-los* para agrupá-los com outros ojbetos na cena virtual e *rotacioná-los* até que tenham a orientação que desejamos. Além disso, também estamos interessados em *projeções* desses objetos, principalmente em *projeção perspectiva*.


<a id="orgd4d1381"></a>

# Transformações Lineares

**Rotação** e **escalamento** são exemplos de **transformações lineares**, que são funções que mapeiam pontos do espaço bi-dimensional para outros pontos deste mesmo espaço. Portanto, uma transformação linear $T$ terá a assinatura

$$T: \mathbf{R}^{2} \to \mathbf{R}^{2}$$

As transformações lineares **preservam a origem** do sistema de coordenadas e **preservam linhas**, de modo que retas paralelas permanecem paralelas após a transformação.


<a id="org5862e0e"></a>
## Rotação

