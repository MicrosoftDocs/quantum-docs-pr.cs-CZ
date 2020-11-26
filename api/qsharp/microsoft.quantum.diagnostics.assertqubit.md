---
uid: Microsoft.Quantum.Diagnostics.AssertQubit
title: Operace AssertQubit
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AssertQubit
qsharp.summary: Asserts that the qubit `q` is in the expected eigenstate of the Pauli Z operator.
ms.openlocfilehash: 0e005230427bbd570133712679c51661e7ae6496
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96202239"
---
# <a name="assertqubit-operation"></a><span data-ttu-id="2b50d-102">Operace AssertQubit</span><span class="sxs-lookup"><span data-stu-id="2b50d-102">AssertQubit operation</span></span>

<span data-ttu-id="2b50d-103">Obor názvů: [Microsoft. prověří. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="2b50d-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="2b50d-104">Balíček: [Microsoft. ProQSharpme. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="2b50d-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="2b50d-105">Vyhodnotí, že qubit `q` je v očekávané eigenstate operátoru Pauli z.</span><span class="sxs-lookup"><span data-stu-id="2b50d-105">Asserts that the qubit `q` is in the expected eigenstate of the Pauli Z operator.</span></span>

```qsharp
operation AssertQubit (expected : Result, q : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="2b50d-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="2b50d-106">Input</span></span>

### <a name="expected--__invalidresult__"></a><span data-ttu-id="2b50d-107">očekáváno __: <Result> neplatné__</span><span class="sxs-lookup"><span data-stu-id="2b50d-107">expected : __invalid<Result>__</span></span>

<span data-ttu-id="2b50d-108">Který stav qubit má být v: `Zero` nebo `One` .</span><span class="sxs-lookup"><span data-stu-id="2b50d-108">Which state the qubit is expected to be in: `Zero` or `One`.</span></span>


### <a name="q--qubit"></a><span data-ttu-id="2b50d-109">Otázka: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="2b50d-109">q : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="2b50d-110">Qubit, jehož stav je uplatněn.</span><span class="sxs-lookup"><span data-stu-id="2b50d-110">The qubit whose state is asserted.</span></span>



## <a name="output--unit"></a><span data-ttu-id="2b50d-111">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="2b50d-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="2b50d-112">Poznámky</span><span class="sxs-lookup"><span data-stu-id="2b50d-112">Remarks</span></span>

<span data-ttu-id="2b50d-113"><xref:microsoft.quantum.diagnostics.assertqubitisinstatewithintolerance> Umožňuje vyhodnotit libovolný stav qubit spíše než jenom $Z $ eigenstates.</span><span class="sxs-lookup"><span data-stu-id="2b50d-113"><xref:microsoft.quantum.diagnostics.assertqubitisinstatewithintolerance> allows for asserting arbitrary qubit states rather than only $Z$ eigenstates.</span></span>

## <a name="see-also"></a><span data-ttu-id="2b50d-114">Viz také</span><span class="sxs-lookup"><span data-stu-id="2b50d-114">See Also</span></span>

- [<span data-ttu-id="2b50d-115">Microsoft. AssertQubitIsInStateWithinTolerance. Diagnostics.</span><span class="sxs-lookup"><span data-stu-id="2b50d-115">Microsoft.Quantum.Diagnostics.AssertQubitIsInStateWithinTolerance</span></span>](xref:Microsoft.Quantum.Diagnostics.AssertQubitIsInStateWithinTolerance)