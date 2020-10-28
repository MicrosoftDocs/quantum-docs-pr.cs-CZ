---
uid: Microsoft.Quantum.Research.Chemistry._DeltaParityCNOTbitstring
title: _DeltaParityCNOTbitstring funkce
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Research.Chemistry
qsharp.name: _DeltaParityCNOTbitstring
qsharp.summary: Classical processing step of `ApplyDeltaParity`. This computes a list of control qubits for evaluating parity difference between any two PQRS... terms of even length.
ms.openlocfilehash: 95b4c2df05f32cb937ec2cf421f43f2fdbf319da
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92697545"
---
# <a name="_deltaparitycnotbitstring-function"></a><span data-ttu-id="c06bc-102">_DeltaParityCNOTbitstring funkce</span><span class="sxs-lookup"><span data-stu-id="c06bc-102">_DeltaParityCNOTbitstring function</span></span>

<span data-ttu-id="c06bc-103">Obor názvů: [Microsoft. Prohledávejte. Research. chemie](xref:Microsoft.Quantum.Research.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="c06bc-103">Namespace: [Microsoft.Quantum.Research.Chemistry](xref:Microsoft.Quantum.Research.Chemistry)</span></span>

<span data-ttu-id="c06bc-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="c06bc-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="c06bc-105">Krok klasického zpracování `ApplyDeltaParity` .</span><span class="sxs-lookup"><span data-stu-id="c06bc-105">Classical processing step of `ApplyDeltaParity`.</span></span>
<span data-ttu-id="c06bc-106">Tato operace vypočítá seznam qubits ovládacího prvku pro vyhodnocení rozdílu parity mezi dvěma PQRS... stejné délky.</span><span class="sxs-lookup"><span data-stu-id="c06bc-106">This computes a list of control qubits for evaluating parity difference between any two PQRS... terms of even length.</span></span>

```qsharp
function _DeltaParityCNOTbitstring (prevFermionicTerm : Int[], nextFermionicTerm : Int[]) : (Int, Bool[])
```


## <a name="input"></a><span data-ttu-id="c06bc-107">Vstup</span><span class="sxs-lookup"><span data-stu-id="c06bc-107">Input</span></span>

### <a name="prevfermionicterm--int"></a><span data-ttu-id="c06bc-108">prevFermionicTerm: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="c06bc-108">prevFermionicTerm : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>




### <a name="nextfermionicterm--int"></a><span data-ttu-id="c06bc-109">nextFermionicTerm: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="c06bc-109">nextFermionicTerm : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>





## <a name="output--intbool"></a><span data-ttu-id="c06bc-110">Výstup: ([int](xref:microsoft.quantum.lang-ref.int),[bool](xref:microsoft.quantum.lang-ref.bool)[])</span><span class="sxs-lookup"><span data-stu-id="c06bc-110">Output : ([Int](xref:microsoft.quantum.lang-ref.int),[Bool](xref:microsoft.quantum.lang-ref.bool)[])</span></span>



## <a name="remarks"></a><span data-ttu-id="c06bc-111">Poznámky</span><span class="sxs-lookup"><span data-stu-id="c06bc-111">Remarks</span></span>

<span data-ttu-id="c06bc-112">To předpokládá, že délka podmínek je sudá.</span><span class="sxs-lookup"><span data-stu-id="c06bc-112">This assumes that the length of terms is even.</span></span>
<span data-ttu-id="c06bc-113">Vypočítá seznam ovládacích prvků pro rozdíly mezi dvěma podmínkami.</span><span class="sxs-lookup"><span data-stu-id="c06bc-113">Computes list of controls for parity difference between any two terms.</span></span>
<span data-ttu-id="c06bc-114">To předpokládá, že vstupní seznamy jsou seřazené ve vzestupném pořadí.</span><span class="sxs-lookup"><span data-stu-id="c06bc-114">This assumes that the input lists is sorted in ascending order.</span></span>