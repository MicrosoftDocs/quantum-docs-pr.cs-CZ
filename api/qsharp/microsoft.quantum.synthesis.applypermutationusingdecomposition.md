---
uid: Microsoft.Quantum.Synthesis.ApplyPermutationUsingDecomposition
title: Operace ApplyPermutationUsingDecomposition
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: ApplyPermutationUsingDecomposition
qsharp.summary: Permutes the amplitudes in a quantum state given a permutation using decomposition-based synthesis.
ms.openlocfilehash: 765b6d301363021f5b57a22f90e2ada38c9c09ec
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98857394"
---
# <a name="applypermutationusingdecomposition-operation"></a><span data-ttu-id="4dd48-102">Operace ApplyPermutationUsingDecomposition</span><span class="sxs-lookup"><span data-stu-id="4dd48-102">ApplyPermutationUsingDecomposition operation</span></span>

<span data-ttu-id="4dd48-103">Obor názvů: [Microsoft. Proshrnutí](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="4dd48-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="4dd48-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="4dd48-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="4dd48-105">Permutes amplitudy ve stavu, který má za následek permutaci s využitím syntézy založené na dekompozici.</span><span class="sxs-lookup"><span data-stu-id="4dd48-105">Permutes the amplitudes in a quantum state given a permutation using decomposition-based synthesis.</span></span>

```qsharp
operation ApplyPermutationUsingDecomposition (perm : Int[], qubits : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="4dd48-106">Popis</span><span class="sxs-lookup"><span data-stu-id="4dd48-106">Description</span></span>

<span data-ttu-id="4dd48-107">Tento postup implementuje postup syntézy založený na dekompozici.</span><span class="sxs-lookup"><span data-stu-id="4dd48-107">This procedure implements the decomposition based synthesis approach.</span></span>  <span data-ttu-id="4dd48-108">Vstup je permutace $ \pi $ over $2 ^ n $ elementy $ \{ 0, \dots, 2 ^ n-1 \} $, které představují funkci $n $-Variable vratné logické hodnoty.</span><span class="sxs-lookup"><span data-stu-id="4dd48-108">The input is a permutation $\pi$ over $2^n$ elements $\{0, \dots, 2^n-1\}$, which represents an $n$-variable reversible Boolean function.</span></span>
<span data-ttu-id="4dd48-109">Algoritmus iterativní provede následující kroky pro každý index proměnné $i $:</span><span class="sxs-lookup"><span data-stu-id="4dd48-109">The algorithm iteratively performs the following steps for each variable index $i$:</span></span>

1. <span data-ttu-id="4dd48-110">COMPUTE $ ((\ pi_l, \ pi_r), \pi ') $ tím, že obrázky $ \ pi_l $ a $ \ pi_r $ nemění bity ve svých prvcích v jiných rejstřících než $i $ a image $ \pi $ nemění bitovou $i $ ve svých prvcích.</span><span class="sxs-lookup"><span data-stu-id="4dd48-110">Compute $((\pi_l, \pi_r), \pi')$ such that the images of $\pi_l$ and $\pi_r$ do not change bits in their elements at indexes other than $i$ and images of $\pi'$ do not change bit $i$ in their elements.</span></span>
2. <span data-ttu-id="4dd48-111">Nastavte $ \pi \leftarrow \pi ' $ a odvodit pravdy tabulky z $ \ pi_l $ a $ \ pi_r $ na základě prvků, které nejsou pevnými body.</span><span class="sxs-lookup"><span data-stu-id="4dd48-111">Set $\pi \leftarrow \pi'$, and derive truth tables from $\pi_l$ and $\pi_r$ based on elements that are not fixed-points.</span></span>

<span data-ttu-id="4dd48-112">Po použití těchto kroků u všech indexů proměnných bude zbývající permutace $ \pi $ identita a na základě shromážděných tabulek a indexů pravdy může jedna použít operace kontrolované v tabulce s @"microsoft.quantum.intrinsic.x" použitím této @"microsoft.quantum.synthesis.applyxcontrolledontruthtable" operace.</span><span class="sxs-lookup"><span data-stu-id="4dd48-112">After applying these steps for all variable indexes, the remaining permutation $\pi$ will be the identity, and based on the collected truth tables and indexes, one can apply truth-table controlled @"microsoft.quantum.intrinsic.x" operations using the @"microsoft.quantum.synthesis.applyxcontrolledontruthtable" operation.</span></span>

<span data-ttu-id="4dd48-113">Proměnná pořadí je $0, \dots, n-$1.</span><span class="sxs-lookup"><span data-stu-id="4dd48-113">The variable order is $0, \dots, n - 1$.</span></span>  <span data-ttu-id="4dd48-114">V operaci lze zadat vlastní proměnnou pořadí @"microsoft.quantum.synthesis.applypermutationusingdecompositionwithvariableorder" .</span><span class="sxs-lookup"><span data-stu-id="4dd48-114">A custom variable order can be specified in the operation @"microsoft.quantum.synthesis.applypermutationusingdecompositionwithvariableorder".</span></span>

## <a name="input"></a><span data-ttu-id="4dd48-115">Vstup</span><span class="sxs-lookup"><span data-stu-id="4dd48-115">Input</span></span>

### <a name="perm--int"></a><span data-ttu-id="4dd48-116">Perm: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="4dd48-116">perm : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="4dd48-117">Permutace prvků $2 ^ n $ počínaje 0.</span><span class="sxs-lookup"><span data-stu-id="4dd48-117">A permutation of $2^n$ elements starting from 0.</span></span>


### <a name="qubits--littleendian"></a><span data-ttu-id="4dd48-118">qubits: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="4dd48-118">qubits : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="4dd48-119">Seznam $n $ qubits, na který se aplikuje permutace</span><span class="sxs-lookup"><span data-stu-id="4dd48-119">A list of $n$ qubits to which the permutation is applied to.</span></span>



## <a name="output--unit"></a><span data-ttu-id="4dd48-120">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="4dd48-120">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="example"></a><span data-ttu-id="4dd48-121">Příklad</span><span class="sxs-lookup"><span data-stu-id="4dd48-121">Example</span></span>

<span data-ttu-id="4dd48-122">Pro syntetizaci `SWAP` operace:</span><span class="sxs-lookup"><span data-stu-id="4dd48-122">To synthesize a `SWAP` operation:</span></span>

```qsharp
using (qubits = Qubit[2]) {
  ApplyPermutationUsingDecomposition([0, 2, 1, 3], LittleEndian(qubits));
}
```

## <a name="references"></a><span data-ttu-id="4dd48-123">Reference</span><span class="sxs-lookup"><span data-stu-id="4dd48-123">References</span></span>

- [<span data-ttu-id="4dd48-124">*Alexis de Vos*, *Yvan van Rentergem*, ADV. v Math. of comm. 2 (2), 2008, PP. 183--200</span><span class="sxs-lookup"><span data-stu-id="4dd48-124">*Alexis De Vos*, *Yvan Van Rentergem*, Adv. in Math. of Comm. 2(2), 2008, pp. 183--200</span></span>](http://www.aimsciences.org/article/doi/10.3934/amc.2008.2.183)
- [<span data-ttu-id="4dd48-125">*Mathias Soeken*, *Laura Tague*, *Gerhard W. Dueck*, *Rolf Drechsler*, deník symbolického výpočtu 73 (2016), PP. 1--26</span><span class="sxs-lookup"><span data-stu-id="4dd48-125">*Mathias Soeken*, *Laura Tague*, *Gerhard W. Dueck*, *Rolf Drechsler*, Journal of Symbolic Computation 73 (2016), pp. 1--26</span></span>](https://www.sciencedirect.com/science/article/pii/S0747717115000188?via%3Dihub)

## <a name="see-also"></a><span data-ttu-id="4dd48-126">Viz také</span><span class="sxs-lookup"><span data-stu-id="4dd48-126">See Also</span></span>

- [<span data-ttu-id="4dd48-127">Microsoft. proshrnutí. ApplyPermutationUsingDecompositionWithVariableOrder</span><span class="sxs-lookup"><span data-stu-id="4dd48-127">Microsoft.Quantum.Synthesis.ApplyPermutationUsingDecompositionWithVariableOrder</span></span>](xref:Microsoft.Quantum.Synthesis.ApplyPermutationUsingDecompositionWithVariableOrder)
- [<span data-ttu-id="4dd48-128">Microsoft. proshrnutí. ApplyPermutationUsingTransformation</span><span class="sxs-lookup"><span data-stu-id="4dd48-128">Microsoft.Quantum.Synthesis.ApplyPermutationUsingTransformation</span></span>](xref:Microsoft.Quantum.Synthesis.ApplyPermutationUsingTransformation)