<!--
ID:       42d8f10f-5001-47b2-84d8-0c82d31d914a
aliases:  Constructing a orthonormal basis from a single vector
projeto:  linear-algebra
zid:      202605091545
tags:     linear-algebra, draft
-->

# Construção de uma base ortonormal a partir de um único vetor

Dado um vetor $\vec{a}$, desejamos construir uma [base vetorial ortonormal](bases-vetoriais-ortonormais.md) $\mathbf{B} =$ $\{\vec{u}, \vec{v}, \vec{w}\}$ tal que $\vec{w}$ seja paralelo a $\vec{a}$. Sabemos que existem inúmeras bases para um espaço vetorial, então não podemos definir um procedimento para encontrar uma *base única*, mas podemos definir um procedimento robusto para *sempre* encontrar uma base.

Seja $$\vec{w} = \frac{\vec{a}}{\lVert\vec{a}\rVert}$$

Para obtermos $\vec{u}$ e $\vec{v}$, precisamos *encontrar um outro vetor* $\vec{t}$ tal que $\vec{t}$ **não** é colinear a $\vec{w}$. Para tanto, tomamos

1. inicialmente $\vec{t}$ $\leftarrow$ $\vec{w}$, isto é, assumimos que $\vec{t}$ é idêntico a $\vec{w}$;
2. em seguida, modificamos *a menor componente* de $\vec{t}$ para $1$.

Por exemplo, seja $\vec{w} = \left(\frac{1}{\sqrt{2}}, \frac{-1}{\sqrt{2}}, 0\right)$. Então teremos $\vec{w} = \left(\frac{1}{\sqrt{2}}, \frac{-1}{\sqrt{2}}, \mathbf{1}\right)$. Os vetores $\vec{u}$ e $\vec{v}$ seguem facilmente:

$$\vec{u} = \frac{\vec{t} \times \vec{w}}{\lVert\vec{t} \times \vec{w}\rVert}$$
$$\vec{v} = \vec{w} \times \vec{u}$$

