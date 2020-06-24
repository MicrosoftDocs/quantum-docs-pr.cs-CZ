---
title: Vektory a matice v kvantových výpočtech
description: Naučte se základy práce s vektory a maticemi.
author: QuantumWriter
uid: microsoft.quantum.concepts.vectors
ms.author: nawiebe@microsoft.com
ms.date: 12/11/2017
ms.topic: article
no-loc:
- $
- $
- $
- $
- $
- $
- '\cdots'
- bmatrix
- '\ddots'
- '\equiv'
- '\sum'
- '\begin'
- '\end'
- '\sqrt'
- '\otimes'
- '{'
- '}'
- '\text'
- '\phi'
- '\kappa'
- '\psi'
- '\alpha'
- '\beta'
- '\gamma'
- '\delta'
- '\omega'
- '\bra'
- '\ket'
- '\boldone'
- '\\\\'
- '\\'
- =
- '\frac'
- '\text'
- '\mapsto'
- '\dagger'
- '\to'
- "\begin{cases}"
- "\end{cases}"
- '\operatorname'
- '\braket'
- '\id'
- '\expect'
- '\defeq'
- '\variance'
- '\dd'
- '&'
- "\begin{align}"
- "\end{align}"
- '\Lambda'
- '\lambda'
- '\Omega'
- '\mathrm'
- '\left'
- '\right'
- '\qquad'
- '\times'
- '\big'
- '\langle'
- '\rangle'
- '\bigg'
- '\Big'
- '|'
- '\mathbb'
- '\vec'
- '\in'
- '\texttt'
- '\ne'
- <
- '>'
- '\leq'
- '\geq'
- ~~
- "~"
- "\begin{bmatrix}"
- "\end{bmatrix}"
- '\_'
ms.openlocfilehash: f9d4e14742b7d06a6e90af0902b31fbdf17aedab
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/23/2020
ms.locfileid: "85269537"
---
# <a name="vectors-and-matrices"></a>Vektory a matice

Pro pochopení výpočetního prostředí je nezbytné, aby byly v některých zkušenostech vektory a matrice. Poskytujeme stručný úvod do výše uvedeného článku a zúčastněné čtenáře se doporučuje přečíst standardní odkaz na lineární algebraický, jako je *Strang, G. (1993). Seznámení s lineárním algebraický (obj. 3). Wellesley, MA: Wellesley-Cambridge Press* nebo online odkaz, jako je [lineární algebraický](http://joshua.smcvt.edu/linearalgebra/).

Vektor sloupce (nebo jednoduše [*Vector*](https://en.wikipedia.org/wiki/Vector_(mathematics_and_physics))) $v $ dimenze (nebo velikosti) $n $ je kolekce $n $ složitých čísel $ (v_1, v_2, \ldots, v_n), uspořádaných jako sloupec:

$ $v = \begin{bmatrix}
v_1\\\\
v_2\\\\
\vdots\\\\
v_n \end{bmatrix}$$

Norma vektorového $v $ je definována jako $ \sqrt { \sum \_ i | v \_ i | ^ 2 } $. Vektor je označován jako Jednotková norma (nebo případně se nazývá [*vektor jednotky*](https://en.wikipedia.org/wiki/Unit_vector)), pokud je jeho norma $1 $ . [*Sousední objekt $v vektoru*](https://en.wikipedia.org/wiki/Adjoint_matrix) $ je označen $v ^ \dagger $ a je definován jako následující vektor řádku, kde $ \* $ označuje komplexně sdružené,

$ $ \begin{ bmatrix } v_1 \\ \\ \vdots \\ \\ v_n \end{ bmatrix } ^ \dagger = \begin{ bmatrix } v_1 ^ * & \cdots & v_n ^ * \end{bmatrix}$$

Nejběžnější způsob, jak vynásobit dva vektory dohromady, je [*vnitřní produkt*](https://en.wikipedia.org/wiki/Inner_product_space), označovaný také jako produkt s tečkou.  Vnitřní produkt poskytuje projekci jednoho vektoru na jiný a je nevýznamný v popisu, jak vyjádřit jeden vektor jako součet dalších jednodušších vektorů.  Vnitřní produkt mezi $u $ a $v $ označený jako $ \left \langle u, v \right \rangle $ je definovaný jako

$ $ \langle u, v \rangle = u ^ \dagger v = u \_ 1 ^ { \* } v_1 + \cdots + u \_ n ^ { \* } v \_ n.
$$

Tento zápis také umožňuje zapsat normu vektorového $v $ jako $ \sqrt { \langle v, v \rangle } $.

Je možné vynásobit vektor číslem $c, aby bylo možné vytvořit $ Nový vektor, jehož záznamy jsou vynásobeny $c $ . Můžeme také přidat dva vektory $u $ a $v $ k vytvoření nového vektoru, jehož položky jsou součtem položek $u $ a $v $ . Následující operace jsou znázorněny níže:

$ $ \mathrm{If } ~ u = \begin{bmatrix}
u_1\\\\
u_2\\\\
\vdots\\\\
u_n \end{ bmatrix } ~ \mathrm{and } ~ v = \begin{bmatrix}
    v_1\\\\
    v_2\\\\
    \vdots\\\\
    v_n \end{ bmatrix } , ~ \mathrm{then } ~ au + BV = \begin{bmatrix}
au_1 + bv_1\\\\
au_2 + bv_2\\\\
\vdots\\\\
au_n + bv_n \end{ bmatrix } .
$$

[*Matice*](https://en.wikipedia.org/wiki/Matrix_(mathematics)) velikosti $m \times n $ je kolekce $MN $ komplexních čísel uspořádaných do $m $ řádků a $n $ sloupců, jak je znázorněno níže:

$ $M = \begin{bmatrix}
M_ {11 } ~ ~ M_ {12 } ~ ~ \cdots ~ ~ M_ {1N } \\ \\ M_ {21 } ~ ~ M_ {22 } ~ ~ \cdots ~ ~ M_ {2N } \\ \\ \ddots\\\\
M_ {M1 } ~ ~ M_ {m2 } ~ ~ \cdots ~ ~ M_ {MN } \\ \\ \end{ bmatrix } . $ $

Všimněte si, že vektor dimenze $n $ je pouze matice velikosti $n \times 1 $ . Stejně jako u vektorů můžeme vynásobit matici s číslem $c $ k získání nové matice, kde je každá položka vynásobena $c $ a můžeme přidat dvě matrice stejné velikosti pro vytvoření nové matrice, jejíž položky jsou součtem odpovídajících položek dvou matric. 

## <a name="matrix-multiplication-and-tensor-products"></a>Násobení a tensor součinů matic

Také je možné vynásobit dvě matrice $M $ dimenzí $m \times n $ a $N $ dimenze $n \times p $ k získání nové matrice $P $ dimenze $m \times p $ , jak je znázorněno níže:

\begin{align}
& \begin{bmatrix}
    M_ {11 } ~ ~ M_ {12 } ~ ~ \cdots ~ ~ M_ {1N } \\ \\ M_ {21 } ~ ~ M_ {22 } ~ ~ \cdots ~ ~ M_ {2N } \\ \\ \ddots\\\\
    M_ {M1 } ~ ~ M_ {m2 } ~ ~ ~ \cdots ~ ~ M_ {MN}
účelubmatrix}
ifunctiondiscoverybmatrix}
N_ {11 } ~ ~ N_ {12 } ~ ~ \cdots ~ ~ N_ N_ {\ddots } \\ \\ {21 } ~ ~ N_ {22 } ~ ~ \cdots ~ ~ N_ {2p } \\ \\\\\\
N_ {N1 } ~ ~ N_ {N2 } ~ ~ \cdots ~ ~ N_ {NP}
\end{ bmatrix } = \begin{bmatrix}
P_ {11 } ~ ~ P_ {12 } ~ ~ \cdots ~ ~ P_ P_ {\ddots } \\ \\ {21 } ~ ~ P_ {22 } ~ ~ \cdots ~ ~ P_ {2p } \\ \\\\\\
P_ {M1 } ~ ~ P_ {m2 } ~ ~ ~ \cdots ~ ~ P_ {MP}
účelubmatrix}
\end{align}

kde jsou položky $P $ $P _ {IK } = \ sum_j M_ {ij} N_ {JK } $. Například položka $P _ {11 } $ je vnitřní produkt prvního řádku $M $ s prvním sloupcem $N $ . Vzhledem k tomu, že vektor je jednoduše speciálním případem matice, tato definice rozšiřuje na násobení vektoru matice. 

Všechny matrice, které považujeme, budou buď čtvercové, kde je počet řádků a sloupců stejný, nebo vektory, které odpovídají pouze $1 $ sloupci. Jednou z speciálních čtvercových matric je [*matice identity*](https://en.wikipedia.org/wiki/Identity_matrix)s označením $ \boldone $ , která má všechny jeho diagonální prvky rovny $1 $ a zbývající prvky se rovnají $0 $ :

$ $ \boldone = \begin{bmatrix}
1 ~ ~ 0 ~ ~ \cdots ~ ~ 0\\\\
0 ~ ~ 1 ~ ~ \cdots ~ ~ 0\\\\
~ ~ \ddots\\\\
0 ~ ~ 0 ~ ~ \cdots ~ ~ 1 \end{ bmatrix } . $ $

U čtvercové matrice $A $ říkáme, že $B matice $ je [*inverzní*](https://en.wikipedia.org/wiki/Invertible_matrix) , pokud $AB = ba = \boldone $ . Inverzní matice nemusí existovat, ale pokud existuje, je jedinečná a $A ^ {-1 } $. 

V případě $M matrice jsou $ sousední nebo sdružená $M $ matice maticí $N $ tak, že $N _ {IJ } = M_ {ji } ^ \* $. Sousední $M $ je obvykle označena $M ^ \dagger $ . Řekněme, že $U matice $ je [*jednotná*](https://en.wikipedia.org/wiki/Unitary_matrix) , pokud $uu ^ \dagger = U ^ \dagger U = \boldone $ nebo ekvivalentní, $U ^ {-1 } = U ^ \dagger $ .  Například nejdůležitější vlastnost maticových matric je, že zachovávají normu vektoru.  K tomu dochází, protože 

$ $ \langle v, v \rangle = v ^ \dagger v = v ^ \dagger U ^ {-1 } u v = v ^ \Dagger u ^ \Dagger u = \Langle u v, U \rangle . $ $  

$M matice $ se označuje jako [*Hermitian*](https://en.wikipedia.org/wiki/Hermitian_matrix) , pokud $M = M ^ \dagger $ .

Nakonec [*produkt tensor*](https://en.wikipedia.org/wiki/Tensor_product) (nebo Kronecker produkt) dvou matic $M $ velikosti $m \times n $ a $N $ velikosti $p \times q $ je větší matrice $P = M \otimes n $ velikosti $MP \times NQ $ a je získána z $M $ a $N následujícím $ způsobem:

\begin{align}
    M \otimes N &= \begin{bmatrix}
        M_ {11 } ~ ~ \cdots ~ ~ M_ {1N } \\ \\ \ddots\\\\
        M_ {M1 } ~ ~ \cdots ~ ~ M_ {MN}
    účelubmatrix}
    \otimes \begin{bmatrix}
        N_ {11 } ~ ~ \cdots ~ ~ N_ {1Q } \\ \\ \ddots\\\\
        N_ {P1 } ~ ~ \cdots ~ ~ N_ {pq}
    \end{ bmatrix } \\ \\ &= \begin{bmatrix}
        M_ {11 } \begin{ bmatrix } N_ {11 } ~ ~ \cdots ~ ~ N_ {1Q } \\ \\ \ddots \\\\ N_ {P1 } ~ ~ \cdots ~ ~ N_ {pq } \end{ bmatrix } ~ ~ \cdots ~ ~ M_ {1N } \begin{ bmatrix } N_ {11 } ~ ~ \cdots ~ ~ N_ {1Q } \\ \\ \ddots \\\\ N_ {P1 } ~ ~ \cdots ~ ~ N_ {pq } \end{ bmatrix } \\ \\ \ddots\\\\
        M_ {M1 } \begin{ bmatrix } N_ {11 } ~ ~ \cdots ~ ~ N_ {1Q } \\ \\ \ddots \\\\ N_ {P1 } ~ ~ \cdots ~ ~ N_ {pq } \end{ bmatrix } ~ ~ \cdots ~ ~ M_ {MN } \begin{ bmatrix } N_ {11 } ~ ~ \cdots ~ ~ N_ {1Q } \\ \\ \ddots \\\\ N_ {P1 } ~ ~ \cdots ~ ~ N_ {pq } \end{bmatrix}
    \end{ bmatrix } .
\end{align}

To je vhodnější v některých příkladech:

$ $ \begin{bmatrix}
        a \\ \\ b \end{ bmatrix } \otimes \begin{ bmatrix } c \\ \\ d \\ \\ e \end{ bmatrix } = \begin{bmatrix}
        \begin{ bmatrix } c \\ \\ d \\ \\ e \end{bmatrix}
        \\\\[1,5 EM] b \begin{ bmatrix } c \\ \\ d \\ \\ e\end{bmatrix}
    účelubmatrix}
    = \begin{ bmatrix } a c \\ \\ a d \\ \\ a e \\ \\ b c \\ \\ b d \\ \\\end{bmatrix}
$$

a

$ $ \begin{bmatrix}
        a \ b \\ \\ c \ d \end{bmatrix}
    \otimes \begin{bmatrix}
        e \ f \\ \\ g \ h \end{bmatrix}
     = \begin{bmatrix}
    určitého\begin{bmatrix}
    e \ f \\\\ g \ h \end{bmatrix}
    b\begin{bmatrix}
    e \ f \\\\ g \ h \end{bmatrix}
    \\\\[1em] c\begin{bmatrix}
    e \ f \\\\ g \ h \end{bmatrix}
    trojrozměrné\begin{bmatrix}
    e \ f \\\\ g \ h \end{bmatrix}
    účelubmatrix}
    = \begin{bmatrix}
    AE \ AF \ je \ BF \\ \\ AG \ Ah \ BG \ BH \\ \\ CE \ CF \ de \ DF \ \\ \\ \ ch \ DG \ DH \end{ bmatrix } .
$$

Konečná užitečná konvence zápisu okolních produktů tensor je to, že pro všechny vektorové $v $ nebo matrice $M $ $v ^ {\otimes n } $ nebo $M ^ {\otimes n } $ je krátká ruka pro $n $ opakovaný tensor produkt.  Příklad:

\begin{align}
& \begin{ bmatrix } 1 \\ \\ 0 \end{ bmatrix } ^ {\otimes 1 } = \begin{ bmatrix } 1 \\ \\ 0 \end{ bmatrix } , \qquad \begin{bmatrix} 1 \\ \\ 0 \end{ bmatrix } ^ {\otimes 2 } = \begin{ bmatrix } 1 \\ \\ 0 \\ \\ 0 \\ \\ 0 \end{ bmatrix } , \qquad \begin{bmatrix} 1 \\ \\ -1 \end{ bmatrix } ^ {\otimes 2 } = \begin{ bmatrix } 1 \\ \\ -1 \\ \\ -1 \\ \\ 1 \end{ bmatrix } , \\ \\ & \begin{ bmatrix } 0 & 1 \\ \\ 1 & 0 \end{ bmatrix } ^ {\otimes 1 } = \begin{ bmatrix } 0 & 1 \\ \\ 1 & 0 \end{ bmatrix } , \qquad \begin{bmatrix} 0 & 1 \\ \\ 1 & 0 \end{ bmatrix } ^ {\otimes 2 } = \begin{ bmatrix } 0 &0&0&1 \\ \\ 0 &0&1&0 \\ \\ 0 &1&0&0 \\\\ 1 &0&0&0 \end{bmatrix} .
\end{align}
