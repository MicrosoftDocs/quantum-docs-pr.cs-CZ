---
uid: Microsoft.Quantum.Simulation.IdxToUnitary
title: IdxToUnitary – funkce
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: IdxToUnitary
qsharp.summary: Used in implementation of `PauliBlockEncoding`
ms.openlocfilehash: dd13b2d2e846dcddb820599ea26aa25b90903dbd
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96229269"
---
# <a name="idxtounitary-function"></a><span data-ttu-id="e16e1-102">IdxToUnitary – funkce</span><span class="sxs-lookup"><span data-stu-id="e16e1-102">IdxToUnitary function</span></span>

<span data-ttu-id="e16e1-103">Obor názvů: [Microsoft.. simulace](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="e16e1-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="e16e1-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="e16e1-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="e16e1-105">Používá se v implementaci `PauliBlockEncoding`</span><span class="sxs-lookup"><span data-stu-id="e16e1-105">Used in implementation of `PauliBlockEncoding`</span></span>

```qsharp
function IdxToUnitary (idx : Int, genFun : (Int -> Microsoft.Quantum.Simulation.GeneratorIndex), genIdxToUnitary : (Microsoft.Quantum.Simulation.GeneratorIndex -> (Qubit[] => Unit is Adj + Ctl))) : (Qubit[] => Unit is Adj + Ctl)
```


## <a name="input"></a><span data-ttu-id="e16e1-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="e16e1-106">Input</span></span>

### <a name="idx--int"></a><span data-ttu-id="e16e1-107">IDX: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="e16e1-107">idx : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>




### <a name="genfun--int---generatorindex"></a><span data-ttu-id="e16e1-108">genFun: [int](xref:microsoft.quantum.lang-ref.int) -> [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="e16e1-108">genFun : [Int](xref:microsoft.quantum.lang-ref.int) -> [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>




### <a name="genidxtounitary--generatorindex---qubit--unit--is-adj--ctl"></a><span data-ttu-id="e16e1-109">genIdxToUnitary: [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex) -> [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [jednotka](xref:microsoft.quantum.lang-ref.unit)  je ADJ + CTL</span><span class="sxs-lookup"><span data-stu-id="e16e1-109">genIdxToUnitary : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex) -> [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>





## <a name="output--qubit--unit--is-adj--ctl"></a><span data-ttu-id="e16e1-110">Výstup: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [jednotka](xref:microsoft.quantum.lang-ref.unit)  je ADJ + CTL</span><span class="sxs-lookup"><span data-stu-id="e16e1-110">Output : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>



## <a name="see-also"></a><span data-ttu-id="e16e1-111">Viz také</span><span class="sxs-lookup"><span data-stu-id="e16e1-111">See Also</span></span>

- [<span data-ttu-id="e16e1-112">Microsoft. v. simulace. PauliBlockEncoding</span><span class="sxs-lookup"><span data-stu-id="e16e1-112">Microsoft.Quantum.Simulation.PauliBlockEncoding</span></span>](xref:Microsoft.Quantum.Simulation.PauliBlockEncoding)