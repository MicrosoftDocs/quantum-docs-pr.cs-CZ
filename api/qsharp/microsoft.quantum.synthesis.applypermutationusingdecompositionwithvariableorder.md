---
uid: Microsoft.Quantum.Synthesis.ApplyPermutationUsingDecompositionWithVariableOrder
title: Operace ApplyPermutationUsingDecompositionWithVariableOrder
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: ApplyPermutationUsingDecompositionWithVariableOrder
qsharp.summary: Permutes the amplitudes in a quantum state given a permutation using decomposition-based synthesis.
ms.openlocfilehash: 1edbc0a2948fdf3ae67f14b3c552676feaa7f498
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92709207"
---
# <a name="applypermutationusingdecompositionwithvariableorder-operation"></a><span data-ttu-id="f8d82-102">Operace ApplyPermutationUsingDecompositionWithVariableOrder</span><span class="sxs-lookup"><span data-stu-id="f8d82-102">ApplyPermutationUsingDecompositionWithVariableOrder operation</span></span>

<span data-ttu-id="f8d82-103">Obor názvů: [Microsoft. Proshrnutí](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="f8d82-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="f8d82-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="f8d82-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="f8d82-105">Permutes amplitudy ve stavu, který má za následek permutaci s využitím syntézy založené na dekompozici.</span><span class="sxs-lookup"><span data-stu-id="f8d82-105">Permutes the amplitudes in a quantum state given a permutation using decomposition-based synthesis.</span></span>

```qsharp
operation ApplyPermutationUsingDecompositionWithVariableOrder (perm : Int[], variableOrder : Int[], qubits : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="description"></a><span data-ttu-id="f8d82-106">Popis</span><span class="sxs-lookup"><span data-stu-id="f8d82-106">Description</span></span>

<span data-ttu-id="f8d82-107">Tato operace je obecnější verze, @"microsoft.quantum.synthesis.applypermutationusingdecomposition" ve které lze určit pořadí proměnných.</span><span class="sxs-lookup"><span data-stu-id="f8d82-107">This operation is a more general version of @"microsoft.quantum.synthesis.applypermutationusingdecomposition" in which the variable order can be specified.</span></span> <span data-ttu-id="f8d82-108">Jiné pořadí proměnných změní pořadí rozkladu a tabulky pravdy používané pro řízené @"microsoft.quantum.intrinsic.x" brány.</span><span class="sxs-lookup"><span data-stu-id="f8d82-108">A different variable order changes the decomposition sequence and the truth tables used for the controlled @"microsoft.quantum.intrinsic.x" gates.</span></span>  <span data-ttu-id="f8d82-109">Proto změna pořadí proměnných změní počet všech bran používaných k realizaci permutace.</span><span class="sxs-lookup"><span data-stu-id="f8d82-109">Therefore, changing the variable order changes the number of overall gates used to realize the permutation.</span></span>

## <a name="input"></a><span data-ttu-id="f8d82-110">Vstup</span><span class="sxs-lookup"><span data-stu-id="f8d82-110">Input</span></span>

### <a name="perm--int"></a><span data-ttu-id="f8d82-111">Perm: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="f8d82-111">perm : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="f8d82-112">Permutace prvků $2 ^ n $ počínaje 0.</span><span class="sxs-lookup"><span data-stu-id="f8d82-112">A permutation of $2^n$ elements starting from 0.</span></span>


### <a name="variableorder--int"></a><span data-ttu-id="f8d82-113">variableOrder: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="f8d82-113">variableOrder : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="f8d82-114">Permutace $n $ prvků od 0.</span><span class="sxs-lookup"><span data-stu-id="f8d82-114">A permutation of $n$ elements starting from 0.</span></span>


### <a name="qubits--littleendian"></a><span data-ttu-id="f8d82-115">qubits: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="f8d82-115">qubits : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="f8d82-116">Seznam $n $ qubits, na který se aplikuje permutace</span><span class="sxs-lookup"><span data-stu-id="f8d82-116">A list of $n$ qubits to which the permutation is applied to.</span></span>



## <a name="output--unit"></a><span data-ttu-id="f8d82-117">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="f8d82-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="f8d82-118">Viz také</span><span class="sxs-lookup"><span data-stu-id="f8d82-118">See Also</span></span>

- [<span data-ttu-id="f8d82-119">Microsoft. proshrnutí. ApplyPermutationUsingDecomposition</span><span class="sxs-lookup"><span data-stu-id="f8d82-119">Microsoft.Quantum.Synthesis.ApplyPermutationUsingDecomposition</span></span>](xref:Microsoft.Quantum.Synthesis.ApplyPermutationUsingDecomposition)
- [<span data-ttu-id="f8d82-120">Microsoft. proshrnutí. ApplyPermutationUsingTransformation</span><span class="sxs-lookup"><span data-stu-id="f8d82-120">Microsoft.Quantum.Synthesis.ApplyPermutationUsingTransformation</span></span>](xref:Microsoft.Quantum.Synthesis.ApplyPermutationUsingTransformation)