---
title: Pokročilé koncepty matice
description: Přečtěte si o exponenciálních eigenvectors, eigenvalues a matricích, které se používají k popisu a simulaci algoritmů pro plnění.
author: QuantumWriter
uid: microsoft.quantum.concepts.matrix-advanced
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
- $$
- $$
- $$
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
ms.openlocfilehash: 71923247121eae6a1d4e26d2664d8e547370ba3a
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/23/2020
ms.locfileid: "85269452"
---
# <a name="advanced-matrix-concepts"></a>Pokročilé koncepty matrice #

Teď rozšíříme své manipulace s matricemi na [*eigenvalues, eigenvectors*](https://en.wikipedia.org/wiki/Eigenvalues_and_eigenvectors) a [*exponenciální*](https://en.wikipedia.org/wiki/Matrix_exponential) , které tvoří základní sadu nástrojů, které potřebujeme k popisu a implementaci algoritmů.

## <a name="eigenvalues-and-eigenvectors"></a>Eigenvalues a eigenvectors ##

Nechejte $M $ být čtvercovou maticí a $v $ být vektor, který není vektorem všechny nuly (tj. vektor se všemi položkami rovnými $0 $ ).

Řekněme, $ že $v je [*eigenvector*](https://en.wikipedia.org/wiki/Eigenvalues_and_eigenvectors) $M, $ Pokud $MV = cv $ pro určité číslo $c $ . Říkáme, $c $ je [*eigenvalue*](https://en.wikipedia.org/wiki/Eigenvalues_and_eigenvectors) odpovídající $v eigenvector $ . V obecné matrici $M $ může transformovat vektor na jakýkoliv jiný vektor, ale eigenvector je speciální, protože je ponechán beze změny s výjimkou vynásobeného číslem. Všimněte si, že pokud $ je $v eigenvector s eigenvalue $c $ , $AV $ je také eigenvector (pro nenulové $a $ ) se stejným eigenvalue.

Například pro matici identity je každé vektorové $v $ eigenvector s eigenvalue $1 $ .

Jako další příklad zvažte [*diagonální matici*](https://en.wikipedia.org/wiki/Diagonal_matrix) $D $ , která má v diagonálním případě pouze nenulové položky:

$ $ \begin{bmatrix}
d_1 & 0 & 0 \\ \\ 0 & d_2 & 0 \\ \\ 0 & 0 & D_3 \end{ bmatrix } .
$$

Vektory

$ $ \begin{ bmatrix } 1 \\ \\ 0 \\ \\ 0 \end{ bmatrix } , \begin{ bmatrix } 0 \\ \\ 1 \\ \\ 0 \end{bmatrix} a \begin{ bmatrix } 0 0 \\ \\ \\ \\ 1\end{bmatrix}$$

eigenvectors z této matice s eigenvalues $d _1 $ , $d _2 $ a $d _3 $ , v uvedeném pořadí. Pokud $d _1 $ , $d _2 $ a $d _3 $ jsou odlišná čísla, pak jsou tyto vektory (a jejich násobky) jediným eigenvectors $D matice $ . Obecně platí, že pro diagonální matrici je snadné číst z eigenvalues a eigenvectors. Eigenvalues jsou všechna čísla, která se zobrazují na diagonále a jejich příslušné eigenvectors jsou vektory jednotek s jednou položkou rovnající se $1 $ a zbývající položky rovnající se $0 $ .

Všimněte si výše uvedeného příkladu, že eigenvectors $D $ tvoří základ pro $3 $ multidimenzionální vektory. Základem je sada vektorů, což znamená, že každý vektor lze zapsat jako lineární kombinaci. Explicitní, $v _1 $ , $v _2 $ a $v _3 $ formu, pokud kterýkoli $v $ může být zapsaný jako $v = A_1 v_1 + a_2 v_2 + a_3 v_3 $ pro některá čísla $a _1 $ , $a _2 $ a $a _3 $ .

Odvolání, že matice Hermitian (označovaná také jako samostatně sousedící) je složitá čtvercová matice, která se rovná svému vlastnímu komplexu, zatímco Jednotková matice je složitá čtvercová matice, jejíž invertování je rovno složitosti.
V případě Hermitian a maticových matric, které jsou v podstatě pouze v případě, že se jedná o výpočetní výkon, je k dispozici obecný výsledek, který je známý jako [*spektrální věta*](https://en.wikipedia.org/wiki/Spectral_theorem), který vyhodnotí následující: pro všechny Hermitian nebo $M jednotkové matrice $ existuje v $ $ některých diagonálních maticových $DCH $M $U = u ^ \dagger D u $ . Kromě toho se diagonální položky $D $ eigenvalues $M $ .

Už víte, jak vypočítat eigenvalues a eigenvectors diagonální matrice $D $ . Pomocí tohoto větau víme, že pokud $ je $v eigenvector $D $ s eigenvalue $c $ , tj. $DV = cv $ , pak $U ^ \dagger v $ bude eigenvector $M $ s eigenvalue $c $ . Důvodem je to, že

$ $M (U ^ \dagger v) = U ^ \dagger D U (U ^ \dagger v) = U ^ \dagger D (U U ^ \dagger) v = U ^ \dagger D v = c U ^ \dagger v. $ $

## <a name="matrix-exponentials"></a>Exponenciální matice
Exponenciální funkce lze definovat také pomocí [*exponenciálního*](https://en.wikipedia.org/wiki/Matrix_exponential) analogie matice.  Exponenciální exponent matice $A $ lze vyjádřit jako

$ $ e ^ A = \boldone + A + \frac{A ^ 2 } {2!} + \frac{A ^ 3 } {3!} + \cdots $ $

To je důležité kvůli tomu, že při vývoji v mechanickém čase je popsána jednotná matice formuláře $e $B matice ^ {iB } $ pro Hermitian $ .  Z tohoto důvodu je provádění exponenciálních exponenciálních výpočetních operací základní částí výpočetní funkce a jako takové Q # nabízí vnitřní rutiny pro popis těchto operací.
Existuje mnoho způsobů, jak na klasický počítač vypočítat exponenciální exponenciálu matrice, a obecně numericky přibližně fraught s Peril.  Viz [*Cleve Moler a Charles Van půjčka. "Devatenáct podezřelých způsoby výpočtu exponenciálního podílu matice." SIAM revize 20,4 (1978): 801-836*](https://doi.org/10.1137/S00361445024180) pro další informace o problémech, které se týkají.

Nejjednodušší způsob, jak porozumět tomu, jak vypočítat exponenciální část matice, je prostřednictvím eigenvalues a eigenvectors této matrice.  Konkrétně věta spektrálních popisů uvádí, že pro každou Hermitian nebo jednotnou matrici $A $ existuje jedna matice $U $ a Úhlopříčná matice $D $ taková $A = u ^ \dagger D U $ .  Z důvodu vlastností unitarity máme $A ^ 2 = U ^ \dagger D ^ 2 U $ a podobně jako u všech $p napájení $ $A ^ p = u ^ \dagger D ^ p u $ .  Pokud tuto část nasadíme do definice operátora exponenciálního operátoru, získáte:

$ $ e ^ A = U ^ \dagger \left (\boldone + D + \frac{D ^ 2 } {2!} + \cdots \right) U = u ^ \dagger \begin{ bmatrix } \exp (D_ {11 } ) & 0 & \cdots &0 \\\\ 0 & \exp (D_ {22 } ) & \cdots & 0 \\\\ \vdots & \vdots & \ddots & \vdots \\\\ 0&0 & \cdots & \exp (D_ {NN } ) \end{ bmatrix } U. $ $

Jinými slovy, pokud Transformujte na eigenbasis matice $A poté, co $ Výpočet matice vypočítá jako normální exponenciální eigenvalues matice.  Tolik operací v případě, že výpočetní výkon zahrnuje provádění exponenciálních exponenciálních výpočetních funkcí, je tento způsob transformace do eigenbasis matice, aby se zjednodušila i četnost exponenciálního zobrazení operátorů.

Další užitečnou vlastností je, že pokud $ je $B Jednotková i Hermitianá, tj. $B = b ^ {-1 } = b ^ \dagger, $ $B ^ 2 = \boldone $ . Když použijete toto pravidlo na výše uvedené rozšíření matice exponenciálního součtu a seskupením $ \boldone $ a $ podmínek $B společně, může se zobrazit jakákoli skutečná hodnota $x $ identity.

$ $e ^ {iBx } = \boldone \cos (x) + iB\sin (x) $ $


ryby. Tento zdvih je zvláště užitečný, protože umožňuje odůvodnění exponenciálních exponenciálních akcí, a to i v případě, že je dimenze $B $ exponenciálně velká, a to i v případě, že je $B $ jednotně i Hermitian.
