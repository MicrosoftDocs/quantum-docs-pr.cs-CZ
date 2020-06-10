---
title: Pauli měření
description: Naučte se pracovat s operacemi měření jednoduchých a qubit Pauli.
author: QuantumWriter
uid: microsoft.quantum.concepts.pauli
ms.author: nawiebe@microsoft.com
ms.date: 12/11/2017
ms.topic: article
no-loc:
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
ms.openlocfilehash: 115c1703e433f24930e4be61b545048c95da28d1
ms.sourcegitcommit: e23178d32b316d05784a02ba3cd6166dad177e89
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/09/2020
ms.locfileid: "84630302"
---
# <a name="pauli-measurements"></a><span data-ttu-id="8b0ce-103">Pauli měření</span><span class="sxs-lookup"><span data-stu-id="8b0ce-103">Pauli Measurements</span></span>

<span data-ttu-id="8b0ce-104">V předchozích diskusích jsme se zaměřili na výpočetní základní měření.</span><span class="sxs-lookup"><span data-stu-id="8b0ce-104">In the previous discussions, we have focused on computational basis measurements.</span></span>
<span data-ttu-id="8b0ce-105">Ve skutečnosti existují další běžná měření, ke kterým dochází v množství náročném na výpočetní výkon, který je ze zapsaných perspektiv pohodlný, aby se vyjádřily na základě výpočetních měření.</span><span class="sxs-lookup"><span data-stu-id="8b0ce-105">In fact, there are other common measurements that occur in quantum computing that, from a notational perspective, are convenient to express in terms of computational basis measurements.</span></span>
<span data-ttu-id="8b0ce-106">Při práci s Q # se nejběžnější druh měření, na který budete spouštět, pravděpodobně *Pauli měřením*, která generalizace výpočetního základu zahrnuje měření v jiných základech, a parity mezi různými qubits.</span><span class="sxs-lookup"><span data-stu-id="8b0ce-106">As you work with Q#, the most common kind of measurements that you'll run into will likely be *Pauli measurements*, which generalize computational basis measurements to include measurements in other bases, and of parity between different qubits.</span></span>
<span data-ttu-id="8b0ce-107">V takových případech je běžné projednávat měření Pauli operátoru, a to obecně operátor, jako je $X, Y, Z $ nebo $Z \otimes Z, x \otimes X, x \otimes Y $ a tak dále.</span><span class="sxs-lookup"><span data-stu-id="8b0ce-107">In such cases, it is common to discuss measuring a Pauli operator, in general an operator such as $X,Y,Z$ or $Z\otimes Z, X\otimes X, X\otimes Y$, and so forth.</span></span>

> [!TIP]
> <span data-ttu-id="8b0ce-108">V Q # jsou operátory qubit Pauli obvykle zastoupeny poli typu `Pauli[]` .</span><span class="sxs-lookup"><span data-stu-id="8b0ce-108">In Q#, multi-qubit Pauli operators are generally represented by arrays of type `Pauli[]`.</span></span>
> <span data-ttu-id="8b0ce-109">Například pro reprezentaci $X \otimes Z \otimes Y $ lze použít pole `[PauliX, PauliZ, PauliY]` .</span><span class="sxs-lookup"><span data-stu-id="8b0ce-109">For example, to represent $X \otimes Z \otimes Y$, you can use the array `[PauliX, PauliZ, PauliY]`.</span></span>

<span data-ttu-id="8b0ce-110">Projednávání měření v rámci Pauli operátorů je zvlášť běžné v podpoli s opravou chyb pro každé z nich.</span><span class="sxs-lookup"><span data-stu-id="8b0ce-110">Discussing measurement in terms of Pauli operators is especially common in the subfield of quantum error correction.</span></span>
<span data-ttu-id="8b0ce-111">V Q # sledujeme podobnou konvenci. nyní vysvětlujeme toto alternativní zobrazení měření.</span><span class="sxs-lookup"><span data-stu-id="8b0ce-111">In Q#, we follow a similar convention; we now explain this alternative view of measurements.</span></span>

<span data-ttu-id="8b0ce-112">Než se pustíte do detailů o tom, jak si představit Pauli měření, je vhodné se seznámit s tím, jak měření jedné qubit v rámci počítače ve státě</span><span class="sxs-lookup"><span data-stu-id="8b0ce-112">Before delving into the details of how to think of a Pauli measurement, it is useful to think about what measuring a single qubit inside a quantum computer does to the quantum state.</span></span>
<span data-ttu-id="8b0ce-113">Představte si, že máme $n $ qubit, a pak si jednou z nich odqubit pravidla $ , která můžou být ve stavu.</span><span class="sxs-lookup"><span data-stu-id="8b0ce-113">Imagine that we have an $n$-qubit quantum state; then measuring one qubit immediately rules out half of the $2^n$ possibilities that state could be in.</span></span>
<span data-ttu-id="8b0ce-114">Jinými slovy, měření rozloží stav na jednu ze dvou polovičních mezer.</span><span class="sxs-lookup"><span data-stu-id="8b0ce-114">In other words, the measurement projects the quantum state onto one of two half-spaces.</span></span>
<span data-ttu-id="8b0ce-115">Můžeme zobecnit způsob, jak si myslíme na měření, aby odrážel tento Intuition.</span><span class="sxs-lookup"><span data-stu-id="8b0ce-115">We can generalize the way we think about measurement to reflect this intuition.</span></span>

<span data-ttu-id="8b0ce-116">Pro výstižnější identifikaci těchto podprostorů potřebujeme jazyk, který popisuje jejich popis.</span><span class="sxs-lookup"><span data-stu-id="8b0ce-116">In order to concisely identify these subspaces, we need a language for describing them.</span></span>
<span data-ttu-id="8b0ce-117">Jedním ze způsobů, jak popsání dvou podprostorů, je jejich zadání prostřednictvím matrice, která má pouze dvě jedinečné eigenvalues, kterou zabere konvence $ \Pm 1 $ .</span><span class="sxs-lookup"><span data-stu-id="8b0ce-117">One way to describe the two subspaces is by specifying them through a matrix that just has two unique eigenvalues, taken by convention to be $\pm 1$.</span></span>
<span data-ttu-id="8b0ce-118">Jednoduchým příkladem popisujících mezery tímto způsobem je zvážit $Z $ :</span><span class="sxs-lookup"><span data-stu-id="8b0ce-118">For a simple example of describing subspaces in this way, consider $Z$:</span></span>

<span data-ttu-id="8b0ce-119">$ $ \begin{align}</span><span class="sxs-lookup"><span data-stu-id="8b0ce-119">$$ \begin{align}</span></span>
  <span data-ttu-id="8b0ce-120">Z & = \begin{ bmatrix } 1 & 0 \\ \\ 0 &-1 \end{ bmatrix } .</span><span class="sxs-lookup"><span data-stu-id="8b0ce-120">Z & = \begin{bmatrix} 1 & 0 \\\\ 0 & -1 \end{bmatrix}.</span></span>
<span data-ttu-id="8b0ce-121">\end{align}</span><span class="sxs-lookup"><span data-stu-id="8b0ce-121">\end{align}</span></span>
$$

<span data-ttu-id="8b0ce-122">Po přečtení diagonálních prvků matice Pauli-$Z $ vidíte, že $Z $ má dvě eigenvectors, $ \ket{0 } $ a $ \ket{1 } $, s odpovídajícím eigenvalues $ \Pm 1 $ .</span><span class="sxs-lookup"><span data-stu-id="8b0ce-122">By reading the diagonal elements of the Pauli-$Z$ matrix, we can see that $Z$ has two eigenvectors, $\ket{0}$ and $\ket{1}$, with corresponding eigenvalues $\pm 1$.</span></span>
<span data-ttu-id="8b0ce-123">Proto pokud měříme qubit a získáme `Zero` (odpovídající stavu $ \ket{0 } $), víme, že stav našeho qubit je $ + 1 $ eigenstate $ operátoru $Z.</span><span class="sxs-lookup"><span data-stu-id="8b0ce-123">Thus, if we measure the qubit and obtain `Zero` (corresponding to the state $\ket{0}$), we know that the state of our qubit is a $+1$ eigenstate of the $Z$ operator.</span></span>
<span data-ttu-id="8b0ce-124">Podobně, pokud získáme `One` , víme, že stav našeho qubit je $-1 $ eigenstate z $Z $ .</span><span class="sxs-lookup"><span data-stu-id="8b0ce-124">Similarly, if we obtain `One`, we know that the state of our qubit is a $-1$ eigenstate of $Z$.</span></span>
<span data-ttu-id="8b0ce-125">Tento proces se označuje v jazyce Pauli měření jako "měřicí Pauli $Z $ a je zcela ekvivalentní k provádění výpočetních měření.</span><span class="sxs-lookup"><span data-stu-id="8b0ce-125">This process is referred to in the language of Pauli measurements as "measuring Pauli $Z$," and is entirely equivalent to performing a computational basis measurement.</span></span>

<span data-ttu-id="8b0ce-126">Každá \times matice $2 2 $ , která představuje jednotnou transformaci $Z $ také splňuje tato kritéria.</span><span class="sxs-lookup"><span data-stu-id="8b0ce-126">Any $2\times 2$ matrix that is a unitary transformation of $Z$ also satisfies this criteria.</span></span>
<span data-ttu-id="8b0ce-127">To znamená, že můžeme také použít matici $A = U ^ \dagger Z $ , kde $U $ je jakákoli jiná Jednotková matice, a poskytnout tak matrici, která definuje dva výsledky měření v jeho eigenvectors $ \Pm 1 $ .</span><span class="sxs-lookup"><span data-stu-id="8b0ce-127">That is, we could also use a matrix $A=U^\dagger Z U$, where $U$ is any other unitary matrix, to give a matrix that defines the two outcomes of a measurement in its $\pm 1$ eigenvectors.</span></span>
<span data-ttu-id="8b0ce-128">Zápis měření Pauli odkazuje na tuto jednotnou rovnocennost tím, že identifikuje $X, Y, Z $ měření jako ekvivalentní měření, které může udělat pro získání informací z qubit.</span><span class="sxs-lookup"><span data-stu-id="8b0ce-128">The notation of Pauli measurements references this unitary equivalence by identifying $X,Y,Z$ measurements as equivalent measurements that one could do to gain information from a qubit.</span></span>
<span data-ttu-id="8b0ce-129">Tato měření jsou uvedena níže pro usnadnění práce.</span><span class="sxs-lookup"><span data-stu-id="8b0ce-129">These measurements are given below for convenience.</span></span>


|<span data-ttu-id="8b0ce-130">Pauli měření</span><span class="sxs-lookup"><span data-stu-id="8b0ce-130">Pauli Measurement</span></span>  |<span data-ttu-id="8b0ce-131">Jednotná transformace</span><span class="sxs-lookup"><span data-stu-id="8b0ce-131">Unitary transformation</span></span>  |
|-------------------|------------------------|
| <span data-ttu-id="8b0ce-132">$Z$</span><span class="sxs-lookup"><span data-stu-id="8b0ce-132">$Z$</span></span>               | <span data-ttu-id="8b0ce-133">$ \boldone$</span><span class="sxs-lookup"><span data-stu-id="8b0ce-133">$\boldone$</span></span>             |
| <span data-ttu-id="8b0ce-134">$X$</span><span class="sxs-lookup"><span data-stu-id="8b0ce-134">$X$</span></span>               | <span data-ttu-id="8b0ce-135">$H$</span><span class="sxs-lookup"><span data-stu-id="8b0ce-135">$H$</span></span>                    |
| <span data-ttu-id="8b0ce-136">$Y$</span><span class="sxs-lookup"><span data-stu-id="8b0ce-136">$Y$</span></span>               | <span data-ttu-id="8b0ce-137">$HS ^ {\dagger}$</span><span class="sxs-lookup"><span data-stu-id="8b0ce-137">$HS^{\dagger}$</span></span>         |

<span data-ttu-id="8b0ce-138">To znamená, že s použitím tohoto jazyka je "Measure $Y $ " ekvivalentem použití $HS ^ \dagger $ a pak měření v výpočetních intervalech, kde [`S`](xref:microsoft.quantum.intrinsic.s) se jedná o vnitřní operaci na základě fáze, která se někdy označuje jako "brána", a může být simulována jednotnou maticí.</span><span class="sxs-lookup"><span data-stu-id="8b0ce-138">That is, using this language, "measure $Y$" is equivalent to applying $HS^\dagger$ and then measuring in the computational basis, where [`S`](xref:microsoft.quantum.intrinsic.s) is an intrinsic quantum operation sometimes called the "phase gate," and can be simulated by the unitary matrix</span></span>

<span data-ttu-id="8b0ce-139">$ $ \begin{align}</span><span class="sxs-lookup"><span data-stu-id="8b0ce-139">$$ \begin{align}</span></span>
    <span data-ttu-id="8b0ce-140">S = \begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="8b0ce-140">S = \begin{bmatrix}</span></span>
        <span data-ttu-id="8b0ce-141">1 & 0 \\ \\ 0 & \end{ bmatrix } .</span><span class="sxs-lookup"><span data-stu-id="8b0ce-141">1 & 0 \\\\ 0 & i \end{bmatrix}.</span></span>
<span data-ttu-id="8b0ce-142">\end{align}</span><span class="sxs-lookup"><span data-stu-id="8b0ce-142">\end{align}</span></span>
$$

<span data-ttu-id="8b0ce-143">Je také ekvivalentní použít $HS ^ \dagger $ na vektor stavu a pak měření $Z $ , takže následující operace je ekvivalentní `Measure([PauliY], [q])` :</span><span class="sxs-lookup"><span data-stu-id="8b0ce-143">It is also equivalent to applying $HS^\dagger$ to the quantum state vector and then measuring $Z$, such that the following operation is equivalent to `Measure([PauliY], [q])`:</span></span>

```Q#
operation MeasureY(qubit : Qubit) : Result {
    mutable result = Zero;
    within {
        H(q);
        Adjoint S(q);
    } apply {
        set result = M(q);
    }
    return result;
}
```

<span data-ttu-id="8b0ce-144">Správný stav by se pak našel tak, že transformuje zpět na výpočetní základ, který se musí použít $SH $ na vektor stavu. ve výše uvedeném fragmentu kódu je transformace zpět na výpočetní základ zpracována automaticky pomocí `within … apply` bloku.</span><span class="sxs-lookup"><span data-stu-id="8b0ce-144">The correct state would then be found by transforming back to the computational basis, which amounts to applying $SH$ to the quantum state vector; in the above snippet, the transformation back to the computational basis is handled automatically by the use of the `within … apply` block.</span></span>

<span data-ttu-id="8b0ce-145">V Q # říkáme výsledek---to znamená, že klasické informace extrahované z interakce se stavem---jsou předány `Result` hodnotou $j \in \\ {\Texttt{Zero } , \texttt{One } \\ } $, která označuje, jestli je výsledek v $ (-1) ^ j $ eigenspace operátoru Pauli měřený.</span><span class="sxs-lookup"><span data-stu-id="8b0ce-145">In Q#, we say the outcome---that is, the classical information extracted from interacting with the state---is given by a `Result` value $j \in \\{\texttt{Zero}, \texttt{One}\\}$ indicating if the result is in the $(-1)^j$ eigenspace of the Pauli operator measured.</span></span>


## <a name="multiple-qubit-measurements"></a><span data-ttu-id="8b0ce-146">Měření s více qubit</span><span class="sxs-lookup"><span data-stu-id="8b0ce-146">Multiple-qubit measurements</span></span>

<span data-ttu-id="8b0ce-147">Měření qubitch operátorů Pauli je definováno podobně, jak je vidět na základě těchto možností:</span><span class="sxs-lookup"><span data-stu-id="8b0ce-147">Measurements of multi-qubit Pauli operators are defined similarly, as seen from:</span></span>

<span data-ttu-id="8b0ce-148">$ $ Z \otimes z = \begin{ bmatrix } 1 &0 &0&0 \\\\ 0 & -1&0&0 \\\\ 0&0 & -1&0 \\\\ 0&0&0&1 \end { bmatrix } .</span><span class="sxs-lookup"><span data-stu-id="8b0ce-148">$$ Z\otimes Z = \begin{bmatrix}1 &0 &0&0\\\\  0&-1&0&0\\\\ 0&0&-1&0\\\\ 0&0&0&1\end{bmatrix}.</span></span>
$$

<span data-ttu-id="8b0ce-149">Proto tensor produkty dvou operátorů Pauli-$Z $ tvoří matici složenou ze dvou mezer, které se skládají z $ + 1 $ a $-1 $ eigenvalues.</span><span class="sxs-lookup"><span data-stu-id="8b0ce-149">Thus the tensor products of two Pauli-$Z$ operators forms a matrix composed of two spaces consisting of $+1$ and $-1$ eigenvalues.</span></span>
<span data-ttu-id="8b0ce-150">Stejně jako u jediného qubit, představuje obojí prostor, což znamená, že polovina přístupného vektorového prostoru patří do $ + 1 $ eigenspace a zbylé polovině do $-1 $ eigenspace.</span><span class="sxs-lookup"><span data-stu-id="8b0ce-150">As with the single-qubit case, both constitute a half-space meaning that half of the accessible vector space belongs to the $+1$ eigenspace and the remaining half to the $-1$ eigenspace.</span></span>
<span data-ttu-id="8b0ce-151">Obecně je snadné vidět z definice tensor produktu, že tensor produkt Pauli-$Z $ a identita se taky řídí.</span><span class="sxs-lookup"><span data-stu-id="8b0ce-151">In general, it is easy to see from the definition of the tensor product that any tensor product of Pauli-$Z$ operators and the identity also obeys this.</span></span>
<span data-ttu-id="8b0ce-152">Třeba</span><span class="sxs-lookup"><span data-stu-id="8b0ce-152">For example,</span></span>

<span data-ttu-id="8b0ce-153">$ $ \begin{align}</span><span class="sxs-lookup"><span data-stu-id="8b0ce-153">$$ \begin{align}</span></span>
    <span data-ttu-id="8b0ce-154">Z \otimes \boldone = \begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="8b0ce-154">Z \otimes \boldone = \begin{bmatrix}</span></span>
        <span data-ttu-id="8b0ce-155">1 & 0 & 0 & 0 \\ \\ 0 & 1 & 0 & 0 \\ \\ 0 & 0 &-1 & 0 \\ \\ 0 & 0 & 0 &-1 \end{ bmatrix } .</span><span class="sxs-lookup"><span data-stu-id="8b0ce-155">1 &  0 &  0 &  0 \\\\ 0 &  1 &  0 &  0 \\\\ 0 &  0 & -1 &  0 \\\\ 0 &  0 &  0 & -1 \end{bmatrix}.</span></span>
<span data-ttu-id="8b0ce-156">\end{align}</span><span class="sxs-lookup"><span data-stu-id="8b0ce-156">\end{align}</span></span>
$$

<span data-ttu-id="8b0ce-157">Stejně jako v případě jakékoli jednotkové transformace těchto matic také popisuje dvě poloviční prostory označené pomocí $ \Pm 1 $ eigenvalues.</span><span class="sxs-lookup"><span data-stu-id="8b0ce-157">As before, any unitary transformation of such matrices also describes two half-spaces labeled by $\pm 1$ eigenvalues.</span></span>
<span data-ttu-id="8b0ce-158">Například $X \otimes X = h h \otimes (z \otimes ) h \otimes h $ od identity, kterou $Z = HXH $ .</span><span class="sxs-lookup"><span data-stu-id="8b0ce-158">For example, $X\otimes X = H\otimes H(Z\otimes Z)H\otimes H$  from the identity that $Z=HXH$.</span></span>
<span data-ttu-id="8b0ce-159">Podobně jako u qubitového případu je možné všechny qubit Pauli-měření zapsat jako $U ^ \dagger (Z \otimes \id) u $ pro $4 \times 4 $ jednotkové matice $U $ .</span><span class="sxs-lookup"><span data-stu-id="8b0ce-159">Similar to the one-qubit case, all two-qubit Pauli-measurements can be written as $U^\dagger (Z\otimes \id) U$ for $4\times 4$ unitary matrices $U$.</span></span> <span data-ttu-id="8b0ce-160">Vytvoříme výčet transformací v následující tabulce.</span><span class="sxs-lookup"><span data-stu-id="8b0ce-160">We enumerate the transformations in the following table.</span></span>

> [!NOTE]
> <span data-ttu-id="8b0ce-161">V tabulce níže používáme $ \operatorname{SWAP } $ k označení matice $ $ \begin{align.}</span><span class="sxs-lookup"><span data-stu-id="8b0ce-161">In the table below, we use $\operatorname{SWAP}$ to indicate the matrix $$ \begin{align}</span></span>
>     <span data-ttu-id="8b0ce-162">\operatorname{SWAP } & = \left (\begin{Matrix}</span><span class="sxs-lookup"><span data-stu-id="8b0ce-162">\operatorname{SWAP} & = \left(\begin{matrix}</span></span>
>         <span data-ttu-id="8b0ce-163">1 & 0 & 0 & 0 \\ \\ 0 & 0 & 1 & 0 \\ \\ 0 & 1 & 0 & 0 \\ \\ 0 & 0 & 0 & 1 \end{Matrix } \right) \end{align}</span><span class="sxs-lookup"><span data-stu-id="8b0ce-163">1 & 0 & 0 & 0 \\\\ 0 & 0 & 1 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 0 & 1 \end{matrix}\right) \end{align}</span></span>
> <span data-ttu-id="8b0ce-164">$ $ používá se k simulaci vnitřní operace [`SWAP`](xref:microsoft.quantum.intrinsic) .</span><span class="sxs-lookup"><span data-stu-id="8b0ce-164">$$ used to simulate the intrinsic operation [`SWAP`](xref:microsoft.quantum.intrinsic).</span></span>

|<span data-ttu-id="8b0ce-165">Pauli měření</span><span class="sxs-lookup"><span data-stu-id="8b0ce-165">Pauli Measurement</span></span>     |<span data-ttu-id="8b0ce-166">Jednotná transformace</span><span class="sxs-lookup"><span data-stu-id="8b0ce-166">Unitary transformation</span></span>  |
|----------------------|------------------------|
| <span data-ttu-id="8b0ce-167">$Z \otimes \boldone$</span><span class="sxs-lookup"><span data-stu-id="8b0ce-167">$Z \otimes \boldone$</span></span> | <span data-ttu-id="8b0ce-168">$ \boldone \otimes \boldone$</span><span class="sxs-lookup"><span data-stu-id="8b0ce-168">$\boldone \otimes \boldone$</span></span> |
| <span data-ttu-id="8b0ce-169">$Z \otimes \boldone$</span><span class="sxs-lookup"><span data-stu-id="8b0ce-169">$Z\otimes \boldone$</span></span> | <span data-ttu-id="8b0ce-170">$ \boldone \otimes \boldone$</span><span class="sxs-lookup"><span data-stu-id="8b0ce-170">$\boldone\otimes \boldone$</span></span> |
| <span data-ttu-id="8b0ce-171">$X \otimes \boldone$</span><span class="sxs-lookup"><span data-stu-id="8b0ce-171">$X\otimes \boldone$</span></span> | <span data-ttu-id="8b0ce-172">$H \otimes \boldone$</span><span class="sxs-lookup"><span data-stu-id="8b0ce-172">$H\otimes \boldone$</span></span> |
| <span data-ttu-id="8b0ce-173">$Y \otimes \boldone$</span><span class="sxs-lookup"><span data-stu-id="8b0ce-173">$Y\otimes \boldone$</span></span> | <span data-ttu-id="8b0ce-174">$HS ^ \dagger \otimes \boldone$</span><span class="sxs-lookup"><span data-stu-id="8b0ce-174">$HS^\dagger\otimes \boldone$</span></span> |
| <span data-ttu-id="8b0ce-175">$ \boldone \otimes Z$</span><span class="sxs-lookup"><span data-stu-id="8b0ce-175">$\boldone \otimes Z$</span></span> | <span data-ttu-id="8b0ce-176">$ \operatorname{SWAP}$</span><span class="sxs-lookup"><span data-stu-id="8b0ce-176">$\operatorname{SWAP}$</span></span> |
| <span data-ttu-id="8b0ce-177">$ \boldone \otimes X$</span><span class="sxs-lookup"><span data-stu-id="8b0ce-177">$\boldone \otimes X$</span></span> | <span data-ttu-id="8b0ce-178">$ (H \otimes \boldone) \operatorname{swap}$</span><span class="sxs-lookup"><span data-stu-id="8b0ce-178">$(H\otimes \boldone)\operatorname{SWAP}$</span></span> |
| <span data-ttu-id="8b0ce-179">$ \boldone \otimes Y$</span><span class="sxs-lookup"><span data-stu-id="8b0ce-179">$\boldone \otimes Y$</span></span> | <span data-ttu-id="8b0ce-180">$ (HS ^ \dagger \otimes \boldone) \operatorname{swap}$</span><span class="sxs-lookup"><span data-stu-id="8b0ce-180">$(HS^\dagger\otimes \boldone)\operatorname{SWAP}$</span></span> |
| <span data-ttu-id="8b0ce-181">$Z \otimes Z$</span><span class="sxs-lookup"><span data-stu-id="8b0ce-181">$Z\otimes Z$</span></span> | <span data-ttu-id="8b0ce-182">$ \operatorname{CNOT } \_ {10}$</span><span class="sxs-lookup"><span data-stu-id="8b0ce-182">$\operatorname{CNOT}\_{10}$</span></span> |
| <span data-ttu-id="8b0ce-183">$X \otimes Z$</span><span class="sxs-lookup"><span data-stu-id="8b0ce-183">$X\otimes Z$</span></span> | <span data-ttu-id="8b0ce-184">$ \operatorname{CNOT } \_ {10 } (H \otimes \boldone) $</span><span class="sxs-lookup"><span data-stu-id="8b0ce-184">$\operatorname{CNOT}\_{10}(H\otimes \boldone)$</span></span> |
| <span data-ttu-id="8b0ce-185">$Y \otimes Z$</span><span class="sxs-lookup"><span data-stu-id="8b0ce-185">$Y\otimes Z$</span></span> | <span data-ttu-id="8b0ce-186">$ \operatorname{CNOT } \_ {10 } (HS ^ \dagger \otimes \boldone) $</span><span class="sxs-lookup"><span data-stu-id="8b0ce-186">$\operatorname{CNOT}\_{10}(HS^\dagger\otimes \boldone)$</span></span> |
| <span data-ttu-id="8b0ce-187">$Z \otimes X$</span><span class="sxs-lookup"><span data-stu-id="8b0ce-187">$Z\otimes X$</span></span> | <span data-ttu-id="8b0ce-188">$ \operatorname{CNOT } \_ {10 } (\boldone \otimes H) $</span><span class="sxs-lookup"><span data-stu-id="8b0ce-188">$\operatorname{CNOT}\_{10}(\boldone\otimes H)$</span></span> |
| <span data-ttu-id="8b0ce-189">$X \otimes X$</span><span class="sxs-lookup"><span data-stu-id="8b0ce-189">$X\otimes X$</span></span> | <span data-ttu-id="8b0ce-190">$ \operatorname{CNOT } \_ {10 } (H \otimes h) $</span><span class="sxs-lookup"><span data-stu-id="8b0ce-190">$\operatorname{CNOT}\_{10}(H\otimes H)$</span></span> |
| <span data-ttu-id="8b0ce-191">$Y \otimes X$</span><span class="sxs-lookup"><span data-stu-id="8b0ce-191">$Y\otimes X$</span></span> | <span data-ttu-id="8b0ce-192">$ \operatorname{CNOT } \_ {10 } (HS ^ \dagger \otimes H) $</span><span class="sxs-lookup"><span data-stu-id="8b0ce-192">$\operatorname{CNOT}\_{10}(HS^\dagger\otimes H)$</span></span> |
| <span data-ttu-id="8b0ce-193">$Z \otimes Y$</span><span class="sxs-lookup"><span data-stu-id="8b0ce-193">$Z\otimes Y$</span></span> | <span data-ttu-id="8b0ce-194">$ \operatorname{CNOT } \_ {10 } (\boldone \otimes HS ^ \dagger) $</span><span class="sxs-lookup"><span data-stu-id="8b0ce-194">$\operatorname{CNOT}\_{10}(\boldone \otimes HS^\dagger)$</span></span> |
| <span data-ttu-id="8b0ce-195">$X \otimes Y$</span><span class="sxs-lookup"><span data-stu-id="8b0ce-195">$X\otimes Y$</span></span> | <span data-ttu-id="8b0ce-196">$ \operatorname{CNOT } \_ {10 } (H \otimes HS ^ \dagger) $</span><span class="sxs-lookup"><span data-stu-id="8b0ce-196">$\operatorname{CNOT}\_{10}(H\otimes HS^\dagger)$</span></span> |
| <span data-ttu-id="8b0ce-197">$Y \otimes Y$</span><span class="sxs-lookup"><span data-stu-id="8b0ce-197">$Y\otimes Y$</span></span> | <span data-ttu-id="8b0ce-198">$ \operatorname{CNOT } \_ {10 } (HS ^ \dagger \otimes HS ^ \dagger) $</span><span class="sxs-lookup"><span data-stu-id="8b0ce-198">$\operatorname{CNOT}\_{10}(HS^\dagger\otimes HS^\dagger)$</span></span> |

<span data-ttu-id="8b0ce-199">Tato [`CNOT`](xref:microsoft.quantum.intrinsic.cnot) operace se zobrazí z následujícího důvodu.</span><span class="sxs-lookup"><span data-stu-id="8b0ce-199">Here, the [`CNOT`](xref:microsoft.quantum.intrinsic.cnot) operation appears for the following reason.</span></span>
<span data-ttu-id="8b0ce-200">Každé měření Pauli, které neobsahuje matrici $ \boldone, $ je ekvivalentní až do $Z \otimes Z $ výše uvedeného důvodu.</span><span class="sxs-lookup"><span data-stu-id="8b0ce-200">Each Pauli measurement that does not include the $\boldone$ matrix is equivalent up to a unitary to $Z\otimes Z$ by the above reasoning.</span></span>
<span data-ttu-id="8b0ce-201">Eigenvalues z $Z \otimes z $ pouze závisí na paritě qubits, která zahrnuje každý výpočetní vektor a kontrolované – nečinnosti slouží k výpočtu této parity a jejich uložení v prvním bitu.</span><span class="sxs-lookup"><span data-stu-id="8b0ce-201">The eigenvalues of $Z\otimes Z$ only depend on the parity of the qubits that comprise each computational basis vector, and the controlled-not operations serve to compute this parity and store it in the first bit.</span></span>
<span data-ttu-id="8b0ce-202">Po měření prvního bitu můžeme obnovit identitu výsledného prostoru, který je ekvivalentní k měření Pauli operátoru.</span><span class="sxs-lookup"><span data-stu-id="8b0ce-202">Then once the first bit is measured, we can recover the identity of the resultant half-space, which is equivalent to measuring the Pauli operator.</span></span>

<span data-ttu-id="8b0ce-203">Další Poznámka: i když je možné předpokládat, že měření $Z \otimes Z $ je stejné jako při sekvenčním měření $Z \otimes \mathbb{1 } $ a pak $ \mathbb{1 } \otimes Z $ , tento předpoklad by byl nepravdivý.</span><span class="sxs-lookup"><span data-stu-id="8b0ce-203">One additional note: while it may be tempting to assume that measuring $Z\otimes Z$ is the same as sequentially measuring $Z\otimes \mathbb{1}$ and then $\mathbb{1} \otimes Z$, this assumption would be false.</span></span>
<span data-ttu-id="8b0ce-204">Důvodem je, že měření $Z \otimes z $ projektuje stav neeigenstateu na $ + 1 $ nebo $-1 $ pro tyto operátory.</span><span class="sxs-lookup"><span data-stu-id="8b0ce-204">The reason is that measuring $Z\otimes Z$ projects the quantum state into either the $+1$ or $-1$ eigenstate of these operators.</span></span>
<span data-ttu-id="8b0ce-205">Měření $Z \otimes \mathbb{1 } $ a pak $ \Mathbb{1 } \otimes Z $ projektuje vektor stavu v polovině na polovinu prostoru $Z \otimes \mathbb{1 } $ a pak na polovinu prostoru $ \mathbb{1 } \otimes Z $ . Vzhledem k tomu, že jsou k dispozici čtyři výpočetní vektory, může použití obou měření snížit stav na čtvrtinové místo a tím se sníží na jeden vektor výpočetního základu.</span><span class="sxs-lookup"><span data-stu-id="8b0ce-205">Measuring $Z\otimes \mathbb{1}$ and then $\mathbb{1} \otimes Z$ projects the quantum state vector first onto a half space of $Z\otimes \mathbb{1}$ and then onto a half space of $\mathbb{1} \otimes Z$. As there are four computational basis vectors, performing both measurements reduces the state to a quarter-space and hence reduces it to a single computational basis vector.</span></span>

## <a name="correlations-between-qubits"></a><span data-ttu-id="8b0ce-206">Korelace mezi qubits</span><span class="sxs-lookup"><span data-stu-id="8b0ce-206">Correlations between qubits</span></span>
<span data-ttu-id="8b0ce-207">Další možností, jak se podívat na měření tensor produktů Paulich matric, \otimes jako $ je $X X nebo $Z \otimes Z $ , je, že tato měření vám umožní podívat se na informace, které jsou uložené v korelaci mezi dvěma qubits.</span><span class="sxs-lookup"><span data-stu-id="8b0ce-207">Another way of looking at measuring tensor products of Pauli matrices such as $X\otimes X$ or $Z\otimes Z$ is that these measurements let you look at information stored in the correlations between the two qubits.</span></span>
<span data-ttu-id="8b0ce-208">Měření $X \otimes \id $ vám umožní podívat se na informace, které jsou místně uložené v první qubit.</span><span class="sxs-lookup"><span data-stu-id="8b0ce-208">Measuring $X\otimes \id$ lets you look at information that is locally stored in the first qubit.</span></span>
<span data-ttu-id="8b0ce-209">I když jsou oba typy měření stejně cenné při práci ve výpočetním prostředí, bývalé osvětlení síly při práci.</span><span class="sxs-lookup"><span data-stu-id="8b0ce-209">While both types of measurements are equally valuable in quantum computing, the former illuminates the power of quantum computing.</span></span>
<span data-ttu-id="8b0ce-210">To znamená, že ve výpočetním prostředí se často informace, které chcete vědět, neukládají do žádného qubit, ale místo toho, aby se ukládaly do všech qubits najednou, a proto jenom pomocí společného měření (např. $Z \otimes Z $ ) se tyto informace stanou manifestem.</span><span class="sxs-lookup"><span data-stu-id="8b0ce-210">It reveals that in quantum computing, often the information you wish to learn is not stored in any single qubit but rather stored non-locally in all the qubits at once, and therefore only by looking at it through a joint measurement (e.g. $Z\otimes Z$) does this information become manifest.</span></span>

<span data-ttu-id="8b0ce-211">Například při opravě chyb často chceme zjistit, k jaké chybě došlo při učení o stavu, který se snažíte chránit.</span><span class="sxs-lookup"><span data-stu-id="8b0ce-211">For example, in error correction, we often wish to learn what error occurred while learning nothing about the state that we're trying to protect.</span></span>
<span data-ttu-id="8b0ce-212">[Ukázka bitového překlápění kódu](https://github.com/microsoft/Quantum/tree/master/samples/error-correction/bit-flip-code) ukazuje příklad toho, jak to lze provést pomocí měření, jako je $Z \otimes Z \otimes \id $ a $ \id \Otimes Z \otimes z $ .</span><span class="sxs-lookup"><span data-stu-id="8b0ce-212">The [bit-flip code sample](https://github.com/microsoft/Quantum/tree/master/samples/error-correction/bit-flip-code) shows an example of how you can do that using measurements like $Z \otimes Z \otimes \id$ and $\id \otimes Z \otimes Z$.</span></span>
<!-- TODO: change this to a link to the samples browser as soon as the bit-flip code sample is on-boarded. -->

<span data-ttu-id="8b0ce-213">Lze také změřit libovolné Pauli operátory, jako je například $X \otimes Y \Otimes Z \otimes \boldone $ .</span><span class="sxs-lookup"><span data-stu-id="8b0ce-213">Arbitrary Pauli operators such as $X\otimes Y \otimes Z \otimes \boldone$ can also be measured.</span></span>
<span data-ttu-id="8b0ce-214">Všechny takové tensor produkty operátorů Pauli mají pouze dvě eigenvalues $ \Pm 1 $ a oba eigenspaces představují poloviční prostory celého vektorového prostoru.</span><span class="sxs-lookup"><span data-stu-id="8b0ce-214">All such tensor products of Pauli operators have only two eigenvalues $\pm 1$ and both eigenspaces constitute half-spaces of the entire vector space.</span></span>
<span data-ttu-id="8b0ce-215">Proto se shodují s výše uvedenými požadavky.</span><span class="sxs-lookup"><span data-stu-id="8b0ce-215">Thus they coincide with the requirements stated above.</span></span>

<span data-ttu-id="8b0ce-216">V Q # taková měření vrací $j, $ Pokud měření vyplývají z výsledku eigenspace Sign $ (-1) ^ j $ .</span><span class="sxs-lookup"><span data-stu-id="8b0ce-216">In Q#, such measurements return $j$ if the measurement yields a result in the eigenspace of sign $(-1)^j$.</span></span>
<span data-ttu-id="8b0ce-217">Pauli měření jako integrovaná funkce v Q # je užitečná, protože měření takových operátorů vyžaduje dlouhé řetězy řízených a nevratných operací a základní transformace, které popisují $U diagonalizingou bránu, která je potřeba k tomu, aby se $ operace mohla vyjádřit jako tensor produkt $Z $ a $ \id $ . Díky možnosti určit, že chcete provést jedno z těchto předdefinovaných měření, nemusíte si dělat starosti s tím, jak transformovat svůj základ, aby výpočetní základní měření poskytovalo potřebné informace.</span><span class="sxs-lookup"><span data-stu-id="8b0ce-217">Having Pauli measurements as a built-in feature in Q# is helpful because measuring such operators requires long chains of controlled-NOT gates and basis transformations to describe the diagonalizing $U$ gate needed to express the operation as a tensor product of $Z$ and $\id$. By being able to specify that you wish to do one of these pre-defined measurements, you don't need to worry about how to transform your basis such that a computational basis measurement provides the necessary information.</span></span>
<span data-ttu-id="8b0ce-218">Q # zpracovává všechny potřebné transformace automaticky pro vás.</span><span class="sxs-lookup"><span data-stu-id="8b0ce-218">Q# handles all the necessary basis transformations for you automatically.</span></span>
<span data-ttu-id="8b0ce-219">Další informace najdete v tématu [`Measure`](xref:microsoft.quantum.intrinsic.measure) operace a [`MeasurePaulis`](xref:microsoft.quantum.measurement.measurepaulis) .</span><span class="sxs-lookup"><span data-stu-id="8b0ce-219">For more information, see the [`Measure`](xref:microsoft.quantum.intrinsic.measure) and [`MeasurePaulis`](xref:microsoft.quantum.measurement.measurepaulis) operations.</span></span>

## <a name="the-no-cloning-theorem"></a><span data-ttu-id="8b0ce-220">Věta bez klonování</span><span class="sxs-lookup"><span data-stu-id="8b0ce-220">The No-Cloning Theorem</span></span>

<span data-ttu-id="8b0ce-221">Informace o nemocném případě jsou výkonné.</span><span class="sxs-lookup"><span data-stu-id="8b0ce-221">Quantum information is powerful.</span></span>
<span data-ttu-id="8b0ce-222">Umožňuje nám dělat úžasné věci, jako jsou čísla faktorů exponenciálně rychleji než nejlepší známé klasické algoritmy, nebo efektivně simulovat korelační elektronické systémy, které Classic potřebují k přesnému simulaci exponenciálních nákladů.</span><span class="sxs-lookup"><span data-stu-id="8b0ce-222">It enables us to do amazing things such as factor numbers exponentially faster than the best known classical algorithms, or efficiently simulate correlated electron systems that classically require exponential cost to simulate accurately.</span></span>
<span data-ttu-id="8b0ce-223">Existují však určitá omezení výkonu s využitím nároku na výpočetní výkon.</span><span class="sxs-lookup"><span data-stu-id="8b0ce-223">However, there are limitations to the power of quantum computing.</span></span>
<span data-ttu-id="8b0ce-224">Jedno takové omezení je dáno *větaem bez klonování*.</span><span class="sxs-lookup"><span data-stu-id="8b0ce-224">One such limitation is given by the *No-Cloning Theorem*.</span></span>

<span data-ttu-id="8b0ce-225">Věta pro No-klonování není aptly pojmenováno.</span><span class="sxs-lookup"><span data-stu-id="8b0ce-225">The No-Cloning Theorem is aptly named.</span></span>
<span data-ttu-id="8b0ce-226">Neumožňuje klonování obecných stavových stavů počítačem s více než jednou.</span><span class="sxs-lookup"><span data-stu-id="8b0ce-226">It disallows cloning of generic quantum states by a quantum computer.</span></span>
<span data-ttu-id="8b0ce-227">Důkaz věta je výjimečně přímočarý.</span><span class="sxs-lookup"><span data-stu-id="8b0ce-227">The proof of the theorem is remarkably straightforward.</span></span>
<span data-ttu-id="8b0ce-228">I když je úplný důkaz věta bez klonování pro naši diskuzi příliš technický, důkaz v případě žádného dalšího pomocného qubitsu v rámci našeho rozsahu (pomocné qubits se qubits používá pro pomocné místo během výpočtu a snadno se používá a spravuje v Q # najdete v tématu [výpůjčka qubits](xref:microsoft.quantum.guide.qubits#borrowed-qubits)).</span><span class="sxs-lookup"><span data-stu-id="8b0ce-228">While a full proof of the no-cloning theorem is a little too technical for our discussion here, the proof in the case of no additional auxiliary qubits is within our scope (auxiliary qubits are qubits used for scratch space during a computation and are easily used and managed in Q#, see [borrowed qubits](xref:microsoft.quantum.guide.qubits#borrowed-qubits)).</span></span>

<span data-ttu-id="8b0ce-229">V případě takového počítače s více operačními systémem musí být operace klonování popsána jednotnou maticí.</span><span class="sxs-lookup"><span data-stu-id="8b0ce-229">For such a quantum computer, the cloning operation must be described by a unitary matrix.</span></span>
<span data-ttu-id="8b0ce-230">Nezakážeme měření, protože by došlo k poškození stavu, který se snažíme klonovat.</span><span class="sxs-lookup"><span data-stu-id="8b0ce-230">We disallow measurement, since it would corrupt the quantum state we are trying to clone.</span></span>
<span data-ttu-id="8b0ce-231">Pro simulaci operace klonování chceme, aby jednotná matice používala vlastnost, která je $ $ U \ket { \psi } \ket{0 } = \ket { \psi } \ket { \psi}</span><span class="sxs-lookup"><span data-stu-id="8b0ce-231">To simulate the cloning operation, we want the unitary matrix used to have the property that $$ U \ket{\psi} \ket{0} = \ket{\psi} \ket{\psi}</span></span>
<span data-ttu-id="8b0ce-232">$ $ for any State $ \ket { \psi } $.</span><span class="sxs-lookup"><span data-stu-id="8b0ce-232">$$ for any state $\ket{\psi}$.</span></span>
<span data-ttu-id="8b0ce-233">Vlastnost linearity matice násobení pak znamená, že pro jakýkoliv druhý stav 2 – 2 – { 2 } $ \ket \phi $,</span><span class="sxs-lookup"><span data-stu-id="8b0ce-233">The linearity property of matrix multiplication then implies that for any second quantum state $\ket{\phi}$,</span></span>

<span data-ttu-id="8b0ce-234">$ $ \begin{align}</span><span class="sxs-lookup"><span data-stu-id="8b0ce-234">$$ \begin{align}</span></span>
    <span data-ttu-id="8b0ce-235">U \left [\frac{1 } {\sqrt{2 } } \left (\ket { \phi } + \ket { \psi } \right) \right] \ket{0}</span><span class="sxs-lookup"><span data-stu-id="8b0ce-235">U \left[ \frac{1}{\sqrt{2}}\left(\ket{\phi}+\ket{\psi} \right) \right] \ket{0}</span></span>
    <span data-ttu-id="8b0ce-236">& = \frac{1 } {\sqrt{2 } } U \ket { \phi } \ket{0}</span><span class="sxs-lookup"><span data-stu-id="8b0ce-236">& = \frac{1}{\sqrt{2}} U\ket{\phi}\ket{0}</span></span>
      <span data-ttu-id="8b0ce-237">+ \frac{1 } {\sqrt{2 } } U \ket { \psi } \ket{0 } \\ \\ & = \frac{1 } {\sqrt{2 } } \left (\ket { \phi } \ket { \phi } + \ket { \psi } \ket { \psi}</span><span class="sxs-lookup"><span data-stu-id="8b0ce-237">+ \frac{1}{\sqrt{2}} U\ket{\psi}\ket{0} \\\\ & = \frac{1}{\sqrt{2}} \left( \ket{\phi} \ket{\phi} + \ket{\psi} \ket{\psi}</span></span>
        <span data-ttu-id="8b0ce-238">\right) \\ \\ & \Ne \left (\frac{1 } {\sqrt{2 } } \left (\ket { \phi } + \ket { \psi } \right) \right) \otimes \left (\frac{1 } {\sqrt{2 } } \left (\ket { \phi } + \ket { \psi } \right) \right).</span><span class="sxs-lookup"><span data-stu-id="8b0ce-238">\right) \\\\ & \ne \left( \frac{1}{\sqrt{2}}\left(\ket{\phi}+\ket{\psi} \right) \right) \otimes \left( \frac{1}{\sqrt{2}}\left(\ket{\phi}+\ket{\psi} \right) \right).</span></span>
<span data-ttu-id="8b0ce-239">\end{align}</span><span class="sxs-lookup"><span data-stu-id="8b0ce-239">\end{align}</span></span>
$$

<span data-ttu-id="8b0ce-240">To poskytuje základní Intuition za věta bez klonování: každé zařízení, které kopíruje neznámý stav, musí způsobit chyby alespoň u některých stavů, které kopíruje.</span><span class="sxs-lookup"><span data-stu-id="8b0ce-240">This provides the fundamental intuition behind the No-Cloning Theorem: any device that copies an unknown quantum state must induce errors on at least some of the states it copies.</span></span>
<span data-ttu-id="8b0ce-241">I když klíč předpokládá, že Cloner funguje lineárně na vstupním stavu, může být porušená přidáním a měřením pomocných qubits, takže tyto interakce také nevrací informace o systému prostřednictvím statistik měření a zabrání v takových případech přesné klonování.</span><span class="sxs-lookup"><span data-stu-id="8b0ce-241">While the key assumption that the cloner acts linearly on the input state can be violated through the addition and measurement of auxiliary qubits, such interactions also leak information about the system through the measurement statistics and prevent exact cloning in such cases as well.</span></span>
<span data-ttu-id="8b0ce-242">Další [informace](xref:microsoft.quantum.more-information)o tom, jak se věta bez klonování, najdete v tématu.</span><span class="sxs-lookup"><span data-stu-id="8b0ce-242">For a more complete proof of the No-Cloning Theorem see [For more information](xref:microsoft.quantum.more-information).</span></span>

<span data-ttu-id="8b0ce-243">Věta bez klonování je důležité pro kvalitativní porozumění výpočetním procesorům, protože pokud byste mohli naklonovat stavy nenákladných stavových procesorů, pak by vám byla udělena téměř Magical možnost učit se ze států.</span><span class="sxs-lookup"><span data-stu-id="8b0ce-243">The No-Cloning Theorem is important for qualitative understanding of quantum computing because if you could clone quantum states inexpensively then you would be granted a near-magical ability to learn from quantum states.</span></span>
<span data-ttu-id="8b0ce-244">Ve skutečnosti byste mohli narušit zásadu nejistoty Heisenberg vaunted.</span><span class="sxs-lookup"><span data-stu-id="8b0ce-244">Indeed, you could violate Heisenberg's vaunted uncertainty principle.</span></span>
<span data-ttu-id="8b0ce-245">Alternativně můžete použít optimální Cloner k získání jedné ukázky ze složitosti distribuce nečinnosti a zjistit všechno, co byste se mohli dozvědět o této distribuci jenom z jedné ukázky.</span><span class="sxs-lookup"><span data-stu-id="8b0ce-245">Alternatively, you could use an optimal cloner to take a single sample from a complex quantum distribution and learn everything you could possibly learn about that distribution from just one sample.</span></span>
<span data-ttu-id="8b0ce-246">To by vypadalo jako převrácení mince a pozorování hlav a následného oznámení o tom, že na výsledek má odpovědět "Ah. rozdělení této mince musí být Bernoulliho s $p = 0.512643 \ ldots $ !"</span><span class="sxs-lookup"><span data-stu-id="8b0ce-246">This would be like you flipping a coin and observing heads and then upon telling a friend about the result having them respond "Ah the distribution of that coin must be Bernoulli with $p=0.512643\ldots$!"</span></span>  <span data-ttu-id="8b0ce-247">Takový příkaz by nebyl sensical, protože jeden z bitových informací (výsledek hlav) jednoduše nemůže poskytnout mnoho informací potřebných ke kódování distribuce bez podstatných předchozích informací.</span><span class="sxs-lookup"><span data-stu-id="8b0ce-247">Such a statement would be non-sensical because one bit of information (the heads outcome) simply cannot provide the many bits of information needed to encode the distribution without substantial prior information.</span></span>
<span data-ttu-id="8b0ce-248">Podobně bez předchozích informací nemůžeme zcela klonovat stav, protože nemůžeme připravit komplet těchto mincí, aniž by bylo potřeba znát $p $ .</span><span class="sxs-lookup"><span data-stu-id="8b0ce-248">Similarly, without prior information we cannot perfectly clone a quantum state just as we cannot prepare an ensemble of such coins without knowing $p$.</span></span>

<span data-ttu-id="8b0ce-249">Informace nejsou v výpočetním prostředí bezplatné.</span><span class="sxs-lookup"><span data-stu-id="8b0ce-249">Information is not free in quantum computing.</span></span>
<span data-ttu-id="8b0ce-250">Každá qubit měřená má jedinou bitovou informaci a věta bez klonování ukazuje, že není k dispozici žádné zadní vrátka, které by bylo možné zneužít k získání základních kompromisů mezi informacemi získanými v systému a vyvolaným poruchou.</span><span class="sxs-lookup"><span data-stu-id="8b0ce-250">Each qubit measured gives a single bit of information, and the No-Cloning Theorem shows that there is no backdoor that can be exploited to get around the fundamental tradeoff between information gained about the system and the disturbance invoked upon it.</span></span>
