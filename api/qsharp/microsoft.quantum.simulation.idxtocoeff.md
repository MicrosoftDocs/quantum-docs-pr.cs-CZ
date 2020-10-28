---
uid: Microsoft.Quantum.Simulation.IdxToCoeff
title: IdxToCoeff – funkce
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: IdxToCoeff
qsharp.summary: Used in implementation of `PauliBlockEncoding`
ms.openlocfilehash: 50e0c536b01cddb56482580fd634270c4e104173
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92708871"
---
# <a name="idxtocoeff-function"></a><span data-ttu-id="e967c-102">IdxToCoeff – funkce</span><span class="sxs-lookup"><span data-stu-id="e967c-102">IdxToCoeff function</span></span>

<span data-ttu-id="e967c-103">Obor názvů: [Microsoft.. simulace](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="e967c-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="e967c-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="e967c-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="e967c-105">Používá se v implementaci `PauliBlockEncoding`</span><span class="sxs-lookup"><span data-stu-id="e967c-105">Used in implementation of `PauliBlockEncoding`</span></span>

```qsharp
function IdxToCoeff (idx : Int, genFun : (Int -> Microsoft.Quantum.Simulation.GeneratorIndex), genIdxToCoeff : (Microsoft.Quantum.Simulation.GeneratorIndex -> Double)) : Double
```


## <a name="input"></a><span data-ttu-id="e967c-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="e967c-106">Input</span></span>

### <a name="idx--int"></a><span data-ttu-id="e967c-107">IDX: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="e967c-107">idx : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>




### <a name="genfun--int---generatorindex"></a><span data-ttu-id="e967c-108">genFun: [int](xref:microsoft.quantum.lang-ref.int) -> [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="e967c-108">genFun : [Int](xref:microsoft.quantum.lang-ref.int) -> [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>




### <a name="genidxtocoeff--generatorindex---double"></a><span data-ttu-id="e967c-109">genIdxToCoeff: [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex) -> [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="e967c-109">genIdxToCoeff : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex) -> [Double](xref:microsoft.quantum.lang-ref.double)</span></span>





## <a name="output--double"></a><span data-ttu-id="e967c-110">Výstup: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="e967c-110">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>



## <a name="see-also"></a><span data-ttu-id="e967c-111">Viz také</span><span class="sxs-lookup"><span data-stu-id="e967c-111">See Also</span></span>

- [<span data-ttu-id="e967c-112">Microsoft. v. simulace. PauliBlockEncoding</span><span class="sxs-lookup"><span data-stu-id="e967c-112">Microsoft.Quantum.Simulation.PauliBlockEncoding</span></span>](xref:Microsoft.Quantum.Simulation.PauliBlockEncoding)