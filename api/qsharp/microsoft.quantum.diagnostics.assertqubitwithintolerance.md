---
uid: Microsoft.Quantum.Diagnostics.AssertQubitWithinTolerance
title: Operace AssertQubitWithinTolerance
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AssertQubitWithinTolerance
qsharp.summary: Asserts that the qubit `q` is in the expected eigenstate of the Pauli Z operator up to a given tolerance.
ms.openlocfilehash: 56b7f93f33ae18146c1fb13d404fc1d119eee72e
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96202188"
---
# <a name="assertqubitwithintolerance-operation"></a><span data-ttu-id="26306-102">Operace AssertQubitWithinTolerance</span><span class="sxs-lookup"><span data-stu-id="26306-102">AssertQubitWithinTolerance operation</span></span>

<span data-ttu-id="26306-103">Obor názvů: [Microsoft. prověří. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="26306-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="26306-104">Balíček: [Microsoft. ProQSharpme. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="26306-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="26306-105">Vyhodnotí, že qubit `q` je v očekávané eigenstate operátoru Pauli z až po danou toleranci.</span><span class="sxs-lookup"><span data-stu-id="26306-105">Asserts that the qubit `q` is in the expected eigenstate of the Pauli Z operator up to a given tolerance.</span></span>

```qsharp
operation AssertQubitWithinTolerance (expected : Result, q : Qubit, tolerance : Double) : Unit
```


## <a name="input"></a><span data-ttu-id="26306-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="26306-106">Input</span></span>

### <a name="expected--__invalidresult__"></a><span data-ttu-id="26306-107">očekáváno __: <Result> neplatné__</span><span class="sxs-lookup"><span data-stu-id="26306-107">expected : __invalid<Result>__</span></span>

<span data-ttu-id="26306-108">Který stav qubit má být v: `Zero` nebo `One` .</span><span class="sxs-lookup"><span data-stu-id="26306-108">Which state the qubit is expected to be in: `Zero` or `One`.</span></span>


### <a name="q--qubit"></a><span data-ttu-id="26306-109">Otázka: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="26306-109">q : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="26306-110">Qubit, jehož stav je uplatněn.</span><span class="sxs-lookup"><span data-stu-id="26306-110">The qubit whose state is asserted.</span></span>


### <a name="tolerance--double"></a><span data-ttu-id="26306-111">tolerance: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="26306-111">tolerance : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="26306-112">Tolerance u pravděpodobnosti měření qubit vracející očekávaný výsledek.</span><span class="sxs-lookup"><span data-stu-id="26306-112">Tolerance on the probability of a measurement of the qubit returning the expected result.</span></span>



## <a name="output--unit"></a><span data-ttu-id="26306-113">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="26306-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="26306-114">Poznámky</span><span class="sxs-lookup"><span data-stu-id="26306-114">Remarks</span></span>

<span data-ttu-id="26306-115"><xref:microsoft.quantum.diagnostics.assertqubitisinstatewithintolerance> Umožňuje vyhodnotit libovolný stav qubit spíše než jenom $Z $ eigenstates.</span><span class="sxs-lookup"><span data-stu-id="26306-115"><xref:microsoft.quantum.diagnostics.assertqubitisinstatewithintolerance> allows for asserting arbitrary qubit states rather than only $Z$ eigenstates.</span></span>

## <a name="see-also"></a><span data-ttu-id="26306-116">Viz také</span><span class="sxs-lookup"><span data-stu-id="26306-116">See Also</span></span>

- [<span data-ttu-id="26306-117">Microsoft. AssertQubitIsInStateWithinTolerance. Diagnostics.</span><span class="sxs-lookup"><span data-stu-id="26306-117">Microsoft.Quantum.Diagnostics.AssertQubitIsInStateWithinTolerance</span></span>](xref:Microsoft.Quantum.Diagnostics.AssertQubitIsInStateWithinTolerance)