---
uid: Microsoft.Quantum.Research.Chemistry._DeltaParityCNOTbitstring
title: _DeltaParityCNOTbitstring funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Research.Chemistry
qsharp.name: _DeltaParityCNOTbitstring
qsharp.summary: Classical processing step of `ApplyDeltaParity`. This computes a list of control qubits for evaluating parity difference between any two PQRS... terms of even length.
ms.openlocfilehash: 3dd2d299a094577d377780d731e76287815e8d03
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98847602"
---
# <a name="_deltaparitycnotbitstring-function"></a><span data-ttu-id="113fe-102">_DeltaParityCNOTbitstring funkce</span><span class="sxs-lookup"><span data-stu-id="113fe-102">_DeltaParityCNOTbitstring function</span></span>

<span data-ttu-id="113fe-103">Obor názvů: [Microsoft. Prohledávejte. Research. chemie](xref:Microsoft.Quantum.Research.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="113fe-103">Namespace: [Microsoft.Quantum.Research.Chemistry](xref:Microsoft.Quantum.Research.Chemistry)</span></span>

<span data-ttu-id="113fe-104">Balíček: [Microsoft. prostudoval. Research. chemie](https://nuget.org/packages/Microsoft.Quantum.Research.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="113fe-104">Package: [Microsoft.Quantum.Research.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Research.Chemistry)</span></span>


<span data-ttu-id="113fe-105">Krok klasického zpracování `ApplyDeltaParity` .</span><span class="sxs-lookup"><span data-stu-id="113fe-105">Classical processing step of `ApplyDeltaParity`.</span></span>
<span data-ttu-id="113fe-106">Tato operace vypočítá seznam qubits ovládacího prvku pro vyhodnocení rozdílu parity mezi dvěma PQRS... stejné délky.</span><span class="sxs-lookup"><span data-stu-id="113fe-106">This computes a list of control qubits for evaluating parity difference between any two PQRS... terms of even length.</span></span>

```qsharp
function _DeltaParityCNOTbitstring (prevFermionicTerm : Int[], nextFermionicTerm : Int[]) : (Int, Bool[])
```


## <a name="input"></a><span data-ttu-id="113fe-107">Vstup</span><span class="sxs-lookup"><span data-stu-id="113fe-107">Input</span></span>

### <a name="prevfermionicterm--int"></a><span data-ttu-id="113fe-108">prevFermionicTerm: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="113fe-108">prevFermionicTerm : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>




### <a name="nextfermionicterm--int"></a><span data-ttu-id="113fe-109">nextFermionicTerm: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="113fe-109">nextFermionicTerm : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>





## <a name="output--intbool"></a><span data-ttu-id="113fe-110">Výstup: ([int](xref:microsoft.quantum.lang-ref.int),[bool](xref:microsoft.quantum.lang-ref.bool)[])</span><span class="sxs-lookup"><span data-stu-id="113fe-110">Output : ([Int](xref:microsoft.quantum.lang-ref.int),[Bool](xref:microsoft.quantum.lang-ref.bool)[])</span></span>



## <a name="remarks"></a><span data-ttu-id="113fe-111">Poznámky</span><span class="sxs-lookup"><span data-stu-id="113fe-111">Remarks</span></span>

<span data-ttu-id="113fe-112">To předpokládá, že délka podmínek je sudá.</span><span class="sxs-lookup"><span data-stu-id="113fe-112">This assumes that the length of terms is even.</span></span>
<span data-ttu-id="113fe-113">Vypočítá seznam ovládacích prvků pro rozdíly mezi dvěma podmínkami.</span><span class="sxs-lookup"><span data-stu-id="113fe-113">Computes list of controls for parity difference between any two terms.</span></span>
<span data-ttu-id="113fe-114">To předpokládá, že vstupní seznamy jsou seřazené ve vzestupném pořadí.</span><span class="sxs-lookup"><span data-stu-id="113fe-114">This assumes that the input lists is sorted in ascending order.</span></span>