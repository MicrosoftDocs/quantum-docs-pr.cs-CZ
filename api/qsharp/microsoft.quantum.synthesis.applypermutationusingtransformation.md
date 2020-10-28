---
uid: Microsoft.Quantum.Synthesis.ApplyPermutationUsingTransformation
title: Operace ApplyPermutationUsingTransformation
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: ApplyPermutationUsingTransformation
qsharp.summary: Permutes the amplitudes in a quantum state given a permutation using transformation-based synthesis.
ms.openlocfilehash: b7196c592690a00da49b17f52b30536ba97b6035
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92709202"
---
# <a name="applypermutationusingtransformation-operation"></a><span data-ttu-id="fd423-102">Operace ApplyPermutationUsingTransformation</span><span class="sxs-lookup"><span data-stu-id="fd423-102">ApplyPermutationUsingTransformation operation</span></span>

<span data-ttu-id="fd423-103">Obor názvů: [Microsoft. Proshrnutí](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="fd423-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="fd423-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="fd423-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="fd423-105">Permutes amplitudy ve stavu bez stavového pole s ohledem na permutaci pomocí syntézy založené na transformaci.</span><span class="sxs-lookup"><span data-stu-id="fd423-105">Permutes the amplitudes in a quantum state given a permutation using transformation-based synthesis.</span></span>

```qsharp
operation ApplyPermutationUsingTransformation (perm : Int[], qubits : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="description"></a><span data-ttu-id="fd423-106">Popis</span><span class="sxs-lookup"><span data-stu-id="fd423-106">Description</span></span>

<span data-ttu-id="fd423-107">Tento postup implementuje jednosměrný postup syntézy založený na transformaci.</span><span class="sxs-lookup"><span data-stu-id="fd423-107">This procedure implements the unidirectional transformation based synthesis approach.</span></span>  <span data-ttu-id="fd423-108">Vstup je permutace $ \pi $ over $2 ^ n $ elementy $ \{ 0, \dots, 2 ^ n-1 \} $, které představují funkci $n $-Variable vratné logické hodnoty.</span><span class="sxs-lookup"><span data-stu-id="fd423-108">Input is a permutation $\pi$ over $2^n$ elements $\{0, \dots, 2^n-1\}$, which represents an $n$-variable reversible Boolean function.</span></span>
<span data-ttu-id="fd423-109">Algoritmus provede iterativní provedení následujících kroků:</span><span class="sxs-lookup"><span data-stu-id="fd423-109">The algorithm performs iteratively the following steps:</span></span>

1. <span data-ttu-id="fd423-110">Najde nejmenší $x $ tak, že $x \Ne \pi (x) = y $.</span><span class="sxs-lookup"><span data-stu-id="fd423-110">Find smallest $x$ such that $x \ne \pi(x) = y$.</span></span>
2. <span data-ttu-id="fd423-111">Najděte více řízených Toffoli operací, které se aplikují na výstupy $ \pi (x) = x $ a neměňte $ \pi (x ') $ for All $x ' < x $</span><span class="sxs-lookup"><span data-stu-id="fd423-111">Find multiple-controlled Toffoli operations, which applied to the outputs make $\pi(x) = x$ and do not change $\pi(x')$ for all $x' < x$</span></span>

## <a name="input"></a><span data-ttu-id="fd423-112">Vstup</span><span class="sxs-lookup"><span data-stu-id="fd423-112">Input</span></span>

### <a name="perm--int"></a><span data-ttu-id="fd423-113">Perm: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="fd423-113">perm : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="fd423-114">Permutace prvků $2 ^ n $ počínaje 0.</span><span class="sxs-lookup"><span data-stu-id="fd423-114">A permutation of $2^n$ elements starting from 0.</span></span>


### <a name="qubits--littleendian"></a><span data-ttu-id="fd423-115">qubits: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="fd423-115">qubits : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="fd423-116">Seznam $n $ qubits, na který se aplikuje permutace</span><span class="sxs-lookup"><span data-stu-id="fd423-116">A list of $n$ qubits to which the permutation is applied to.</span></span>



## <a name="output--unit"></a><span data-ttu-id="fd423-117">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="fd423-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="references"></a><span data-ttu-id="fd423-118">Odkazy</span><span class="sxs-lookup"><span data-stu-id="fd423-118">References</span></span>

- [<span data-ttu-id="fd423-119">*D. Michael Miller* , *Dmitri Maslov* , *Gerhard W. Dueck* , proc. DAC 2003, IEEE, PP. 318-323, 2003</span><span class="sxs-lookup"><span data-stu-id="fd423-119">*D. Michael Miller* , *Dmitri Maslov* , *Gerhard W. Dueck* , Proc. DAC 2003, IEEE, pp. 318-323, 2003</span></span>](https://doi.org/10.1145/775832.775915)
- [<span data-ttu-id="fd423-120">*Mathias Soeken* , *Gerhard W. Dueck* , *D. Michael Miller* , proc. RC 2016, Springer, PP. 307-321, 2016</span><span class="sxs-lookup"><span data-stu-id="fd423-120">*Mathias Soeken* , *Gerhard W. Dueck* , *D. Michael Miller* , Proc. RC 2016, Springer, pp. 307-321, 2016</span></span>](https://doi.org/10.1007/978-3-319-40578-0_22)

## <a name="see-also"></a><span data-ttu-id="fd423-121">Viz také</span><span class="sxs-lookup"><span data-stu-id="fd423-121">See Also</span></span>

- [<span data-ttu-id="fd423-122">Microsoft. proshrnutí. ApplyPermutationUsingDecomposition</span><span class="sxs-lookup"><span data-stu-id="fd423-122">Microsoft.Quantum.Synthesis.ApplyPermutationUsingDecomposition</span></span>](xref:Microsoft.Quantum.Synthesis.ApplyPermutationUsingDecomposition)