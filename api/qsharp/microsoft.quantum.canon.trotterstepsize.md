---
uid: Microsoft.Quantum.Canon.TrotterStepSize
title: TrotterStepSize – funkce
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: TrotterStepSize
qsharp.summary: Computes Trotter step size in recursive implementation of Trotter simulation algorithm.
ms.openlocfilehash: fabfbff74572b3c96c701de5443e4265a0468d78
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92698796"
---
# <a name="trotterstepsize-function"></a><span data-ttu-id="38c38-102">TrotterStepSize – funkce</span><span class="sxs-lookup"><span data-stu-id="38c38-102">TrotterStepSize function</span></span>

<span data-ttu-id="38c38-103">Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="38c38-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="38c38-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="38c38-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="38c38-105">Vypočítá Trotter velikost kroku v rekurzivní implementaci Trotter algoritmu simulace.</span><span class="sxs-lookup"><span data-stu-id="38c38-105">Computes Trotter step size in recursive implementation of Trotter simulation algorithm.</span></span>

```qsharp
function TrotterStepSize (order : Int) : Double
```


## <a name="input"></a><span data-ttu-id="38c38-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="38c38-106">Input</span></span>

### <a name="order--int"></a><span data-ttu-id="38c38-107">pořadí: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="38c38-107">order : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>





## <a name="output--double"></a><span data-ttu-id="38c38-108">Výstup: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="38c38-108">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>



## <a name="remarks"></a><span data-ttu-id="38c38-109">Poznámky</span><span class="sxs-lookup"><span data-stu-id="38c38-109">Remarks</span></span>

<span data-ttu-id="38c38-110">Tato operace používá jinou konvenci indexování než [quant-pH/0508139](https://arxiv.org/abs/quant-ph/0508139).</span><span class="sxs-lookup"><span data-stu-id="38c38-110">This operation uses a different indexing convention than that of [quant-ph/0508139](https://arxiv.org/abs/quant-ph/0508139).</span></span> <span data-ttu-id="38c38-111">Konkrétně `DecomposedIntoTimeStepsCA(_, 4)` odpovídá skalární $p _2 (\lambda) $ in quant-pH/0508139.</span><span class="sxs-lookup"><span data-stu-id="38c38-111">In particular, `DecomposedIntoTimeStepsCA(_, 4)` corresponds to the scalar $p_2(\lambda)$ in quant-ph/0508139.</span></span>