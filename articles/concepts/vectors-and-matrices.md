---
title: Vektory a matice | Microsoft Docs
description: Vektory a matice
author: QuantumWriter
uid: microsoft.quantum.concepts.vectors
ms.author: nawiebe@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: 58c96f9cda22b712e1a408e5566e0a8ee987bd6e
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/26/2019
ms.locfileid: "73183739"
---
# <a name="vectors-and-matrices"></a>Vektory a matice

Pro pochopení výpočetního prostředí je nezbytné, aby byly v některých zkušenostech vektory a matrice. Poskytujeme stručný úvod do výše uvedeného článku a zúčastněné čtenáře se doporučuje přečíst standardní odkaz na lineární algebraický, jako je *Strang, G. (1993). Seznámení s lineárním algebraický (obj. 3). Wellesley, MA: Wellesley-Cambridge Press* nebo online odkaz, jako je [lineární algebraický](http://joshua.smcvt.edu/linearalgebra/).

Vektor sloupce (nebo jednoduše [*Vector*](https://en.wikipedia.org/wiki/Vector_(mathematics_and_physics))) $v $ of Dimension (nebo size) $n $ je kolekce $n $ Complex Numbers $ (v_1, v_2, \ldots, v_n) $ uspořádaná jako sloupec:

$ $v = \begin{bmatrix} v_1\\\\ v_2\\\\ \vdots\\\\ v_n \end{bmatrix} $ $

Norma vektorového $v $ je definovaná jako $ \sqrt{\sum\_i | v\_i | ^ 2} $. Vektor je označován jako Jednotková norma (nebo případně se nazývá [*vektor jednotky*](https://en.wikipedia.org/wiki/Unit_vector)), pokud je jeho norma $1 $. [*Sousední objekt vector*](https://en.wikipedia.org/wiki/Adjoint_matrix) $v $ je označen $v ^ \dagger $ a je definován jako následující vektor řádku, kde $\*$ označuje komplexně sdružené,

$ $ \begin{bmatrix}v_1 \\\\ \vdots \\\\ v_n \end{bmatrix} ^ \dagger = \begin{bmatrix}v_1 ^ * & \cdots & v_n ^ * \end{bmatrix} $ $

Nejběžnější způsob, jak vynásobit dva vektory dohromady, je [*vnitřní produkt*](https://en.wikipedia.org/wiki/Inner_product_space), označovaný také jako produkt s tečkou.  Vnitřní produkt poskytuje projekci jednoho vektoru na jiný a je nevýznamný v popisu, jak vyjádřit jeden vektor jako součet dalších jednodušších vektorů.  Vnitřní produkt mezi $u $ a $v $ označený $ \left\langle u, v\right\rangle $ je definován jako

$ $ \langle u, v\rangle = u ^ \dagger v = u\_1 ^ {\*} v_1 + \cdots + u\_n ^ {\*} v\_n.
$$

Tento zápis také umožňuje zapsat normu vektoru $v $, jako $ \sqrt{\langle v, v\rangle} $.

Vektor můžete vynásobit číslem $c $, aby bylo možné vytvořit nový vektor, jehož záznamy jsou vynásobeny $c $. Můžeme také přidat dva vektory $u $ a $v $ pro vytvoření nového vektoru, jehož položky jsou součtem položek $u $ a $v $. Následující operace jsou znázorněny níže:

$ $ \mathrm{If} ~ u = \begin{bmatrix} u_1\\\\ u_2\\\\ \vdots\\\\ u_n \end{bmatrix} ~ \mathrm{and} ~ v = \begin{bmatrix} v_1\\\\ v_2\\\\ \vdots @no__ t_10_ \\ v_n \end{bmatrix}, ~ \mathrm{then} ~ au + BV = \begin{bmatrix} au_1 + bv_1\\\\ au_2 + bv_2\\\\ \vdots\\\\ au_n + bv_n \end{bmatrix}.
$$

[*Matice*](https://en.wikipedia.org/wiki/Matrix_(mathematics)) velikosti $m \times n $ je kolekce $MN komplexních čísel uspořádaných do $m $ rows a $n $ Columns, jak je znázorněno níže:

$ $M = \begin{bmatrix} M_{11} ~ ~ M_{12} ~ ~ \cdots ~ ~ M_ {1N}\\\\ M_{21} ~ ~ M_{22} ~ ~ \cdots ~ ~ M_ {2N}\\\\ \ddots\\\\ M_ {M1} ~ ~ M_ {m2} ~ ~ \cdots ~ ~ M_ {MN}\\@no__ t_11_ \end{bmatrix}. $ $

Všimněte si, že vektor dimenze $n $ je jednoduše matice velikosti $n \times $1. Stejně jako u vektorů můžeme vynásobit matici číslem $c $, aby se získala Nová matice, kde každá položka je vynásobena $c $, a můžeme přidat dvě matrice stejné velikosti a vytvořit novou matrici, jejíž položky jsou součtem odpovídajících položek dvou matric. 

## <a name="matrix-multiplication-and-tensor-products"></a>Násobení a tensor součinů matic

Můžete také vynásobit dvě matrice $M $ of Dimension $m \times n $ a $N $ of Dimension $n \times p $ k získání nové matrice $P $ of Dimension $m \times p $, jak je znázorněno níže:

\begin{align} & \begin{bmatrix} M_{11} ~ ~ M_{12} ~ ~ \cdots ~ ~ M_ {1N}\\\\ M_{21} ~ ~ M_{22} ~ ~ \cdots ~ ~ M_ {2N}\\\\ \ddots\\\\ M_ {M1} ~ ~ M_ {m2} ~ ~ \cdots ~ ~ M_ {MN} \end{bmatrix} \ Begin {bmatrix} N_{11} ~ ~ N_{12} ~ ~ \cdots ~ ~ N_ {}\\\\ N_{21} ~ ~ N_{22} ~ ~ \cdots ~ ~ N_ {2p}\\\\ \ddots\\\\ N_ {N1} ~ ~ N_ {N2} ~ ~ \cdots ~ ~ N_ {NP} \end{bmatrix} = \begin{bmatrix} P_{11} ~ ~ P_{12} ~ ~ \cdots ~ ~ P_ {}\\\\ P_{21} ~ ~ P_{22} ~ ~ \cdots ~ ~ P_ {2p}\\\\ \ddots\\\\ P_ {M1} ~ ~ P_ {m2} ~ ~ \cdots ~ ~ P_ ~ ~ \end{bmatrix} {MP} \end{align}

kde jsou položky $P $ $P _ {IK} = \sum_j M_ {IJ} N_ {JK} $. Například položka $P _{11}$ je vnitřní produkt prvního řádku $M $ s prvním sloupcem $N $. Vzhledem k tomu, že vektor je jednoduše speciálním případem matice, tato definice rozšiřuje na násobení vektoru matice. 

Všechny matrice, které považujeme, budou buď čtvercové, kde je počet řádků a sloupců stejný, nebo vektory, které odpovídají pouze $1 $ sloupci. Jednou speciální maticí je [*matice identity*](https://en.wikipedia.org/wiki/Identity_matrix)označená $ \boldone $, která má všechny jeho diagonální prvky rovnající se $1 $ a zbývající prvky se rovnají $0 $:

$ $ \boldone = \begin{bmatrix} 1 ~ ~ 0 ~ ~ \cdots ~ ~ 0\\\\ 0 ~ ~ 1 ~ ~ \cdots ~ ~ 0\\\\ ~ ~ \ddots\\\\ 0 ~ ~ 0 ~ ~ \cdots ~ ~ 1 \end{bmatrix}. $ $

U čtvercové matrice $A $ říkáme matrici $B $ je jejich [*inverzní*](https://en.wikipedia.org/wiki/Invertible_matrix) , pokud $AB = ba = \boldone $. Invertování matrice nemusí existovat, ale pokud existuje, je jedinečné, ale $A ^{-1}$. 

Pro libovolnou matrici $M $ je to, že $M $ je matice $N $, což $N _ {IJ} = M_ {ji} ^\*$. Sousední soubor $M $ je obvykle označen $M ^ \dagger $. Vyberu si matrici $U $ je [*jednotná*](https://en.wikipedia.org/wiki/Unitary_matrix) , pokud $uu ^ \Dagger = u ^ \dagger U = \boldone $ nebo ekvivalentně $U ^{-1} = u ^ \dagger $.  Například nejdůležitější vlastnost maticových matric je, že zachovávají normu vektoru.  K tomu dochází, protože 

$ $ \langle v, v \rangle = v ^ \dagger v = v ^ \dagger U ^{-1} U = v ^ \dagger U ^ \dagger U = \langle U v, U v\rangle. $ $  

[*Pokud $M*](https://en.wikipedia.org/wiki/Hermitian_matrix) = M ^ \dagger $, je $M matice.

Nakonec [*produkt tensor*](https://en.wikipedia.org/wiki/Tensor_product) (nebo Kronecker produkt) dvou matric $M $ Size $m \times n $ a $N $ Size $p \times q $ je větší maticí $P = M\otimes n $ velikosti $MP \times NQ $ a získá se z $M $ a $N $ následujícím způsobem:

\begin{align} M \otimes N & = \begin{bmatrix} M_{11} ~ ~ \cdots ~ ~ M_ {1N} \\\\ \ddots\\\\ M_ {M1} ~ ~ \cdots ~ ~ M_ {MN} \end{bmatrix} \otimes \begin{bmatrix} N_{11} ~ ~ \cdots ~ ~ N_ {1Q}\\\\ \ddots @no__ t_8_ \\ N_ {P1} ~ ~ \cdots ~ ~ N_ {pq} \end{bmatrix}\\\\ & = \begin{bmatrix} M_{11} \begin{bmatrix} N_{11} ~ ~ \cdots ~ ~ N_ {1Q}\\\\ \ddots\\\\ N_ {P1} ~ ~ \cdots ~ ~ N_ {pq} \end{bmatrix} ~ ~ \cdots ~ ~ M_ {1N} \begin{bmatrix} N_{11} ~ ~ \cdots ~ ~ N_ {1Q}\\\\ \ddots\\\\ N_ {P1} ~ ~ \cdots ~ ~ N_ {pq} \end{bmatrix}\\\\ \ddots\\\\ M_ {M1} \begin{bmatrix} N_{11} ~ ~ \ cdots ~ ~ N_ {1Q}\\\\ \ddots\\\\ N_ {P1} ~ ~ \cdots ~ ~ N_ {pq} \end{bmatrix} ~ ~ \cdots ~ ~ M_ {MN} \begin{bmatrix} N_{11} ~ ~ \cdots ~ ~ N_ {1Q}\\\\ \ddots\\\\ N_ {P1} ~ ~ \cdots ~ ~ N_ {pq} \end {bmatrix} \end{bmatrix}.
\end{align}

To je vhodnější v některých příkladech:

$ $ \begin{bmatrix} a \\\\ b \end{bmatrix} \otimes \begin{bmatrix} c \\\\ d \\\\ e \end{bmatrix} = \begin{bmatrix} a \begin{bmatrix} c \\\\ d \\\\ e \end{bmatrix} @no__ t_10_ \\[1,5 EM] b \begin{bmatrix} c \\\\ d \\\\ e\end {bmatrix} \end{bmatrix} = \begin{bmatrix} a c \\\\ d \\\\ a e \\\\ b c \\\\ b d \\\\ be\end {bmatrix} $ $

a

$ $ \begin{bmatrix} a \ b \\\\ c \ d \end{bmatrix} \otimes \begin{bmatrix} e \ f\\\\g \ h \end{bmatrix} = \begin{bmatrix} a\begin {bmatrix} e \ f\\\\ g \ h \end{bmatrix} b\begin {bmatrix} e \ f\\@no__ t_7_ g \ h \end{bmatrix} \\\\[1em] c\begin {bmatrix} e \ f\\\\ g \ h \end{bmatrix} d\begin {bmatrix} e \ f\\\\ g \ h \end{bmatrix} \end{bmatrix} = \begin{bmatrix} AE \ AF \-BF \\@no__ t_15_ AG \ Ah \ BG \ BH \\\\ CE \ CF \ de \ DF \\\\ a \ ch \ DG \ DH \end{bmatrix}.
$$

Konečná užitečná konvence zápisu okolních produktů tensor je to, že pro všechny vektory $v $ nebo Matrix $M $, $v ^ {\otimes n} $ nebo $M ^ {\otimes n} $ je krátká ruka pro $n opakovaného tensor produktu.  Například:

\begin{align} & \begin{bmatrix} 1 \\\\ 0 \end{bmatrix} ^ {\otimes 1} = \begin{bmatrix} 1 \\\\ 0 \end{bmatrix}, \qquad\begin{bmatrix} 1 \\\\ 0 \end{bmatrix} ^ {\otimes 2} = \begin{bmatrix} 1 \\\\ 0 \\\\0 \\\\0 \end{bmatrix}, \qquad\begin{bmatrix} 1 \\\\-1 \end{bmatrix} ^ {\otimes 2} = \begin{bmatrix} 1 \\\\-1 \\\\-1 \\\\1 \end{bmatrix}, \\\\ & \begin{bmatrix} 0 & 1 \\\\ 1 & 0 \end{bmatrix} ^ {\otimes 1} = \begin{bmatrix} 0 & 1 \\\\ 1 & 0 \end{bmatrix}, \qquad\begin{bmatrix} 0 & 1 \\@no__ t_27_ 1 & 0 \end{bmatrix} ^ {\otimes 2} = \begin{bmatrix} 0 & 0 & 0 & 1 \\\\ 0 & 0 & 1 & 0 \\\\ 0 & 1 & 0 & 0\\\\ 1 & 0 & 0 & 0 \ konec {bmatrix}.
\end{align}

