---
title: Měření Pauli | Microsoft Docs
description: Pauli měření
author: QuantumWriter
uid: microsoft.quantum.concepts.pauli
ms.author: nawiebe@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: 7bea821be7e26e72f2860278486d35be676ca63d
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/26/2019
ms.locfileid: "73183705"
---
# <a name="pauli-measurements"></a><span data-ttu-id="56f8b-103">Pauli měření</span><span class="sxs-lookup"><span data-stu-id="56f8b-103">Pauli Measurements</span></span>

<span data-ttu-id="56f8b-104">V předchozích diskusích jsme se zaměřili na výpočetní základní měření.</span><span class="sxs-lookup"><span data-stu-id="56f8b-104">In the previous discussions, we have focused on computational basis measurements.</span></span>  <span data-ttu-id="56f8b-105">Ve skutečnosti jsou k dispozici další běžná měření, ke kterým dochází v množství náročném na výpočetní výkon, který je ze zapsaných perspektiv pohodlný, a to v souvislosti s výpočetními základními měřeními.</span><span class="sxs-lookup"><span data-stu-id="56f8b-105">In fact there are other common measurements that occur in quantum computing that, from a notational perspective, are convenient to express in terms of computational basis measurements.</span></span>  <span data-ttu-id="56f8b-106">Nejběžnější sadou těchto měření jsou *Pauli měření*.</span><span class="sxs-lookup"><span data-stu-id="56f8b-106">The most common set of these measurements are *Pauli measurements*.</span></span>  <span data-ttu-id="56f8b-107">V takových případech je běžné projednávat měření Pauli operátoru, a to obecně operátor, například $X, Y, Z $ nebo $Z \otimes Z, X\otimes X, X\otimes Y $ a tak dále.</span><span class="sxs-lookup"><span data-stu-id="56f8b-107">In such cases, it is common to discuss measuring a Pauli operator, in general an operator such as $X,Y,Z$ or $Z\otimes Z, X\otimes X, X\otimes Y$ and so forth.</span></span>  <span data-ttu-id="56f8b-108">Projednávání měření v rámci Pauli operátorů je zvlášť běžné v podpoli s opravou chyb pro každé z nich.</span><span class="sxs-lookup"><span data-stu-id="56f8b-108">Discussing measurement in terms of Pauli operators is especially common in the subfield of quantum error correction.</span></span> <span data-ttu-id="56f8b-109">V Q # sledujeme podobnou konvenci. nyní vysvětlujeme toto alternativní zobrazení měření.</span><span class="sxs-lookup"><span data-stu-id="56f8b-109">In Q# we follow a similar convention; we now explain this alternative view of measurements.</span></span>

<span data-ttu-id="56f8b-110">Než se pustíte do detailů o tom, jak si představit Pauli měření, je vhodné se seznámit s tím, jak měření jedné qubit v rámci počítače ve státě</span><span class="sxs-lookup"><span data-stu-id="56f8b-110">Before delving into the details of how to think of a Pauli measurement, it is useful to think about what measuring a single qubit inside a quantum computer does to the quantum state.</span></span>  <span data-ttu-id="56f8b-111">Představte si, že máme $n $-qubitský stav; pak se jednou z nich odměří jedna qubit, což je polovina možností $2 ^ n $, které by mohly být ve stavu.</span><span class="sxs-lookup"><span data-stu-id="56f8b-111">Imagine that we have an $n$-qubit quantum state; then measuring one qubit immediately rules out half of the $2^n$ possibilities that state could be in.</span></span>  <span data-ttu-id="56f8b-112">Jinými slovy, měření rozloží stav na jednu ze dvou polovičních mezer.</span><span class="sxs-lookup"><span data-stu-id="56f8b-112">In other words, the measurement projects the quantum state onto one of two half-spaces.</span></span>  <span data-ttu-id="56f8b-113">Můžeme zobecnit, jak si myslíme o měření, abychom to odráželi.</span><span class="sxs-lookup"><span data-stu-id="56f8b-113">We can generalize the way we think about measurement to reflect this.</span></span>

<span data-ttu-id="56f8b-114">Pro výstižnější identifikaci těchto podprostorů potřebujeme jazyk, který popisuje jejich popis.</span><span class="sxs-lookup"><span data-stu-id="56f8b-114">In order to concisely identify these subspaces, we need a language for describing them.</span></span>  <span data-ttu-id="56f8b-115">Jedním ze způsobů, jak to provést, je popsat dvě podprostory tak, že je zadáte přes matrici, která má pouze dvě jedinečné eigenvalues, kterou používá konvence $ \Pm $1.</span><span class="sxs-lookup"><span data-stu-id="56f8b-115">One way to do this is to describe the two subspaces by specifying them through a matrix that just has two unique eigenvalues, taken by convention to be $\pm 1$.</span></span>  <span data-ttu-id="56f8b-116">Nejjednodušším příkladem je:</span><span class="sxs-lookup"><span data-stu-id="56f8b-116">The simplest example of this is:</span></span>

<span data-ttu-id="56f8b-117">$ $ Z = \begin{bmatrix} 1 & 0 \\\\ 0 &-1 \end{bmatrix}.</span><span class="sxs-lookup"><span data-stu-id="56f8b-117">$$ Z = \begin{bmatrix} 1 & 0 \\\\ 0 & -1 \end{bmatrix}.</span></span>
$$

<span data-ttu-id="56f8b-118">Pauli-$Z $ Matrix má jasně dvě eigenvectors $ \ket{0}$ a $ \ket{1}$ with eigenvalues $ \Pm $1.</span><span class="sxs-lookup"><span data-stu-id="56f8b-118">The Pauli-$Z$ matrix clearly has two eigenvectors $\ket{0}$ and $\ket{1}$ with eigenvalues $\pm 1$.</span></span>  <span data-ttu-id="56f8b-119">Proto pokud měříme qubit a získáme $ \ket{0}$ máme v sadě $ + $1 eigenspace (sada všech vektorů, které jsou tvořeny součty eigenvectors pouze s pozitivním nebo pouze negativním eigenvaluesm) operátoru a pokud měříme $ \ket{1}$, budeme v $-$1 EI genspace $Z $.</span><span class="sxs-lookup"><span data-stu-id="56f8b-119">Thus if we measure the qubit and obtain $\ket{0}$ we are in the $+1$ eigenspace (the set of all vectors that are formed of sums of  eigenvectors with only positive or only negative eigenvalues) of the operator and if we measure $\ket{1}$ we are in the $-1$ eigenspace of $Z$.</span></span>  <span data-ttu-id="56f8b-120">Tento proces se označuje v jazyce Pauli měření jako "měřicí Pauli $Z $" a je zcela stejný jako při provádění výpočetních měření.</span><span class="sxs-lookup"><span data-stu-id="56f8b-120">This process is referred to in the language of Pauli measurements as "measuring Pauli $Z$" and is entirely equivalent to performing a computational basis measurement.</span></span>

<span data-ttu-id="56f8b-121">Samozřejmě každou matrici $2 \ krát $2, která představuje jednotnou transformaci $Z $, také splňuje tato kritéria.</span><span class="sxs-lookup"><span data-stu-id="56f8b-121">Of course any $2\times 2$ matrix that is a unitary transformation of $Z$ also satisfies this criteria.</span></span>  <span data-ttu-id="56f8b-122">To znamená, že můžeme také zvážit $A matice = U ^ \dagger Z U $, pro každou jednotkovou matrici $U $, a poskytnout tak matrici, která definuje dva výsledky měření v jeho $ \Pm $1 eigenvectors.</span><span class="sxs-lookup"><span data-stu-id="56f8b-122">This is to say that we could also consider matrix $A=U^\dagger Z U$, for any unitary matrix $U$, to give a matrix that defines the two outcomes of a measurement in its $\pm 1$ eigenvectors.</span></span>  <span data-ttu-id="56f8b-123">Zápis měření Pauli odkazuje na to tím, že identifikuje $X, Y, Z $ měření jako ekvivalentní měření, které může získat informace z qubit.</span><span class="sxs-lookup"><span data-stu-id="56f8b-123">The notation of Pauli measurements references this by identifying $X,Y,Z$ measurements as equivalent measurements that one could do to gain information from a qubit.</span></span>  <span data-ttu-id="56f8b-124">Tato měření jsou uvedena níže pro usnadnění práce.</span><span class="sxs-lookup"><span data-stu-id="56f8b-124">These measurements are given below for convenience.</span></span>

<span data-ttu-id="56f8b-125">$ $ \begin{Array}{| c | c |} \text{Pauli měření} & U\\\\ Z & \boldone\\\\ X & H\\\\ a & HS ^ \dagger\\\\ \end{Array} $ $</span><span class="sxs-lookup"><span data-stu-id="56f8b-125">$$ \begin{array}{|c|c|} \text{Pauli Measurement} & U\\\\ Z & \boldone\\\\ X & H\\\\ Y & HS^\dagger\\\\ \end{array} $$</span></span>

<span data-ttu-id="56f8b-126">To znamená, že s použitím tohoto jazyka je "Measure $Y $" ekvivalentem použití $HS ^ \dagger $ a pak se měří v výpočetních intervalech, kde $S $ je fáze s názvem, která se nazývá.</span><span class="sxs-lookup"><span data-stu-id="56f8b-126">That is, using this language, "measure $Y$" is equivalent to applying $HS^\dagger$ and then measuring in the computational basis, where $S$ is the so-called phase gate given by</span></span>

<span data-ttu-id="56f8b-127">$ $ \begin{bmatrix}1 & 0\\\\ 0 & i\end {bmatrix}.</span><span class="sxs-lookup"><span data-stu-id="56f8b-127">$$ \begin{bmatrix}1 &0\\\\  0&i\end{bmatrix}.</span></span>
$$

<span data-ttu-id="56f8b-128">Je také ekvivalentní použít $HS ^ \dagger $ na vektor stavu a pak na měření $Z $.</span><span class="sxs-lookup"><span data-stu-id="56f8b-128">It is also equivalent to applying $HS^\dagger$ to the quantum state vector and then measuring $Z$.</span></span>  <span data-ttu-id="56f8b-129">Správný stav by se pak našel tak, že transformuje zpátky na výpočetní základ, který se použije k použití $SH $ na vektor stavu.</span><span class="sxs-lookup"><span data-stu-id="56f8b-129">The correct state would then be found by transforming back to the computational basis, which amounts to applying $SH$ to the quantum state vector.</span></span>

## <a name="q-outcome-classical-information-obtained-from-quantum-state"></a><span data-ttu-id="56f8b-130">Výsledky z nestavových souborů Q # byly získány z nepotřebného stavu</span><span class="sxs-lookup"><span data-stu-id="56f8b-130">Q# outcome classical information obtained from quantum state</span></span>
<span data-ttu-id="56f8b-131">V Q # říkáme výsledek, tj. klasické informace extrahované z interakce se stavem, jsou $j $, který je v sadě $\{0, 1\}$, pokud je výsledek v $ (-1) ^ j $ eigenspace operátoru Pauli.</span><span class="sxs-lookup"><span data-stu-id="56f8b-131">In Q# we say the outcome, i.e., the classical information extracted from interacting with the state, is $j$ which is in the set $\{0,1\}$ if the result is in the $(-1)^j$ eigenspace of the Pauli operator measured.</span></span>

<span data-ttu-id="56f8b-132">Měření qubitch operátorů Pauli je definováno podobně, jak je vidět na základě těchto možností:</span><span class="sxs-lookup"><span data-stu-id="56f8b-132">Measurements of multi-qubit Pauli operators are defined similarly, as seen from:</span></span>

<span data-ttu-id="56f8b-133">$ $ Z\otimes Z = \begin{bmatrix}1 & 0 & 0 & 0\\\\ 0 &-1 & 0 & 0\\\\ 0 & 0 &-1 & 0\\\\ 0 & 0 & 0 & 1 \ konec {bmatrix}.</span><span class="sxs-lookup"><span data-stu-id="56f8b-133">$$ Z\otimes Z = \begin{bmatrix}1 &0 &0&0\\\\  0&-1&0&0\\\\ 0&0&-1&0\\\\ 0&0&0&1\end{bmatrix}.</span></span>
$$

<span data-ttu-id="56f8b-134">Proto tensor produkty dvou operátorů Pauli-$Z $ tvoří matici tvořenou dvěma mezerami, které se skládají z $ + $1 a $-$1 eigenvalues.</span><span class="sxs-lookup"><span data-stu-id="56f8b-134">Thus the tensor products of two Pauli-$Z$ operators forms a matrix composed of two spaces consisting of $+1$ and $-1$ eigenvalues.</span></span>  <span data-ttu-id="56f8b-135">Stejně jako u jediného qubit, představuje obojí prostor, což znamená, že polovina přístupného vektorového prostoru patří do $ + $1 eigenspace a zbylé polovině k $-$1 eigenspace.</span><span class="sxs-lookup"><span data-stu-id="56f8b-135">As with the single-qubit case, both constitute a half-space meaning that half of the accessible vector space belongs to the $+1$ eigenspace and the remaining half to the $-1$ eigenspace.</span></span>  <span data-ttu-id="56f8b-136">Obecně se dá snadno zobrazit z definice tensor produktu, že se jedná o tensor produkt Pauli-$Z $ a identitu taky dodržuje tyto informace.</span><span class="sxs-lookup"><span data-stu-id="56f8b-136">In general, it is easy to see from the definition of the tensor product that any tensor product of Pauli-$Z$ operators and the identity also obeys this.</span></span>  <span data-ttu-id="56f8b-137">Například:</span><span class="sxs-lookup"><span data-stu-id="56f8b-137">For example,</span></span>

<span data-ttu-id="56f8b-138">$ $ Z\otimes\boldone = \begin{bmatrix} 1 & 0 & 0 & 0\\\\ 0 & 1 & 0 & 0\\\\ 0 & 0 &-1 & 0\\\\ 0 & 0 & 0 &-1 \ konec {bmatrix}.</span><span class="sxs-lookup"><span data-stu-id="56f8b-138">$$ Z\otimes\boldone=\begin{bmatrix} 1&0&0&0\\\\  0&1&0&0\\\\  0&0&-1&0\\\\ 0&0&0&-1\end{bmatrix}.</span></span>
$$

<span data-ttu-id="56f8b-139">Stejně jako v případě jakékoli jakékoli jednotkové transformace těchto matic také popisuje dvě poloviční prostory označené pomocí $ \Pm $1 eigenvalues.</span><span class="sxs-lookup"><span data-stu-id="56f8b-139">As before, any unitary transformation of such matrices also describes two half-spaces labeled by $\pm 1$ eigenvalues.</span></span>  <span data-ttu-id="56f8b-140">Například $X \otimes X = H\otimes H (Z\otimes Z) H\otimes H $ z identity, která $Z = HXH $.</span><span class="sxs-lookup"><span data-stu-id="56f8b-140">For example, $X\otimes X = H\otimes H(Z\otimes Z)H\otimes H$  from the identity that $Z=HXH$.</span></span>  <span data-ttu-id="56f8b-141">Podobně jako u qubitového případu můžete všechna qubit Pauli-měření zapsat jako $U ^ \dagger (Z\otimes \id) U $ pro $4 \ krát $4 jednotkových matric $U $.</span><span class="sxs-lookup"><span data-stu-id="56f8b-141">Similar to the one-qubit case, all two-qubit Pauli-measurements can be written as $U^\dagger (Z\otimes \id) U$ for $4\times 4$ unitary matrices $U$.</span></span>  <span data-ttu-id="56f8b-142">Vyčíslení transformací v následující tabulce, kde zavádíme pro usnadnění práce s bránou pro zahození, která zaměňuje qubits $0 $ a $1 $: $ \operatorname{SWAP} = \operatorname{CNOT}\_{01}\operatorname{CNOT}\_{10}\operatorname{ CNOT}\_{01}$:</span><span class="sxs-lookup"><span data-stu-id="56f8b-142">We enumerate the transformations in the following table where we introduce for convenience the swap gate which swaps qubits $0$ and $1$: $\operatorname{SWAP}=\operatorname{CNOT}\_{01}\operatorname{CNOT}\_{10}\operatorname{CNOT}\_{01}$:</span></span>

<span data-ttu-id="56f8b-143">$ $ \begin{Array}{| c | c |} \text{Pauli měření} & U\\\\ \hline Z\otimes \boldone & \boldone\otimes \boldone\\\\ X\otimes \boldone & H\otimes \boldone\\\\ Y\otimes \boldone & HS ^ \dagger\ otimes \boldone\\\\ \boldone \otimes Z & \operatorname{SWAP}\\\\ \boldone \otimes X & (H\otimes \boldone) \operatorname{SWAP}\\\\ \boldone \otimes Y & (HS ^ \dagger\otimes \boldone) \ operator {SWAP}\\\\ Z\otimes Z & \operatorname{CNOT}\_{10}\\\\ X\otimes Z & \operatorname{CNOT}\_{10}(H\otimes \boldone)\\\\ Y\otimes Z & \ operator {CNOT}\_{10}(HS ^ \dagger\otimes \boldone)\\\\ Z\otimes X & \operatorname{CNOT}\_{10}(\boldone\otimes H)\\\\ X\otimes X & \operatorname{CNOT}\_@no__t _31_ (H\otimes H)\\\\ Y\otimes X & \operatorname{CNOT}\_{10}(HS ^ \dagger\otimes H)\\\\ Z\otimes Y & \operatorname{CNOT}\_{10}(\boldone \otimes HS ^ \dagger)\\\\ X\otimes Y & \operatorname{CNOT}\_{10}(H\otimes HS ^ \dagger)\\\\ Y\otimes Y & \operatorname{CNOT}\_{10}(HS ^ \dagger\otimes HS ^ \dagger)\\\\ \end{Array} $ $</span><span class="sxs-lookup"><span data-stu-id="56f8b-143">$$ \begin{array}{|c|c|} \text{Pauli Measurement} & U\\\\ \hline Z\otimes \boldone & \boldone\otimes \boldone\\\\ X\otimes \boldone & H\otimes \boldone\\\\ Y\otimes \boldone & HS^\dagger\otimes \boldone\\\\ \boldone \otimes Z & \operatorname{SWAP}\\\\ \boldone \otimes X & (H\otimes \boldone)\operatorname{SWAP}\\\\ \boldone \otimes Y & (HS^\dagger\otimes \boldone)\operatorname{SWAP}\\\\ Z\otimes Z & \operatorname{CNOT}\_{10}\\\\ X\otimes Z & \operatorname{CNOT}\_{10}(H\otimes \boldone)\\\\ Y\otimes Z & \operatorname{CNOT}\_{10}(HS^\dagger\otimes \boldone)\\\\ Z\otimes X & \operatorname{CNOT}\_{10}(\boldone\otimes H)\\\\ X\otimes X & \operatorname{CNOT}\_{10}(H\otimes H)\\\\ Y\otimes X & \operatorname{CNOT}\_{10}(HS^\dagger\otimes H)\\\\ Z\otimes Y & \operatorname{CNOT}\_{10}(\boldone \otimes HS^\dagger)\\\\ X\otimes Y & \operatorname{CNOT}\_{10}(H\otimes HS^\dagger)\\\\ Y\otimes Y & \operatorname{CNOT}\_{10}(HS^\dagger\otimes HS^\dagger)\\\\ \end{array} $$</span></span>

<span data-ttu-id="56f8b-144">Z následujícího důvodu se zobrazí okno Brána $ \operatorname{CNOT}\_{10}$.</span><span class="sxs-lookup"><span data-stu-id="56f8b-144">Here the gate $\operatorname{CNOT}\_{10}$ appears for the following reason.</span></span>  <span data-ttu-id="56f8b-145">Každé měření Pauli, které neobsahuje matrici $ \boldone $, je ekvivalentní až s jednou jednotkou $Z \otimes Z $ výše uvedenými důvody.</span><span class="sxs-lookup"><span data-stu-id="56f8b-145">Each Pauli measurement that does not include the $\boldone$ matrix is equivalent up to a unitary to $Z\otimes Z$ by the above reasoning.</span></span>  <span data-ttu-id="56f8b-146">Eigenvalues $Z \otimes Z $ závisí pouze na paritě qubits, která zahrnuje každý výpočetní vektor a kontrolované – nečinnosti, které se zobrazují v tomto seznamu, k výpočtu této parity a jejich uložení v prvním bitu.</span><span class="sxs-lookup"><span data-stu-id="56f8b-146">The eigenvalues of $Z\otimes Z$ only depend on the parity of the qubits that comprise each computational basis vector and the controlled-not operations that appear in this list serve to compute this parity and store it in the first bit.</span></span>  <span data-ttu-id="56f8b-147">Po měření prvního bitu můžeme obnovit identitu výsledného prostoru, který je ekvivalentní k měření Pauli operátoru.</span><span class="sxs-lookup"><span data-stu-id="56f8b-147">Then once the first bit is measured, we can recover the identity of the resultant half-space which is equivalent to measuring the Pauli operator.</span></span>

<span data-ttu-id="56f8b-148">Jedna další Poznámka, i když se může stát, že měření $Z \otimes Z $ je stejné jako měření $Z \otimes \id $ a pak $ \id \otimes Z $, tento předpoklad by byl nepravdivý.</span><span class="sxs-lookup"><span data-stu-id="56f8b-148">One additional note, while it may be tempting to assume that measuring $Z\otimes Z$ is the same as measuring $Z\otimes \id$ and then $\id \otimes Z$, this assumption would be false.</span></span>  <span data-ttu-id="56f8b-149">Důvodem je to, že měření $Z \otimes Z $ projekty se stavem do $ + $1 nebo $-$1 eigenstate těchto operátorů.</span><span class="sxs-lookup"><span data-stu-id="56f8b-149">The reason is that measuring $Z\otimes Z$ projects the quantum state into either the $+1$ or $-1$ eigenstate of these operators.</span></span>  <span data-ttu-id="56f8b-150">Měření $Z \otimes \id $ a pak $ \id \otimes Z $ projekty se vektorem stavu napředí na polovinu prostoru $Z \otimes \id $ a pak na poloviční prostor z $ \id \otimes Z $.</span><span class="sxs-lookup"><span data-stu-id="56f8b-150">Measuring $Z\otimes \id$ and then $\id \otimes Z$ projects the quantum state vector first onto a half space of $Z\otimes \id$ and then onto a half space of $\id \otimes Z$.</span></span>  <span data-ttu-id="56f8b-151">Vzhledem k tomu, že jsou k dispozici čtyři výpočetní vektory, může použití obou měření snížit stav na čtvrtinové místo a tím se sníží na jeden vektor výpočetního základu.</span><span class="sxs-lookup"><span data-stu-id="56f8b-151">As there are four computational basis vectors, performing both measurements reduces the state to a quarter-space and hence reduces it to a single computational basis vector.</span></span>


## <a name="correlations-between-qubits"></a><span data-ttu-id="56f8b-152">Korelace mezi qubits</span><span class="sxs-lookup"><span data-stu-id="56f8b-152">Correlations between qubits</span></span>
<span data-ttu-id="56f8b-153">Další možností, jak se podívat na měření tensor produktů Paul, například $X \otimes X $ nebo $Z \otimes Z $, je, že tato měření vám umožní podívat se na informace, které jsou uložené v korelaci mezi dvěma qubitsy.</span><span class="sxs-lookup"><span data-stu-id="56f8b-153">Another way of looking at measuring tensor products of Paulis such as $X\otimes X$ or $Z\otimes Z$ is that these measurements let you look at information stored in the correlations between the two qubits.</span></span>  <span data-ttu-id="56f8b-154">Měření $X \otimes \id $ vám umožní podívat se na informace, které jsou místně uložené v prvním qubit.</span><span class="sxs-lookup"><span data-stu-id="56f8b-154">Measuring $X\otimes \id$ lets you look at information that is locally stored in the first qubit.</span></span>  <span data-ttu-id="56f8b-155">I když jsou oba typy měření stejně cenné při práci ve výpočetním prostředí, bývalé osvětlení síly při práci.</span><span class="sxs-lookup"><span data-stu-id="56f8b-155">While both types of measurements are equally valuable in quantum computing, the former illuminates the power of quantum computing.</span></span> <span data-ttu-id="56f8b-156">To znamená, že v případě velmi náročného výpočetního prostředí se informace, které chcete vědět, neukládají do žádného qubit, ale místo toho, aby se ukládaly do všech qubits najednou, a jenom tak, že je prohlížíte pomocí společného měření s $Z \otimes Z $ se tyto informace stanou zřetel.</span><span class="sxs-lookup"><span data-stu-id="56f8b-156">It reveals that in quantum computing often the information you wish to learn is not stored in any single qubit but rather stored non-locally in all the qubits at once, and only by looking at it through a joint measurement with $Z\otimes Z$ does this information become manifest.</span></span>

<span data-ttu-id="56f8b-157">Lze také změřit libovolné Pauli operátory, jako je například $X \otimes Y \otimes Z \otimes \boldone $.</span><span class="sxs-lookup"><span data-stu-id="56f8b-157">Arbitrary Pauli operators such as $X\otimes Y \otimes Z \otimes \boldone$ can also be measured.</span></span>  <span data-ttu-id="56f8b-158">Všechny takové produkty tensor operátorů Pauli mají pouze dva eigenvalues $ \Pm $1 a oba eigenspaces představují poloviční prostory celého vektorového prostoru.</span><span class="sxs-lookup"><span data-stu-id="56f8b-158">All such tensor products of Pauli operators have only two eigenvalues $\pm 1$ and both eigenspaces constitute half-spaces of the entire vector space.</span></span>  <span data-ttu-id="56f8b-159">Proto se shodují s výše uvedenými požadavky.</span><span class="sxs-lookup"><span data-stu-id="56f8b-159">Thus they coincide with the requirements stated above.</span></span>

<span data-ttu-id="56f8b-160">V Q # taková měření vrací $j $, pokud měření vyplývají z výsledku eigenspace Sign $ (-1) ^ j $.</span><span class="sxs-lookup"><span data-stu-id="56f8b-160">In Q#, such measurements return $j$ if the measurement yields a result in the eigenspace of sign $(-1)^j$.</span></span>  <span data-ttu-id="56f8b-161">To je užitečné v případě, že je předdefinovaná funkce v Q # užitečná, protože měření takových operátorů vyžaduje dlouhé řetězy řízených a nevratných operací a základní transformace, které popisují diagonalizingou bránu $U $, která je potřeba k tomu, aby se operace mohla vyjádřit jako tensor $Z $ a $ \id $.</span><span class="sxs-lookup"><span data-stu-id="56f8b-161">Having this as a built-in feature in Q# is helpful because measuring such operators requires long chains of controlled-NOT gates and basis transformations to describe the diagonalizing $U$ gate needed to express the operation as a tensor product of $Z$ and $\id$.</span></span>  <span data-ttu-id="56f8b-162">Když jednoduše určíte, že chcete provést jedno z těchto předdefinovaných měření, nemusíte si dělat starosti s tím, jak transformovat svůj základ, aby měření na základě výpočtů poskytovalo potřebné informace.</span><span class="sxs-lookup"><span data-stu-id="56f8b-162">By simply being able to specify that you wish to do one of these pre-defined measurements, you don't need to worry about how to transform your basis such that a computational basis measurement provides the necessary information.</span></span>  <span data-ttu-id="56f8b-163">Q # zpracovává všechny potřebné transformace automaticky pro vás.</span><span class="sxs-lookup"><span data-stu-id="56f8b-163">Q# handles all the necessary basis transformations for you automatically.</span></span> <span data-ttu-id="56f8b-164">Pauli měření najdete v tématu [Referenční dokumentace knihovny Q #](/qsharp/api/canon/microsoft.quantum.canon.measurepaulis)</span><span class="sxs-lookup"><span data-stu-id="56f8b-164">See [Q# library reference for Pauli measurements](/qsharp/api/canon/microsoft.quantum.canon.measurepaulis)</span></span>

## <a name="the-no-cloning-theorem"></a><span data-ttu-id="56f8b-165">Věta bez klonování</span><span class="sxs-lookup"><span data-stu-id="56f8b-165">The No-Cloning Theorem</span></span>
<span data-ttu-id="56f8b-166">Informace o nemocném případě jsou výkonné.</span><span class="sxs-lookup"><span data-stu-id="56f8b-166">Quantum information is powerful.</span></span>  <span data-ttu-id="56f8b-167">Umožňuje nám dělat úžasné věci, jako jsou čísla faktorů exponenciálně rychleji než nejlepší známé klasické algoritmy, nebo efektivně simulovat korelační elektronické systémy, které Classic potřebují k přesnému simulaci exponenciálních nákladů.</span><span class="sxs-lookup"><span data-stu-id="56f8b-167">It enables us to do amazing things such as factor numbers exponentially faster than the best known classical algorithms, or efficiently simulate correlated electron systems that classically require exponential cost to simulate accurately.</span></span>  <span data-ttu-id="56f8b-168">Existují však určitá omezení výkonu s využitím nároku na výpočetní výkon.</span><span class="sxs-lookup"><span data-stu-id="56f8b-168">However, there are limitations to the power of quantum computing.</span></span>  <span data-ttu-id="56f8b-169">Jedno takové omezení je dáno *větaem bez klonování*.</span><span class="sxs-lookup"><span data-stu-id="56f8b-169">One such limitation is given by the *No-Cloning Theorem*.</span></span>

<span data-ttu-id="56f8b-170">Věta pro No-klonování není aptly pojmenováno.</span><span class="sxs-lookup"><span data-stu-id="56f8b-170">The No-Cloning Theorem is aptly named.</span></span>
<span data-ttu-id="56f8b-171">Neumožňuje klonování obecných stavových stavů počítačem s více než jednou.</span><span class="sxs-lookup"><span data-stu-id="56f8b-171">It disallows cloning of generic quantum states by a quantum computer.</span></span>
<span data-ttu-id="56f8b-172">Důkaz věta je výjimečně přímočarý.</span><span class="sxs-lookup"><span data-stu-id="56f8b-172">The proof of the theorem is remarkably straightforward.</span></span>
<span data-ttu-id="56f8b-173">I když je úplný důkaz větaa bez klonování pro naši diskuzi příliš technický, důkaz o věta v případě, že v daném počítači neplatí žádné další ancilla qubits, je v rámci našeho oboru (ancilla qubits jsou qubits použité pro úplně novou. místo během výpočtu a snadno se používá a spravuje v Q #, viz <xref:microsoft.quantum.techniques.qubits>).</span><span class="sxs-lookup"><span data-stu-id="56f8b-173">While a full proof of the no-cloning theorem is a little too technical for our discussion here, the proof of the theorem in the case where the quantum computer in question has no additional ancilla qubits is within our scope (ancilla qubits are qubits used for scratch space during a computation and are easily used and managed in Q#, see <xref:microsoft.quantum.techniques.qubits>).</span></span>
<span data-ttu-id="56f8b-174">V případě takového počítače s více operačními systémem musí být operace klonování jednotnou maticí.</span><span class="sxs-lookup"><span data-stu-id="56f8b-174">For such a quantum computer, the cloning operation must be a unitary matrix.</span></span> <span data-ttu-id="56f8b-175">Nezakážeme měření, protože by došlo k poškození stavu, který se snažíme klonovat.</span><span class="sxs-lookup"><span data-stu-id="56f8b-175">We disallow measurement, since it would corrupt the quantum state we are trying to clone.</span></span> <span data-ttu-id="56f8b-176">Jednotná matice musí mít vlastnost, kterou má $ $ U \ket{\psi} \ket{0} = \ket{\psi} \ket{\psi}, $ $ for any State $ \ket{\psi} $.</span><span class="sxs-lookup"><span data-stu-id="56f8b-176">The unitary matrix we want must have the property that $$ U \ket{\psi} \ket{0} = \ket{\psi} \ket{\psi}, $$ for any state $\ket{\psi}$.</span></span>
<span data-ttu-id="56f8b-177">Vlastnost linearity matice násobení pak znamená, že pro jakýkoliv druhý stav 2 – 2 \ket{\phi} $,</span><span class="sxs-lookup"><span data-stu-id="56f8b-177">The linearity property of matrix multiplication then implies that for any second quantum state $\ket{\phi}$,</span></span>

<span data-ttu-id="56f8b-178">\begin{align} & U\left [\frac{1}{\sqrt{2}} \left (\ket{\phi} + \ket{\psi} \right) \right] \ket{0}= \frac{1}{\sqrt{2}} U\ket {\ fí} \ KET{0}+ \frac{1}{\sqrt{2}} U\ket {\ psí} \ KET{0}@no__ t_9_ \\ & \qquad\qquad = \frac{1}{\sqrt{2}} \left (\ket{\phi}\ket{\phi} + \ket{\psi}\ket{\psi}\right)\\\\ & \qquad\qquad\ne \left (\frac{1}{\sqrt{2}} \left (\ket{\phi} + \ket{\psi} \ Right) \right) \otimes\left (\frac{1}{\sqrt{2}} \left (\ket{\phi} + \ket{\psi} \right) \right).</span><span class="sxs-lookup"><span data-stu-id="56f8b-178">\begin{align} &U\left[\frac{1}{\sqrt{2}}\left(\ket{\phi}+\ket{\psi} \right)\right]\ket{0}=\frac{1}{\sqrt{2}}U\ket{\phi}\ket{0}+\frac{1}{\sqrt{2}}U\ket{\psi}\ket{0}\\\\ &\qquad\qquad=\frac{1}{\sqrt{2}}\left(\ket{\phi}\ket{\phi}+\ket{\psi}\ket{\psi}\right)\\\\ &\qquad\qquad\ne \left(\frac{1}{\sqrt{2}}\left(\ket{\phi}+\ket{\psi} \right)\right)\otimes\left(\frac{1}{\sqrt{2}}\left(\ket{\phi}+\ket{\psi} \right)\right).</span></span>
<span data-ttu-id="56f8b-179">\end{align}</span><span class="sxs-lookup"><span data-stu-id="56f8b-179">\end{align}</span></span>

<span data-ttu-id="56f8b-180">To poskytuje základní Intuition za věta bez klonování: každé zařízení, které kopíruje neznámý stav, musí způsobit chyby alespoň u některých stavů, které kopíruje.</span><span class="sxs-lookup"><span data-stu-id="56f8b-180">This provides the fundamental intuition behind the No-Cloning Theorem: any device that copies an unknown quantum state must induce errors on at least some of the states it copies.</span></span>  <span data-ttu-id="56f8b-181">I když klíč předpokládá, že Cloner funguje lineárně na vstupním stavu, může být porušená přidáním ancilla a měřením ancilla qubits. Tyto interakce také zakládají informace o systému prostřednictvím statistik měření a zabraňují přesné klonování v takových případech také.</span><span class="sxs-lookup"><span data-stu-id="56f8b-181">While the key assumption that the cloner acts linearly on the input state can be violated through the addition of ancilla and measurement of the ancilla qubits, such interactions also leak information about the system through the measurement statistics and prevent exact cloning in such cases as well.</span></span>  <span data-ttu-id="56f8b-182">Další [informace](xref:microsoft.quantum.more-information)o tom, jak se věta bez klonování, najdete v tématu.</span><span class="sxs-lookup"><span data-stu-id="56f8b-182">For a more complete proof of the No-Cloning Theorem see [For more information](xref:microsoft.quantum.more-information).</span></span>

<span data-ttu-id="56f8b-183">Věta bez klonování je důležité pro kvalitativní porozumění výpočetním procesorům, protože pokud byste mohli naklonovat stavy nenákladných stavových procesorů, pak by vám byla udělena téměř Magical možnost učit se ze států.</span><span class="sxs-lookup"><span data-stu-id="56f8b-183">The No-Cloning Theorem is important for qualitative understanding of quantum computing because if you could clone quantum states inexpensively then you would be granted a near-magical ability to learn from quantum states.</span></span>  <span data-ttu-id="56f8b-184">Ve skutečnosti byste mohli narušit zásadu nejistoty Heisenberg vaunted.</span><span class="sxs-lookup"><span data-stu-id="56f8b-184">Indeed, you could violate Heisenberg's vaunted uncertainty principle.</span></span>  <span data-ttu-id="56f8b-185">Alternativně můžete použít optimální Cloner k získání jedné ukázky ze složitosti distribuce nečinnosti a zjistit všechno, co byste se mohli dozvědět o této distribuci jenom z jedné ukázky.</span><span class="sxs-lookup"><span data-stu-id="56f8b-185">Alternatively, you could use an optimal cloner to take a single sample from a complex quantum distribution and learn everything you could possibly learn about that distribution from just one sample.</span></span>  <span data-ttu-id="56f8b-186">To by vypadalo jako převrácení mince a pozorování hlav a následného oznámení o tom, že na výsledek má odpovědět "Ah. rozdělení této mince musí být Bernoulliho s $p = 0.512643 \ ldots $!"</span><span class="sxs-lookup"><span data-stu-id="56f8b-186">This would be like you flipping a coin and observing heads and then upon telling a friend about the result having them respond "Ah the distribution of that coin must be Bernoulli with $p=0.512643\ldots$!"</span></span>  <span data-ttu-id="56f8b-187">Takový příkaz by nebyl sensical, protože jeden z bitových informací (výsledek hlav) jednoduše nemůže poskytnout mnoho informací potřebných ke kódování distribuce bez podstatných předchozích informací.</span><span class="sxs-lookup"><span data-stu-id="56f8b-187">Such a statement would be non-sensical because one bit of information (the heads outcome) simply cannot provide the many bits of information needed to encode the distribution without substantial prior information.</span></span>  <span data-ttu-id="56f8b-188">Podobně bez předchozích informací nemůžeme zcela klonovat stav, protože nemůžeme připravit komplet těchto mincí bez znalosti $p $.</span><span class="sxs-lookup"><span data-stu-id="56f8b-188">Similarly, without prior information we cannot perfectly clone a quantum state just as we cannot prepare an ensemble of such coins without knowing $p$.</span></span>

<span data-ttu-id="56f8b-189">Informace nejsou v výpočetním prostředí bezplatné.</span><span class="sxs-lookup"><span data-stu-id="56f8b-189">Information is not free in quantum computing.</span></span>  <span data-ttu-id="56f8b-190">Každá qubit měřená má jedinou bitovou informaci a věta bez klonování ukazuje, že není k dispozici žádné zadní vrátka, které by bylo možné zneužít k získání základních kompromisů mezi informacemi získanými v systému a vyvolaným poruchou.</span><span class="sxs-lookup"><span data-stu-id="56f8b-190">Each qubit measured gives a single bit of information, and the No-Cloning Theorem shows that there is no backdoor that can be exploited to get around the fundamental tradeoff between information gained about the system and the disturbance invoked upon it.</span></span>
