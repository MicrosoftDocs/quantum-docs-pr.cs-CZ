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
# <a name="vectors-and-matrices"></a><span data-ttu-id="a5464-103">Vektory a matice</span><span class="sxs-lookup"><span data-stu-id="a5464-103">Vectors and Matrices</span></span>

<span data-ttu-id="a5464-104">Pro pochopení výpočetního prostředí je nezbytné, aby byly v některých zkušenostech vektory a matrice.</span><span class="sxs-lookup"><span data-stu-id="a5464-104">Some familiarity with vectors and matrices is essential to understand quantum computing.</span></span> <span data-ttu-id="a5464-105">Poskytujeme stručný úvod do výše uvedeného článku a zúčastněné čtenáře se doporučuje přečíst standardní odkaz na lineární algebraický, jako je *Strang, G. (1993). Seznámení s lineárním algebraický (obj. 3). Wellesley, MA: Wellesley-Cambridge Press* nebo online odkaz, jako je [lineární algebraický](http://joshua.smcvt.edu/linearalgebra/).</span><span class="sxs-lookup"><span data-stu-id="a5464-105">We provide a brief introduction below and interested readers are recommended to read a standard reference on linear algebra such as *Strang, G. (1993). Introduction to linear algebra (Vol. 3). Wellesley, MA: Wellesley-Cambridge Press* or an online reference such as [Linear Algebra](http://joshua.smcvt.edu/linearalgebra/).</span></span>

<span data-ttu-id="a5464-106">Vektor sloupce (nebo jednoduše [*Vector*](https://en.wikipedia.org/wiki/Vector_(mathematics_and_physics))) $v $ dimenze (nebo velikosti) $n $ je kolekce $n $ složitých čísel $ (v_1, v_2, \ldots, v_n), uspořádaných jako sloupec:</span><span class="sxs-lookup"><span data-stu-id="a5464-106">A column vector (or simply [*vector*](https://en.wikipedia.org/wiki/Vector_(mathematics_and_physics))) $v$ of dimension (or size) $n$ is a collection of $n$ complex numbers $(v_1,v_2,\ldots,v_n)$ arranged as a column:</span></span>

<span data-ttu-id="a5464-107">$ $v = \begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="a5464-107">$$v =\begin{bmatrix}</span></span>
<span data-ttu-id="a5464-108">v_1\\\\</span><span class="sxs-lookup"><span data-stu-id="a5464-108">v_1\\\\</span></span>
<span data-ttu-id="a5464-109">v_2\\\\</span><span class="sxs-lookup"><span data-stu-id="a5464-109">v_2\\\\</span></span>
<span data-ttu-id="a5464-110">\vdots\\\\</span><span class="sxs-lookup"><span data-stu-id="a5464-110">\vdots\\\\</span></span>
<span data-ttu-id="a5464-111">v_n \end{bmatrix}$$</span><span class="sxs-lookup"><span data-stu-id="a5464-111">v_n \end{bmatrix}$$</span></span>

<span data-ttu-id="a5464-112">Norma vektorového $v $ je definována jako $ \sqrt { \sum \_ i | v \_ i | ^ 2 } $.</span><span class="sxs-lookup"><span data-stu-id="a5464-112">The norm of a vector $v$ is defined as $\sqrt{\sum\_i |v\_i|^2}$.</span></span> <span data-ttu-id="a5464-113">Vektor je označován jako Jednotková norma (nebo případně se nazývá [*vektor jednotky*](https://en.wikipedia.org/wiki/Unit_vector)), pokud je jeho norma $1 $ .</span><span class="sxs-lookup"><span data-stu-id="a5464-113">A vector is said to be of unit norm (or alternatively it is called a [*unit vector*](https://en.wikipedia.org/wiki/Unit_vector)) if its norm is $1$.</span></span> <span data-ttu-id="a5464-114">[*Sousední objekt $v vektoru*](https://en.wikipedia.org/wiki/Adjoint_matrix) $ je označen $v ^ \dagger $ a je definován jako následující vektor řádku, kde $ \* $ označuje komplexně sdružené,</span><span class="sxs-lookup"><span data-stu-id="a5464-114">The [*adjoint of a vector*](https://en.wikipedia.org/wiki/Adjoint_matrix) $v$ is denoted $v^\dagger$ and is defined to be the following row vector where $\*$ denotes the complex conjugate,</span></span>

<span data-ttu-id="a5464-115">$ $ \begin{ bmatrix } v_1 \\ \\ \vdots \\ \\ v_n \end{ bmatrix } ^ \dagger = \begin{ bmatrix } v_1 ^ \* & \cdots & v_n ^ \* \end{bmatrix}$$</span><span class="sxs-lookup"><span data-stu-id="a5464-115">$$\begin{bmatrix}v_1 \\\\ \vdots \\\\ v_n \end{bmatrix}^\dagger = \begin{bmatrix}v_1^\* & \cdots & v_n^\* \end{bmatrix}$$</span></span>

<span data-ttu-id="a5464-116">Nejběžnější způsob, jak vynásobit dva vektory dohromady, je [*vnitřní produkt*](https://en.wikipedia.org/wiki/Inner_product_space), označovaný také jako produkt s tečkou.</span><span class="sxs-lookup"><span data-stu-id="a5464-116">The most common way to multiply two vectors together is through the [*inner product*](https://en.wikipedia.org/wiki/Inner_product_space), also known as a dot product.</span></span>  <span data-ttu-id="a5464-117">Vnitřní produkt poskytuje projekci jednoho vektoru na jiný a je nevýznamný v popisu, jak vyjádřit jeden vektor jako součet dalších jednodušších vektorů.</span><span class="sxs-lookup"><span data-stu-id="a5464-117">The inner product gives the projection of one vector onto another and is invaluable in describing how to express one vector as a sum of other simpler vectors.</span></span>  <span data-ttu-id="a5464-118">Vnitřní produkt mezi $u $ a $v $ označený jako $ \left \langle u, v \right \rangle $ je definovaný jako</span><span class="sxs-lookup"><span data-stu-id="a5464-118">The inner product between $u$ and $v$, denoted $\left\langle u, v\right\rangle$ is defined as</span></span>

<span data-ttu-id="a5464-119">$ $ \langle u, v \rangle = u ^ \dagger v = u \_ 1 ^ { \* } v_1 + \cdots + u \_ n ^ { \* } v \_ n.</span><span class="sxs-lookup"><span data-stu-id="a5464-119">$$ \langle u, v\rangle = u^\dagger v=u\_1^{\*} v_1 + \cdots + u\_n^{\*} v\_n.</span></span>
$$

<span data-ttu-id="a5464-120">Tento zápis také umožňuje zapsat normu vektorového $v $ jako $ \sqrt { \langle v, v \rangle } $.</span><span class="sxs-lookup"><span data-stu-id="a5464-120">This notation also allows the norm of a vector $v$ to be written as $\sqrt{\langle v, v\rangle}$.</span></span>

<span data-ttu-id="a5464-121">Je možné vynásobit vektor číslem $c, aby bylo možné vytvořit $ Nový vektor, jehož záznamy jsou vynásobeny $c $ .</span><span class="sxs-lookup"><span data-stu-id="a5464-121">We can multiply a vector with a number $c$ to form a new vector whose entries are multiplied by $c$.</span></span> <span data-ttu-id="a5464-122">Můžeme také přidat dva vektory $u $ a $v $ k vytvoření nového vektoru, jehož položky jsou součtem položek $u $ a $v $ .</span><span class="sxs-lookup"><span data-stu-id="a5464-122">We can also add two vectors $u$ and $v$ to form a new vector whose entries are the sum of the entries of $u$ and $v$.</span></span> <span data-ttu-id="a5464-123">Následující operace jsou znázorněny níže:</span><span class="sxs-lookup"><span data-stu-id="a5464-123">These operations are depicted below:</span></span>

<span data-ttu-id="a5464-124">$ $ \mathrm{If } ~ u = \begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="a5464-124">$$\mathrm{If}~u =\begin{bmatrix}</span></span>
<span data-ttu-id="a5464-125">u_1\\\\</span><span class="sxs-lookup"><span data-stu-id="a5464-125">u_1\\\\</span></span>
<span data-ttu-id="a5464-126">u_2\\\\</span><span class="sxs-lookup"><span data-stu-id="a5464-126">u_2\\\\</span></span>
<span data-ttu-id="a5464-127">\vdots\\\\</span><span class="sxs-lookup"><span data-stu-id="a5464-127">\vdots\\\\</span></span>
<span data-ttu-id="a5464-128">u_n \end{ bmatrix } ~ \mathrm{and } ~ v = \begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="a5464-128">u_n \end{bmatrix}~\mathrm{and}~ v =\begin{bmatrix}</span></span>
    <span data-ttu-id="a5464-129">v_1\\\\</span><span class="sxs-lookup"><span data-stu-id="a5464-129">v_1\\\\</span></span>
    <span data-ttu-id="a5464-130">v_2\\\\</span><span class="sxs-lookup"><span data-stu-id="a5464-130">v_2\\\\</span></span>
    <span data-ttu-id="a5464-131">\vdots\\\\</span><span class="sxs-lookup"><span data-stu-id="a5464-131">\vdots\\\\</span></span>
    <span data-ttu-id="a5464-132">v_n \end{ bmatrix } , ~ \mathrm{then } ~ au + BV = \begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="a5464-132">v_n \end{bmatrix},~\mathrm{then}~ au+bv =\begin{bmatrix}</span></span>
<span data-ttu-id="a5464-133">au_1 + bv_1\\\\</span><span class="sxs-lookup"><span data-stu-id="a5464-133">au_1+bv_1\\\\</span></span>
<span data-ttu-id="a5464-134">au_2 + bv_2\\\\</span><span class="sxs-lookup"><span data-stu-id="a5464-134">au_2+bv_2\\\\</span></span>
<span data-ttu-id="a5464-135">\vdots\\\\</span><span class="sxs-lookup"><span data-stu-id="a5464-135">\vdots\\\\</span></span>
<span data-ttu-id="a5464-136">au_n + bv_n \end{ bmatrix } .</span><span class="sxs-lookup"><span data-stu-id="a5464-136">au_n+bv_n \end{bmatrix}.</span></span>
$$

<span data-ttu-id="a5464-137">[*Matice*](https://en.wikipedia.org/wiki/Matrix_(mathematics)) velikosti $m \times n $ je kolekce $MN $ komplexních čísel uspořádaných do $m $ řádků a $n $ sloupců, jak je znázorněno níže:</span><span class="sxs-lookup"><span data-stu-id="a5464-137">A [*matrix*](https://en.wikipedia.org/wiki/Matrix_(mathematics)) of size $m \times n$ is a collection of $mn$ complex numbers arranged in $m$ rows and $n$ columns as shown below:</span></span>

<span data-ttu-id="a5464-138">$ $M = \begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="a5464-138">$$M = \begin{bmatrix}</span></span>
<span data-ttu-id="a5464-139">M_ {11 } ~ ~ M_ {12 } ~ ~ \cdots ~ ~ M_ {1N } \\ \\ M_ {21 } ~ ~ M_ {22 } ~ ~ \cdots ~ ~ M_ {2N } \\ \\ \ddots\\\\</span><span class="sxs-lookup"><span data-stu-id="a5464-139">M_{11} ~~ M_{12} ~~ \cdots ~~ M_{1n}\\\\ M_{21} ~~ M_{22} ~~ \cdots ~~ M_{2n}\\\\ \ddots\\\\</span></span>
<span data-ttu-id="a5464-140">M_ {M1 } ~ ~ M_ {m2 } ~ ~ \cdots ~ ~ M_ {MN } \\ \\ \end{ bmatrix } . $ $</span><span class="sxs-lookup"><span data-stu-id="a5464-140">M_{m1} ~~ M_{m2} ~~ \cdots ~~ M_{mn}\\\\ \end{bmatrix}.$$</span></span>

<span data-ttu-id="a5464-141">Všimněte si, že vektor dimenze $n $ je pouze matice velikosti $n \times 1 $ .</span><span class="sxs-lookup"><span data-stu-id="a5464-141">Note that a vector of dimension $n$ is simply a matrix of size $n \times 1$.</span></span> <span data-ttu-id="a5464-142">Stejně jako u vektorů můžeme vynásobit matici s číslem $c $ k získání nové matice, kde je každá položka vynásobena $c $ a můžeme přidat dvě matrice stejné velikosti pro vytvoření nové matrice, jejíž položky jsou součtem odpovídajících položek dvou matric.</span><span class="sxs-lookup"><span data-stu-id="a5464-142">As with vectors, we can multiply a matrix with a number $c$ to obtain a new matrix where every entry is multiplied with $c$, and we can add two matrices of the same size to produce a new matrix whose entries are the sum of the respective entries of the two matrices.</span></span> 

## <a name="matrix-multiplication-and-tensor-products"></a><span data-ttu-id="a5464-143">Násobení a tensor součinů matic</span><span class="sxs-lookup"><span data-stu-id="a5464-143">Matrix Multiplication and Tensor Products</span></span>

<span data-ttu-id="a5464-144">Také je možné vynásobit dvě matrice $M $ dimenzí $m \times n $ a $N $ dimenze $n \times p $ k získání nové matrice $P $ dimenze $m \times p $ , jak je znázorněno níže:</span><span class="sxs-lookup"><span data-stu-id="a5464-144">We can also multiply two matrices $M$ of dimension $m\times n$ and $N$ of dimension $n \times p$ to get a new matrix $P$ of dimension $m \times p$ as follows:</span></span>

<span data-ttu-id="a5464-145">\begin{align}</span><span class="sxs-lookup"><span data-stu-id="a5464-145">\begin{align}</span></span>
<span data-ttu-id="a5464-146">& \begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="a5464-146">&\begin{bmatrix}</span></span>
    <span data-ttu-id="a5464-147">M_ {11 } ~ ~ M_ {12 } ~ ~ \cdots ~ ~ M_ {1N } \\ \\ M_ {21 } ~ ~ M_ {22 } ~ ~ \cdots ~ ~ M_ {2N } \\ \\ \ddots\\\\</span><span class="sxs-lookup"><span data-stu-id="a5464-147">M_{11} ~~ M_{12} ~~ \cdots ~~ M_{1n}\\\\ M_{21} ~~ M_{22} ~~ \cdots ~~ M_{2n}\\\\ \ddots\\\\</span></span>
    <span data-ttu-id="a5464-148">M_ {M1 } ~ ~ M_ {m2 } ~ ~ ~ \cdots ~ ~ M_ {MN}</span><span class="sxs-lookup"><span data-stu-id="a5464-148">M_{m1} ~~ M_{m2} ~~ \cdots ~~ M_{mn}</span></span>
<span data-ttu-id="a5464-149">účelubmatrix}</span><span class="sxs-lookup"><span data-stu-id="a5464-149">\end{bmatrix}</span></span>
<span data-ttu-id="a5464-150">ifunctiondiscoverybmatrix}</span><span class="sxs-lookup"><span data-stu-id="a5464-150">\begin{bmatrix}</span></span>
<span data-ttu-id="a5464-151">N_ {11 } ~ ~ N_ {12 } ~ ~ \cdots ~ ~ N_ N_ {\ddots } \\ \\ {21 } ~ ~ N_ {22 } ~ ~ \cdots ~ ~ N_ {2p } \\ \\\\\\</span><span class="sxs-lookup"><span data-stu-id="a5464-151">N_{11} ~~ N_{12} ~~ \cdots ~~ N_{1p}\\\\ N_{21} ~~ N_{22} ~~ \cdots ~~ N_{2p}\\\\ \ddots\\\\</span></span>
<span data-ttu-id="a5464-152">N_ {N1 } ~ ~ N_ {N2 } ~ ~ \cdots ~ ~ N_ {NP}</span><span class="sxs-lookup"><span data-stu-id="a5464-152">N_{n1} ~~ N_{n2} ~~ \cdots ~~ N_{np}</span></span>
<span data-ttu-id="a5464-153">\end{ bmatrix } = \begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="a5464-153">\end{bmatrix}=\begin{bmatrix}</span></span>
<span data-ttu-id="a5464-154">P_ {11 } ~ ~ P_ {12 } ~ ~ \cdots ~ ~ P_ P_ {\ddots } \\ \\ {21 } ~ ~ P_ {22 } ~ ~ \cdots ~ ~ P_ {2p } \\ \\\\\\</span><span class="sxs-lookup"><span data-stu-id="a5464-154">P_{11} ~~ P_{12} ~~ \cdots ~~ P_{1p}\\\\ P_{21} ~~ P_{22} ~~ \cdots ~~ P_{2p}\\\\ \ddots\\\\</span></span>
<span data-ttu-id="a5464-155">P_ {M1 } ~ ~ P_ {m2 } ~ ~ ~ \cdots ~ ~ P_ {MP}</span><span class="sxs-lookup"><span data-stu-id="a5464-155">P_{m1} ~~ P_{m2} ~~ \cdots ~~ P_{mp}</span></span>
<span data-ttu-id="a5464-156">účelubmatrix}</span><span class="sxs-lookup"><span data-stu-id="a5464-156">\end{bmatrix}</span></span>
<span data-ttu-id="a5464-157">\end{align}</span><span class="sxs-lookup"><span data-stu-id="a5464-157">\end{align}</span></span>

<span data-ttu-id="a5464-158">kde jsou položky $P $ $P _ {IK } = \ sum_j M_ {ij} N_ {JK } $.</span><span class="sxs-lookup"><span data-stu-id="a5464-158">where the entries of $P$ are $P_{ik} = \sum_j M_{ij}N_{jk}$.</span></span> <span data-ttu-id="a5464-159">Například položka $P _ {11 } $ je vnitřní produkt prvního řádku $M $ s prvním sloupcem $N $ .</span><span class="sxs-lookup"><span data-stu-id="a5464-159">For example, the entry $P_{11}$ is the inner product of the first row of $M$ with the first column of $N$.</span></span> <span data-ttu-id="a5464-160">Vzhledem k tomu, že vektor je jednoduše speciálním případem matice, tato definice rozšiřuje na násobení vektoru matice.</span><span class="sxs-lookup"><span data-stu-id="a5464-160">Note that since a vector is simply a special case of a matrix, this definition extends to matrix-vector multiplication.</span></span> 

<span data-ttu-id="a5464-161">Všechny matrice, které považujeme, budou buď čtvercové, kde je počet řádků a sloupců stejný, nebo vektory, které odpovídají pouze $1 $ sloupci.</span><span class="sxs-lookup"><span data-stu-id="a5464-161">All the matrices we consider will either be square matrices, where the number of rows and columns are equal, or vectors, which corresponds to only $1$ column.</span></span> <span data-ttu-id="a5464-162">Jednou z speciálních čtvercových matric je [*matice identity*](https://en.wikipedia.org/wiki/Identity_matrix)s označením $ \boldone $ , která má všechny jeho diagonální prvky rovny $1 $ a zbývající prvky se rovnají $0 $ :</span><span class="sxs-lookup"><span data-stu-id="a5464-162">One special square matrix is the [*identity matrix*](https://en.wikipedia.org/wiki/Identity_matrix), denoted $\boldone$, which has all its diagonal elements equal to $1$ and the remaining elements equal to $0$:</span></span>

<span data-ttu-id="a5464-163">$ $ \boldone = \begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="a5464-163">$$\boldone=\begin{bmatrix}</span></span>
<span data-ttu-id="a5464-164">1 ~ ~ 0 ~ ~ \cdots ~ ~ 0\\\\</span><span class="sxs-lookup"><span data-stu-id="a5464-164">1 ~~ 0 ~~ \cdots ~~ 0\\\\</span></span>
<span data-ttu-id="a5464-165">0 ~ ~ 1 ~ ~ \cdots ~ ~ 0\\\\</span><span class="sxs-lookup"><span data-stu-id="a5464-165">0 ~~ 1 ~~ \cdots ~~ 0\\\\</span></span>
<span data-ttu-id="a5464-166">~ ~ \ddots\\\\</span><span class="sxs-lookup"><span data-stu-id="a5464-166">~~ \ddots\\\\</span></span>
<span data-ttu-id="a5464-167">0 ~ ~ 0 ~ ~ \cdots ~ ~ 1 \end{ bmatrix } . $ $</span><span class="sxs-lookup"><span data-stu-id="a5464-167">0 ~~ 0 ~~ \cdots ~~ 1 \end{bmatrix}.$$</span></span>

<span data-ttu-id="a5464-168">U čtvercové matrice $A $ říkáme, že $B matice $ je [*inverzní*](https://en.wikipedia.org/wiki/Invertible_matrix) , pokud $AB = ba = \boldone $ .</span><span class="sxs-lookup"><span data-stu-id="a5464-168">For a square matrix $A$, we say a matrix $B$ is its [*inverse*](https://en.wikipedia.org/wiki/Invertible_matrix) if $AB = BA = \boldone$.</span></span> <span data-ttu-id="a5464-169">Inverzní matice nemusí existovat, ale pokud existuje, je jedinečná a $A ^ {-1 } $.</span><span class="sxs-lookup"><span data-stu-id="a5464-169">The inverse of a matrix need not exist, but when it exists it is unique and we denote it $A^{-1}$.</span></span> 

<span data-ttu-id="a5464-170">V případě $M matrice jsou $ sousední nebo sdružená $M $ matice maticí $N $ tak, že $N _ {IJ } = M_ {ji } ^ \* $.</span><span class="sxs-lookup"><span data-stu-id="a5464-170">For any matrix $M$, the adjoint or conjugate transpose of $M$ is a matrix $N$ such that $N_{ij} = M_{ji}^\*$.</span></span> <span data-ttu-id="a5464-171">Sousední $M $ je obvykle označena $M ^ \dagger $ .</span><span class="sxs-lookup"><span data-stu-id="a5464-171">The adjoint of $M$ is usually denoted $M^\dagger$.</span></span> <span data-ttu-id="a5464-172">Řekněme, že $U matice $ je [*jednotná*](https://en.wikipedia.org/wiki/Unitary_matrix) , pokud $uu ^ \dagger = U ^ \dagger U = \boldone $ nebo ekvivalentní, $U ^ {-1 } = U ^ \dagger $ .</span><span class="sxs-lookup"><span data-stu-id="a5464-172">We say a matrix $U$ is [*unitary*](https://en.wikipedia.org/wiki/Unitary_matrix) if $UU^\dagger = U^\dagger U = \boldone$ or equivalently, $U^{-1} = U^\dagger$.</span></span>  <span data-ttu-id="a5464-173">Například nejdůležitější vlastnost maticových matric je, že zachovávají normu vektoru.</span><span class="sxs-lookup"><span data-stu-id="a5464-173">Perhaps the most important property of unitary matrices is that they preserve the norm of a vector.</span></span>  <span data-ttu-id="a5464-174">K tomu dochází, protože</span><span class="sxs-lookup"><span data-stu-id="a5464-174">This happens because</span></span> 

<span data-ttu-id="a5464-175">$ $ \langle v, v \rangle = v ^ \dagger v = v ^ \dagger U ^ {-1 } u v = v ^ \Dagger u ^ \Dagger u = \Langle u v, U \rangle . $ $</span><span class="sxs-lookup"><span data-stu-id="a5464-175">$$\langle v,v \rangle=v^\dagger v = v^\dagger U^{-1} U v = v^\dagger U^\dagger U v = \langle U v, U v\rangle.$$</span></span>  

<span data-ttu-id="a5464-176">$M matice $ se označuje jako [*Hermitian*](https://en.wikipedia.org/wiki/Hermitian_matrix) , pokud $M = M ^ \dagger $ .</span><span class="sxs-lookup"><span data-stu-id="a5464-176">A matrix $M$ is said to be [*Hermitian*](https://en.wikipedia.org/wiki/Hermitian_matrix) if $M=M^\dagger$.</span></span>

<span data-ttu-id="a5464-177">Nakonec [*produkt tensor*](https://en.wikipedia.org/wiki/Tensor_product) (nebo Kronecker produkt) dvou matic $M $ velikosti $m \times n $ a $N $ velikosti $p \times q $ je větší matrice $P = M \otimes n $ velikosti $MP \times NQ $ a je získána z $M $ a $N následujícím $ způsobem:</span><span class="sxs-lookup"><span data-stu-id="a5464-177">Finally, the [*tensor product*](https://en.wikipedia.org/wiki/Tensor_product) (or Kronecker product) of two matrices $M$ of size $m\times n$ and $N$ of size $p \times q$ is a larger matrix $P=M\otimes N$ of size $mp \times nq$, and is obtained from $M$ and $N$ as follows:</span></span>

<span data-ttu-id="a5464-178">\begin{align}</span><span class="sxs-lookup"><span data-stu-id="a5464-178">\begin{align}</span></span>
    <span data-ttu-id="a5464-179">M \otimes N &= \begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="a5464-179">M \otimes N &= \begin{bmatrix}</span></span>
        <span data-ttu-id="a5464-180">M_ {11 } ~ ~ \cdots ~ ~ M_ {1N } \\ \\ \ddots\\\\</span><span class="sxs-lookup"><span data-stu-id="a5464-180">M_{11} ~~ \cdots ~~ M_{1n} \\\\ \ddots\\\\</span></span>
        <span data-ttu-id="a5464-181">M_ {M1 } ~ ~ \cdots ~ ~ M_ {MN}</span><span class="sxs-lookup"><span data-stu-id="a5464-181">M_{m1}  ~~ \cdots ~~ M_{mn}</span></span>
    <span data-ttu-id="a5464-182">účelubmatrix}</span><span class="sxs-lookup"><span data-stu-id="a5464-182">\end{bmatrix}</span></span>
    <span data-ttu-id="a5464-183">\otimes \begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="a5464-183">\otimes \begin{bmatrix}</span></span>
        <span data-ttu-id="a5464-184">N_ {11 } ~ ~ \cdots ~ ~ N_ {1Q } \\ \\ \ddots\\\\</span><span class="sxs-lookup"><span data-stu-id="a5464-184">N_{11}  ~~ \cdots ~~ N_{1q}\\\\ \ddots\\\\</span></span>
        <span data-ttu-id="a5464-185">N_ {P1 } ~ ~ \cdots ~ ~ N_ {pq}</span><span class="sxs-lookup"><span data-stu-id="a5464-185">N_{p1} ~~ \cdots ~~ N_{pq}</span></span>
    <span data-ttu-id="a5464-186">\end{ bmatrix } \\ \\ &= \begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="a5464-186">\end{bmatrix}\\\\ &= \begin{bmatrix}</span></span>
        <span data-ttu-id="a5464-187">M_ {11 } \begin{ bmatrix } N_ {11 } ~ ~ \cdots ~ ~ N_ {1Q } \\ \\ \ddots \\\\ N_ {P1 } ~ ~ \cdots ~ ~ N_ {pq } \end{ bmatrix } ~ ~ \cdots ~ ~ M_ {1N } \begin{ bmatrix } N_ {11 } ~ ~ \cdots ~ ~ N_ {1Q } \\ \\ \ddots \\\\ N_ {P1 } ~ ~ \cdots ~ ~ N_ {pq } \end{ bmatrix } \\ \\ \ddots\\\\</span><span class="sxs-lookup"><span data-stu-id="a5464-187">M_{11} \begin{bmatrix} N_{11}  ~~ \cdots ~~ N_{1q}\\\\ \ddots\\\\ N_{p1} ~~ \cdots ~~ N_{pq} \end{bmatrix}~~ \cdots ~~ M_{1n} \begin{bmatrix} N_{11}  ~~ \cdots ~~ N_{1q}\\\\ \ddots\\\\ N_{p1} ~~ \cdots ~~ N_{pq} \end{bmatrix}\\\\ \ddots\\\\</span></span>
        <span data-ttu-id="a5464-188">M_ {M1 } \begin{ bmatrix } N_ {11 } ~ ~ \cdots ~ ~ N_ {1Q } \\ \\ \ddots \\\\ N_ {P1 } ~ ~ \cdots ~ ~ N_ {pq } \end{ bmatrix } ~ ~ \cdots ~ ~ M_ {MN } \begin{ bmatrix } N_ {11 } ~ ~ \cdots ~ ~ N_ {1Q } \\ \\ \ddots \\\\ N_ {P1 } ~ ~ \cdots ~ ~ N_ {pq } \end{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="a5464-188">M_{m1} \begin{bmatrix} N_{11}  ~~ \cdots ~~ N_{1q}\\\\ \ddots\\\\ N_{p1} ~~ \cdots ~~ N_{pq} \end{bmatrix}~~ \cdots ~~ M_{mn} \begin{bmatrix} N_{11}  ~~ \cdots ~~ N_{1q}\\\\ \ddots\\\\ N_{p1} ~~ \cdots ~~ N_{pq} \end{bmatrix}</span></span>
    <span data-ttu-id="a5464-189">\end{ bmatrix } .</span><span class="sxs-lookup"><span data-stu-id="a5464-189">\end{bmatrix}.</span></span>
<span data-ttu-id="a5464-190">\end{align}</span><span class="sxs-lookup"><span data-stu-id="a5464-190">\end{align}</span></span>

<span data-ttu-id="a5464-191">To je vhodnější v některých příkladech:</span><span class="sxs-lookup"><span data-stu-id="a5464-191">This is better demonstrated with some examples:</span></span>

<span data-ttu-id="a5464-192">$ $ \begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="a5464-192">$$ \begin{bmatrix}</span></span>
        <span data-ttu-id="a5464-193">a \\ \\ b \end{ bmatrix } \otimes \begin{ bmatrix } c \\ \\ d \\ \\ e \end{ bmatrix } = \begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="a5464-193">a \\\\ b  \end{bmatrix} \otimes \begin{bmatrix} c \\\\ d \\\\ e \end{bmatrix} = \begin{bmatrix}</span></span>
        <span data-ttu-id="a5464-194">\begin{ bmatrix } c \\ \\ d \\ \\ e \end{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="a5464-194">a \begin{bmatrix} c \\\\ d \\\\ e \end{bmatrix}</span></span>
        <span data-ttu-id="a5464-195">\\\\[1,5 EM] b \begin{ bmatrix } c \\ \\ d \\ \\ e\end{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="a5464-195">\\\\[1.5em] b \begin{bmatrix} c \\\\ d \\\\ e\end{bmatrix}</span></span>
    <span data-ttu-id="a5464-196">účelubmatrix}</span><span class="sxs-lookup"><span data-stu-id="a5464-196">\end{bmatrix}</span></span>
    <span data-ttu-id="a5464-197">= \begin{ bmatrix } a c \\ \\ a d \\ \\ a e \\ \\ b c \\ \\ b d \\ \\\end{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="a5464-197">= \begin{bmatrix} a c \\\\ a d \\\\ a e \\\\ b c \\\\ b d \\\\ be\end{bmatrix}</span></span>
$$

<span data-ttu-id="a5464-198">a</span><span class="sxs-lookup"><span data-stu-id="a5464-198">and</span></span>

<span data-ttu-id="a5464-199">$ $ \begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="a5464-199">$$ \begin{bmatrix}</span></span>
        <span data-ttu-id="a5464-200">a \ b \\ \\ c \ d \end{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="a5464-200">a\ b \\\\ c\ d \end{bmatrix}</span></span>
    <span data-ttu-id="a5464-201">\otimes \begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="a5464-201">\otimes \begin{bmatrix}</span></span>
        <span data-ttu-id="a5464-202">e \ f \\ \\ g \ h \end{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="a5464-202">e\ f\\\\g\ h \end{bmatrix}</span></span>
     <span data-ttu-id="a5464-203">= \begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="a5464-203">= \begin{bmatrix}</span></span>
    <span data-ttu-id="a5464-204">určitého\begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="a5464-204">a\begin{bmatrix}</span></span>
    <span data-ttu-id="a5464-205">e \ f \\\\ g \ h \end{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="a5464-205">e\ f\\\\ g\ h \end{bmatrix}</span></span>
    <span data-ttu-id="a5464-206">b\begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="a5464-206">b\begin{bmatrix}</span></span>
    <span data-ttu-id="a5464-207">e \ f \\\\ g \ h \end{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="a5464-207">e\ f\\\\ g\ h \end{bmatrix}</span></span>
    <span data-ttu-id="a5464-208">\\\\[1em] c\begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="a5464-208">\\\\[1em] c\begin{bmatrix}</span></span>
    <span data-ttu-id="a5464-209">e \ f \\\\ g \ h \end{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="a5464-209">e\ f\\\\ g\ h \end{bmatrix}</span></span>
    <span data-ttu-id="a5464-210">trojrozměrné\begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="a5464-210">d\begin{bmatrix}</span></span>
    <span data-ttu-id="a5464-211">e \ f \\\\ g \ h \end{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="a5464-211">e\ f\\\\ g\ h \end{bmatrix}</span></span>
    <span data-ttu-id="a5464-212">účelubmatrix}</span><span class="sxs-lookup"><span data-stu-id="a5464-212">\end{bmatrix}</span></span>
    <span data-ttu-id="a5464-213">= \begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="a5464-213">= \begin{bmatrix}</span></span>
    <span data-ttu-id="a5464-214">AE \ AF \ je \ BF \\ \\ AG \ Ah \ BG \ BH \\ \\ CE \ CF \ de \ DF \ \\ \\ \ ch \ DG \ DH \end{ bmatrix } .</span><span class="sxs-lookup"><span data-stu-id="a5464-214">ae\ af\ be\ bf \\\\ ag\ ah\ bg\ bh \\\\ ce\ cf\ de\ df \\\\ cg\ ch\ dg\ dh \end{bmatrix}.</span></span>
$$

<span data-ttu-id="a5464-215">Konečná užitečná konvence zápisu okolních produktů tensor je to, že pro všechny vektorové $v $ nebo matrice $M $ $v ^ {\otimes n } $ nebo $M ^ {\otimes n } $ je krátká ruka pro $n $ opakovaný tensor produkt.</span><span class="sxs-lookup"><span data-stu-id="a5464-215">A final useful notational convention surrounding tensor products is that, for any vector $v$ or matrix $M$, $v^{\otimes n}$ or $M^{\otimes n}$ is short hand for an $n$-fold repeated tensor product.</span></span>  <span data-ttu-id="a5464-216">Příklad:</span><span class="sxs-lookup"><span data-stu-id="a5464-216">For example:</span></span>

<span data-ttu-id="a5464-217">\begin{align}</span><span class="sxs-lookup"><span data-stu-id="a5464-217">\begin{align}</span></span>
<span data-ttu-id="a5464-218">& \begin{ bmatrix } 1 \\ \\ 0 \end{ bmatrix } ^ {\otimes 1 } = \begin{ bmatrix } 1 \\ \\ 0 \end{ bmatrix } , \qquad \begin{bmatrix} 1 \\ \\ 0 \end{ bmatrix } ^ {\otimes 2 } = \begin{ bmatrix } 1 \\ \\ 0 \\ \\ 0 \\ \\ 0 \end{ bmatrix } , \qquad \begin{bmatrix} 1 \\ \\ -1 \end{ bmatrix } ^ {\otimes 2 } = \begin{ bmatrix } 1 \\ \\ -1 \\ \\ -1 \\ \\ 1 \end{ bmatrix } , \\ \\ & \begin{ bmatrix } 0 & 1 \\ \\ 1 & 0 \end{ bmatrix } ^ {\otimes 1 } = \begin{ bmatrix } 0 & 1 \\ \\ 1 & 0 \end{ bmatrix } , \qquad \begin{bmatrix} 0 & 1 \\ \\ 1 & 0 \end{ bmatrix } ^ {\otimes 2 } = \begin{ bmatrix } 0 &0&0&1 \\ \\ 0 &0&1&0 \\ \\ 0 &1&0&0 \\\\ 1 &0&0&0 \end{bmatrix} .</span><span class="sxs-lookup"><span data-stu-id="a5464-218">&\begin{bmatrix} 1 \\\\ 0 \end{bmatrix}^{\otimes 1} = \begin{bmatrix} 1 \\\\ 0 \end{bmatrix}, \qquad\begin{bmatrix} 1 \\\\ 0 \end{bmatrix}^{\otimes 2} = \begin{bmatrix} 1 \\\\ 0 \\\\0 \\\\0 \end{bmatrix}, \qquad\begin{bmatrix} 1 \\\\ -1 \end{bmatrix}^{\otimes 2} = \begin{bmatrix} 1 \\\\ -1 \\\\-1 \\\\1 \end{bmatrix}, \\\\ &\begin{bmatrix}  0 & 1 \\\\ 1& 0   \end{bmatrix}^{\otimes 1}= \begin{bmatrix}    0& 1 \\\\ 1& 0  \end{bmatrix},  \qquad\begin{bmatrix} 0 & 1 \\\\ 1& 0   \end{bmatrix}^{\otimes 2}= \begin{bmatrix} 0 &0&0&1 \\\\ 0 &0&1&0 \\\\ 0 &1&0&0\\\\ 1 &0&0&0\end{bmatrix}.</span></span>
<span data-ttu-id="a5464-219">\end{align}</span><span class="sxs-lookup"><span data-stu-id="a5464-219">\end{align}</span></span>
