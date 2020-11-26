---
uid: Microsoft.Quantum.Diagnostics._assertEqualOnBasisVector
title: operace _assertEqualOnBasisVector
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: _assertEqualOnBasisVector
qsharp.summary: Checks if the result of applying two operations `givenU` and `expectedU` to a basis state is the same. The basis state is described by `basis` parameter. See <xref:microsoft.quantum.extensions.fliptobasis> function for more details on this description.
ms.openlocfilehash: d8f2195f75de49918032053dc8d1fa4fb4eba840
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96213765"
---
# <a name="_assertequalonbasisvector-operation"></a><span data-ttu-id="583fd-102">operace _assertEqualOnBasisVector</span><span class="sxs-lookup"><span data-stu-id="583fd-102">_assertEqualOnBasisVector operation</span></span>

<span data-ttu-id="583fd-103">Obor názvů: [Microsoft. prověří. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="583fd-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="583fd-104">Balíček: [Microsoft. ProQSharpme. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="583fd-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="583fd-105">Kontroluje, zda je výsledek použití dvou operací `givenU` a `expectedU` na základní stav stejný.</span><span class="sxs-lookup"><span data-stu-id="583fd-105">Checks if the result of applying two operations `givenU` and `expectedU` to a basis state is the same.</span></span> <span data-ttu-id="583fd-106">Základní stav je popsán podle `basis` parametru.</span><span class="sxs-lookup"><span data-stu-id="583fd-106">The basis state is described by `basis` parameter.</span></span>
<span data-ttu-id="583fd-107"><xref:microsoft.quantum.extensions.fliptobasis>Další podrobnosti o tomto popisu najdete v tématu funkce.</span><span class="sxs-lookup"><span data-stu-id="583fd-107">See <xref:microsoft.quantum.extensions.fliptobasis> function for more details on this description.</span></span>

```qsharp
operation _assertEqualOnBasisVector (basis : Int[], givenU : (Qubit[] => Unit), expectedU : (Qubit[] => Unit is Adj)) : Unit
```


## <a name="input"></a><span data-ttu-id="583fd-108">Vstup</span><span class="sxs-lookup"><span data-stu-id="583fd-108">Input</span></span>

### <a name="basis--int"></a><span data-ttu-id="583fd-109">Základna: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="583fd-109">basis : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="583fd-110">Základní stav určený ID stavu s jednou qubit (0 <= ID <= 3) pro každý $n $ qubits.</span><span class="sxs-lookup"><span data-stu-id="583fd-110">Basis state specified by a single-qubit basis state ID (0 <= id <= 3) for each of $n$ qubits.</span></span>


### <a name="givenu--qubit--unit"></a><span data-ttu-id="583fd-111">předané: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="583fd-111">givenU : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="583fd-112">Bude zkontrolována operace na $n $ qubits.</span><span class="sxs-lookup"><span data-stu-id="583fd-112">Operation on $n$ qubits to be checked.</span></span>


### <a name="expectedu--qubit--unit--is-adj"></a><span data-ttu-id="583fd-113">očekává se: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [jednotka](xref:microsoft.quantum.lang-ref.unit)  je ADJ.</span><span class="sxs-lookup"><span data-stu-id="583fd-113">expectedU : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="583fd-114">Operace reference na $n $ qubits, která má být porovnána s.</span><span class="sxs-lookup"><span data-stu-id="583fd-114">Reference operation on $n$ qubits that givenU is to be compared against.</span></span>



## <a name="output--unit"></a><span data-ttu-id="583fd-115">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="583fd-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

