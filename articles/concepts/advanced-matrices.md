---
title: Pokročilé koncepty matice
description: Přečtěte si o exponenciálních eigenvectors, eigenvalues a matricích, které se používají k popisu a simulaci algoritmů pro plnění.
author: QuantumWriter
uid: microsoft.quantum.concepts.matrix-advanced
ms.author: nawiebe@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: a83911e01ad758bbcb7f701000fd58b4f1c91cd2
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/28/2020
ms.locfileid: "77907575"
---
# <a name="advanced-matrix-concepts"></a>Pokročilé koncepty matrice #

Teď rozšíříme své manipulace s matricemi na [*eigenvalues, eigenvectors*](https://en.wikipedia.org/wiki/Eigenvalues_and_eigenvectors) a [*exponenciální*](https://en.wikipedia.org/wiki/Matrix_exponential) , které tvoří základní sadu nástrojů, které potřebujeme k popisu a implementaci algoritmů.

## <a name="eigenvalues-and-eigenvectors"></a>Eigenvalues a eigenvectors ##

Nechejte $M $ být čtvercovou maticí a $v $ je vektor, který není vektorem všechny nuly (tj. vektor se všemi položkami rovnající se $0 $).

Řekněme, že $v $ je [*eigenvector*](https://en.wikipedia.org/wiki/Eigenvalues_and_eigenvectors) $M $ if $MV = CV $ pro některé číslo $c $. Řekněme, že $c $ je [*eigenvalue*](https://en.wikipedia.org/wiki/Eigenvalues_and_eigenvectors) , které odpovídá $v eigenvector $. V obecné matrici $M $ může transformovat vektor na jakýkoliv jiný vektor, ale eigenvector je speciální, protože je ponechán beze změny, s výjimkou vynásobeného číslem. Všimněte si, že pokud $v $ je eigenvector s eigenvalue $c $, pak $av $ je také eigenvectorou (pro nenulové $a $) se stejným eigenvalue.

Například pro matici identita každý vektor $v $ je eigenvector s eigenvalue $1 $.

Jako další příklad zvažte [*diagonální matici*](https://en.wikipedia.org/wiki/Diagonal_matrix) $D $, která má pouze nenulové položky na diagonále:

$ $ \begin{bmatrix} d_1 & 0 & 0 \\\\ 0 & d_2 & 0 \\\\ 0 & 0 & d_3 \end{bmatrix}.
$$

Vektory

$ $ \begin{bmatrix}1 \\\\ 0 \\\\ 0 \end{bmatrix}, \begin{bmatrix}0 \\\\ 1 \\\\ 0 \ end {bmatrix} a \begin{bmatrix}0 \\\\ 0 \\\\ 1 \ end {bmatrix} $ $

eigenvectors z této matice s eigenvalues $d _1 $, $d _2 $ a $d _3 $, v uvedeném pořadí. Pokud $d _1 $, $d _2 $, a $d _3 $ jsou odlišná čísla, pak jsou tyto vektory (a jejich násobky) jediným eigenvectors matice $D $. Obecně platí, že pro diagonální matrici je snadné číst z eigenvalues a eigenvectors. Eigenvalues jsou všechna čísla zobrazená na diagonále a jejich příslušné eigenvectors jsou vektory jednotek s jednou položkou rovnající se $1 $ a zbývající položky rovnající se $0 $.

V příkladu výše si všimněte, že eigenvectors $D $ Form je základem pro $3 $ multidimenzionální vektory. Základem je sada vektorů, což znamená, že každý vektor lze zapsat jako lineární kombinaci. $V _1 $, $v _2 $ a $v _3 $ formu, pokud je jakýkoli vektorový $v $ možné zapsat jako $v = a_1 v_1 + a_2 v_2 + a_3 v_3 $ pro některá čísla $a _1 $, $a _2 $ a $a _3 $.

Odvolání, že matice Hermitian (označovaná také jako samostatně sousedící) je složitá čtvercová matice, která se rovná svému vlastnímu komplexu, zatímco Jednotková matice je složitá čtvercová matice, jejíž invertování je rovno složitosti.
V případě Hermitian a maticových matric, které jsou v podstatě pouze v případě, že se jedná o výpočetní výkon, je obecný výsledek známý jako [*spektrální věta*](https://en.wikipedia.org/wiki/Spectral_theorem), který vyhodnotí následující: pro každou Hermitian nebo jednotkovou matrici $M $ existuje jednotková $U $, kterou $M = U ^ \Dagger D u $ pro některé úhlopříčné matrice $D $. Kromě toho budou položky diagonálního $D $ eigenvalues $M $.

Už víte, jak vypočítat eigenvalues a eigenvectors úhlopříčné matrice $D $. Pomocí tohoto větau víme, že pokud je $v $ eigenvector $D $ with eigenvalue $c $, tj. $Dv = CV $, pak $U ^ \dagger v $ bude eigenvector $M $ s eigenvalue $c $. Důvodem je to, že

$ $M (U ^ \dagger v) = U ^ \dagger D U (U ^ \dagger v) = U ^ \dagger D (U U ^ \dagger) v = U ^ \dagger D v = c U ^ \dagger v. $ $

## <a name="matrix-exponentials"></a>Exponenciální matice
Exponenciální funkce lze definovat také pomocí [*exponenciálního*](https://en.wikipedia.org/wiki/Matrix_exponential) analogie matice.  Maticový exponenciální matrice $A $ může být vyjádřen jako

$ $ e ^ A = \boldone + A + \frac{A ^ 2} {2!} + \frac{A ^ 3} {3!} + \cdots $ $

To je důležité kvůli tomu, že při vývoji v mechanickém čase je popsána jednotná matice formuláře $e ^ {iB} $ for Hermitian Matrix $B $.  Z tohoto důvodu je provádění exponenciálních exponenciálních výpočetních operací základní částí výpočetní funkce a jako takové Q # nabízí vnitřní rutiny pro popis těchto operací.
Existuje mnoho způsobů, jak na klasický počítač vypočítat exponenciální exponenciálu matrice, a obecně numericky přibližně fraught s Peril.  Viz [*Cleve Moler a Charles Van půjčka. "Devatenáct podezřelých způsoby výpočtu exponenciálního podílu matice." SIAM revize 20,4 (1978): 801-836*](https://doi.org/10.1137/S00361445024180) pro další informace o problémech, které se týkají.

Nejjednodušší způsob, jak porozumět tomu, jak vypočítat exponenciální část matice, je prostřednictvím eigenvalues a eigenvectors této matrice.  Konkrétně věta spektrální popis uvádí, že pro každou Hermitian nebo jednotnou matrici $A $ existuje jednotná matice $U $ a Úhlopříčná matice $D $, což $A = U ^ \dagger D U $.  Vzhledem k vlastnostem unitarity máme $A ^ 2 = U ^ \dagger D ^ 2 U $ a podobně jako u všech Power $p $ $A ^ p = U ^ \dagger D ^ p U $.  Pokud tuto část nasadíme do definice operátora exponenciálního operátoru, získáte:

$ $ e ^ A = U ^ \dagger \left (\boldone + D + \frac{D ^ 2} {2!} + \cdots \right) U = U ^ \dagger \begin{bmatrix}\exp (D_{11}) & 0 & \cdots & 0\\\\ 0 & \exp (D_{22}) & \cdots & 0\\\\ \vdots & \vdots & \ddots & \vdots\\\\ 0 & 0 & \cdots & \exp (D_ {NN}) \end{bmatrix} U. $ $

Jinými slovy, pokud Transformujte na eigenbasis matice $A $ poté, co výpočet matice vypočítá jako normální exponenciální eigenvalues matice.  Tolik operací s výpočetními procesory zahrnuje provádění exponenciálních exponenciálních výpočetních matric. Tento způsob transformace do eigenbasis matice zjednodušuje, že exponenciální zobrazení operátoru je často a je základem pro mnoho algoritmů, jako je například Trotter – metody simulace neSuzukich procesorů, které jsou popsány dále v tomto průvodci.

Další užitečnou vlastností je, že pokud je $B $ jak Jednotková, tak Hermitian, tj. $B = B ^{-1}= B ^ \dagger $, $B ^ 2 = \boldone $. Když použijete toto pravidlo na výše uvedené rozšíření matice exponenciálního součtu a seskupením $ \boldone $ a $B $ terms, může se vám zobrazit jakákoli skutečná hodnota $x $ identity.

$ $e ^ {iBx} = \boldone \cos (x) + iB\sin (x) $ $


ryby. Tento zdvih je zvlášť užitečný, protože umožňuje odůvodnění exponenciálních exponentů matic, a to i v případě, že dimenze $B $ je exponenciálně velká, a to i v případě, že $B $ je jak Hermitian, tak pro zvláštní případ.
